<template>
  <view class="component-list">
    <view class="component-item" v-for="(item, index) in list" :key="index" @click="navigateTo(item.path)">
      <view>{{ item.name }}</view>
      <uni-icons type="arrowright" color="#999" size="16"></uni-icons>
    </view>
  </view>
</template>

<script>
import UniIcons from '../../components/uni-icons/uni-icons.vue'
export default {
  components: {
    UniIcons,
  },
  data() {
    return {
      list: [
        {
          name: 'slider-range',
          path: '/pages/slider-range/index',
        },
        {
          name: 'skeleton',
          path: '/pages/skeleton/index',
        },
      ],
    }
  },
  methods: {
    navigateTo(url) {
      uni.navigateTo({
        url: url,
      })
    },
  },
}
</script>

<style>
.component-list {
  padding: 30rpx 20rpx 20rpx;
}
.component-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: #666;
  padding: 20rpx;
}
.component-item:not(:last-child) {
  border-bottom: 1px solid #eee;
}
</style>
