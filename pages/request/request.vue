<template>
	<html-parse :html="html"/>
</template>

<script>
//#ifdef MP
let Fly = require('flyio/dist/npm/wx');
let fly = new Fly();
// #endif

//#ifdef H5
let fly = require('flyio');
//#endif

//#ifdef APP-PLUS
let Fly = require('flyio/dist/npm/weex');
let fly = new Fly();
//#endif

export default {
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
