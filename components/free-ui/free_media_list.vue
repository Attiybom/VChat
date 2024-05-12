<template>
	<view hover-class="bg-danger">
		<div class="flex align-stretch" style="display: flex" @click="handleContentClick" @longpress="handleLongpress">
			<view class="flex align-center justify-center border" style="width: 145rpx">
				<!-- 头像 -->
				<freeAvaterVue :src="item.avatar" size="92" />
				<!-- 消息个数圆角 -->
				<freeBadgeVue badge-style="top:15rpx; right:15rpx" badge-class="position-absolute" :contentCount="item.contentCount" />
				<!-- <text style="padding-left: 14rpx;padding-right: 14rpx; padding-top: 6rpx;padding-bottom: 6rpx;top: 15rpx;right: 15rpx;" class="bg-danger position-absolute font-sm text-white rounded-circle">1</text> -->
			</view>
			<!-- 具体信息 -->
			<view class="flex flex-column border-bottom flex-1 py-3 pr-3" :style="{ width: remainingWidth + 'px' }">
				<view class="flex align-center justify-between mb-1">
					<view class="font-md">{{ item.nickname }}</view>
					<view class="font-sm text-light-muted">{{ item.update_time | formatTime }}</view>
				</view>

				<text class="font text-ellipsis text-light-muted">{{ item.content }}</text>
			</view>
		</div>
	</view>
</template>

<script>
import freeAvaterVue from '@/components/free-ui/free_avater.vue';
import freeBadgeVue from '@/components/free-ui/free_badge.vue';

// utils
import $Time from '@/common/free-lib/time.js';

import freeBase from '@/common/mixin/free-base.js'

export default {
	mixins: [freeBase],
	components: {
		freeAvaterVue,
		freeBadgeVue
	},
	props: {
		item: Object,
		index: Number
	},
	methods: {
		handleLongpress(e) {
			console.log('handleLongpress', e);
		},
		handleContentClick(e) {
			this.$emit('click')
			console.log('handleContentClick', e);
		}
	}
};
</script>

<style></style>
