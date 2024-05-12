<template>
	<view class="">
		<!-- 导航栏 -->
		<view class="bg-light" :class="fixed? 'fixed-top' : ''">
			<!-- 状态栏 -->
			<view :style="{ height: statusbarHeight + 'px' }"></view>
			<!-- 导航 -->
			<view class="w-100 flex align-center justify-between border" style="height: 90rpx">
				<!-- 左边 -->
				<view class="flex align-center">
					<!-- 标题 -->
					<text v-if="isShowTitle" class="font-md ml-3">
						<!-- <slot></slot> -->
						{{ getTitle }}
					</text>
				</view>

				<!-- 右边 -->
				<view class="flex align-center justify-end">
					<view class="flex align-center justify-center" style="height: 90rpx; width: 90rpx">
						<text class="iconfont font-md" @click="search">&#xe6e3;</text>
					</view>
					<view class="flex align-center justify-center" style="height: 90rpx; width: 90rpx">
						<text class="iconfont font-md" @click="openExtend">&#xe682;</text>
					</view>
				</view>
			</view>
		</view>
		<!-- 占位 -->
		<view v-if="fixed" :style="fixedHeight"></view>	
	</view>
</template>

<script>
export default {
	components: {},
	props: {
		isShowTitle: {
			type: Boolean,
			default: true
		},
		title: {
			type: String,
			default: ''
		},
		contentCountSum: {
			type: Number,
			default: 0
		},
		fixed: {
			type: Boolean,
			default: true
		}	
	},
	data() {
		return {
			statusbarHeight: 0,
			navBarHeight: 0
		};
	},
	mounted() {
		// #ifdef APP-PLUS-NVUE
		this.statusbarHeight = plus.navigator.getStatusbarHeight();
		// #endif
		this.navBarHeight = this.statusbarHeight + uni.upx2px(90);
	},
	methods: {
		openExtend() {
			console.log('openExtend')
			this.$emit('openExtend')
		},
		search() {
			
		}
	},
	computed: {
		fixedHeight() {
			return `height: ${this.navBarHeight}px`;
		},
		getTitle() {
			if (this.contentCountSum > 0) {
				return `${this.title}(${this.contentCountSum})`
			}
			return `0`
		}
	}
};
</script>

<style></style>
