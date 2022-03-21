<template>
	<view class="search_box">
		<input class="search_inp" type="text"  placeholder="请输入内容" disabled=true />
	</view>
</template>

<script>
</script>

<style lang="scss" scoped>
	.search_box{
		width: 100%;
		height: 70rpx;
		position: absolute;
		left: 0;
		top: 30rpx;
		z-index: 9999;
		padding: 0 40rpx;
		.search_inp{
			text-align: center;
			height: 70rpx;
			line-height: 70rpx;
			background: #F8F8F8;
			border-radius: 15px;
		}
	}
</style>
