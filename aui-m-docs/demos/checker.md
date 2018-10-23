---
nav: zh-CN
---


### Checker

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/checker" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div style="padding: 15px 0;">
    <aui-divider>{{ $t('Radio: no default value') }}</aui-divider>
    <div class="box">
      <aui-checker v-model="demo1" default-item-class="demo1-item" selected-item-class="demo1-item-selected">
        <aui-checker-item value="1">{{ $t('潘') }}</aui-checker-item>
        <aui-checker-item value="2">{{ $t('闲') }}</aui-checker-item>
        <aui-checker-item value="3">{{ $t('邓') }}</aui-checker-item>
        <aui-checker-item value="4">{{ $t('小') }}</aui-checker-item>
        <aui-checker-item value="5">{{ $t('驴') }}</aui-checker-item>
      </aui-checker>
      <br>
      <span>{{ $t('Current value is') }}: {{ demo1 }}</span>
      <br>
    </div>

    <aui-divider>{{ $t('radioRequired') }}</aui-divider>
    <div class="box">
      <aui-checker v-model="demo1Required" radio-required default-item-class="demo1-item" selected-item-class="demo1-item-selected">
      <aui-checker-item value="1">{{ $t('潘') }}</aui-checker-item>
      <aui-checker-item value="2">{{ $t('闲') }}</aui-checker-item>
      <aui-checker-item value="3">{{ $t('邓') }}</aui-checker-item>
      <aui-checker-item value="4">{{ $t('小') }}</aui-checker-item>
      <aui-checker-item value="5">{{ $t('驴') }}</aui-checker-item>
      </aui-checker>
      <br>
      <span>{{ $t('Current value is') }}: {{ demo1Required }}</span>
      <br>
    </div>
  
    <aui-divider>{{ $t('Radio: object value') }}</aui-divider>
    <div class="box">
      <aui-checker v-model="demo11" default-item-class="demo1-item" selected-item-class="demo1-item-selected">
        <aui-checker-item :value="item" v-for="(item, index) in items1" :key="index">{{item.value}}</aui-checker-item>
      </aui-checker>
      <br>
      <span>{{ $t('Current value is') }}: {{demo11}}</span>
      <br>
      <br>
      <aui-checker v-model="demo12" default-item-class="demo1-item" selected-item-class="demo1-item-selected">
        <aui-checker-item :value="item" v-for="(item, index) in items1" :key="index">{{item.value}}</aui-checker-item>
      </aui-checker>
      <br>
      <span>{{ $t('Current value is') }}: {{demo12}}</span>
      <br>
    </div>
  
    <aui-divider>{{ $t('Checkbox: object value') }}</aui-divider>
    <div class="box">
      <aui-checker v-model="demo21" type="checkbox" default-item-class="demo1-item" selected-item-class="demo1-item-selected">
        <aui-checker-item :value="item" v-for="(item, index) in items1" :key="index">{{item.value}}</aui-checker-item>
      </aui-checker>
      <br>
      <span>{{ $t('Current value is') }}: {{demo21}}</span>
      <br>
      <br>
      <aui-checker v-model="demo22" type="checkbox" default-item-class="demo1-item" selected-item-class="demo1-item-selected">
        <aui-checker-item :value="item" v-for="(item, index) in items1" :key="index">{{item.value}}</aui-checker-item>
      </aui-checker>
      <br>
      <span>{{ $t('Current value is') }}: {{demo22}}</span>
      <br>
      <br>
      <aui-checker v-model="demo23" type="checkbox" default-item-class="demo1-item" selected-item-class="demo1-item-selected" :max="2">
        <aui-checker-item :value="item" v-for="(item, index) in items1" :key="index">{{item.value}}</aui-checker-item>
      </aui-checker>
      <br>
      <span>{{ $t('Current value is') }}: {{demo23}}</span>
      <br>
    </div>
  

    <aui-divider>{{ $t('Checkbox') }}</aui-divider>
    <div class="box">
      <aui-checker v-model="demo1Checkbox" type="checkbox" default-item-class="demo1-item" selected-item-class="demo1-item-selected">
        <aui-checker-item :value="1">{{ $t('白') }}</aui-checker-item>
        <aui-checker-item :value="2">{{ $t('富') }}</aui-checker-item>
        <aui-checker-item :value="3">{{ $t('美') }}</aui-checker-item>
      </aui-checker>
      <br>
      <span>{{ $t('Current value is') }}: {{demo1Checkbox}}</span>
      <br>
    </div>
  
    <aui-divider>{{ $t('Checkbox with max limit 2') }}</aui-divider>
    <div class="box">
      <aui-checker v-model="demo1CheckboxMax" :max="2" type="checkbox" default-item-class="demo1-item" selected-item-class="demo1-item-selected">
        <aui-checker-item value="1">1</aui-checker-item>
        <aui-checker-item value="2">2</aui-checker-item>
        <aui-checker-item value="3">3</aui-checker-item>
      </aui-checker>
      <br>
      <span>{{ $t('Current value is') }}: {{demo1CheckboxMax}}</span>
      <br>
    </div>
  
    <aui-divider>{{ $t('Default value 2') }}</aui-divider>
    <div class="box">
      <aui-checker v-model="demo2" default-item-class="demo2-item" selected-item-class="demo2-item-selected">
        <aui-checker-item value="1">1</aui-checker-item>
        <aui-checker-item value="2">2</aui-checker-item>
        <aui-checker-item value="3">3</aui-checker-item>
      </aui-checker>
      <br>
      <span>{{ $t('Current value is') }}: {{demo2}}</span>
      <br>
    </div>
  
    <aui-divider>{{ $t('Custom styles') }}</aui-divider>
    <div class="box">
      <aui-checker v-model="demo3" default-item-class="demo3-item" selected-item-class="demo3-item-selected">
        <aui-checker-item value="one">
          <img src="http://placeholder.qiniudn.com/80x50/FF3B3B/ffffff" alt="">
        </aui-checker-item>
        <aui-checker-item value="two">
          <img src="http://placeholder.qiniudn.com/80x50/FFEF7D/ffffff" alt="">
        </aui-checker-item>
        <aui-checker-item value="three">
          <img src="http://placeholder.qiniudn.com/80x50/8AEEB1/ffffff" alt="">
        </aui-checker-item>
      </aui-checker>
      <br>
      <span>{{ $t('Current value is') }}: {{demo3}}</span>
      <br>
    </div>
  
    <aui-divider>{{ $t('Used in a popup') }}</aui-divider>
    <aui-group>
      <aui-cell :title="$t('Select color')" :value="demo4" is-link @click.native="showPopup=true"></aui-cell>
    </aui-group>
    <div v-transfer-dom>
      <aui-popup v-model="showPopup" class="aui-checker-popup">
        <div style="padding:10px 10px 40px 10px;">
          <p style="padding: 5px 5px 5px 2px;color:#888;">Colors</p>
          <aui-checker
          v-model="demo4"
          default-item-class="demo4-item"
          selected-item-class="demo4-item-selected"
          disabled-item-class="demo4-item-disabled">
            <aui-checker-item :value="$t('花跟叶')" @item-click="onItemClick"> {{ $t('花跟叶') }} </aui-checker-item>
            <aui-checker-item :value="$t('鸟与树')" @item-click="onItemClick"> {{ $t('鸟与树') }} </aui-checker-item>
            <aui-checker-item :value="$t('我和你')" @item-click="onItemClick"> {{ $t('我和你') }} </aui-checker-item>
            <aui-checker-item :value="$t('全套礼品装')" disabled @item-click="onItemClick"> {{ $t('全套礼品装') }} </aui-checker-item>
          </aui-checker>
        </div>
      </aui-popup>
    </div>
  
    <aui-divider>{{ $t('A real world radio example') }} {{demo5}}</aui-divider>
    <aui-checker
    v-model="demo5"
    default-item-class="demo5-item"
    selected-item-class="demo5-item-selected"
    >
      <aui-checker-item v-for="i in [1, 2, 3]" :key="i" :value="i">￥{{i*300}}</aui-checker-item>
    </aui-checker>
    <br/>
    <aui-divider>{{ $t('A real world checkbox example') }} {{demo6}}</aui-divider>
    <aui-checker
    v-model="demo6"
    type="checkbox"
    default-item-class="demo5-item"
    selected-item-class="demo5-item-selected"
    >
      <aui-checker-item v-for="i in [1, 2, 3]" :key="i" :value="i">{{[$t('good'), $t('nice'),$t('awesome')][i - 1]}}</aui-checker-item>
    </aui-checker>
  </div>
