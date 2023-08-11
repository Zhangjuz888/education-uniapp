<template>
	<view class="banner-box">
		<view class="banner-bg" :style="{'background-image': `linear-gradient(${bannerBackground || '#009b8c'} 50%, #fff)`}" />
		<swiper class="banner-swipper" indicator-dots indicator-color="rgba(255,255,255,0.5)"
			indicator-active-color="#fff" autoplay :interval="4000" @change="swiperChange">
			<swiper-item v-for="(bannerItems, bannerIndex) in bannerList" :key="bannerIndex"
				:current="current" class="swiper-item">
				<image :src="bannerItems.imageUrl" />
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		props: {
			bannerList: {
				type: Array,
				default: () => [{
						id: 1,
						background: '#009b8c',
						imageUrl: "/static/images/it01.png",
					},
					{
						id: 2,
						background: '#6e3de6',
						imageUrl: "/static/images/it02.png",
					},
					{
						id: 3,
						background: '#0066F6',
						imageUrl: "/static/images/it03.png",
					},
					{
						id: 4,
						background: '#008D00',
						imageUrl: "/static/images/it04.png",
					}
				]
			}
		},
		data() {
			return {
				current: 0, // 当前从第几张图开始
				bannerBackground: '' // 背景颜色
			}
		},
		methods: {
			swiperChange(e) {
				this.current = e.detail.current;
				this.bannerBackground = this.bannerList[this.current].background;
			}
		}
	}
</script>

<style lang="scss">
	.banner-box {
		padding-top: 120rpx;
		/* #ifdef APP-PLUS */
		padding-top: calc(var(--status-bar-height) + 80rpx);
		/* #endif */ 
		.banner-bg {
			position: absolute;
			top: 0;
			width: 100%;
			height: 470rpx;
			transform: .5s;
			background-image: linear-gradient(red 50%, #fff);
		}

		.banner-swipper {
			width: 100%;
			height: 350rpx;

			.swiper-item {
				width: 100%;
				height: 100%;
				padding: 0 30rpx;
				box-sizing: border-box;

				image {
					width: 100%;
					height: 100%;
					border-radius: 15rpx;
				}
			}
		}
	}
</style>