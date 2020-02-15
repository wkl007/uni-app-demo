<template>
	<html-parse :html="html"/>
</template>

<script>
//#ifdef MP-WEIXIN
import Fly from 'flyio/dist/npm/wx';
const fly = new Fly();
// #endif

//#ifndef MP-WEIXIN
import fly from 'flyio';
// #endif
import HtmlParse from '@/components/html-parse/html-parse.vue';

export default {
	components:{
		HtmlParse
	},
	data() {
		return {
			url: 'https://guixiang.oss-cn-chengdu.aliyuncs.com/website/caches/news1.html',
			html: ''
		};
	},
	onLoad() {
		this.getData();
	},
	methods: {
		async getData() {
			const result = await fly.get(this.url);
			this.html = result.data;
		}
	}
};
</script>
