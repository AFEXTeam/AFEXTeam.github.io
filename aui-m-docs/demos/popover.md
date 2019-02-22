<!-- ---
nav: zh-CN
--- -->


### Popover

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/popover" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div style="text-align:center;">
    <aui-popover placement="top" style="margin: 20px;" @show="onShow" @hide="onHide">
      <div slot="content" class="popover-demo-content">
        hello world
      </div>
      <button class="btn btn-default">{{ $t('Popover on top') }}</button>
      <button class="btn btn-default">{{ $t('Popover on top') }}</button>
    </aui-popover>

    <aui-popover placement="bottom" style="margin: 20px;">
      <div slot="content" class="popover-demo-content">
        hello world
      </div>
      <button class="btn btn-default">{{ $t('Popover on bottom') }}</button>
      <button class="btn btn-default">{{ $t('Popover on bottom') }}</button>
    </aui-popover>

    <aui-popover placement="left" style="margin: 20px;">
      <div slot="content" class="popover-demo-content">
        hello world
      </div>
      <button class="btn btn-default">{{ $t('Popover on left') }}</button>
      <button class="btn btn-default">{{ $t('Popover on left') }}</button>
    </aui-popover>

    <aui-popover placement="right" style="margin: 20px;">
      <div slot="content" class="popover-demo-content">
        hello world
      </div>
      <button class="btn btn-default">{{ $t('Popover on right') }}</button>
      <button class="btn btn-default">{{ $t('Popover on right') }}</button>
    </aui-popover>
  </div>
</template>



<script>
export default {
  methods: {
    onShow () {
      console.log('on show')
    },
    onHide () {
      console.log('on hide')
    }
  }
}
</script>

<style scoped>
.popover-demo-content {
  /* padding: 5px 10px; */
}
</style>
```


#### Github Issue