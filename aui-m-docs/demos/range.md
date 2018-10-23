---
nav: zh-CN
---


### Range

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/range" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group title="default range">
      <aui-cell title="Default" :inline-desc="'value: '+data1" primary="content">
        <aui-range v-model="data1" @change="onChange"></aui-range>
      </aui-cell>
      <aui-cell title="allow decimals" :inline-desc="'value is: '+data2" primary="content">
        <aui-range v-model="data2" decimal></aui-range>
      </aui-cell>
      <aui-cell title="value=20" :inline-desc="'value is: '+data3" primary="content">
        <aui-range v-model="data3"></aui-range>
      </aui-cell>
    </aui-group>
    <aui-group title="min and max">
      <aui-cell title="min=8" :inline-desc="'value is: '+data4" primary="content">
        <aui-range v-model="data4" :min="8"></aui-range>
      </aui-cell>
      <aui-cell title="max=88" :inline-desc="'value is: '+data5" primary="content">
        <aui-range v-model="data5" :max="88"></aui-range>
      </aui-cell>
      <aui-cell title="min and max" :inline-desc="'value is: '+data6" primary="content">
        <aui-range v-model="data6" :min="7" :max="77"></aui-range>
      </aui-cell>
      <aui-cell title="change min and max" primary="content">
        <aui-range v-model="dynamiValue" :min="min" :max="max" :step="step"></aui-range>
      </aui-cell>
      <aui-cell title="current value" :value="dynamiValue + ''"></aui-cell>
    </aui-group>
    <br>
    <div style="margin:0 10px;">
      <aui-button type="primary" @click.native="update">update min = {{min}}, max = {{max}} and step = {{step}}</aui-button>
    </div>

    <aui-group title="Step">
      <aui-cell title="step=10" :inline-desc="'valus is: '+data7" primary="content">
        <aui-range v-model="data7" :min="7" :max="77" :step="10"></aui-range>
      </aui-cell>
    </aui-group>

    <aui-group title="disabled">
      <aui-cell title="disabled=true" :inline-desc="'valus is: '+data8" primary="content">
        <aui-range v-model="data8" disabled></aui-range>
      </aui-cell>
      <aui-cell title="Opacity" :inline-desc="'valus is: '+data8" primary="content">
        <aui-range v-model="data8" disabled :disabled-opacity="0.1"></aui-range>
      </aui-cell>
    </aui-group>

    <aui-group title="bar height">
      <aui-cell title="Line width" :inline-desc="'value is: '+data9" primary="content">
        <aui-range v-model="data9" :range-bar-height="4"></aui-range>
      </aui-cell>
    </aui-group>

    <aui-group title="custom min and max html">
      <aui-cell title="文字大小" :inline-desc="'font size: ' + data10" primary="content">
        <aui-range v-model="data10" :min="12" :max="22" min-HTML="<span style='font-size:12px;'>小</span>" max-HTML="<span style='font-size:22px;'>大</span>"></aui-range>
      </aui-cell>
      <aui-cell title="bcontentness" :inline-desc="'value is: ' + data11 + '%'" primary="content">
        <aui-range v-model="data11" min-HTML="<span style='font-size:16px;color:#F90;'>☼</span>" max-HTML="<span style='font-size:30px;color:#F90;'>☼</span>"></aui-range>
      </aui-cell>
    </aui-group>

    <aui-group title="two way binding">
      <aui-cell title="Default" primary="content">
        <aui-range v-model="data12"></aui-range>
      </aui-cell>
      <aui-cell title="Default" primary="content">
        <aui-range v-model="data12"></aui-range>
      </aui-cell>
    </aui-group>

    <aui-group :title="'use v-show ' + 'data: ' + data13">
      <aui-cell title="Default" primary="content">
        <aui-range :step="10" v-model="data13" v-show="showData13"></aui-range>
      </aui-cell>
    </aui-group>

  </div>
</template>

<script>

export default {
  mounted () {
    setTimeout(() => {
      this.showData13 = true
    }, 2000)
  },
  data () {
    return {
      data1: 0,
      data2: 0,
      data3: 20,
      data4: 18,
      data5: 28,
      data6: 37,
      data7: 17,
      data8: 25,
      data9: 50,
      data10: 14,
      data11: 30,
      data12: 0,
      data13: 10,
      showData13: false,
      min: 0,
      max: 100,
      step: 1,
      dynamiValue: 0
    }
  },
  methods: {
    onChange (val) {
      console.log('change', val)
    },
    update () {
      this.min = Math.floor(Math.random() * 30)
      this.max = Math.floor(50 + Math.random() * 100)
      this.step = 1 + Math.floor(Math.random() * 10)
    }
  }
}
</script>

```


#### Github Issue