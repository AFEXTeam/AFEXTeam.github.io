---
nav: zh-CN
---


### Checklist

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/checklist" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-checklist :title="$t('Basic Usage')" :label-position="labelPosition" required :options="commonList" v-model="checklist001" @change="change"></aui-checklist>
    <div style="padding:15px;">
      <aui-button @click.native="labelPosition = labelPosition === 'left' ? '' : 'left'" type="primary">切换 label 位置</aui-button>
      <aui-button @click.native="selectFirst" type="primary">选择第1个值</aui-button>
      <aui-button @click.native="selectFirstTwo" type="primary">选择前两个值</aui-button>
      <aui-button @click.native="selectLeft" type="primary">选择剩下值</aui-button>
    </div>
  
    <aui-checklist :title="$t('preselect China and Japan(disabled)')" disabled label-position="left" :options="commonList" v-model="checklist002" @change="change"></aui-checklist>
  
    <aui-checklist :title="$t('set max=2')" :options="commonList" v-model="checklist003" :max=2 @change="change"></aui-checklist>
  
    <aui-checklist :title="$t('set max=1(radio mode)')" :options="commonList" v-model="radioValue" :max="1" @change="change"></aui-checklist>

    <aui-checklist :title="$t('set random order')" random-order :options="checklist005" v-model="checklist005Value" @change="change"></aui-checklist>
  
    <aui-checklist ref="demoObject" :title="$t('Option Array with key and value(key must be string)')" :options="objectList" v-model="objectListValue" @change="change"></aui-checklist>
    <aui-group>
      <aui-cell-box>{{ fullValues }}</aui-cell-box>
    </aui-group>
    <div style="padding:15px;">
      <aui-button type="primary" @click.native="fullValues = $refs.demoObject.getFullValue()">getFullValue()</aui-button>
    </div>
  
    <aui-checklist :title="$t('Option is Object with InlineDesc')" :options="inlineDescList" v-model="inlineDescListValue" @change="change"></aui-checklist>
  
    <aui-checklist :title="$t('Async list')" :max="3" :options="asyncList" v-model="asyncListValue" @change="change"></aui-checklist>
  
    <aui-divider>Reference</aui-divider>
    <aui-group title="See also">
      <aui-cell title="Checker" is-link link="/component/checker"></aui-cell>
    </aui-group>
  </div>
</template>



<script>
import _ from 'lodash'

export default {
  mounted() {
    setTimeout(() => {
      this.asyncList = ['A', 'B', 'C', 'D']
    }, 3000)
  },
  methods: {
    change (val, label) {
      console.log('change', val, label)
    },
    selectFirst() {
      this.checklist001 = ['China']
    },
    selectFirstTwo() {
      this.checklist001 = ['China', 'Japan']
    },
    selectLeft() {
      const left = _.without.apply(_, [this.commonList].concat(this.checklist001))
      this.checklist001 = left
    }
  },
  data() {
    return {
      fullValues: [],
      labelPosition: '',
      error: '',
      commonList: ['China', 'Japan', 'America'],
      checklist001: [],
      checklist0011: [],
      checklist002: ['China', 'Japan'],
      checklist003: ['China', 'Japan'],
      checklist005: ['01', '02', '03'],
      checklist005Value: [],
      objectList: [{ key: '1', value: '001 value' }, { key: '2', value: '002 value' }, { key: '3', value: '003 value' }],
      objectListValue: ['1', '2'],
      inlineDescList: [
        { key: '1', value: 'tiger is good', inlineDesc: 'Tiger is the king of mountain' },
        { key: '2', value: 'lion is better', inlineDesc: 'Lion is the king of woods' },
        { key: '3', value: 'camel is best, no inline-desc' }
      ],
      inlineDescListValue: [1],
      asyncList: [],
      asyncListValue: [],
      radioValue: ['China']
    }
  }
}
</script>

<style scoped>
.error {
  padding-left: 15px;
  line-height: 28px;
  color: #888;
  font-size: 12px;
}
</style>

```


#### Github Issue