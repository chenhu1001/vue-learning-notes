## 1、登录接口
**描述：** 

- 用户登录接口

**请求URL：** 
- ` http://xx.com/user/login `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|username |是  |string |用户名   |
|password |是  |string | 密码    |

 **返回示例**

``` 
{
    "data": {
        "createTime": "2017-12-14 08:57:20",
        "createUser": "admin",
        "detailAddress": "成都市天府新区",
        "email": "admin@tianfugroup.com",
        "id": 1,
        "mobile": "2147483647",
        "modifyTime": "2017-12-21 08:57:32",
        "modifyUser": "admin",
        "nickName": "administrator",
        "passWord": "admin",
        "permissions": [
            {
                "children": [
                    {
                        "children": [],
                        "id": 2,
                        "isMenu": 0,
                        "isSystemPermission": 0,
                        "moduleId": 1,
                        "parentId": 1,
                        "permissionName": "新建用户",
                        "permissionType": 1,
                        "status": 1,
                        "url": "/userManager?method=addUser"
                    },
                    {
                        "children": [],
                        "id": 3,
                        "isMenu": 0,
                        "isSystemPermission": 0,
                        "moduleId": 1,
                        "parentId": 1,
                        "permissionName": "修改用户",
                        "permissionType": 1,
                        "status": 1,
                        "url": "/userManager?method=updateUser"
                    },
                    {
                        "children": [],
                        "id": 4,
                        "isMenu": 0,
                        "isSystemPermission": 0,
                        "moduleId": 1,
                        "parentId": 1,
                        "permissionName": "删除用户",
                        "permissionType": 1,
                        "status": 1,
                        "url": "/userManager?method=deleteUser"
                    }
                ],
                "id": 1,
                "isMenu": 1,
                "isSystemPermission": 1,
                "moduleId": 1,
                "parentId": 0,
                "permissionName": "用户管理",
                "permissionType": 1,
                "status": 1,
                "url": "#"
            },
            {
                "children": [
                    {
                        "children": [],
                        "id": 6,
                        "isMenu": 0,
                        "isSystemPermission": 0,
                        "moduleId": 2,
                        "parentId": 5,
                        "permissionName": "新建组织",
                        "permissionType": 1,
                        "status": 1,
                        "url": "/groupManager?method=addGroup"
                    },
                    {
                        "children": [],
                        "id": 7,
                        "isMenu": 0,
                        "isSystemPermission": 0,
                        "moduleId": 2,
                        "parentId": 5,
                        "permissionName": "修改组织",
                        "permissionType": 1,
                        "status": 1,
                        "url": "/groupManager?method=updateGroup"
                    }
                ],
                "id": 5,
                "isMenu": 1,
                "isSystemPermission": 1,
                "moduleId": 2,
                "parentId": 0,
                "permissionName": "组织管理",
                "permissionType": 1,
                "status": 1,
                "url": "#"
            }
        ],
        "qq": "567894321",
        "status": 1,
        "trueName": "administrator",
        "userName": "admin",
        "wechat": "admin003"
    },
    "expires": 3600,
    "msg": "操作成功",
    "statusCode": "0",
    "token": "eyJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE1MTQxNjg4MDksInN1YiI6IntcInVzZXJuYW1lXCI6XCJhZG1pblwifSJ9.CTCSt7LHLbZoy_b0scsBN-llLjd3jDG8NpM_Y-Ig_Fs"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|token |string   |token验证  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 2、模块列表 
**描述：** 

- 模块列表接口

**请求URL：** 
- ` http://xx.com/api/module/selectAll `
  
**请求方式：**
- POST 

**参数：** 
无

 **返回示例**

