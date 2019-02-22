<!-- ---
nav: zh-CN
--- -->


### AuiImg

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/aui-img" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <div v-for="src in list" style="background-color:yellow;text-align:center;">
      <span style="font-size:20px;">Loading</span>
      <aui-img :src="src" :webp-src="`${src}?type=webp`" @success="success" @error="error" class="ximg-demo" error-class="ximg-error" :offset="-100" container="#aui_view_box_body"></aui-img>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    success (src, ele) {
      console.log('success load', src)
      const span = ele.parentNode.querySelector('span')
      ele.parentNode.removeChild(span)
    },
    error (src, ele, msg) {
      console.log('error load', msg, src)
      const span = ele.parentNode.querySelector('span')
      span.innerText = 'load error'
    }
  },
  data () {
    return {
      list: [
        'https://o5omsejde.qnssl.com/demo/test1.jpg',
        'https://o5omsejde.qnssl.com/demo/test2.jpg',
        'https://o5omsejde.qnssl.com/demo/test0.jpg',
        'https://o5omsejde.qnssl.com/demo/test4.jpg',
        'https://o5omsejde.qnssl.com/demo/test5.jpg',
        'https://o5omsejde.qnssl.com/demo/test6.jpg',
        'https://o5omsejde.qnssl.com/demo/test7.jpg',
        'https://o5omsejde.qnssl.com/demo/test8.jpg'
      ]
    }
  }
}
</script>

<style>
.ximg-demo {
  width: 100%;
  height: auto;
}
.ximg-error {
  background-color: yellow;
}
.ximg-error:after {
  content: '加载失败';
  color: red;
}
</style>

```


#### Github Issue