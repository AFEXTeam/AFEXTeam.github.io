<!-- ---
nav: zh-CN
--- -->


### InlineNumber

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/inline-number" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
    <div>
        <br>
        <div style="text-align:center;">
            <aui-inline-number width="50px"></aui-inline-number>
        </div>
        <br>
        <div style="text-align:center;">
            <aui-inline-number width="50px" button-style="round"></aui-inline-number>
        </div>
        <aui-group>
            <aui-cell title="used within cell">
                <aui-inline-number style="display:block;" :min="0" width="50px" button-style="round"></aui-inline-number>
            </aui-cell>
        </aui-group>
    </div>
</template>

<script>
export default {
}
</script>

```


#### Github Issue