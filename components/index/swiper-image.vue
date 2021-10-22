<template>
	<view>
		<swiper indicator-dots autoplay :interval="3000" :duration="1000" circular>
			<block v-for="(item,index) in resdata" :key="index">
				<swiper-item>
					<view class="swiper-item" @tap="event(item)">
						<image :src="item.src" lazy-load style="height: 350upx;"></image>
					</view>
				</swiper-item>
			</block>
		</swiper>
	</view>
</template>

<script>
	export default {
		name: "swiper-image",
		props: {
			resdata: Array
		},
		data() {
			return {

			};
		},
		methods: {
			event(item) {
				console.log("ggg", item.src);
			}
		},
	}
</script>

<style>

</style>
