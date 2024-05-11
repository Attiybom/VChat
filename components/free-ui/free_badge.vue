<template>
	<text :style="badgeStyle" class="free-badge bg-danger font-sm text-white rounded-circle" :class="badgeClass" v-if="contentCount > 0">{{ contentCount }}</text>
</template>

<script>
export default {
	props: {
		badgeClass: {
			type: String,
			default: ''
		},
		badgeStyle: {
			type: String,
			default: ''
		},
		contentCount: {
			type: Number,
			default: 0
		}
	}
};
</script>

<style>
.free-badge {
	padding-left: 14rpx;
	padding-right: 14rpx;
	padding-top: 6rpx;
	padding-bottom: 6rpx;
}
</style>
