# Entity 

创建实体对象.

项目最麻烦的地方就是对 Entity 分类控制显隐. 文档中有 entities 对象, 或许使用起来会简单很多.

[在线文档](http://support.supermap.com.cn:8090/webgl/Build/Documentation/Entity.html?classFilter=Entity)

> 已经添加的 entity 点, 再次天机会报错. 添加 entity 必须在创建 viewer 之后.



## 创建

```js
var entity = new Cesium.Entity( opt )
```



## Options

太多就不写了. 参考文档: [在线文档](http://support.supermap.com.cn:8090/webgl/Build/Documentation/Entity.html?classFilter=Entity)

### 类型

- 盒 entity.box
- 圈和椭圆 entity.ellipse
- 走廊 entity.corridor
- 气缸和锥体 entity.cylinder
- 多边形 entity.polygon
- 折线 entity.polyline [Demo](<http://support.supermap.com.cn:8090/webgl/examples/editor.html#Polyline>)
- 折线卷 entity.polylineVolume
- 矩形 entity.rectangle
- 球体和椭球体 entity.ellipsoid
- 墙壁 entity.wall



## Cesium.EntityCollection

[在线文档](http://support.supermap.com.cn:8090/webgl/Build/Documentation/EntityCollection.html)

```js
// 例子: 视角跳转到 entity
viewer.zoomTo( entity )
```

### 获取

```js
var entities = viewer.enities
```



### viewer 方法

| 方法               | 参数               | 描述                  |
| ------------------ | ------------------ | --------------------- |
| zoomTo             | ( entity: Entity ) | 视角跳转到目标 entity |
| entities.remove    | ( entity: Entity ) | 删除单个 entity       |
| entities.removeAll |                    | 删除所有 entity       |
| entities.add       | ( entity: Enity )  | 添加单个 entity       |

### viewer 属性

| 属性                    | 类型   | 描述                             |
| ----------------------- | ------ | -------------------------------- |
| selectedEntity          | Entity | 获取设置选中的 entity            |
| entities.entities.array | Array  | 获取 viewer 下所有的 entity 集合 |
|                         |        |                                  |



## 实例属性

| 属性 | 类型   | 描述         |
| ---- | ------ | ------------ |
| id   | String | entity 的 id |
|      |        |              |
|      |        |              |



## 实例方法

| 方法 | 参数 | 描述 |
| ---- | ---- | ---- |
|      |      |      |
|      |      |      |
|      |      |      |



## 添加 3D 模型

```js
var viewer = new Cesium.Viewer('cesiumContainer');
var entity = viewer.entities.add({
    position : Cesium.Cartesian3.fromDegrees(-123.0744619, 44.0503706),
    model : {
        uri : '../Apps/SampleData/models/CesiumGround/Cesium_Ground.gltf'
    }
})
```





## Setting





## example

### 绘制虚线

```js
let entity = new Cesium.Entity( {
    polyline: {
        show: true,
        width: 2,
        outline: false,
        // granularity: 1,
        material: new Cesium.PolylineDashMaterialProperty( {
            color: new Cesium.Color( 212 / 255, 43 / 255, 47 / 255, 1 )
        } ),
        positions: Cesium.Cartesian3.fromDegreesArray( [
            +doorStart.lng, +doorStart.lat,
            +doorEnd.lng, +doorEnd.lat
        ] )
    },
    position: Cesium.Cartesian3.fromDegrees(
        +doorStart.lng,
        +doorStart.lat,
        +doorStart.height
    )
} )
```





