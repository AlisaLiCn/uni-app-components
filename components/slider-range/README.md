# slider-range
uni-app 滑块区间选择组件  

可根据具体需求，修改、自定义其他内容。

## 属性说明

|属性名|类型|默认值|说明|
| -- | -- | --|--|
| value | Array<Number, Number> | [0,100] |滑块已选中区间的值|
| min | Number|  0 | 滑块区间最小值 |
| max | Number | 100 | 滑块区间最大值 | 
| step | Number | 1 | 拖动时的步长 |
| disabled | Boolean | false | 是否为禁用状态 |
| height | Number | 50 | 滑块容器高度 |
| barHeight | Number | 5 | 滑块进度条高度 |
| backgroundColor | String | #e9e9e9| 滑块进度条背景色|
| activeColor | String | #1aad19 | 已选中区间进度条颜色|
| blockSize | Number | 20 | 滑块大小 |
| blockColor | String | #fff | 滑块颜色 |
| decorationVisible | Boolean | false | 是否显示滑块内装饰元素|
| tipVisible | Boolean | true | 是否显示滑块值提示文本 |
| fomat| Function | | 滑块值提示文本格式化函数，**注意**：小程序中此属性必传，否则会报错，如果无需格式化，可以简单返回原始值： `format(val) {  return val    }`；H5中可以不传。|


## 使用示例

```html

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
  :decorationVisible="true"
  @change="handleRangeChange"
></slider-range>


```

```javascript

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
	  return val + '%'
	},
	handleRangeChange(e) {
	  this.rangeValue = e
	}
  }
}
```

效果图

![](http://images.alisali.cn/img_20190715175325.png)
