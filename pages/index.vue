<template>
  <view class="demo-page">
    <slider-range
      :value="rangeValue"
      :min="rangeMin"
      :max="rangMax"
      :step="5"
      :bar-height="3"
      :block-size="26"
      background-color="#EEEEF6"
      active-color="#FF6B00"
      :format="format"
      @change="handleRangeChange"
    ></slider-range>
  </view>
</template>

<script>
import SliderRange from '../components/slider-range/index.vue'
export default {
  components: {
    SliderRange
  },
  data() {
    return {
      rangeMin: 5,
      rangMax: 200,
      rangeValue: [10, 50]
    }
  },
  methods: {
    format(val) {
      return val + 'Íò'
    },
    handleRangeChange(e) {
      this.rangeValue = e
    }
  }
}
</script>

<style>
  .demo-page{
    padding: 200upx 40upx 0;
  }
</style>
