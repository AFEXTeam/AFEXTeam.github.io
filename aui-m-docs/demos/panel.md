---
nav: zh-CN
---


### Panel

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/panel" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group title="switch the type">
      <aui-radio title="type" v-model="type" :options="['1', '2', '3', '4', '5']"></aui-radio>
    </aui-group>
    <aui-panel header="图文组合列表" :footer="footer" :list="list" :type="type"  @img-error="onImgError"></aui-panel>
  </div>
</template>

<script>

export default {

  data() {
    return {
      type: '1',
      list: [{
        src: 'http://somedomain.somdomain/x.jpg',
        fallbackSrc: 'http://placeholder.qiniudn.com/60x60/3cc51f/ffffff',
        title: '标题一',
        desc: '由各种物质组成的巨型球状天体，叫做星球。星球有一定的形状，有自己的运行轨道。',
        url: '/component/cell'
      }, {
        src: 'http://somedomain.somdomain/x.jpg',
        fallbackSrc: 'http://placeholder.qiniudn.com/60x60/3cc51f/ffffff',
        title: '标题二',
        desc: '由各种物质组成的巨型球状天体，叫做星球。星球有一定的形状，有自己的运行轨道。',
        url: {
          path: '/component/radio',
          replace: false
        },
        meta: {
          source: '来源信息',
          date: '时间',
          other: '其他信息'
        }
      }],
      footer: {
        title: '查看更多',
        url: 'http://www.agree.com.cn'
      }
    }
  },
  methods: {
    onImgError (item, $event) {
      console.log(item, $event)
    }
  },
}
</script>
```


#### Github Issue