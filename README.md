# vue-learning-notes

## 1、npm换源
* 查看源
```
npm config get registry

// 或
npm config list
```
* 修改源
```
# 默认源
npm config set registry https://registry.npmjs.org

# https -> http，这样网速就会好很多
npm config set registry http://registry.npmjs.org 

# 如果还不能下载，就切换成淘宝源
npm config set registry https://registry.npm.taobao.org
```
* 如果只是临时改变源，可以这样
```
npm --registry=https://registry.npm.taobao.org
```

## 2、npm常用命令
```
// 查找命令
npm search element-ui --registry=https://registry.npmjs.org

// --save参数表示将该模块写入dependencies属性
npm install express --save

// --save-dev表示将该模块写入devDependencies属性
npm install express --save-dev
```

## 3、Vue的api跨域请求问题

使用vue做跨域请求的时候的基本操作是
```javascript

// config/index.js
module.exports = {
  // ...
  dev: {
    proxyTable: {
      // proxy all requests starting with /api to jsonplaceholder
      '/api/**': {
        target: 'http://jsonplaceholder.typicode.com',
        changeOrigin: true,
        pathRewrite: {
          '^/api' :'/'
        }
      }
    }
  }
}
```
(详情见：[https://vuejs-templates.github.io/webpack/proxy.html](https://vuejs-templates.github.io/webpack/proxy.html))

相当于开发环境下的``'/api'``路由是指向xxx.com地址的,同时重定向了你的路由所有带``'/api'``的都是空，即用axios请求数据的时候控制台里看到的其实并没有``/api``这四个字符。``changeOrigin:true``则会自动给请求头加入Host首部。

**但是这个时候就会有一个问题，即一旦项目中的路由一多起来，难免会出现路由的冲突问题，并且上面这个常规操作只是让浏览器认为它没有``'/api'``这个字符，我们码畜还得自己手码啊！每次多打四个字多费时间啊！于是为了懒，我们就要找稍微高端点的操作了！**

整一个变量，让这个变量代替``'/api'``，那tm不就少打字了吗？于是在入口文件引入axios的时候同时把这个变量定下来：
```javascript

// main.js

import axios from "axios"

axios.defaults.baseURL = 'api'
```
好了，这个时候再请求数据的时候就可以少打四个字了。

同样的，这里还是会存在一个弊端，那就算不能区分到底是生产环境还是开发环境。那么为了区分这个情况，我们在config目录下新建一个api.config.js文件来区分它。

```javascript

const isPro = Object.is(process.env.NODE_ENV, 'production')

module.exports = {
  baseURL: isPro ? 'http://jsonplaceholder.typicode.com/api/' :'api/'
}
```
有了这个文件以后，再在入口文件里用它。
```javascript

// main.js
import Vue from 'vue'
import App from './App'
import router from './router'
import axios from "axios"

import apiConfig from '../config/api.config'
axios.defaults.baseURL = apiConfig.baseURL
```

这样就一劳永逸啦！

## 4、服务器实现跨域REST请求
* 配置web.xml
```
<!-- 通过CORS技术实现AJAX跨域访问 -->
<filter>
    <filter-name>corsFilter</filter-name>
    <filter-class>cn.edu.tju.rico.filter.CorsFilter</filter-class>
    <init-param>
        <param-name>allowOrigin</param-name>
        <param-value>http://localhost:8080</param-value>
    </init-param>
    <init-param>
        <param-name>allowMethods</param-name>
        <param-value>GET,POST,PUT,DELETE,OPTIONS</param-value>
    </init-param>
    <init-param>
        <param-name>allowCredentials</param-name>
        <param-value>true</param-value>
    </init-param>
    <init-param>
        <param-name>allowHeaders</param-name>
        <param-value>Content-Type,X-Token</param-value>
    </init-param>
</filter>
<filter-mapping>
    <filter-name>corsFilter</filter-name>
    <url-pattern>/*</url-pattern>
</filter-mapping>
```
* 添加CorsFilter
```
package cn.edu.tju.rico.filter;

import java.io.IOException;
import java.util.Arrays;
import java.util.List;

import javax.servlet.Filter;
import javax.servlet.FilterChain;
import javax.servlet.FilterConfig;
import javax.servlet.ServletException;
import javax.servlet.ServletRequest;
import javax.servlet.ServletResponse;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

import cn.edu.tju.rico.utils.CollectionUtil;
import cn.edu.tju.rico.utils.StringUtil;

/**        
 * Title: 跨域访问处理(跨域资源共享)    
 * Description: 解决前后端分离架构中的跨域问题
 * @author rico       
 * @created 2017年7月4日 下午5:00:09    
 */      
public class CorsFilter implements Filter {
    private String allowOrigin;
    private String allowMethods;
    private String allowCredentials;
    private String allowHeaders;
    private String exposeHeaders;

    @Override
    public void init(FilterConfig filterConfig) throws ServletException {
        allowOrigin = filterConfig.getInitParameter("allowOrigin");
        allowMethods = filterConfig.getInitParameter("allowMethods");
        allowCredentials = filterConfig.getInitParameter("allowCredentials");
        allowHeaders = filterConfig.getInitParameter("allowHeaders");
        exposeHeaders = filterConfig.getInitParameter("exposeHeaders");
    }


    /** 
     * @description 通过CORS技术实现AJAX跨域访问,只要将CORS响应头写入response对象中即可
     * @author rico       
     * @created 2017年7月4日 下午5:02:38      
     * @param req
     * @param res
     * @param chain
     * @throws IOException
     * @throws ServletException     
     * @see javax.servlet.Filter#doFilter(javax.servlet.ServletRequest, javax.servlet.ServletResponse, javax.servlet.FilterChain)     
     */  
    @Override
    public void doFilter(ServletRequest req, ServletResponse res,
            FilterChain chain) throws IOException, ServletException {
        HttpServletRequest request = (HttpServletRequest) req;
        HttpServletResponse response = (HttpServletResponse) res;
        String currentOrigin = request.getHeader("Origin");
        if (StringUtil.isNotEmpty(allowOrigin)) {
            List<String> allowOriginList = Arrays
                    .asList(allowOrigin.split(","));
            if (CollectionUtil.isNotEmpty(allowOriginList)) {
                if (allowOriginList.contains(currentOrigin)) {
                    response.setHeader("Access-Control-Allow-Origin",
                            currentOrigin);
                }
            }
        }
        if (StringUtil.isNotEmpty(allowMethods)) {
            response.setHeader("Access-Control-Allow-Methods", allowMethods);
        }
        if (StringUtil.isNotEmpty(allowCredentials)) {
            response.setHeader("Access-Control-Allow-Credentials",
                    allowCredentials);
        }
        if (StringUtil.isNotEmpty(allowHeaders)) {
            response.setHeader("Access-Control-Allow-Headers", allowHeaders);
        }
        if (StringUtil.isNotEmpty(exposeHeaders)) {
            response.setHeader("Access-Control-Expose-Headers", exposeHeaders);
        }
        chain.doFilter(req, res);
    }

    @Override
    public void destroy() {
    }
}
```
* 工具类
```
StringUtil

package cn.edu.tju.rico.utils;

  
/**        
 * Title: 字符串工具类    
 * @author rico       
 * @created 2017年7月4日 下午5:15:29    
 */      
public class StringUtil {
	  
	/**     
	 * @description 给定字符串是否为空或空串
	 * @author rico       
	 * @created 2017年7月4日 下午5:15:46     
	 * @param str
	 * @return     
	 */
	public static boolean isNotEmpty(String str) {
		if (str != null && str.length() != 0) {
			return true;
		}
		return false;
	}

	/**     
	 * @description 给定字符串是否为空或空串
	 * @author rico       
	 * @created 2017年7月4日 下午5:15:46     
	 * @param str
	 * @return     
	 */
	public static boolean isEmpty(String str) {
		if (str != null && str.length() != 0) {
			return false;
		}
		return true;
	}
}
```
```
CollectionUtil

package cn.edu.tju.rico.utils;

import java.util.Collection;

  
/**        
 * Title: Collection 工具类    
 * Description: 
 * @author rico       
 * @created 2017年7月4日 下午5:14:01    
 */      
public class CollectionUtil {
	public static boolean isNotEmpty(Collection<?> c){
		if (c != null && c.size() != 0 ) {
			return true;
		}
		return false;
	}
}
```
## 5、watch钩子函数的用法
```
watch: {
  radio: {
    handler: function (val, oldval) {
      console.log(val)
    }
  }
}
```
