<template>
	<image :src="src" class="rounded" mode="widthFix" :style="getStyle"></image>
	
</template>

<script>

	export default {
		props: {
			size: {
				type: [String, Number],
				default: 90
			},
			src: {
				type: String,
				default: ''
			},
			isRounded: {
				type: String,
				default: 'rounded'
			}
		},
		computed: {
			getStyle() {
				return `width: ${this.size}rpx; height: ${this.size}rpx`
			}
		}
	}
</script>

<style>
</style>