<template>
	<view>
		<parser :html="html"/>
	</view>
</template>

<script>
import Parser from '@/components/html-parse/jyf-parser';
// https://shancai-1257275967.coscd.myqcloud.com/shancai/images/20190731/center2019073111173646.html
export default {
	components: {
		Parser
	},
	props: {
		html: {
			type: String,
			default: ''
		}
	}
};
</script>
