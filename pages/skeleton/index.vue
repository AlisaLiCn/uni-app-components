<template>
  <view class="demo-skeleton">
    <view class="section-title">显示头像、标题</view>
    <skeleton
      :loading="loading"
      :avatarSize="skeleton1.avatarSize"
      :row="skeleton1.row"
      :showTitle="skeleton1.showTitle"
    >
      <view class="section-content">我是段落1</view>
    </skeleton>
    <view class="section-title">普通用法</view>
    <skeleton
      :loading="loading"
      :row="skeleton2.row"
      :showAvatar="skeleton2.showAvatar"
      :showTitle="skeleton2.showTitle"
    >
      <view class="section-content">我是段落2</view>
    </skeleton>
  </view>
</template>

<script>
import Skeleton from '../../components/skeleton/index.vue'
export default {
  components: {
    Skeleton,
  },
  data() {
    return {
      loading: true,
      skeleton1: {
        avatarSize: '52px',
        row: 3,
        showTitle: true,
      },
      skeleton2: {
        row: 5,
        showAvatar: false,
        showTitle: false,
      },
    }
  },
  created() {
    this.reloadData()
  },
  methods: {
    reloadData() {
      this.loading = true
      setTimeout(() => {
        this.loading = false
      }, 3000)
    },
  },
}
</script>

<style>
.demo-skeleton {
  padding: 40rpx 0;
}
.section-title {
  padding: 40rpx 32rpx 0;
  color: #666;
  font-size: 16px;
}
.demo-skeleton /deep/ .section-content {
  padding: 40rpx;
  color: #999;
  font-size: 14px;
}
</style>
