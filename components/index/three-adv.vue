<template>
	<!-- 左边w:373 h530 -->
	<!-- 右边w:375 h264  边h2-->
	<view class="d-flex">
		<image :src="resdata.big.src" lazy-load style="width: 373upx;height: 530upx;border-right: 2upx solid #F5F5F5;"
			@tap="event(resdata.big.src)"></image>
		<view class="d-flex flex-column">
			<image :src="resdata.smalltop.src" style="width: 375upx;height: 264upx;border-bottom: 2upx solid #F5F5F5;"
				@tap="event(resdata.smalltop.src)"></image>
			<image :src="resdata.smallbottom.src" style="width: 375upx;height: 264upx;" @tap="event(resdata.smallbottom.src)">
			</image>
		</view>
	</view>
</template>

<script>
	export default {
		name: "three-adv",
		props: {
			resdata: Object
		},
		data() {
			return {

			};
		},
		methods: {
			event(obj) {
				console.log(obj)
			}
		}
	}
</script>

<style>

</style>
