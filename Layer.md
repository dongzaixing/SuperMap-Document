# S3MTilesLayer

需要部署服务器

[在线文档](http://support.supermap.com.cn:8090/webgl/Build/Documentation/S3MTilesLayer.html?classFilter=layer)



> 图块/图元: 图层下面的块.



## 加载图层

### 单个图层

```js
CesiumCtl.viewer.scene.addS3MTilesLayerByScp( url, opt )
```

| 参数 | 类型   | 描述                     |
| ---- | ------ | ------------------------ |
| url  | String | 图层路径                 |
| opt  | Object | { name... } 设置图层属性 |

### 多个图层

```js
// 使用方法同 promise.when
Cesium.when.all( layerPromises: Array )
```



## 代码

```js
/**
 * 加载单个图层
 * @param { String } id 图层名 example: XZMTGX // 现状码头岸线
 */
load ( id ) {
    return CesiumCtl.viewer.scene.addS3MTilesLayerByScp( ( IP + URLS[ id ].url ), {
        name: URLS[ id ].name
    } ).then( ( layer ) => {
        // do something...

        console.log( '>>> Layer load succeed:', layer.name )
    }, ( error ) => {
        console.log( '<<< Layer load fail:', error )
    } )
},
```



## Layers

[在线文档](http://support.supermap.com.cn:8090/webgl/Build/Documentation/Layers.html?classFilter=layer)

### 获取

```js
// 创建
var layers = new Cesium.Layers()
```

```js
// imagerLayers 影像服务实例
var layer = imageryLayers._layers
```



### 方法

| 方法             | 参数                       | 描述             |
| ---------------- | -------------------------- | ---------------- |
| find             | ( name: String )  图层名称 | 查找图层         |
| add              | ( layer: S3MTilesLayer )   | 向图层集添加图层 |
| getSelectedLayer |                            | 获取选中的图层   |



## 实例属性

| 属性    | 类型    | 描述           |
| ------- | ------- | -------------- |
| visible | Boolean | 是否可见, 显示 |
|         |         |                |



## 实例方法

| 方法           | 参数                               | 描述                                                         |
| -------------- | ---------------------------------- | ------------------------------------------------------------ |
| getSelection   |                                    | 获取选中的图块                                               |
| setObjsVisible | ( ids: Array, isVisible: Boolean ) | 根据图元ID列表，设置对应的图元的可见性，并与该图层其他图元成互斥可见关系 |
|                |                                    |                                                              |



## Setting

### 图层多选

```js
this.layer.multiChoose = true
```

