<template>
	<view class="list-box">
		<view class="title space-between center">
			<view class="center">
				<text class="name">热门推荐</text>
				<text class="word">HOT</text>
			</view>
			<view class="all">
				<text>全部</text>
				<text class="iconfont icon-youjiantou"></text>
			</view>
		</view>
		<swiper class="list-swiper" next-margin="30rpx">
			<swiper-item v-for="(n, index) in 2" :key="index" class="swiper-item">
				<courseItem v-for="(items, i) in 4" :key="i" />
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	import courseItem from "@/components/common/course-item/course-item.vue";
	export default {
		components: {
			courseItem
		}
	}
</script>

<style lang="scss">
	.list-box {
		@import "../../../uni.scss";
		margin-top: 60rpx;
		padding: 0 30rpx;
		.name{
			font-size: 38rpx;
			font-weight: 500;
			color: #303133;
			margin-right: 10rpx;
		}
		.word {
			font-size: 20rpx;
			background-image: linear-gradient(to right, $studyUniApp-color-orange, red);
			color: #fff;
			padding: 0 10rpx;
			border-radius: 30rpx 30rpx 30rpx 0;
		}
		
		.all{
			font-weight: normal;
			color: $studyUniApp-text-color-grey;
			font-size: 28rpx;
			.iconfont{
				font-size: 25rpx;
			}
		}
		.list-swiper{
			height: 800rpx;
		}
	}
</style> 