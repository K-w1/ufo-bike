<template>
	<view class="wrap">
		<text>uFo</text>
		<button @click="toLogin">注册/登录</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		onLoad() {

		},
		methods: {
			toLogin(){
				uni.navigateTo({
					url:'/pages/login/login'
				})
			}
		}
	}
</script>

<style lang="scss">
.wrap{
	background: #666;
	padding-bottom: 152rpx;
	display: flex;
	flex-direction: column;
	justify-content: flex-end;
	align-items: center;
	text{
		font-size: 100rpx;
		color: #fff;
		font-weight: 500;
		margin-bottom: 56rpx;
	}
	button{
		width: 382rpx;
		height: 72rpx;
		border-radius: 32rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 28rpx;
	}
}
</style>
