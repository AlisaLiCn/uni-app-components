# skeleton
uni-app 骨架屏组件，用于数据加载时显示占位元素

## 属性说明

|属性名|类型|默认值|说明|
| -- | -- | --|--|
| loading | Boolean | true | 是否显示占位图 |
| showAvatar | Boolean | true | 是否显示头像占位图 |
| AvatarSize | String | 50px | 头像站占位图大小 |
| AvatarShape | String | round | 头像形状，可选值：round, square |
| showTitle | Boolean | true | 是否显示标题占位图 |
| titleWidth | String | 40% | 标题占位图宽度 |
| row | Number|  3 | 段落占位图行数 |
| animate | Boolean | true | 是否开启动画 |

## 使用示例

```html
<skeleton
  :loading="loading"
  :avatarSize="skeleton1.avatarSize"
  :row="skeleton1.row"
  :showTitle="skeleton1.showTitle"
>
  <view class="section-content">我是段落1</view>
</skeleton>
```

```javascript
import Skeleton from '../components/skeleton/index.vue'
export default {
  components: {
    Skeleton
  },
  data() {
    return {
      loading: true,
      skeleton1 : {
        avatarSize: '52px',
        row: 3,
        showTitle: true,
      }
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
```

## 效果图

![](http://images.alisali.cn/img_20191014113211.png)
