<script>
	export default {
		globalData: {
			// 全局设置状态栏和导航栏高度
			statusBarH: 0,
			customBarH: 0,
		},
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	/* 官方ui库 */
	@import "/common/uni.css";
	/* 第三方UI库 */
	@import "animate.css";
	/* 指定义图标库 */
	@import "/common/icon.css";
	/* UI基础库 */
	@import "/common/zcm-main.css";
	/* 公共样式 */
	@import "/common/common.css";

	.container {
		width: 100%;
		height: calc(100vh - 70px);
		overflow: hidden;
	}

	.container scroll-view {
		height: 100%;
	}
</style>
