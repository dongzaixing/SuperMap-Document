# Property



## Cesium.Color

```js
var color = new Cesium.Color( 255 / 255, 0 / 255, 255 / 0, 1 ) // rgba
```



## Cesium.CallbackProperty

创建响应属性

```js
new Cesium.Entity( {
    corridor: {
        show: true,
        width: 5,
        outline: false,
        material: new Cesium.Color( 40 / 255, 148 / 255, 240 / 255, 1 ),
        positions: new Cesium.CallbackProperty( () => {
            return Cesium.Cartesian3.fromDegreesArray( this[ points ] )
        }, false )
    }
} )
```

