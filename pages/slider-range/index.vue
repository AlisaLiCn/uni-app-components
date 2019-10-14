<template>
  <view class="demo-slider-range">
    <view class="section-title">普通用法</view>
    <view class="slider-item">
      <slider-range
        :value="slider1.rangeValue"
        :min="slider1.min"
        :max="slider1.max"
        :step="slider1.step"
        :bar-height="barHeight"
        :block-size="blockSize"
        :background-color="backgroundColor"
        :format="format1"
        @change="handleRangeChange"
      ></slider-range>
    </view>
    <view class="section-title">自定义</view>
    <view class="slider-item">
      <slider-range
        :value="slider2.rangeValue"
        :min="slider2.min"
        :max="slider2.max"
        :step="slider2.step"
        :bar-height="barHeight"
        :block-size="blockSize"
        :background-color="backgroundColor"
        :active-color="slider2.activeColor"
        :format="format2"
        :decorationVisible="slider2.decorationVisible"
        @change="handleRangeChange"
      ></slider-range>
    </view>
  </view>
</template>

<script>
import SliderRange from '../../components/slider-range/index.vue'
export default {
  components: {
    SliderRange,
  },
  data() {
    return {
      barHeight: 3,
      blockSize: 26,
      backgroundColor: '#EEEEF6',
      slider1: {
        min: 50,
        max: 200,
        step: 10,
        rangeValue: [50, 150],
      },
      slider2: {
        rangeMin: 0,
        rangMax: 100,
        rangeValue: [8, 80],
        step: 1,
        activeColor: '#FF6B00',
        decorationVisible: true,
      },
    }
  },
  methods: {
    format1(val) {
      return val
    },
    format2(val) {
      return `${val}%`
    },
    handleRangeChange(e) {
      this.rangeValue = e
    },
  },
}
</script>
<style>
.demo-slider-range {
  background-color: #fff;
  padding: 100rpx 40rpx 0;
}

.section-title {
  padding: 0 0 20rpx;
  color: #666;
}

.slider-item:not(:last-child) {
  margin-bottom: 100rpx;
}
</style>
