<template>
	<view>
		<uni-badge text="1"></uni-badge>
		<uni-badge text="2" type="success"></uni-badge>
		<uni-badge text="3" type="primary" :inverted="true"></uni-badge>
		<uni-calendar></uni-calendar>
	</view>
</template>

<script>
import { uniBadge ,uniCalendar} from '@dcloudio/uni-ui';

export default {
	components: {
		uniBadge,
		uniCalendar
	},
	data() {
		return {};
	}
};
</script>

<style lang="scss"></style>
