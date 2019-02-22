<!-- ---
nav: zh-CN
--- -->


### Clocker

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/clocker" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <p style="padding:15px;">
      <span>{{ $t('Basic Usage') }}: </span>
      <aui-clocker :time="time1"></aui-clocker>
    </p>

    <aui-group :title=" $t('Use in cell') ">
      <aui-cell :title=" $t('Date: 2018-08-01')">
        <aui-clocker time="2018-08-01" slot="value"></aui-clocker>
      </aui-cell>
    </aui-group>

    <aui-group :title=" $t('Custom template')">
      <aui-cell :title=" $t('Date: 2018-08-01') ">
        <aui-clocker time="2018-08-01" slot="value">
          <span style="color:red">%D 天</span>
          <span style="color:green">%H 小时</span>
          <span style="color:blue">%M 分 %S 秒</span>
        </aui-clocker>
      </aui-cell>
      <aui-cell title="2018-08-08">
        <aui-clocker time="2018-08-08" slot="value">
          <span class="day">%_D1</span>
          <span class="day">%_D2</span>天
          <span class="day">%_H1</span>
          <span class="day">%_H2</span>时
          <span class="day">%_M1</span>
          <span class="day">%_M2</span>分
          <span class="day">%_S1</span>
          <span class="day">%_S2</span>秒
        </aui-clocker>
      </aui-cell>
    </aui-group>

  </div>
</template>

<script>

export default {
  ready () {
    setTimeout(() => {
      this.time1 = '2017-08-13 22:54'
    }, 5000)
  },
  data () {
    return {
      time1: '2017-07-13 21:54'
    }
  }
}
</script>

<style scoped>
.day {
  background-color:#000;
  color:#fff;
  text-align:center;
  display:inline-block;
  padding:0 3px;
  border-radius:3px;
}
</style>

```


#### Github Issue