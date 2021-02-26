<template>
  <div class="home">
    <!-- 搜索 -->
    <div class="cu-bar search bg-olive light">
      <div class="search-form round">
        <text class="cuIcon-search"></text>
        <input @focus="InputFocus" @blur="InputBlur" :adjust-position="false" type="text" placeholder="搜索图书" confirm-type="search"/>
      </div>
      <div class="action">
        <button class="cu-btn bg-green shadow-blur round">搜索</button>
      </div>
    </div>
    <!-- 轮播图 -->
    <swiper class="screen-swiper" :indicator-dots="true" :circular="true"
		 :autoplay="true" interval="2000" duration="500">
			<swiper-item v-for="(item,index) in swiperList" :key="index">
				<image :src="item.url" mode="aspectFill" v-if="item.type=='image'"></image>
				<video :src="item.url" autoplay loop muted :show-play-btn="false" :controls="false" objectFit="cover" v-if="item.type=='video'"></video>
			</swiper-item>
		</swiper>
    <!-- 分类 -->
    <div class="cu-list grid no-border" :class="['col-' + gridCol]">
      <div class="cu-item" v-for="(item,index) in cuIconList" :key="index">
        <div :class="['cuIcon-' + item.cuIcon,'text-' + item.color]">
          <div class="cu-tag badge" v-if="item.badge!=0">
            <block v-if="item.badge!=1">{{item.badge>99?'99+':item.badge}}</block>
          </div>
        </div>
        <text>{{item.name}}</text>
      </div>
    </div>
    <!-- 推荐列表 -->
    <view class="cu-card article no-card">
			<view class="cu-item shadow">
				<view class="content">
					<image src="/static/image/book/1.webp"
					 mode="aspectFill"></image>
					<view class="desc">
            <view class="text-cut">2021最新民法典及相关司法解释汇编</view>
						<view class="text-content">法律出版社法规中心 著</view>
						<view>
							<view class="cu-tag bg-red light bi round">¥ 8</view>
              <span class="cart-btn">
                <text class="text-mi cu-btn cuIcon-cart bg-green text-white round"></text>
              </span>
						</view>
					</view>
				</view>
			</view>
      <view class="cu-item shadow">
				<view class="content">
					<image src="/static/image/book/2.webp"
					 mode="aspectFill"></image>
					<view class="desc">
            <view class="text-cut">我真的坐不住了</view>
						<view class="text-content">孙悦礼 著</view>
						<view>
							<view class="cu-tag bg-red light bi round">¥ 26</view>
              <span class="cart-btn">
                <text class="text-mi cu-btn cuIcon-cart bg-green text-white round"></text>
              </span>
						</view>
					</view>
				</view>
			</view>
		</view>
  </div>
</template>

<script>
export default {
  data() {
    return {
      swiperList: [{
        id: 0,
        type: 'image',
        url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg'
      }, {
        id: 1,
        type: 'image',
        url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big37006.jpg',
      }, {
        id: 2,
        type: 'image',
        url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big39000.jpg'
      }, {
        id: 3,
        type: 'image',
        url: '/static/image/swiper1.png'
      }],
      cuIconList: [{
        cuIcon: 'read',
        color: 'yellow',
        badge: 0,
        name: '教材'
      }, {
        cuIcon: 'form',
        color: 'blue',
        badge: 0,
        name: '小说'
      }, {
        cuIcon: 'discover',
        color: 'olive',
        badge: 0,
        name: '彩绘'
      }, {
        cuIcon: 'upstagefill',
        color: 'cyan',
        badge: 0,
        name: '考试'
      }],
      gridCol: 4,
    };
  },
  methods: {
    InputFocus(e) {
      this.InputBottom = e.detail.height
    },
    InputBlur(e) {
      this.InputBottom = 0
    }
  }
}
</script>
<style scoped>
  .home {}
  .swiper-box {
    margin: 0px 15px 0 15px
  }
  .cart-btn {
    position: absolute;
    right: 15px;
  }
</style>