``` 
{
    "data": {
        "modules": [
            {
                "createTime": "2017-12-12 09:18:50",
                "createUser": "admin",
                "description": "管理用户的维护",
                "id": 1,
                "modifyTime": "2017-12-21 09:18:55",
                "modifyUser": "admin",
                "moduleName": "用户管理",
                "orderNum": 1
            },
            {
                "createTime": "2017-12-19 09:19:16",
                "createUser": "admin",
                "description": "管理组织的维护",
                "id": 2,
                "modifyTime": "2017-12-21 09:19:23",
                "modifyUser": "admin",
                "moduleName": "组织管理",
                "orderNum": 2
            },
            {
                "createTime": "2017-12-20 09:19:49",
                "createUser": "admin",
                "description": "管理角色的维护",
                "id": 3,
                "modifyTime": "2017-12-21 09:19:56",
                "modifyUser": "admin",
                "moduleName": "角色管理",
                "orderNum": 3
            },
            {
                "createTime": "2017-12-13 09:20:21",
                "createUser": "admin",
                "description": "管理模块的维护",
                "id": 4,
                "modifyTime": "2017-12-21 09:20:29",
                "modifyUser": "admin",
                "moduleName": "模块管理",
                "orderNum": 4
            },
            {
                "createTime": "2017-12-15 09:20:51",
                "createUser": "admin",
                "description": "管理权限的维护",
                "id": 5,
                "modifyTime": "2017-12-21 09:20:59",
                "modifyUser": "admin",
                "moduleName": "权限管理",
                "orderNum": 5
            },
            {
                "createTime": "2017-12-16 09:21:16",
                "createUser": "admin",
                "description": "管理系统的维护",
                "id": 6,
                "modifyTime": "2017-12-21 09:21:23",
                "modifyUser": "admin",
                "moduleName": "系统管理",
                "orderNum": 6
            },
            {
                "createTime": "2017-12-26 11:22:40",
                "id": 7,
                "modifyTime": "2017-12-26 11:24:16",
                "moduleName": "用户管理1"
            }
        ]
    },
    "expires": 0,
    "msg": "操作成功",
    "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|moduleName |string   |模块名  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 3、菜单列表
**描述：** 

- 菜单列表接口

**请求URL：** 
- ` http://xx.com/module/selectMenu `
  
**请求方式：**
- POST 

**参数：** 
无

 **返回示例**

``` 
{
    "data": {
        "menus": [
            {
                "id": 1,
                "moduleName": "用户管理"
            },
            {
                "id": 2,
                "moduleName": "组织管理"
            },
            {
                "id": 3,
                "moduleName": "角色管理"
            },
            {
                "id": 4,
                "moduleName": "模块管理"
            },
            {
                "id": 5,
                "moduleName": "权限管理"
            },
            {
                "id": 6,
                "moduleName": "系统管理"
            },
            {
                "id": 7,
                "moduleName": "用户管理1"
            },
            {
                "id": 10,
                "moduleName": "用户管理4"
            }
        ]
    },
    "expires": 0,
    "msg": "操作成功",
    "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| moduleName |string   |模块名  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 4、新增模块
**描述：** 

- 新增模块接口

**请求URL：** 
- ` http://xx.com/module/save `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|moduleName |是  |string |模块名   |

 **返回示例**

``` 
{
    "expires": 0,
    "msg": "操作成功",
    "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 5、修改模块
**描述：** 

- 修改模块接口

**请求URL：** 
- ` http://xx.com/module/update `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|id |是  |int |模块id   |
|moduleName |是  |string |模块名   |

 **返回示例**

``` 
{
    "expires": 0,
    "msg": "操作成功",
    "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 6、删除模块
**描述：** 

- 删除模块接口

**请求URL：** 
- ` http://xx.com/module/delete `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| moduleIds |是  |string |模块id集合-多个用竖线\|隔开   |

 **返回示例**

``` 
{
    "expires": 0,
    "msg": "操作成功",
    "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 7、用户列表
**描述：** 

- 用户列表接口

**请求URL：** 
- ` http://xx.com/user/getUserInfoList `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| pageSize |是  |int |分页大小   |
| currentPage |是  |int |当前分页   |
| userName |否  |string |用户名   |
| trueName |否  |string |真实姓名   |
| roles |否  |string |多个角色名   |
| all |否  |string |筛选条件-按userName-trueName-roles   |

 **返回示例**

