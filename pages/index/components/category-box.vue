<template>
	<view class="category-box">
		<view v-for="(categoryItems, categoryIndex) in categoryList" :key="categoryIndex">
			{{categoryItems.name}}
		</view>
		<view>全部分类</view>
	</view>
</template>

<script>
	export default {
		props: {
			categoryList: {
				type: Array,
				default: () => [{
						id: 1,
						name: '前端'
					},
					{
						id: 2,
						name: '后端'
					},
					{
						id: 3,
						name: '运维'
					},
					{
						id: 4,
						name: 'IOS'
					},
					{
						id: 5,
						name: '大数据'
					},
					{
						id: 6,
						name: '安卓'
					},
					{
						id: 7,
						name: '嵌入式开发'
					}
				]
			}
		}
	}
</script>

<style lang="scss">
	.category-box {
		display: flex;
		justify-content: space-around;
		flex-wrap: wrap;
		padding: 20rpx 30rpx 0 30rpx;
		>view{
			width: 160rpx;
			height: 70rpx;
			background: #f8f9fb;
			text-align: center;
			line-height: 70rpx;
			font-size: 26rpx;
			border-radius: 20rpx;
			overflow: hidden;
			margin-top: 15rpx;
		}
	}
</style>