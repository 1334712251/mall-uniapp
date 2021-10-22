<template>
	<view class="prohibition">
		<!-- <view class="demo"
			:style="'height:' +  demo.height + 'px;' + 'padding-top:' + demo.top + 'px;padding-bottom:10rpx'">
			<view class="left" :style="'top:' + demo.top + 'px'">
				<view class="iconfont icon-xiaoxi"></view>
			</view>
			测试辣
		</view> -->
		<view style="width: 100%; height: 150upx; background-color: #007AFF;"></view>
		<view class="container">
			<scroll-view scroll-y="true">
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
				<view>测试</view>
			</scroll-view>
		</view>
	</view>
</template>

<script>
	export default {
		name: "index-padding",
		data() {
			return {
				// demo: {
				// 	top: 0,
				// 	height: 0
				// }
			};
		},
		// created() {
		// 	const demo = uni.getMenuButtonBoundingClientRect()
		// 	this.demo.top = demo.top
		// 	this.demo.height = demo.height
		// }
	}
</script>

<style>
	// .demo {
	// 	position: relative;
	// 	display: flex;
	// 	align-items: center;
	// 	justify-content: center;
	// 	background: #fff;
	// 	font-size: 26rpx;

	// 	.left {
	// 		float: left;
	// 		position: absolute;
	// 		width: max-content;
	// 		height: max-content;
	// 		top: 0;
	// 		bottom: 0;
	// 		left: 20rpx;
	// 		margin: auto;

	// 		.iconfont {
	// 			color: #3C3C3C;
	// 		}
	// 	}
	// }
</style>
