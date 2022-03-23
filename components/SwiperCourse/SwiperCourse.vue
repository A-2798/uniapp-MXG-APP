<template>
	<list-box :name="name" :word="word" :params="params">
		<swiper class="list-swiper" next-margin="30rpx" :style="{height: `${200*rows}rpx`}">
			<swiper-item class="swiper-item" v-for="(n, index) in column" :key="index">
				<course-item v-for="(item, i) in courseData.slice(index*rows, (index+1)*rows)" :key="i" :item="item"></course-item>
			</swiper-item>
		</swiper>
	</list-box>
</template>

<script>
	import courseData from '@/mock/courseData.js'
	export default {
		props: {
			name: {
				type: String,
				default: '热门推荐'
			},
			word: { // HOT  null
				type: String,
				default: 'HOT'
			},
			column: { // 默认swiper-item展示2列
				type: Number,
				default: 2
			},
			rows: { // 默认4行
				type: Number,
				default: 3
			},
			courseData: {
				type: Array,
				default: () => courseData
			},
			
			params: Object, // 点击`全部`按钮要向搜索页传递的查询条件
		}
	}
</script>

<style lang="scss">
	// .list-swiper {
	// 	height: 800rpx;
	// }
</style>
