---
nav: zh-CN
---


### Countdown

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/countdown" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group title="auto countdown">
      <aui-cell title="15s" v-model="value">
        <aui-countdown  v-model="time1" @finish="finish" v-show="show"></aui-countdown>
      </aui-cell>
    </aui-group>
    <aui-group title="manually">
      <aui-switch title="start" v-model="start"></aui-switch>
      <aui-cell title="15s">
        <aui-countdown  v-model="time2" :start="start" @finish="finish2"></aui-countdown>
      </aui-cell>
    </aui-group>
  </div>
</template>

<script>

export default {
  methods: {
    finish (index) {
      this.show = false
      this.value = 'completed'
      console.log('current index', index)
    },
    finish2 (index) {
      this.start = false
      this.time = 20
    }
  },
  data () {
    return {
      show: true,
      time1: 15,
      time2: 15,
      value: '',
      start: false
    }
  }
}
</script>
```


#### Github Issue