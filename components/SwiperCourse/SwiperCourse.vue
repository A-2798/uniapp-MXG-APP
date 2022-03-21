<template>
	<view class="Course_box">
		<view class="bg_Course">
			<view class="Course_Bx">
				<text class="text_name">热门推荐</text>
				<text class="ico">HOT</text>
			</view>
			<view class="Course_Bs">
				<text class="Course_title">全部</text>
				<text class="iconfont icon-right"></text>
			</view>
		</view>
		
		<swiper next-margin="30rpx">
			<swiper-item class="swiper-item" v-for="(list,item) in 2" :key="item">
				<view class="swiper-item" v-for="(i,index) in 4" :key="index">
					{{item}} --- {{index}}
				</view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		}
	}
</script>

<style lang="scss" scoped>
	.bg_Course{
		display:flex;
		justify-content: space-between;
		.Course_Bx{
			.text_name{}
			.ico{
				margin-left: 10rpx;
				padding: 0 20rpx;
				font-size: 24rpx;
				color: #FFFFFF;
				background: #ff0000;
				border-radius: 30rpx 30rpx 30rpx 0;
			}
		}
		.Course_Bs{
			color:$mxg-text-color-placeholder;
			.Course_title{
				font-size: 26rpx;
			}
			.iconfont{
				font-size: 24rpx;
			}
		}
	}	
</style>
