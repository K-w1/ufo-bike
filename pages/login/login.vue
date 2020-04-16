<template>
  <view class="wrap">
    <view class="logo">
      <image src="https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=162479919,1590832576&fm=26&gp=0.jpg"></image>
    </view>
    <text>ufo共享单车</text>
    <input class="phone" type="number" placeholder="输入手机号码">
    <view class="vertification-code">
      <input type="number" placeholder="输入验证码">
      <button>获取验证码</button>
    </view>
    <view class="agreement">
      <checkbox style="transform:scale(0.7)" :checked="isAgree"/>
      <text>我已阅读，并同意用户注册协议</text>
    </view>
    <button class="confirm-btn" @click="toDeposit">验证手机</button>
    <view class="bottom-login">
      <text>微信登陆</text>
      <text>QQ登录</text>
    </view>
  </view>
</template>

<script>
  export default {
    data(){
      isAgree:false
    },
    methods:{
      toDeposit(){
        uni.navigateTo({
          url:'/pages/deposit/deposit'
        })
      }
    }
  }
</script>

<style lang="scss">
.wrap{
  padding: 160rpx 40rpx 26rpx;
  display: flex;
  flex-direction: column;
  align-items: center;
  .logo{
    width: 100rpx;
    height: 100rpx;
    margin-bottom: 10rpx;
    image{
      width: 100%;
      height: 100%;
    }
  }
  .logo+text{
    margin-bottom: 40rpx;
  }
  input{
    border-bottom: 1px solid #eee;
    width: 100%;
    height: 80rpx;
    padding: 20rpx 0;
  }
  .phone{
    margin-bottom: 10rpx;
  }
  .vertification-code{
    width: 100%;
    display: flex;
    margin-bottom: 10rpx;
    button{
      min-width: 200rpx;
      max-width: 200rpx;
      background: $theme-color;
      height: 80rpx;
      margin-left: 10rpx;
      font-size: 28rpx;
      color: #fff;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }
  .agreement{
    align-self: start;
    margin-bottom: 52rpx;
    text{
      font-size: 22rpx;
      color: #999;
    }
  }
  .confirm-btn{
    margin-bottom: auto;
    height: 80rpx;
    line-height: 80rpx;
    width: 100%;
    background: $theme-color;
    color: #fff;
    font-size: 32rpx;
  }
  .bottom-login{
    color: #666;
    text{
      padding: 0 50rpx;
    }
    text:first-child{
      border-right: 1px solid #999;
      
    }
  }
}
</style>