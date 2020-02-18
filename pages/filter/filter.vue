<template>
	<view>
		<view>格式化时间：{{new Date()|dateFormat}}</view>
		<view>格式化数字：{{123456|numberFormat}}</view>
		<view>阿拉伯数字转中文数字：{{123456789|nzhFormat}}</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">

</style>
