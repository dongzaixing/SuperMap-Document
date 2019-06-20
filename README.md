# 项目中使用到的超图接口

[![Commit](https://img.shields.io/github/last-commit/sz-znv/SuperMap-Document.svg)](https://github.com/sz-znv/SuperMap-Document/commits/master) [![Tag](https://img.shields.io/github/tag/sz-znv/SuperMap-Document.svg)](https://github.com/sz-znv/SuperMap-Document/tags) [![license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/sz-znv/SuperMap-Document/blob/master/LICENSE)

**@author PinghuaZhuang**

记录项目中使用的部分超图功能以及接口.

面向前端. 欢迎补充.



## Links

+ [官网在线示例][1]
+ [在线演示][4]
+ [SuperMap相关类接口文档][2]
+ [Cesium类接口文档1][3]
+ [Cesium类接口文档2][6]
+ [官方技术资源][5]
+ [官方开发文档][7]



## :pill:关键属性

### viewer

```js
var viewer = new Cesium.Viewer( ... )
```

1. 操控视图. 例如鼠标样式, 是否显示绿色边框等.
2. 注册影像服务.
3. 获取 camera, scene 对象.

### camera

```js
var camera = viewer.camera
```

1. 视角相关.

### scene

```js
var scene = viewer.scene
```

1. [坐标相关](./Coordinate.md). 



## :open_file_folder:Document

+ [Coordinate](./Coordinate.md): 坐标相关.
+ [Entity](./Entity.md): entity 实体.
+ [Event](./Event.md): 事件相关.
+ [Example](./Example.md): 项目中的一些案例.
+ [Layer](./Layer.md): 图层相关.
+ [Property](./Property.md): Cesium 属性.
+ [QuickStart](./QuickStart.md): 快速启动( 加载底图 ).
+ [Setting](./Setting.md): 地图上的一些设置.



## QuickStart

[QuickStart](./QuickStart.md)



---

[1]: http://support.supermap.com.cn:8090/webgl/examples/editor.html#tianditu	"在线示例"
[2]: https://www.supermap.com/EN/online/iClient%206R/iClient%206R%20for%20JavaScript/apidoc/files/SuperMap/BaseTypes/Bounds-js.html#SuperMap.Bounds	"SuperMap 相关类接口文档"
[3]: http://support.supermap.com.cn:8090/webgl/Build/Documentation	"在线文档1"
[4]: https://cesiumjs.org/Cesium/Apps/Sandcastle/index.html?src=Billboards.html	"在线演示"
[5]: http://support.supermap.com.cn/product/CodeLibrary.aspx?PRODUCT_TYPE=2	"官方自私资源"
[6]: https://cesiumjs.org/Cesium/Build/Documentation/	"在线文档2"
[7]: https://www.supermapol.com/developer/index.html	"官方开发文档"
