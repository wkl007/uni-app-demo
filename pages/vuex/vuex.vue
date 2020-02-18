<template>
	<view>
		当前颜色：{{currentColor}}
	</view>
</template>

<script>
import { mapGetters } from 'vuex';
export default {
	computed:{
		...mapGetters(['currentColor'])
	},
	data() {
		return {};
	},
	created() {
		console.log(this.currentColor,this)
	}
};
</script>

<style lang="scss"></style>
