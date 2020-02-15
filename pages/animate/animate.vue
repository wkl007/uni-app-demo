<template>
	<view class="animate">
		<Text>动画演示一</Text>
		<view class="animated animate-item" hover-class="fadeIn">fadeIn</view>
		<view class="animated animate-item" hover-class="bounce">bounce</view>
	</view>
</template>

<script>
export default {
	data() {
		return {};
	},
	onLoad() {
		console.log('load');
	},
	onReady() {
		console.log('ready')
	},
	methods: {}
};
</script>

<style lang="scss">
.animate {
	text-align: center;
	.animate-item {
		margin: 30rpx 0;
		border: 1rpx solid red;
		border-radius: 5rpx;
		padding: 20rpx;
		text-align: center;
	}
}
</style>
