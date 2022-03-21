<template>
	<view>
		<view class="category">
			<view v-for="(item,index) in categor.slice(0,7)" :key="index">{{item.name}}</view>
			
			<view class="">全部分类 ></view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				categor:[
					{
						id:0,
						name:'swiper boot'
					},
					{
						id:1,
						name:'pythone'
					},
					{
						id:2,
						name:'Java'
					},{
						id:3,
						name:'UI'
					},
					{
						id:4,
						name:'arganle'
					},
					{
						id:5,
						name:'戟方天画戟'
					},
					{
						id:6,
						name:'前端'
					},
					{
						id:6,
						name:'MySql'
					}
				]
			}
		},
	}
</script>

<style lang="scss" scoped>
	.category {
		display: flex;
		justify-content: space-around;
		flex-wrap: wrap;
		padding: 0 20rpx;

		view {
			min-width: 160rpx;
			height: 70rpx;
			line-height: 70rpx;
			text-align: center;
			background: $mxg-color-grey;
			margin-top: 20rpx;
			font-size: 26rpx;
			padding: 0 10px;
		}
	}
</style>
