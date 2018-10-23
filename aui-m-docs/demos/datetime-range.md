---
nav: zh-CN
---


### DatetimeRange

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/datetime-range" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
        <aui-dev-tip>该组件和 `Datetime` 组件不同的地方是`年月日`集中显示在一栏，适合范围不大的日期选择。</aui-dev-tip>
    <aui-group :title="value + ''">
      <aui-datetime-range :title="$t('Choose')" start-date="2017-01-01" end-date="2017-02-02" :format="$t('daterange-format')" v-model="value" @change="onChange"></aui-datetime-range>
    </aui-group>


  </div>
</template>



<script>

export default {
  methods: {
    onChange (val) {
      console.log('change', val)
    }
  },
  data () {
    return {
      value: ['2017-01-15', '03', '05']
    }
  }
}
</script>
```


#### Github Issue