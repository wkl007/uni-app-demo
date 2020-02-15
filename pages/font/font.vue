<template>
	<view class="font">
		<view class="icon-list">
			<view class="icon-item" v-for="(item,index) in iconList" :key="index">
				<text class="iconfont" :class="item"></text>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			iconList:[
				'icon-ren',
				'icon-daohanggerenzhongxin',
				'icon-wode2',
				'icon-tubiao-',
				'icon-lijitoudi'
			]
		};
	},
};
</script>

<style lang="scss">
	.font{
		text-align: center;
		.iconfont{
			font-size: 80rpx;
		}
	}
</style>
