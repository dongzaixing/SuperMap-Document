# Event

注册事件.



> 1. KeyboardEventModifier: alt + 点击, Cesium.KeyboardEventModifier.ALT
>
> 2. 好像没办法单独删除一个事件. 只能根据事件 handler 以及事件类型来删除. 但是可以使用发布订阅的模式来注册事件.



## 鼠标

[在线文档](http://support.supermap.com.cn:8090/webgl/Build/Documentation/ScreenSpaceEventHandler.html?classFilter=ScreenSpaceEventHandler)

```js
var handler = new Cesium.ScreenSpaceEventHandler( scene.canvas )
```

### 注册事件

```js
// mousedown 左键点击
handler.setInputAction( function ( e ) {
	// do something...
}, Cesium.ScreenSpaceEventType.LEFT_DOWN /* modifier */ )
```

### 注销事件

```js
handler.removeInputAction( Cesium.ScreenSpaceEventType.LEFT_CLICK )
```

### 方法

| 方法    | 参数 | 描述                         |
| ------- | ---- | ---------------------------- |
| destroy |      | 解除 handler 所有绑定的事件. |
|         |      |                              |
|         |      |                              |



## 量算

[在线文档](http://support.supermap.com.cn:8090/webgl/Build/Documentation/MeasureHandler.html?classFilter=Handler)

```js
// @param { MeasureMode } mode 指定测量模式
var handler = new new Cesium.MeasureHandler( viewer, mode )
```



## 视角变化事件

```js
camera.changed.addEventListener( callback: Function )
camera.changed.removeEventListener( callback: Function )
```

```js
// 视角高度变化判断
static [ _changeCamera ] () {
    let ctl = this.entites.ctl
    let cartographic = Cesium.Cartographic.fromCartesian( ctl.scene.camera.position )

    this.pointHeight = ctl.camera.height

    if ( cartographic.height > this.cameraHight ) {
        // 缩小成点
        this.trigger( {
            type: 'camera:small',
            ctl,
            camera: ctl.camera
        } )
    } else {
        // 正常显示
        this.trigger( {
            type: 'camera:normal',
            ctl,
            camera: ctl.camera
        } )
    }
}
```



## 其他事件

- [DrawHandler](http://support.supermap.com.cn:8090/webgl/Build/Documentation/DrawHandler.html)
- [MeasureHandler](http://support.supermap.com.cn:8090/webgl/Build/Documentation/MeasureHandler.html)
- [ScreenSpaceEventHandler](http://support.supermap.com.cn:8090/webgl/Build/Documentation/ScreenSpaceEventHandler.html)
- [SvgPathBindingHandler](http://support.supermap.com.cn:8090/webgl/Build/Documentation/SvgPathBindingHandler.html)