---
nav: zh-CN
---


### AuiTextarea

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/aui-textarea" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
      <aui-textarea :max="20" :placeholder="$t('placeholder')" @focus="onEvent('focus')" @blur="onEvent('blur')"></aui-textarea>
    </aui-group>
    <aui-group :title="$t('used with input')">
      <aui-input :placeholder="$t('title')"></aui-input>
      <aui-textarea :max="200" name="description" :placeholder="$t('placeholder')"></aui-textarea>
    </aui-group>
    <aui-group :title="$t('hide counter')">
      <aui-textarea :max="200" name="detail" :placeholder="$t('placeholder')" :show-counter="false"></aui-textarea>
    </aui-group>
    <aui-group :title="$t('autosize')">
      <aui-textarea :placeholder="$t('Type something')" :show-counter="false" :rows="1" autosize></aui-textarea>
      <aui-textarea :title="$t('title')" :placeholder="$t('Type something')" :show-counter="false" :rows="1" autosize></aui-textarea>
    </aui-group>
    <aui-group :title="$t('set height=200')">
      <aui-textarea :title="$t('title')" :max="200" :placeholder="$t('placeholder')" :show-counter="false" :height="200" :rows="8" :cols="30"></aui-textarea>
    </aui-group>
  </div>
</template>



<script>

export default {
 
  methods: {
    onEvent (event) {
      console.log('on', event)
    }
  }
}
</script>

```


#### Github Issue