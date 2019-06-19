# 项目中的案例



## 相机旋转

```js
// 旋转
var handler = new Cesium.DrawHandler( viewer, Cesium.DrawMode.Point )
this.state = START // 状态, 进入旋转状态
handler.drawEvt.addEventListener( ( event ) => { // 旋转中
    window.setTimeout( () => this.state = ROTATING, 100 ) // 状态, 旋转中
    scene.camera.flyCircle( event.nativeEvent.object.position, 5000 )
} )
handler.activate() // 开始旋转

// 点击暂停|播放
var handlerClick = new Cesium.ScreenSpaceEventHandler( scene.canvas )
handler.setInputAction( function ( e ) {
    // 不在旋转退出
	if ( this.state !== ROTATING && this.state !== PAUSE ) { 
        return
    }

    // 正在旋转
    if ( this.scene.camera._isFlyCircle ) { // 暂停旋转
        // console.log( '>>> Stop rotate.' )
        this.scene.camera._isFlyCircle = false
        this.state = PAUSE // 状态, 暂停
    } else { // 继续旋转
        console.log( '>>> Reset rotate.' )
        this.handler.activate()
        this.scene.camera._isFlyCircle = true
    }
}, Cesium.ScreenSpaceEventType.LEFT_DOWN )
```



## 滑行

这个功能没有案例, 原理就是动态改变视角, 性能很差.

获取可以参考飞行案例. [飞行案例](http://support.supermap.com.cn:8090/webgl/examples/editor.html#flyRoute)



## 量算

官网有案例, 很详细. [在线示例](http://support.supermap.com.cn:8090/webgl/examples/editor.html#measureHandler)

