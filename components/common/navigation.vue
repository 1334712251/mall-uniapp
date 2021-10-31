<template>
	<view class="">
		<!-- <view :style="{'height':systemBarHeight+'px'}" style="background-color: #555555; width: 750rpx;"></view> -->
		<view :style="{'height':StatusBar+'px'}" style="width: 750rpx; background-color: #FFFFFF;"></view>
		<view :style="{'height':Page_MagTOP+'px'}" style="width: 750rpx; background-color: #007AFF;"></view>
		<!-- 		<view class="status_bar_my " :style="{'height':StatusBar+'rpx','background-color':Statusbar_top_bgc}"></view>
 -->
		<!-- <view class="" style="width: 750rpx;position: fixed;z-index: 16000;"
			:style="{'top':StatusBar+'rpx','height':CustomBar+'rpx'}">
			<view class="page_title_ii" style="z-index: 999;"
				:style="{'height':CustomBar+'rpx','background-color':Statusbar_bgc,'color':color}">
				<view class="" style="
								width: 50rpx;
								" @tap="childMethod()" :style="{'height':NavHeight+'rpx','line-height':NavHeight+'rpx'}">
					<span class="iconfont" v-if='iSTotheArrow' style="font-size: 34rpx;font-weight: 700;"
						:style="{'color':color}">&#xe601;</span>
				</view>
				<text class="font-size-tile" :style="{'height':NavHeight+'rpx','line-height':NavHeight+'rpx'}"
					style="">{{HeadLineTitle}}</text>
				<view class="navigateBackrr"></view>
			</view>
		</view> -->
	</view>
</template>

<script>
	export default {
		name: "navigation",
		props: {
			HeadLineTitle: {
				type: String,
				default: '顶部标题'
			},
			Statusbar_top_bgc: {
				type: String,
				default: '#000666'
			},
			Statusbar_bgc: {
				type: String,
				default: '#fff'
			},
			color: {
				type: String,
				default: '#000'
			},
			fatherMethod: {
				type: Function,
				default: null
			},
			iSTotheArrow: {
				type: Boolean,
				default: true
			}
		},
		data() {
			return {
				StatusBar: 0,
				CustomBar: 0,
				NvaMartom: 0,
				NavHeight: 0,
				Page_MagTOP: 0,
				systemBarHeight: 0,
				systemHeight:0,
			};
		},
		methods: {
			childMethod() {
				if (this.fatherMethod) {
					this.fatherMethod()
				}
			},
			calculateHeigth() {
				let that = this
				uni.getSystemInfo({
					success: function(e) {
						console.log("uniapp提供的系统信息接口", e);
						let myStatusBar = 0
						let myCustomBar = 0
						let myNvaMartom = 0
						let myNavHeight = 0
						let custom = uni.getMenuButtonBoundingClientRect();
						console.log("小程序按钮", custom)
						myStatusBar = e.statusBarHeight;
						myNavHeight = custom.height
						myNvaMartom = custom.top - e.statusBarHeight
						myCustomBar = (myNvaMartom * 2 + custom.height) - 2
						that.StatusBar = myStatusBar * 750 / wx.getSystemInfoSync()
							.windowWidth;
						that.CustomBar = (myCustomBar * 750 / wx.getSystemInfoSync()
							.windowWidth) + 12;
						that.NvaMartom = myNvaMartom * 750 / wx.getSystemInfoSync()
							.windowWidth;
						that.NavHeight = myNavHeight * 750 / wx.getSystemInfoSync()
							.windowWidth;
						that.Page_MagTOP = that.CustomBar + that.StatusBar
					}
				})
				this.$emit("ZXNavigtionHeigth", that.Page_MagTOP)
				this.$emit("ZXStatusBar", that.StatusBar)
				this.$emit("ZXNavHeight", that.NavHeight)

				console.log("顶部状态栏高度", that.StatusBar)
				console.log("导航栏高度", that.CustomBar)
				console.log("胶囊按钮上边距", that.NvaMartom)
				console.log("胶囊按钮高度", that.NavHeight)
				console.log("页面内容距离顶部的上边距,导航栏全部高度", that.Page_MagTOP)
			},
			calculateMenu() {
				let custom = uni.getMenuButtonBoundingClientRect();
				console.log("小程序按钮", custom)
				this.StatusBar = custom.top;
				this.Page_MagTOP = custom.height;
			},
			// 获取系统信息
			getSysteminfo() {
				uni.getSystemInfo({
					success: res => {
						console.log("系统信息",res)
						this.systemHeight = res.windowHeight;
						this.systemBarHeight = res.statusBarHeight;
					}
				});
			}
		},
		mounted() {
			// this.calculateHeigth();
			this.calculateMenu();
			this.getSysteminfo();
		}

	}
</script>

<style>
	/* 	// .status_bar_my {
	// 	position: fixed;
	// 	top: 0rpx;
	// 	height: var(--status-bar-height);
	// 	width: 750rpx;
	// 	z-index: 1000;
	// 	background-color: #ffffff;
	// }

	// .page_title_ii {
	// 	display: flex;
	// 	justify-content: space-between;
	// 	align-items: center;
	// 	font-size: 36rpx;
	// 	z-index: 999;
	// 	padding: 0 25rpx;

	// 	.navigateBackrr {
	// 		width: 50rpx;
	// 		height: 50rpx;
	// 	}
	// } */
</style>
