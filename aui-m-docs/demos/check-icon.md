<!-- ---
nav: zh-CN
--- -->


### CheckIcon

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/check-icon" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
    <div>
        <div style="padding:15px;">
            <aui-check-icon :value.sync="demo1">Do you agree? ({{ demo1 }})</aui-check-icon>
            <br>
            <br>
            <aui-check-icon :value.sync="demo2"
                        type="plain">Do you agree?({{ demo2 }})</aui-check-icon>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            demo1: false,
            demo2: true
        }
    }
}
</script>

```


#### Github Issue