``` 
{
  "data": {
    "currentPage": 1,
    "datas": [
      {
        "createTime": "2017-12-14 08:57:20",
        "id": 1,
        "roles": "总监,开发人员,总经理",
        "status": 1,
        "trueName": "administrator",
        "userName": "admin"
      }
    ],
    "pageSize": 0,
    "totals": 1
  },
  "msg": "操作成功",
  "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |
| roles |string   |多个角色名  |
| trueName |string   |真实姓名  |
| userName |string   |用户名  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 8、新增用户
**描述：** 

- 新增用户接口

**请求URL：** 
- ` http://xx.com/user/addUser `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| userName |是  |string |用户名   |
| password |是  |string |密码   |
| trueName |否  |string |真实姓名   |
| nickName |否  |string |昵称   |
| mobile |否  |string |手机号   |
| detailAddress |否  |string |详细地址   |
| email |否  |string |电子邮箱   |
| qq |否  |string |QQ   |
| wechat |否  |string |微信   |
| status |否  |int |状态   |
| groupids |否  |string |组织id组   |
| roleids |否  |string |角色id组   |

 **返回示例**

``` 
{
  "msg": "操作成功",
  "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 9、角色列表
**描述：** 

- 角色列表接口

**请求URL：** 
- ` http://xx.com/role/getRoleList `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| pageSize |是  |int |分页大小   |
| currentPage |是  |int |当前分页   |
| selectAll |否  |string |全部   |
| roleName |否  |string |角色名   |
| createUser |否  |string |创建用户   |

 **返回示例**

``` 
{
  "data": {
    "currentPage": 3,
    "datas": [
      {
        "createTime": 1513559114000,
        "createUser": "admin",
        "description": "负责全局事务",
        "id": 1,
        "isSystemRole": 1,
        "modifyTime": 1513645504000,
        "modifyUser": "admin",
        "roleName": "总经理",
        "status": 1
      },
      {
        "createTime": 1513645552000,
        "createUser": "admin",
        "description": "协助总经理",
        "id": 2,
        "isSystemRole": 0,
        "modifyTime": 1513731945000,
        "modifyUser": "admin",
        "roleName": "总监",
        "status": 1
      },
      {
        "createTime": 1513731985000,
        "createUser": "admin",
        "description": "实现具体功能",
        "id": 3,
        "isSystemRole": 1,
        "modifyTime": 1513818374000,
        "modifyUser": "admin",
        "roleName": "开发人员",
        "status": 1
      }
    ],
    "pageSize": 2,
    "totals": 1
  },
  "msg": "操作成功",
  "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 10、新增角色
**描述：** 

- 新增角色接口

**请求URL：** 
- ` http://xx.com/role/save `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| id |是  |int |角色id   |
| roleName |否  |string |角色名   |
| createTime |否  |string |创建时间   |
| createUser |否  |string |创建用户   |
| description |否  |string |描述   |
| isSystemRole |否  |int |是否系统角色   |
| modifyTime |否  |string |修改时间   |
| modifyUser |否  |string |修改用户   |
| status |否  |int |状态   |

 **返回示例**

``` 
{
  "msg": "操作成功",
  "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 11、修改角色
**描述：** 

- 修改角色接口

**请求URL：** 
- ` http://xx.com/role/update `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| id |是  |int |角色id   |
| roleName |否  |string |角色名   |
| createTime |否  |string |创建时间   |
| createUser |否  |string |创建用户   |
| description |否  |string |描述   |
| isSystemRole |否  |int |是否系统角色   |
| modifyTime |否  |string |修改时间   |
| modifyUser |否  |string |修改用户   |
| status |否  |int |状态   |

 **返回示例**

``` 
{
  "msg": "操作成功",
  "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 12、删除角色
**描述：** 

- 删除角色接口

**请求URL：** 
- ` http://xx.com/role/deleteRoles `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| roleIds |是  |string |角色ids   |

 **返回示例**

``` 
{
  "msg": "操作成功",
  "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 13、查询角色
**描述：** 

- 查询角色接口

**请求URL：** 
- ` http://xx.com/role/getRoleInfoById `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| id |是  |int |角色id   |

 **返回示例**

