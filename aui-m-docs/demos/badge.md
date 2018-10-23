---
nav: zh-CN
---


### Badge
#### 交互&设计参考
- [这个控件叫：Badge/徽标/小红点](https://zhuanlan.zhihu.com/p/26107887)

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/badge" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-badge value="1"></aui-badge>
    <br>
    <aui-badge :value="123" :max="99"></aui-badge>
    <br>
    <aui-group :title="$t('Used in a Cell')">
      <aui-cell :title="$t('Red dot')"
            is-link>
        <div class="badge-value">
          <span class="vertical-middle">{{ $t('New Messages') }} &nbsp;</span>
          <aui-badge></aui-badge>
        </div>
      </aui-cell>
      <aui-cell :title="$t('Single digit')"
            is-link>
        <div class="badge-value">
          <span class="vertical-middle">{{ $t('New Messages') }} &nbsp;</span>
          <aui-badge value="8"></aui-badge>
        </div>
      </aui-cell>
      <aui-cell :title="$t('Big Number')"
            is-link>
        <div class="badge-value">
          <span class="vertical-middle">{{ $t('New Messages') }} &nbsp;</span>
          <aui-badge value="888"></aui-badge>
        </div>
      </aui-cell>
    </aui-group>
  </div>
</template>



<script>

export default {
}
</script>

<style lang="less">
.badge-value {
  display: inline-block!important;
}

.vertical-middle {
  vertical-align: middle;
}
</style>

```


#### Github Issue