<template>
  <view class="wrap">
    <view class="progress">
      <uniSteps class="step" active-color="#f0ad4e" :options="options" :active="1"></uniSteps>
    </view>
    <view class="content">
      <view class="money">
        <text>押金</text>
        <text>（可退）</text>
        <text>99元</text>
      </view>
      <view class="dec">为确保合规用车，需交纳押金</view>
      <view class="dec">可随时退回付款账户</view>
      <view v-for="(item,index) in payWays" :key="index" class="pay-way">
        <text :class="item.icon"></text>
        <text>{{item.name}}</text>
        <radio style="transform:scale(0.7)" color="#f0ad4e" :value="item.value" :checked="item.checked" @click="selectPay(index)" />
      </view>
      <button class="pay-btn" @click="pay">押金充值</button>
      <text class="bottom-text">我是学生/教职工，去认证</text>
    </view>
  </view>
</template>

<script>
import uniSteps from '@/components/uni-steps/uni-steps.vue'
  export default {
    data(){
      return{
        options:[
          {title: '手机验证'}, 
          {title: '押金交纳'}, 
          {title: '实名认证'}, 
          {title: '立即用车'}
        ],
        payWays:[
          {
            name:'支付宝支付',
            value:1,
            icon:'iconfont iconzhifubao',
            checked:true
          },
          {
            name:'微信支付',
            value:2,
            icon:'iconfont iconweixin',
            checked:false
          },
        ],
      }
    },
    components:{
      uniSteps
    },
    methods:{
      selectPay(i){
        this.payWays.forEach(item=>{
          item.checked=false
        })
        this.payWays[i].checked=true
      },
      pay(){
        let payValue=this.payWays.filter(item=>{
          return item.checked
        })[0].value
        console.log(payValue,'选择的支付方式')
      }
    }
  }
</script>

<style lang="scss">
.wrap{
  display: flex;
  flex-direction: column;
  .progress{
    height: 190rpx;
    background: #f0f0f0;
    display: flex;
    align-items: center;
    justify-content: center;
    .step{
      width: 95%;
    }
  }
  .content{
    height: calc(100% - 190rpx);
    padding: 50rpx 40rpx 26rpx;
    display: flex;
    flex-direction: column;
    .money{
      display: flex;
      align-items: flex-end;
      height: 60rpx;
      margin-bottom: 24rpx;
      text:not(:nth-child(2)){
        font-size: 36rpx;
      }
      text:nth-child(2){
        font-size: 20rpx;
        color: #666;
        margin-right: auto;
      }
    }
    .dec{
      font-size: 22rpx;
      color: #666;
      line-height: 40rpx;
      &:last-child{
        margin-bottom: 34rpx;
      }
    }
    .pay-way{
      height: 80rpx;
      display: flex;
      align-items: center;
      border-bottom: 1px solid #eee;
      .iconzhifubao{
        color: #1296db;
      }
      .iconweixin{
        color: rgb(0,200,0);
      }
      text:nth-child(2){
        margin-left: 22rpx;
      }
      radio{
        margin-left: auto;
      }
      &:last-of-type{
        margin-bottom: 40rpx;
      }
    }
    .pay-btn{
      width: 100%;
      margin-bottom: auto;
      height: 80rpx;
      line-height: 80rpx;
      background: $theme-color;
      color: #fff;
    }
    .bottom-text{
      text-align: center;
      color: #666;
    }
  }
}
</style>