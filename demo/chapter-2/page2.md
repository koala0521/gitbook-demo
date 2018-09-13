#接入快应用官网统计

## 下载SDK

下载 SDK文件并解压，将其中的 appStatistics.min.js、statistics.config.js拷贝到app.ux同级的目录（src目录下）；


----------


## 修改配置文件
用编辑器打开statistics.config.js ，修改其中的 app_id 配置:

```javascript

export default{
    app_key: ''
}

```


----------
## 接入SDK

使用编辑器打开 app.ux 文件 , 引入 SDK 文件：

```javascript
    import APP_STATISTICS from "appStatistics.js"

``` 


----------


## 初始化打点

在 app.ux 的 onCreate 函数中，增加统计打点代码：

```javascript
    // app.ux文件

    onCreate:function(){
        
        //统计打点
        APP_STATISTICS.app_sta_init( this );

        // 其他业务代码...

    },    

```


----------


## 依赖检查

- 内置模块依赖

    由于快应用部分内置模块 ,需要在manifest.json 的 features 属性中 声明才可以使用，请检查依赖模块是否已经声明。SDK 使用到的内置模块包括： 
    
    storage (缓存)
    nativeFetch（网络请求）
    device（设备信息）
    geolocation （地理位置）
    network （网络信息）
    service.account (账号接口) 
 
- 依赖声明方式 

```json
    // manifest.json 文件
    
    "features": [
        { "name": "system.fetch"},
        {"name": "system.storage"},
        {"name": "system.device"},
        {"name": "system.geolocation"},
        {"name": "system.network"},
        {"name": "service.account"},
    ]

    
```


----------


## 接入完成
确认完成以上步骤之后，就可以使用我们提供的统计功能啦。
