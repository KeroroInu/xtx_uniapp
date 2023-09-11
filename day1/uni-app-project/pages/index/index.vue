<template>
	<view>
		<swiper class="banner" indicator-dots circular autoplay >
			<swiper-item v-for="item in pictures" :key="item.id" >
				<image @tap="onPreviewImage(item.url)" :src="item.url" ></image>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				 // 轮播图数据
				      pictures: [
				        {
				          id: '1',
				          url: 'https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_1.jpg',
				        },
				        {
				          id: '2',
				          url: 'https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_2.jpg',
				        },
				        {
				          id: '3',
				          url: 'https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_3.jpg',
				        },
				        {
				          id: '4',
				          url: 'https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_4.jpg',
				        },
				        {
				          id: '5',
				          url: 'https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_5.jpg',
				        },
				      ],
			}
		},
		onLoad() {

		},
		methods: {
			onPreviewImage(url) {
				// console.log(url)
				uni.previewImage({
					urls: this.pictures.map(item => item.url),
					current: url
				})
			}
		}
	}
</script>

<style>
	.banner,
	.banner image{
		width: 750rpx;
		height: 750rpx;
	}
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
