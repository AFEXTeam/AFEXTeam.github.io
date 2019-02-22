<!-- ---
nav: zh-CN
--- -->


### PopupHeader

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/popup-header" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
    <div>
        <aui-popup-header :left-text="$t('cancel')" :right-text="$t('done')" :title="$t('Please select your card')"></aui-popup-header>
        <aui-group>
            <aui-switch v-model="show1" :title="$t('used with Popup')"></aui-switch>
        </aui-group>
        <div v-transfer-dom>
            <aui-popup v-model="show1">
                <!-- group already has a top border, so we need to hide header's bottom border-->
                <aui-popup-header :left-text="$t('cancel')" :right-text="$t('done')" :title="$t('Please select your card')" :show-bottom-border="false" @click-left="show1 = false" @click-right="show1 = false"></aui-popup-header>
                <aui-group gutter="0">
                    <aui-radio :options="[$t('Card 1'), $t('Card 2'), $t('Card 3'), $t('Card 4')]"></aui-radio>
                </aui-group>
            </aui-popup>
        </div>
    </div>
</template>



<script>
export default {
    data() {
        return {
            show1: false
        }
    }
}
</script>

```


#### Github Issue