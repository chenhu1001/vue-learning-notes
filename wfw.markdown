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


