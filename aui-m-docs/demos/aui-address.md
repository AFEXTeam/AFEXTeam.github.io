<!-- ---
nav: zh-CN
--- -->


### AuiAddress

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/aui-address" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
      <aui-address @hide="logHide" @show="logShow" :title="title" v-model="value" :list="addressData" @shadow-change="onShadowChange" placeholder="请选择地址" inline-desc="可以设置placeholder" :show.sync="showAddress"></aui-address>
      <aui-cell title="上面value值" :value="value"></aui-cell>
    </aui-group>

    <div style="padding: 15px;">
      <aui-address style="display:none;" :popup-title="$t('selecte address')" :title="title" v-model="value" :list="addressData" placeholder="请选择地址" :show.sync="showAddress"></aui-address>
      <aui-button type="primary" @click.native="doShowAddress">单独控制显示(2s后关闭)</aui-button>
    </div>

    <aui-group>
      <aui-address :title="title" @hide="logHide" v-model="value_0_1" :list="addressData" placeholder="请选择地址">
        <template slot="title" slot-scope="props">
          <span :class="props.labelClass" :style="props.labelStyle" style="height:24px;">
            <span class="demo-icon demo-icon-big" style="font-size:20px;vertical-align:middle;"></span>
            <span style="vertical-align:middle;">地址</span>
          </span>
        </template>
      </aui-address>
    </aui-group>
    <br>
    <aui-group label-width="5em" label-align="left">
      <aui-address :title="title2" v-model="value2" raw-value :list="addressData" value-text-align="left"></aui-address>
    </aui-group>
    <br/>
    <div style="padding: 0 15px;">
      <aui-button type="primary" @click.native="changeData">改变数据（通过 id）</aui-button>
      <aui-button type="primary" @click.native="changeDataByLabels">改变数据（通过文字值）</aui-button>
      <aui-button type="primary" @click.native="changeDataByLabels2">改变数据（两级，通过文字值）</aui-button>
    </div>
    <br/>

    <aui-group>
      <aui-address title="二级省市" v-model="value3" raw-value :list="addressData"></aui-address>
    </aui-group>
    <aui-group>
      <aui-address title="只显示省市" v-model="value4" raw-value :list="addressData" hide-district></aui-address>
      <aui-cell title="value值" :value="value4"></aui-cell>
      <aui-cell title="转换成文字值" :value="getName(value4)"></aui-cell>
    </aui-group>

    <br/>
    <aui-group title="错误的地址将不能正确渲染到相应位置">
      <aui-address title="错误的值" v-model="value5" raw-value :list="addressData" inline-desc="广东省, 深圳市, 南山区"></aui-address>
    </aui-group>
  </div>
</template>



<script>
import {ChinaAddressData} from '../../src/utils'
import {value2name,name2value} from '../../src/utils'
export default {
  data() {
    return {
      title: '默认为空',
      value_0_1: [],
      value: [],
      title2: '设置值',
      value2: ['天津市', '市辖区', '和平区'],
      value3: ['广东省', '中山市', '--'],
      addressData: ChinaAddressData,
      value4: [],
      value5: ['广东省', '深圳市', '南山区'],
      showAddress: false
    }
  },
  methods: {
    doShowAddress () {
      this.showAddress = true
      setTimeout(() => {
        this.showAddress = false
      }, 2000)
    },
    onShadowChange(ids, names) {
      console.log(ids, names)
    },
    changeData() {
      this.value2 = ['430000', '430400', '430407']
    },
    getName(value) {
      // console.log(value2name(value, ChinaAddressData))
      return value2name(value, ChinaAddressData)
    },
    logHide(str) {
      console.log('hide', str)
    },
    logShow(str) {
      console.log('show')
    },
    changeDataByLabels() {
      this.value2 = ['广东省', '广州市', '天河区']
    },
    changeDataByLabels2() {
      this.value2 = ['广东省', '中山市', '--']
    },
  }
}
</script>

```


#### Github Issue