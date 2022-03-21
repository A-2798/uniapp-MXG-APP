<template>
	<view>
		<!-- #ifdef MP -->
		<search></search>
		<!-- #endif -->
		<SwiperBanner></SwiperBanner>
		<category></category>
		
		<view class="bg_box">
			<SwiperCourse></SwiperCourse>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
			
			}
		},
		async onLoad() {
			// #ifdef APP-PLUS
			this.placeholderData()
			// #endif
		},
		methods: {
			// 搜索框提示内容
			placeholderData() {
				// 获取当前页面实例 
				const webView = this.$scope.$getAppWebview();
				// 搜索框提示内容定时从这数组中获取
				let arr = ['APP · 微信小程序', 'Java · SpringBoot', 'SpringCloud · SpringSecurity', 'Vue · React']
				// 一加载页面就调用第1次
				let i = 0;
				webView.setStyle({
					"titleNView": {
						"searchInput": {
							"placeholder": arr[i]
						}
					}
				})

				const len = arr.length - 1
				setInterval(() => {
					// 第2次，就是下标1，每次+1，如果到达最后一个元素，则重新从0开始
					i = i < len ? ++i : 0
					webView.setStyle({
						"titleNView": {
							"searchInput": {
								"placeholder": arr[i]
							}
						}
					})
				}, 3000)
			},
		}
	}
</script>

<style lang="scss" scoped>
	.bg_box{
		padding: 10rpx 30rpx 0 30rpx;
	}

</style>
