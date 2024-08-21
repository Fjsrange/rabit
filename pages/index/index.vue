<template>
	<swiper class="banner" indicator-dots autoplay interval="3000" circular>
		<swiper-item v-for="item in images" :key="item.id">
			<image :src="item.url" @tap="onPrveImg(item.url)"></image>
		</swiper-item>
	</swiper>
</template>

<script>
	export default {
		data() {
			return {
				images: [
					{id: '1', url: "https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_1.jpg"},
					{id: '2', url: "https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_2.jpg"},
					{id: '3', url: "https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_3.jpg"},
					{id: '4', url: "https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_4.jpg"},
					{id: '5', url: "https://pcapi-xiaotuxian-front-devtest.itheima.net/miniapp/uploads/goods_preview_5.jpg"},
				],
			}
		},
		onLoad() {
			
		},
		methods: {
			// 点击预览轮播图
			onPrveImg(url){
				console.log(url);
				uni.previewImage({
					urls: this.images.map(v=>v.url),
					current: url
				})
			},
		}
	}
</script>

<style>
	.banner,
	.banner image{
		/* width: 100%; */
		width: 750rpx;
		height: 750rpx;
	}
</style>
