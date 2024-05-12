<template>
	<div class="" style="z-index: 9999;overflow: hidden;" v-if="isShow">
		<!-- 蒙版 -->
		<div v-if="mask" class="position-fixed top-0 left-0 right-0 bottom-0" :style="getMaskColor" @click="hidden">
			
		</div>
		
		<!-- 弹出框内容 -->
		<div class="position-fixed bg-white" :class="getBodyClass" :style="getBodyStyle">
			<slot></slot>
		</div>
	</div>
</template>

<script>
	export default {
		props: {
			maskColor: {
				type: Boolean,
				default: false
			},
			// 是否开启蒙版
			mask: {
				type: Boolean,
				default: true
			},
			// 蒙版是否处于底部
			isFixedBottom:{
				type: Boolean,
				default: false
			}
		},
		data() {
			return {
				isShow: false,
				x: -1,
				y: -1 
			}
		},
		computed: {
			getMaskColor() {
				let hasMask = this.maskColor ? 0.5 : 0
				return `background-color: rgba(0, 0, 0, ${hasMask});`
			},
			getBodyClass() {
				let fixedBottom = this.isFixedBottom ? "left-0 right-0 bottom-0" : 'rounded border top-0'
				return fixedBottom
			},
			getBodyStyle() {
				let left = this.x > -1 ? `left:${this.x}px;` : ``
				let top = this.y > -1 ? `top:${this.y}px;` : ``
				return left + top
			}
		},
		methods: {
			show(x = -1, y = -1) {
				this.x = x
				this.y = y
				this.isShow = true
			},
			hidden() {
				this.isShow = false
			}
		}
	}
</script>

<style>
</style>