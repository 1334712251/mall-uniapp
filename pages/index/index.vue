<template>
	<view>
		<index-head></index-head>
		<scroll-view scroll-y="true" style="width: 750rpx;" :style="{'height':slideHeigth+'px'}">
			<view class="animate__bounce" style="background-color: #0077AA; height: 100rpx;"></view>
			<!-- 轮播图组件 -->
			<swiper-image :resdata="swipers" />
			<!-- 分类组件 -->
			<index-nav :resdata="indexnavs" />
			<!-- 全局分割线 -->
			<divider />
			<!-- 三图广告 -->
			<three-adv :resdata="threeAdv" />
			<divider />
			<!-- 大图广告位 -->
			<card headTitle="每日精选" bodyCover="../../static/images/demo/demo4.jpg" />
		</scroll-view>
	</view>
</template>

<script>
	import indexHead from "../../components/index/index-head.vue"
	import swiperImage from "../../components/index/swiper-image.vue";
	import indexNav from "../../components/index/index-nav.vue";
	import threeAdv from '../../components/index/three-adv.vue';
	import card from '../../components/common/card.vue';
	export default {
		components: {
			indexHead,
			swiperImage,
			indexNav,
			threeAdv,
			card
		},
		data() {
			return {
				swipers: [{
						src: "../../static/images/demo/demo4.jpg"
					},
					{
						src: "../../static/images/demo/demo4.jpg"
					},
					{
						src: "../../static/images/demo/demo4.jpg"
					}
				],
				indexnavs: [{
						src: "../../static/images/indexnav/1.png",
						text: "新品发布"
					},
					{
						src: "../../static/images/indexnav/1.png",
						text: "新品发布"
					},
					{
						src: "../../static/images/indexnav/1.png",
						text: "新品发布"
					},
					{
						src: "../../static/images/indexnav/1.png",
						text: "新品发布"
					},
					{
						src: "../../static/images/indexnav/1.png",
						text: "新品发布"
					},
					{
						src: "../../static/images/indexnav/1.png",
						text: "新品发布"
					},
					{
						src: "../../static/images/indexnav/1.png",
						text: "新品发布"
					},
					{
						src: "../../static/images/indexnav/1.png",
						text: "新品发布"
					},
					{
						src: "../../static/images/indexnav/1.png",
						text: "新品发布"
					},
					{
						src: "../../static/images/indexnav/1.png",
						text: "新品发布"
					}
				],
				threeAdv: {
					"big": {
						src: "../../static/images/demo/demo1.jpg"
					},
					"smalltop": {
						src: "../../static/images/demo/demo2.jpg"
					},
					"smallbottom": {
						src: "../../static/images/demo/demo3.jpg"
					}
				},
				capsuleTop: 0,
				capsuleHeight: 0,
				systemHeight: 0,
				systemBarHeight: 0,
			}
		},
		computed: {
			slideHeigth: function() {
				return this.systemHeight - (this.capsuleTop + this.capsuleHeight) * 2;
			},
		},
		onLoad() {
			// console.log("slideHeigth",slideHeigth)
			this.getMenuButtonBoundingClientRect();
			this.getSystemInfo();
		},
		methods: {
			getMenuButtonBoundingClientRect() {
				let result = uni.getMenuButtonBoundingClientRect();
				// console.log("小程序按钮", result)
				this.capsuleTop = result.top;
				this.capsuleHeight = result.height;
			},
			// 获取系统信息
			getSystemInfo() {
				uni.getSystemInfo({
					success: res => {
						// console.log("系统信息", res)
						this.systemHeight = res.windowHeight;
						this.systemBarHeight = res.statusBarHeight;
					}
				});
			}
		}
	}
</script>

<style>
</style>
