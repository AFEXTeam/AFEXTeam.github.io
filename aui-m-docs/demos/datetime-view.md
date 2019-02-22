<!-- ---
nav: zh-CN
--- -->


### DatetimeView

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/datetime-view" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
    <div>
        <aui-datetime-view v-model="value1" ref="datetime" :format="format"></aui-datetime-view>
        <p class="info">current value: {{ value1 }}</p>
        <div style="padding:15px;">
            <aui-button @click.native="changeValue('2017-11-11')" :disabled="format !== 'YYYY-MM-DD'" type="primary">set 2017-11-11</aui-button>
            <aui-button @click.native="changeValue('2016-08-08')" :disabled="format !== 'YYYY-MM-DD'" type="primary">set 2016-08-08</aui-button>
            <aui-button @click.native="toggleFormat" type="primary">toggle format</aui-button>
            <aui-button @click.native="showPopup = true" type="primary">show popup with datetime-view</aui-button>
        </div>
        <div v-transfer-dom>
            <aui-popup v-model="showPopup">
                <aui-datetime-view v-model="value2"></aui-datetime-view>
            </aui-popup>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            value1: '2017-10-11',
            value2: '2017-10-24',
            showPopup: false,
            format: 'YYYY-MM-DD'
        }
    },
    methods: {
        toggleFormat() {
            if (this.format === 'YYYY-MM-DD') {
                this.format = 'YYYY-MM-DD HH:mm:ss'
            } else {
                this.format = 'YYYY-MM-DD'
            }
        },
        changeValue(val) {
            this.value1 = val
            this.$refs.datetime.render()
        }
    }
}
</script>

<style scoped>
.info {
    padding-top: 15px;
    text-align: center;
    color: #666;
}
</style>

```


#### Github Issue