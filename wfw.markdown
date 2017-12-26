## 1、登录接口
**简要描述：** 

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

- 更多返回错误代码请看首页的错误代码描述




