<!-- ---
nav: zh-CN
--- -->


### Selector

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/selector" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group :title="'no placeholder, the current value is : ' + defaultValue">
      <aui-selector ref="defaultValueRef" title="省份" :options="list" v-model="defaultValue"></aui-selector>
    </aui-group>

    <div style="padding:15px;">
      <aui-button type="primary" @click.native="getValue('defaultValueRef')">get full value</aui-button>
    </div>
    <aui-group title="with placeholder">
      <aui-selector placeholder="请选择省份" v-model="demo01" title="省份" name="district" :options="list" @change="onChange"></aui-selector>
    </aui-group>

    <aui-group title="without title">
      <aui-selector placeholder="请选择省份" v-model="demo02" :options="list"></aui-selector>
    </aui-group>

    <aui-group title="set value=广西">
      <aui-selector v-model="value1" title="省份" :options="plainList" @change="onChange"></aui-selector>
    </aui-group>

    <aui-group title="readonly, displays just like a cell">
      <aui-selector value="gd" readonly title="省份" :options="list"></aui-selector>
    </aui-group>

    <aui-group title="use plain options">
      <aui-selector ref="plainValueRef" value="C" title="Selector" :options="list1" @change="onChange"></aui-selector>
    </aui-group>

    <div style="padding:15px;">
      <aui-button type="primary" @click.native="getValue('plainValueRef')">get full value</aui-button>
    </div>

    <aui-group :title="'boolean selector: ' + value3">
      <aui-selector v-model="value3" title="Aui Is Cool" :options="list2"></aui-selector>
    </aui-group>

        <aui-group :title="$t('set valueMap for directly using API data')" label-width="5em">
      <aui-selector ref="valueMapRef" v-model="valueMapValue" :value-map="['idValue', 'idLabel']" title="Selector" :options="valueMapList" @change="onChange"></aui-selector>
      <aui-cell-box align-items="flex-start"><pre>{{ valueMapList }}</pre></aui-cell-box>
      <aui-cell title="value" :value="valueMapValue"></aui-cell>
    </aui-group>
    
    <div style="padding:15px;">
      <aui-button type="primary" @click.native="getValue('valueMapRef')">get full value</aui-button>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      demo01: null,
      demo02: '',
      defaultValue: 'gd',
      plainList: ['广东', '广西'],
      list: [{key: 'gd', value: '广东'}, {key: 'gx', value: '广西'}],
      list2: [{key: true, value: '是'}, {key: false, value: '否'}],
      value1: '广西',
      value2: 'gd',
      value3: true,
      list1: ['A', 'B', 'C'],
      valueMapValue: 'key01',
      valueMapList: [{
        idValue: 'key01',
        idLabel: 'value01',
        otherProp: 'prop01'
      }, {
        idValue: 'key02',
        idLabel: 'value02',
        otherProp: 'prop02'
      }]
    }
  },
  methods: {
    onChange (val) {
      console.log(val)
    },
    getValue (ref) {
      this.$aui.alert.show({
        title: 'getFullValue',
        content: this.$refs[ref].getFullValue()
      })
    }
  }
}
</script>

```


#### Github Issue