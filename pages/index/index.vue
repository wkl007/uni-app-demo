<template>
	<view class="index">
		<image class="logo" src="/static/logo.png"></image>
		<uni-grid :column="3" @change="handleChange">
			<uni-grid-item v-for="(item, index) in pageList" :key="index" :index="index">
				<text class="text">{{ item.name }}</text>
			</uni-grid-item>
		</uni-grid>
	</view>
</template>

<script>
import { uniGrid, uniGridItem } from '@dcloudio/uni-ui';

export default {
	components: {
		uniGrid,
		uniGridItem
	},
	data() {
		return {
			pageList: [
				{
					name: '动画',
					url: '/pages/animate/animate'
				},
				{
					name: '字体图标',
					url: '/pages/font/font'
				},
				{
					name: '富文本解析',
					url: '/pages/parse/parse'
				},
				{
					name: 'request请求',
					url: '/pages/request/request'
				},
				{
					name: 'ucharts图表',
					url: '/pages/ucharts/ucharts'
				},
				{
					name: 'uni-ui演示',
					url: '/pages/uniUI/uniUI'
				},
				{
					name: 'tabList演示',
					url: '/pages/tabList/tabList'
				},
				{
					name: '自定义导航',
					url: '/pages/navBar/navBar'
				},
				{
					name: 'vuex演示',
					url: '/pages/vuex/vuex'
				},
				{
					name:'过滤器演示',
					url:'/pages/filter/filter'
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
		},
		handleChange({ detail: { index } }) {
			this.goPage(this.pageList[index].url);
		}
	}
};
</script>

<style lang="scss">
@function rpx($value) {
	@return $value * 1rpx;
}

.index {
	text-align: center;

	.logo {
		height: rpx(200);
		width: rpx(200);
		margin-top: rpx(200);
		margin-left: auto;
		margin-right: auto;
		margin-bottom: rpx(50);
	}

	.text {
		line-height: rpx(248);
	}
}
</style>
