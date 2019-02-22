<!-- ---
nav: zh-CN
--- -->


### Calendar

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/calendar" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
           <aui-calendar :readonly="readonly" v-model="demo1" :title="$t('Basic Usage')" disable-past placeholder="placeholder" @show="log('show')" @hide="log('hide')"></aui-calendar>
    </aui-group>
    
    <div style="padding:15px;">
      <aui-button type="primary" @click.native="readonly = !readonly">{{ $t('Toggle readonly') }}</aui-button>
    </div>
    
    <aui-group>
      <aui-calendar v-model="demo2" :title="$t('Set value as TODAY')" disable-past></aui-calendar>
    </aui-group>

    <aui-group>
      <aui-calendar @change="onChange" v-model="demo3" :title="$t('Disable future')" disable-future></aui-calendar>
    </aui-group>

    <aui-group>
      <aui-calendar @change="onChange" v-model="demo4" :title="$t('Show popup header')" show-popup-header :popup-header-title="$t('Please select')" disable-future></aui-calendar>
    </aui-group>
    
    <aui-group>
      <aui-calendar placeholder="placeholder" @change="onChange" v-model="demo5" :title="$t('Multiple dates')" :popup-header-title="$t('Please select')" disable-future></aui-calendar>
    </aui-group>

     <aui-group>
      <aui-calendar :display-format="displayFormat" :placeholder="$t('Please select')" @change="onChange" v-model="demo6" :title="$t('Format multiple dates')" :popup-header-title="$t('please select')" ></aui-calendar>
      <aui-cell-box align-items="flex-start">
        <span class="selected-days">value:</span>
        <div>
          <aui-badge v-for="day in demo6" :text="day" :key="day" style="margin-right:10px;"></aui-badge>
        </div>
      </aui-cell-box>
    </aui-group>
    <div style="padding:15px;">
      <aui-button type="primary" @click.native="demo6 = []">{{ $t('Empty value') }}</aui-button>
    </div>
  </div>
</template>



<script>
export default {
  data() {
    return {
      readonly: false,
      demo1: "",
      demo2: "TODAY",
      demo3: "TODAY",
      demo4: "TODAY",
      demo5: [],
      demo6: [],
      displayFormat(value, type) {
        if (type === "string") {
          return value;
        } else {
          return value.length ? value.length + " days" : "";
        }
      }
    };
  },
  methods: {
    log(str) {
      console.log(str);
    },
    onChange(val) {
      console.log("on change", val);
    }
  }
};
</script>
<style scoped>
.selected-days {
  color: #999;
  width: 90px;
}
</style>
```


#### Github Issue