``` 
{
  "data": {
    "createTime": 1513731985000,
    "createUser": "admin",
    "description": "实现具体功能",
    "id": 3,
    "isSystemRole": 1,
    "modifyTime": 1513818374000,
    "modifyUser": "admin",
    "roleName": "开发人员",
    "status": 1
  },
  "msg": "操作成功",
  "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |
| msg |string   |状态信息  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 14、角色用户列表
**描述：** 

- 角色用户列表接口

**请求URL：** 
- ` http://xx.com/userRole/getRoleUserList `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| id |是  |int |角色id   |

 **返回示例**

``` 
{
  "data": [
    {
      "createTime": "2017-12-14 08:57:20",
      "createUser": "admin",
      "detailAddress": "成都市天府新区",
      "email": "admin@tianfugroup.com",
      "id": 1,
      "mobile": "2147483647",
      "modifyTime": "2017-12-21 08:57:32",
      "modifyUser": "admin",
      "nickName": "administrator",
      "passWord": "admin",
      "qq": "567894321",
      "status": 1,
      "trueName": "administrator",
      "userName": "admin",
      "wechat": "admin003"
    },
    {
      "createTime": "2017-12-27 09:18:53",
      "createUser": "admin",
      "detailAddress": "成都市青羊区",
      "email": "jie.liu@tianfugroup.com",
      "id": 170,
      "mobile": "13666668899",
      "modifyTime": "2017-12-27 09:18:45",
      "modifyUser": "admin",
      "nickName": "jackYao",
      "passWord": "123456",
      "qq": "277139277",
      "status": 2,
      "trueName": "刘杰",
      "userName": "liuj",
      "wechat": "yao277"
    }
  ],
  "msg": "操作成功",
  "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |
| msg |string   |状态信息  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 15、删除角色用户
**描述：** 

- 删除角色用户接口

**请求URL：** 
- ` http://xx.com/userRole/deleteRoleUser `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| roleId |是  |int |角色id   |
| userIds |是  |string |用户ids   |

 **返回示例**

``` 
{
  "msg": "操作成功",
  "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |
| msg |string   |状态信息  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 16、添加角色用户
**描述：** 

- 添加角色用户接口

**请求URL：** 
- ` http://xx.com/userRole/addRoleUser `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| roleId |是  |int |角色id   |
| userIds |是  |string |用户ids   |

 **返回示例**

``` 
{
  "msg": "操作成功",
  "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |
| msg |string   |状态信息  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 17、清空角色用户
**描述：** 

- 清空角色用户接口

**请求URL：** 
- ` http://xx.com/userRole/emptyRoleUser `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| roleId |是  |int |角色id   |

 **返回示例**

``` 
{
  "msg": "操作成功",
  "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |
| msg |string   |状态信息  |

 **备注** 

- 更多返回错误代码请看错误代码描述

## 18、组织树
**描述：** 

- 组织树接口

**请求URL：** 
- ` http://xx.com/organization/organizationTree `
  
**请求方式：**
- POST 

**参数：** 
无

 **返回示例**

``` 
{
  "data": [
    {
      "children": [
        {
          "children": [],
          "id": 4,
          "label": "综合部",
          "pid": 1
        },
        {
          "children": [],
          "id": 5,
          "label": "项目部",
          "pid": 1
        },
        {
          "children": [],
          "id": 6,
          "label": "技术部",
          "pid": 1
        },
        {
          "children": [],
          "id": 8,
          "label": "test",
          "pid": 1
        }
      ],
      "id": 1,
      "label": "科技信息事业部",
      "pid": 0
    },
    {
      "children": [],
      "id": 2,
      "label": "互联网金融事业部",
      "pid": 0
    },
    {
      "children": [],
      "id": 3,
      "label": "汽车金融事业部",
      "pid": 0
    }
  ],
  "msg": "操作成功",
  "statusCode": "0"
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
| statusCode |int   |状态码  |
| msg |string   |状态信息  |

 **备注** 

- 更多返回错误代码请看错误代码描述
