<template>
	<view class="">
		<list-box :name="name" :word="word"></list-box>
		<scroll-view class="scroll-view noScorll" scroll-x="true" show-scrollbar="falst" scroll-left="0">
			<view class="scroll_bgbox" v-for="(item, i) in courseData" :key="i">
				<view class="scroll_on">
					<image :src="item.mainImage" lazy-load></image>
				</view>
				<view class="scroll_tw">{{item.title}}</view>
				<view class="scroll_th iconfont icon-laoshi2">{{item.nickName}}</view>
				<view class="ifont">
					<view class="scroll_fo iconfont icon-moneybag">
						{{item.priceOriginal || item.priceDiscount}}
					</view>
					<view class="scroll_fv iconfont icon-video">{{item.studyTotal}}人在学</view>
				</view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	import courseData from '@/mock/courseData.js'
	import common from '@/common/css/common.css'
	export default {
		props: {
			name: {
				type: String,
				default: '热门推荐'
			},
			word: { // HOT
				type: String,
				default: null
			},
			column: { // 默认swiper-item展示2列
				type: Number,
				default: 3
			},
			courseData: {
				type: Array,
				default: () => courseData
			},

			params: Object, // 点击`全部`按钮要向搜索页传递的查询条件
		},
		data() {
			return {

			}
		},
	}
</script>

<style lang="scss" scoped>
	.scroll-view  {
		display: flex;
		white-space: nowrap; //表示在一行显示

		.scroll_bgbox {
			display: inline-block;
			margin-right: 20rpx;
			background-color: #ffffff;
			border-radius: 10rpx;
			box-shadow: 1px 1px  3px rgba(0, 0, 0, 0.1);

			.scroll_on {
				width: 310rpx;
				height: 160rpx;

				image {
					width: 100%;
					height: 100%;
					border-radius: 10rpx;
				}
			}

			.scroll_tw {
				width: 290rpx;
				font-size: 12px;
				// 显示1行，超出部分…显示
				overflow: hidden;
				text-overflow: ellipsis; //显示省略号
				-webkit-line-clamp: 1; //最多2行
				display: -webkit-box;
				-webkit-box-orient: vertical;
				white-space: normal;
			}

			.scroll_th {
				font-size: 12px;
				padding: 10rpx 0;
				color: #999;
			}

			.ifont {
				display: flex;
				justify-content: space-between;

				.scroll_fo {
					color: $mxg-color-orange;
					font-size: 12px;
				}

				.scroll_fv {
					font-size: 12px;
				}
			}

		}
	}
</style>
