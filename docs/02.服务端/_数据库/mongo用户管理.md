mongod --dbpath d:/mongodb/data  开启服务是不带权限验证的

通过mongo进入后 用show dbs 显示数据库


use admin后，加入一个用户 //admin存放的是用户信息

db.createUser( { "user" : "zhengjx1",
                 "pwd": "123456",
                 "roles" : [ { role: "clusterAdmin", db: "admin" },
                             { role: "readWriteAnyDatabase", db: "admin" },
                             "readWrite"
                             ] } )



下次用mongod --dbpath d:/mongodb/data --auth 开启服务

用mongo [数据库名] -u [用户名] -p [密码] 登录