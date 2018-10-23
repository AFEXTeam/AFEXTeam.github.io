---
nav: zh-CN
---


### Alert

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/alert" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
      <aui-switch :title="$t('Show Me')" v-model="show"></aui-switch>
    </aui-group>
    <div v-transfer-dom>
      <aui-alert v-model="show" :title="$t('Congratulations')" @show="onShow" @hide="onHide"> {{ $t('Your Message is sent successfully~') }}</aui-alert>
    </div>
  
    <aui-group title="Prop: content">
      <aui-switch :title="$t('Show Me')" v-model="show2"></aui-switch>
    </aui-group>
    <div v-transfer-dom>
      <aui-alert v-model="show2" :title="$t('Congratulations')" :content="$t('Your Message is sent successfully~')"></aui-alert>
    </div>
  
    <aui-group :title="$t('Use as a plugin')">
      <aui-cell :title="$t('Show Me')" @click.native="showPlugin" is-link></aui-cell>
      <aui-cell :title="$t('Will auto close in 3s')" @click.native="showPluginAuto" is-link></aui-cell>
    </aui-group>

    <aui-group :title="$t('Use as a module')">
      <aui-cell :title="$t('Show Me')" @click.native="showModule" is-link></aui-cell>
      <aui-cell :title="$t('Will auto close in 3s')" @click.native="showModuleAuto" is-link></aui-cell>
    </aui-group>
  </div>
</template>



<script>
import AlertModule from '../../src/plugins/alert/module.js'
export default {
  data() {
    return {
      show: false,
      show1: false,
      show2: false
    };
  },
  methods: {
    showModule() {
      AlertModule.show({
        title: "AUI is Cool",
        content: this.$t("Do you agree?"),
        onShow() {
          console.log("Module: I'm showing");
        },
        onHide() {
          console.log("Module: I'm hiding now");
        }
      });
    },
    showModuleAuto() {
      this.showModule();
      setTimeout(() => {
        AlertModule.hide();
      }, 3000);
    },
    onHide() {
      console.log("on hide");
    },
    onShow() {
      console.log("on show");
    },
    showPlugin() {
      this.$aui.alert.show({
        title: "AUI is Cool",
        content: this.$t("Do you agree?"),
        onShow() {
          console.log("Plugin: I'm showing");
        },
        onHide() {
          console.log("Plugin: I'm hiding now");
        }
      });
    },
    showPluginAuto() {
      this.showPlugin();
      setTimeout(() => {
        this.$aui.alert.hide();
      }, 3000);
    }
  }
};
</script>

```


#### Github Issue