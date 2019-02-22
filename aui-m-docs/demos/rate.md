<!-- ---
nav: zh-CN
--- -->


### Rate

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/rate" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group title="Normal Usage">
      <aui-cell title="set default score = 5" inline-desc="total 5 stars if not specified">
        <aui-rate v-model="data3" slot="value"></aui-rate>
      </aui-cell>
      <aui-cell title="change color">
        <aui-rate v-model="data3" :max="6" active-color="#04BE02"></aui-rate>
      </aui-cell>
    </aui-group>

    <aui-group title="disabled = true">
      <aui-cell title="Your history score">
        <aui-rate v-model="data4" disabled></aui-rate>
      </aui-cell>
      <aui-cell :title="'Decimal score ' + data41 ">
        <aui-rate v-model="data41" active-color="#04BE02" disabled></aui-rate>
      </aui-cell>
      <aui-cell title="custom font-size(15px)">
        <aui-rate v-model="data42" active-color="#04BE02" :font-size="15" disabled></aui-rate>
      </aui-cell>
    </aui-group>

    <aui-group title="custom star, some symbols like ♥ ❤ are not proper.">
      <aui-cell title="loving">
        <aui-rate v-model="data4" star="♡" active-color="red" :margin="15"></aui-rate>
      </aui-cell>
            <aui-cell title="Use html">
        <aui-rate v-model="data41" star="<span>X</span>" active-color="red" :margin="15"></aui-rate>
      </aui-cell>
      <aui-cell title="Sunshine">
        <aui-rate v-model="data5" star="☼" active-color="#FF9900" :margin="4"></aui-rate>
      </aui-cell>
      <aui-cell title="Smilies">
        <aui-rate v-model="data5" star="☻" active-color="#FF9900" :margin="4"></aui-rate>
      </aui-cell>
      <aui-cell title="Different stars">
        <aui-rate v-model="data5" star="✩" active-color="#FF9900" :margin="4"></aui-rate>
      </aui-cell>
      <aui-cell title="How embarrass">
        <aui-rate v-model="data5" star="囧" active-color="#FF9900" :margin="4"></aui-rate>
      </aui-cell>
    </aui-group>

    <aui-group title="two way binding">
      <aui-cell title="Your history score">
        <aui-rate v-model="data6" active-color="#04BE02" slot="value"></aui-rate>
      </aui-cell>
      <aui-cell title="range" primary="content" :inline-desc="data6 + ''">
        <aui-range v-model="data6" :step="1" :min="0" :max="5"></aui-range>
      </aui-cell>
    </aui-group>

  </div>
</template>

<script>

export default {
  data () {
    return {
      data1: 0,
      data2: 5,
      data3: 5,
      data4: 3,
      data41: 3.7,
      data42: 3.5,
      data5: 3,
      data6: 3
    }
  }
}
</script>

```


#### Github Issue