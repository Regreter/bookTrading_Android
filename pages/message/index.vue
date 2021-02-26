<template>
  <div class="message">
    <view class="cu-bar bg-white solid-bottom margin-top">
      <view class="action">
        <text class="cuIcon-title text-orange "></text> 消息列表
      </view>
    </view>
    <view class="cu-list menu-avatar">
      <view class="cu-item" @click="toChatBox">
        <view class="cu-avatar round lg" style="background-image:url(https://ossweb-img.qq.com/images/lol/web201310/skin/big10001.jpg);"></view>
        <view class="content">
          <view class="text-black">凯尔</view>
          <view class="text-gray text-sm flex">
            <view class="text-cut">
              我已天理为凭，踏入这片荒芜，不再受凡人的枷锁遏制。我已天理为凭，踏入这片荒芜，不再受凡人的枷锁遏制。
            </view>
          </view>
        </view>
        <view class="action">
          <view class="text-grey text-xs">22:20</view>
          <view class="cu-tag round bg-red sm">5</view>
        </view>
      </view>
    </view>
  </div>
</template>

<script>
export default {
  data() {
    return {
    };
  },
  methods: {
    toChatBox() {
      uni.navigateTo({
        url: '/pages/message/component/chatBox'
      });
    }
  }
}
</script>
<style scoped>

</style>