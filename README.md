## YunBa - Wi-Fi灯泡web端声控说明

使用 Web Audio API 和 [云巴智能灯泡](https://github.com/yunbaidea/yunbabulb)的Restful API,在web端通过声音控制云巴智能小灯泡的亮度和颜色。

## 使用方法

###安装

1. `git clone git@github.com:GabrielchenCN/yunba-wifi-bulb-example.git`
2. [使用nginx部署应用和跨域问题处理](http://www.cnblogs.com/gabrielchen/p/5066120.html)
 

###配置

1. 首先确保云巴灯泡有相应别名和正确连接上服务器，详见:[云巴智能灯泡](https://github.com/yunbaidea/yunbabulb)。

2. 在app2.js中配置frevolObj对象的正确别名。

 `var frevolObj={"Sarah":{"r":105,"g":"","b":255,"volume":0}}; `

3. 因为是前端AJAX请求，所以直接请求url可能遇到跨域问题。设置`urlproxy`参数,可能遇到的[跨域访问问题解决方案](http://www.cnblogs.com/gabrielchen/p/5066120.html)。
- 直接请求url以及参数设置如下：
   - alias: 别名
   - p    : 默认1000
   - rgb  : 分别为对应rgb值，范围0～22222，值越大亮度越大
   - http method: GET
   -  ```var url = 'http://rest.yunba.io:8080?method=publish_to_alias&appkey=56556dd4f085fc471efe0688&seckey=sec-uTYMY37JTlH5hEmsvmgO8FkZYwkkPA45VAuDifUeQIsh4enS&alias='+config.alias+'&msg={"p":'+config.p+',"r":'+config.red+',"g":'+config.green+',"b":'+config.blue+'}';```

###运行

- 运行index.html
- 建议使用firefox运行或47版本以下chrome，并允许浏览器共享麦克风。

###浏览器支持

- chrome 47 以下(出于安全原因，47以上需要https协议访问[详见](https://sites.google.com/a/chromium.org/dev/Home/chromium-security/deprecating-powerful-features-on-insecure-origins))
- firefox


###相关引用

- [soundcloud-visualizer](https://github.com/michaelbromley/soundcloud-visualizer)
- [web audio api 简单开始](http://www.cnblogs.com/gabrielchen/p/5078760.html)
