<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
@import url('./static/iconfont.css');
	/*每个页面公共css */
	page{
		font-size: 28rpx;
		color:#333;
		letter-spacing: 3rpx;
		height: 100%;
	}
	.wrap{
		height: 100%;
	}
	view,text,div,span,input{
		box-sizing: border-box;
	}
</style>
