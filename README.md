<view class="container">
  <view class="user" tt:if="{{hasUser}}">
    <text class="text">Hello World</text>
     <button bindtap="tap">Button</button>
  </view>
</view>
<view class="container">
  <view class="userinfo">
    <button bindtap="showMessage">点击按钮显示Message</button>
  </view>
  <view class="textinfo" tt:if="{{isShowMessage}}">
    <text class="text">{{message}}</text>
  </view>
</view>
const app = getApp()
Page({
  data: {
    message: 'Hello World',
    isShowMessage: false,
  },
  showMessage() {
    this.setData({
      isShowMessage: true,
    })
  },
})
<view class="container">
  <view class="model">
    <text class="info">{{message}}</text>
    <button bindtap="showModel">显示设备型号</button>
  </view>
</view>
const app = getApp()
Page({
  data: {
    message: '',
  },
  showModel() {
    // 获取设备信息
    tt.getSystemInfo({
      success: (res) => {
        // 调用this.setData可以进行状态管理
        this.setData({
          message: res.model,
        })
      },
    })
  }
})
