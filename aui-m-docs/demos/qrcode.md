<!-- ---
nav: zh-CN
--- -->


### Qrcode

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/qrcode" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div style="text-align:center;margin-top:15px;">
    <aui-divider>{{ $t('default type = img') }}</aui-divider>
    <aui-qrcode value="http://www.agree.com.cn" type="img"></aui-qrcode>
    <br>
    <br>
    <aui-divider>{{ $t('type = canvas') }}</aui-divider>
    <aui-qrcode value="http://www.agree.com.cn"></aui-qrcode>
    <br>
    <aui-qrcode :value="value" :fg-color="fgColor"></aui-qrcode>
    <br>
    <span>{{ $t('current url') }}: {{value}}</span>
    <br>
    <span>{{ $t('current fgColor') }}: {{fgColor}}</span>
  </div>
</template>



<script>

export default {
  mounted () {
    setInterval(() => {
      this.value = `http://www.agree.com.cn?t=${Math.random()}`
      this.fgColor = `#${Math.floor(Math.random() * 16777215).toString(16)}`
    }, 1000)
  },
  data () {
    return {
      value: 'http://www.agree.com.cn',
      fgColor: '#000000'
    }
  }
}
</script>
```


#### Github Issue