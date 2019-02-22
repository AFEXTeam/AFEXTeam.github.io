<!-- ---
nav: zh-CN
--- -->


### AuiCircle

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/aui-circle" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div class="aui-circle-demo">
    <br>

      <aui-circle :percent="percent1" :stroke-width="10" stroke-color="#04BE02" >
        <span>{{percent1}}</span>
      </aui-circle>

    <br>

      <aui-circle :percent="percent1" :stroke-width="5" stroke-color="#04BE02">
        <span>{{percent1}}</span>
      </aui-circle>

    <br>

      <aui-circle :circleWidth="50" :circleHeight="50" :percent="percent1" :stroke-width="5" stroke-color="#04BE02">
        <span>{{percent1}}</span>
      </aui-circle>
    <br>
    <div style="width:180px;">
      <aui-range v-model="percent1" :min="0" :max="100"></aui-range>
    </div>
    <br>

      <aui-circle :percent="100" :stroke-width="3" stroke-color="#04BE02">
        <aui-icon type="success"></aui-icon>
      </aui-circle>

    <br>
      <aui-circle :percent="percent2" :stroke-width="6" :trail-width="6" :stroke-color="strokeColor2" trail-color="#ececec">
        <span :style="{color: strokeColor2}">{{percent2}}%</span>
      </aui-circle>

  </div>
</template>

<script>
export default {
  ready() {
    setInterval(this.update2, 2000);
  },

  data() {
    return {
      percent1: 10,
      percent2: 30,
      strokeColor2: "#3FC7FA"
    };
  },
  methods: {
    update2() {
      const colorMap = ["#3FC7FA", "#85D262", "#FE8C6A"];
      this.percent2 = parseInt(Math.random() * 100, 10);
      this.strokeColor2 = colorMap[parseInt(Math.random() * 3, 10)];
    }
  }
};
</script>

<style scoped>
.aui-circle-demo {
  text-align: center;
}
.aui-circle-demo > div {
  margin: 0 auto;
}
</style>

```


#### Github Issue