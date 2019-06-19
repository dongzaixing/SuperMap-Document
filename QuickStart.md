# QuickStart



## 加载底图

```js
init () {
    console.log( '>>> Cesium Init' )
	
    // 创建 viewer 示例
    this.viewer = new Cesium.Viewer( this.id, {
        infoBox: true, // 是否显示 infoBox
        selectionIndicator: true, // 选中 entity 实体后显示的绿色边框
    } );
	
    // 注册影像服务, 这里使用了天地图
    this.viewer.imageryLayers.addImageryProvider( new Cesium.TiandituImageryProvider( {
        credit: new Cesium.Credit(
            '天地图全球影像服务 数据来源：国家地理信息公共服务平台 & 四川省测绘地理信息局'
        ),
        // token 项目中使用的是官网提供的公用 token, 可自行到官网注册.
        // https://www.supermapol.com/developer
        token: URL_CONFIG.TOKEN_TIANDITU
    } ) )

    // 取消双击事件, 双击跟踪行为.
    this.viewer.cesiumWidget.screenSpaceEventHandler
        .removeInputAction( Cesium.ScreenSpaceEventType.LEFT_DOUBLE_CLICK )

    this.scene = this.viewer.scene
    this.camera = this.viewer.camera // 相机
}
```

> 注意: 需要在页面加载完成后才能创建 viewer 实例.