<template>
	<view>
		<uni-nav-bar color="#ffffff" background-color="#007AFF" :status-bar="true" left-icon="arrowleft" left-text="返回" title="标题" @clickLeft="back" right-text="收藏"/>
		
	</view>
</template>

<script>
import { uniNavBar } from '@dcloudio/uni-ui';

export default {
	components: {
		uniNavBar
	},
	data() {
		return {};
	},
	methods: {
		back() {
			uni.navigateBack({
				delta: 1
			})
		},
	},
	onPullDownRefresh() {
		console.log('onPullDownRefresh')
		setTimeout(function() {
			uni.stopPullDownRefresh()
			console.log('stopPullDownRefresh')
		}, 1000)
	}
};
</script>
