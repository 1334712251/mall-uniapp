<template>
	<view style="width: 750rpx; background-color: #FFFFFF; background-image: url(../../static/jd/ii.png);"
		:style="{'height':(capsuleTop+capsuleHeight)*2+'px'}">
		<!-- 	<image src="../../static/images/demo/cate_01.png" :style="{'height':(capsuleTop+capsuleHeight)*2+'px'}">
			
		</image> -->
		<!-- 自定义Placeholder -->
		<view :style="{'height':(capsuleTop+capsuleHeight)+'px'}"></view>
		<view :style="{'height':(capsuleTop+capsuleHeight)+'px'}">
			<uni-search-bar :radius="100" :cancelButton="auto" placeholder="电动牙刷" @confirm="search" :focus="true"
				bgColor="#F5F5F5">
			</uni-search-bar>
		</view>
	</view>
</template>

<script>
	export default {
		name: "index-head",
		data() {
			return {
				capsuleTop: 0,
				capsuleHeight: 0,
				systemHeight: 0,
				systemBarHeight: 0,
			};
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
		},
		mounted() {
			// this.calculateHeigth();
			this.getMenuButtonBoundingClientRect();
			this.getSystemInfo();
		}
	}
</script>

<style scoped>
</style>
