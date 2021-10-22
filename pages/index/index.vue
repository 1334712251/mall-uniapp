<template>
	<view>
		<!-- 轮播图组件 -->
		<swiper-image :resdata="swipers" />
		<index-nav :resdata="indexnavs" />
		<!-- 全局分割线 -->
		<divider />
		<!-- 三图广告 -->
		<three-adv :resdata="threeAdv" />
		<divider />
		<!-- 大图广告位 -->
		<card headTitle="每日精选" bodyCover="../../static/images/demo/demo4.jpg" />
	</view>
</template>

<script>
	import swiperImage from "../../components/index/swiper-image.vue";
	import indexNav from "../../components/index/index-nav.vue";
	import threeAdv from '../../components/index/three-adv.vue';
	import card from '../../components/common/card.vue';
	export default {
		components: {
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
				}
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>

</style>