</template>



<script>

export default {
  methods: {
    onItemClick (value, disabled) {
      console.log(value, disabled)
      if (!this.disabled) {
        this.showPopup = false
      }
    }
  },
  data () {
    return {
      items1: [{
        key: '1',
        value: 'A'
      }, {
        key: '2',
        value: 'B'
      }, {
        key: '3',
        value: 'C'
      }],
      demo1: '',
      demo1Required: '',
      demo11: null,
      demo12: {key: '2', value: 'B'},
      demo21: null,
      demo22: [{key: '2', value: 'B'}],
      demo23: null,
      demo1Checkbox: [2, 1],
      demo1CheckboxMax: ['2', '3'],
      demo2: '2',
      demo3: '',
      demo4: this.$t('花跟叶'),
      showPopup: false,
      demo5: 1,
      demo6: [2, 3]
    }
  }
}
</script>

<style scoped>
.box {
  padding: 0 15px;
}
.demo1-item {
  border: 1px solid #ececec;
  padding: 5px 15px;
}
.demo1-item-selected {
  border: 1px solid green;
}
.demo2-item {
  width: 40px;
  height: 40px;
  border: 1px solid #ccc;
  display: inline-block;
  border-radius: 50%;
  line-height: 40px;
  text-align: center;
}
.demo2-item-selected {
  border-color: green;
}
.demo3-item {
  padding: 5px 5px;
  font-size: 0;
}
.demo3-item-selected {
  outline: 1px solid #8B8AEE;
}
.demo4-item {
  background-color: #ddd;
  color: #222;
  font-size: 14px;
  padding: 5px 10px;
  margin-right: 10px;
  line-height: 18px;
  border-radius: 15px;
}
.demo4-item-selected {
  background-color: #FF3B3B;
  color: #fff;
}
.demo4-item-disabled {
  color: #999;
}
.demo5-item {
  width: 100px;
  height: 26px;
  line-height: 26px;
  text-align: center;
  border-radius: 3px;
  border: 1px solid #ccc;
  background-color: #fff;
  margin-right: 6px;
}
.demo5-item-selected {
  background: #ffffff url(../assets/demo/checker/active.png) no-repeat right bottom;
  border-color: #ff4a00;
}
</style>

```


#### Github Issue