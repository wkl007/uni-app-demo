<template>
	<view class="index">
		<image class="logo" src="/static/logo.png"></image>
		<view class="page-list">
			<view class="page-item" v-for="(item, index) in pageList" :key="index" @click="goPage(item.url)">
				<text>{{ item.name }}</text>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			pageList: [
				{
					name: '动画',
					url: '/pages/animate/animate'
				},
				{
					name: '字体',
					url: '/pages/font/font'
				},
				{
					name: '富文本解析',
					url: '/pages/parse/parse'
				},
				{
					name: 'request请求',
					url: '/pages/request/request'
				}
			]
		};
	},
	onLoad() {},
	methods: {
		// 前往页面
		goPage(url) {
			if (!url) return;
			uni.navigateTo({
				url
			});
		}
	}
};
</script>

<style lang="scss">
.index {
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}
	.page-list {
		width: 750rpx;
		display: flex;
		flex-wrap: wrap;
		.page-item {
			width: 375rpx;
			text-align: center;
			line-height: 100rpx;
		}
	}
}
</style>
