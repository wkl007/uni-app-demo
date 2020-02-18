<template>
	<div class="content">
		<view class="tab-list">
			<view class="tab-item" v-for="(item, index) in tabList" :key="index" :class="item.active ? 'active' : ''" @click="handleTabClick(item, index)">{{ item.name }}</view>
		</view>
		<swiper class="tab-content" :current="tabIndex" :duration="300" @change="handleSwiperChange">
			<swiper-item v-for="(item, index) in tabList" :key="index">
				<scroll-view
					:key="index"
					scroll-y
					style="height: 100%;"
					enableBackToTop
					@scrolltolower="loadMore()"
					refresher-enabled
					:refresher-threshold="100"
					refresher-background="lightgreen"
					:refresher-triggered="item.triggered"
					@refresherrefresh="handleRefresh"
				>
					<view class="list-item" v-for="(item, index) in list" :key="index">{{ item }}</view>
				</scroll-view>
			</swiper-item>
		</swiper>
	</div>
</template>

<script>
export default {
	data() {
		return {
			tabList: [
				{
					id: 'tab01',
					name: '大公司',
					newsid: 23,
					active: true,
					triggered: false
				},
				{
					id: 'tab02',
					name: '内容',
					newsid: 223,
					triggered: false
				},
				{
					id: 'tab03',
					name: '消费',
					newsid: 221,
					triggered: false
				}
			],
			tabIndex: 0,
			list: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15]
		};
	},
	onLoad() {
		this.tabList[0].triggered = true;
		setTimeout(() => {
			this.tabList[0].triggered = false;
		}, 3000);
	},
	onPullDownRefresh() {
		console.log('refresh');
		setTimeout(function() {
			uni.stopPullDownRefresh();
		}, 1000);
	},
	methods: {
		// 自定义下拉刷新
		handleRefresh() {
			if (this._freshing) return;
			this._freshing = true;
			this.tabList[this.tabIndex].triggered = true;
			setTimeout(() => {
			this.tabList[this.tabIndex].triggered = false;
				this._freshing = false;
			}, 1000);
		},
		handleTabClick(item, index) {
			if (item.active) return;
			this.tabList.forEach(i => {
				i.active = false;
			});
			this.tabList[index].active = true;
			this.tabIndex = index;
		},
		handleSwiperChange({ detail: { current } }) {
			console.log(current);
			this.tabList.forEach(i => {
				i.active = false;
			});
			this.tabList[current].active = true;
			this.tabIndex = current;
		},
		loadMore() {
			console.log('next');
		}
	}
};
</script>

<style lang="scss">
.content {
	height: 100vh;
	display: flex;
	flex-direction: column;
	.tab-list {
		display: flex;
		height: 100rpx;
		line-height: 100rpx;
		.tab-item {
			flex: 1;
			width: 100rpx;
			text-align: center;
			&.active {
				color: red;
			}
		}
	}
	.tab-content {
		flex: 1;
		.list-item {
			height: 100rpx;
			line-height: 100rpx;
			text-align: center;
			&:nth-child(2n) {
				background: #ccc;
			}
		}
	}
}
</style>
