<!-- ---
nav: zh-CN
--- -->


### Countup

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/countup" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div style="text-align:center;">
    <aui-countup :start-val="1" :end-val="1388" :duration="2" class="demo1"></aui-countup>
    <br/>
    <aui-countup :end-val="88.88" :duration="3" :decimals="2" class="demo1"></aui-countup>
    <br>
    <aui-countup :end-val="1024" :duration="2" :start="doStart" class="demo1"></aui-countup>
    <div style="padding:0 15px;">
      <aui-button @click.native="doStart=true" type="primary">Start</aui-button>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      doStart: false
    }
  }
}
</script>

<style scoped>
.demo1 {
  font-family: 'Source Sans Pro', Helvetica, Arial, sans-serif;
  font-size: 6em;
  color: #04BE02;
}
</style>

```


#### Github Issue