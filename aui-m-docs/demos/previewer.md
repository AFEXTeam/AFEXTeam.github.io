---
nav: zh-CN
---


### Previewer

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/previewer" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <img class="previewer-demo-img"
         v-for="(item, index) in list"
         :key="index"
         :src="item.src"
         width="100"
         @click="show(index)">
    <aui-previewer :list="list"
               ref="previewer"
               :options="options"></aui-previewer>
    <div v-transfer-dom>
      <aui-previewer :list="list"
                 ref="previewer"
                 :options="options"></aui-previewer>
    </div>
  </div>
</template>

<script>


export default {

  methods: {
    show(index) {
      this.$refs.previewer.show(index)
    }
  },
  data() {
    return {
      list: [{
        src: 'https://static.vux.li/demo/1.jpg',
        w: 800,
        h: 400
      },
      {
        src: 'https://static.vux.li/demo/1.jpg',
      }, {
        src: 'https://static.vux.li/demo/1.jpg'
      }],
      options: {
        getThumbBoundsFn(index) {
          // find thumbnail element
          let thumbnail = document.querySelectorAll('.previewer-demo-img')[index]
          // get window scroll Y
          let pageYScroll = window.pageYOffset || document.documentElement.scrollTop
          // optionally get horizontal scroll
          // get position of element relative to viewport
          let rect = thumbnail.getBoundingClientRect()
          // w = width
          return { x: rect.left, y: rect.top + pageYScroll, w: rect.width }
          // Good guide on how to get element coordinates:
          // http://javascript.info/tutorial/coordinates
        }
      }
    }
  }
}
</script>
```


#### Github Issue