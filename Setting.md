# Setting

设置一些属性, 功能.



## 设置视角变化的灵敏度

```js
scene.camera.percentageChanged = .001;
```



## 双击 Entity 跟踪行为

```js
this.viewer.cesiumWidget.screenSpaceEventHandler
        .removeInputAction( Cesium.ScreenSpaceEventType.LEFT_DOUBLE_CLICK )
```



## 禁止用于右键缩放

```js
scene.screenSpaceCameraController.zoomEventTypes = Cesium.CameraEventType.WHEEL
```



## 图层多选

```js
// layer 是图层对象
this.layer.multiChoose = true
```



## Other

```js
// 如果为真，则允许用户旋转相机。如果为假，相机将锁定到当前标题。此标志仅适用于2D和3D
scene.screenSpaceCameraController.enableRotate = false;
// 如果为真，则允许用户平移地图。如果为假，相机将保持锁定在当前位置。
// 此标志仅适用于2D和Columbus视图模式
scene.screenSpaceCameraController.enableTranslate = false;
// 如果为真，则允许用户放大和缩小。如果为假，相机将锁定到距离椭圆体的当前距离。
scene.screenSpaceCameraController.enableZoom = false;
// 如果为真，则允许用户倾斜相机。如果为假，相机将锁定到当前标题。这个标志只适用于3D和哥伦布视图。
scene.screenSpaceCameraController.enableTilt = false;
// 如果为真，则允许用户使用免费外观。如果为假，摄像机视图方向只能通过转换或旋转进行更改。
// 此标志仅适用于3D和哥伦布视图模式。
scene.screenSpaceCameraController.enableLook = false;
```

