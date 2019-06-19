# Coordinate

坐标相关.



## 坐标介绍

Cesium中的坐标系：

- WGS84经纬度坐标系（没有实际的对象）
- WGS84弧度坐标系（Cartographic）
- 笛卡尔空间直角坐标系（Cartesian3）
- 平面坐标系（Cartesian2）
- 4D笛卡尔坐标系（Cartesian4）



## 项目中使用的坐标系

- 笛卡尔空间直角坐标系（Cartesian3）{ x, y, z }
- WGS84弧度坐标系 (Cartesian3.fromDegrees) { longitude, latitude, height }
- 平面坐标系（Cartesian2）{ x, y }



## 坐标转换

### 笛卡尔坐标 ==> WGS84弧度坐标系

```js
// 经纬度坐标
new Cesium.Cartesian3.fromDegrees( longitude, latitude [, height ] ) ;
// 卡迪尔坐标
new Cesium.Cartesian3( x, y, z );

// 在事件中获取
function ( e ) {
    //获取点击位置笛卡尔坐标
    var position = scene.pickPosition( e.position );

    //将笛卡尔坐标转化为经纬度坐标
    var mousePosition = scene.pickPosition( position );
    // 笛卡尔坐标 ==> WGS84弧度坐标系
    var cartographic = Cesium.Cartographic.fromCartesian( position );
    var longitude = Cesium.Math.toDegrees( cartographic.longitude );  // 经度
    var latitude = Cesium.Math.toDegrees( cartographic.latitude );    // 纬度
}
```

##  WGS84弧度坐标系 ==> 笛卡尔坐标

```js
var ellipsoid = viewer.scene.globe.ellipsoid;

// 装换为笛卡尔坐标实例
var cartesian3 = new Cesium.Cartesian3(
    scene.camera.position.x,
	scene.camera.position.y,
    scene.camera.position.z
);

// 转换
var cartographic = ellipsoid.cartesianToCartographic( cartesian3 );
var lat = Cesium.Math.toDegrees( cartographic.latitude );
var lng = Cesium.Math.toDegrees( cartographic.longitude );
var height = cartographic.height;
```

