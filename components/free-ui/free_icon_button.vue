<template>
	<view class="flex align-center justify-center" style="height: 90px; width: 90px">
		<text class="iconfont font-md" @click="$emit('click')">
			<slot></slot>
		</text>
	</view>
</template>

<script>
export default {
};
</script>

<style></style>
