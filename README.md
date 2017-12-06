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

## npm常用命令
```
// 查找命令
npm search element-ui --registry=https://registry.npmjs.org

// --save参数表示将该模块写入dependencies属性
npm install express --save

// --save-dev表示将该模块写入devDependencies属性
npm install express --save-dev
```