<template>
  <view class="demo-page">
    <view class="slider-item">
      <slider-range
        :value="rangeValue"
        :min="rangeMin"
        :max="rangMax"
        :step="step"
        :bar-height="3"
        :block-size="26"
        background-color="#EEEEF6"
        @change="handleRangeChange"
      ></slider-range>
    </view>
    <view class="slider-item">
      <slider-range
        :value="rangeValue"
        :min="rangeMin"
        :max="rangMax"
        :step="step"
        :bar-height="3"
        :block-size="26"
        background-color="#EEEEF6"
        active-color="#FF6B00"
        :format="format"
        :decorationVisible="true"
        @change="handleRangeChange"
      ></slider-range>
    </view>
  </view>
</template>

<script>
import SliderRange from '../components/slider-range/index.vue'
export default {
  components: {
    SliderRange,
  },
  data() {
    return {
      rangeMin: 50,
      rangMax: 200,
      rangeValue: [60, 150],
      step: 10,
    }
  },
  methods: {
    format(val) {
      return `${val}%`
    },
    handleRangeChange(e) {
      this.rangeValue = e
    },
  },
}
</script>
<style>
.demo-page {
  background-color: #fff;
  padding: 200upx 40upx 0;
}

.slider-item {
  margin-bottom: 60upx;
}
</style>
