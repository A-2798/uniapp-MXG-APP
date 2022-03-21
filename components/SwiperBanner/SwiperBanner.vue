<template>
	<view class="banner_box">
		<view class="banner_bg" :style="{'background-image':`linear-gradient(${bannerColor || '#345DC2'} ,#fff)`}">
		</view>
		<swiper class="swiper" :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000"
			indicator-color="rgba(255, 255, 255, 0.3)" indicator-active-color="#ffffff" :current="current"
			@change="changeAutoplay">
			<swiper-item v-for="(item,index) in listswiper" :key="index">
				<image :src="item.image"></image>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		data() { 
			return {
				current: 0,
				bannerColor: '',
				listswiper: [{
						id: 1,
						background: '#45238C',
						advertUrl: '/pages/course/course-details',
						image: '/static/images/banner1.jpg'
					},
					{
						id: 2,
						background: '#006C00',
						advertUrl: '/pages/course/course-details',
						image: '/static/images/banner2.jpg'
					},
					{
						id: 3,
						background: '#0072B7',
						advertUrl: '/pages/course/course-details',
						image: '/static/images/banner3.jpg'
					}
				]
			}
		},
		methods: {
			changeAutoplay(e) {
				// console.log('e', e.detail.current, this.current)
				this.current = e.detail.current
				this.bannerColor = this.listswiper[this.current].background
			}
		},
		watch: {
			listswiper: {
				handler(newVal) {
					if (newVal && newVal.length > 0) { //获取第一个元素背景色
						this.current = 0
						this.bannerColor = this.listswiper[0] && this.listswiper[0].background
					}
				},
				immediater: true //第一次加载就执行次监听器
			}
		}

	}
</script>

<style lang="scss" scoped>
	.banner_box {
		padding-top: 120rpx;
		// background-color: red;

		/*#ifdef APP-PLUS*/
		padding-top: calc(var(--status-bar-height) + 120rpx);

		/*#endif*/
		.banner_bg {
			width: 100%;
			height: 470rpx;
			position: absolute;
			top: 0;
			// background-image: linear-gradient(to bottom ,#ff0000,#fff);//图片颜色渐变
			/*#ifdef APP-PLUS*/
			height: calc(var(--status-bar-height) + 470rpx);
			/*#endif*/
		}

		.swiper {
			width: 100%;
			height: 350rpx;
			padding: 0 30rpx;

			swiper-item {
				width: 100%;
				height: 100%;

				image {
					width: 100%;
					height: 100%;
				}
			}
		}
	}
</style>
