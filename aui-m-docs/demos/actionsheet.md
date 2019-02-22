<!-- ---
nav: zh-CN
--- -->


### Actionsheet

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/actionsheet" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
      <aui-switch :title="$t('Basic Usage')" v-model="show1"></aui-switch>
      <aui-switch :title="$t('Android Theme')" v-model="show7"></aui-switch>
      <aui-switch :title="$t('Show cancel menu')" v-model="show2"></aui-switch>
      <aui-switch :title="$t('Array menu')" v-model="show5"></aui-switch>
    </aui-group>
  
    <aui-group :title="$t('Prevent closing when clicking mask')">
      <aui-switch :title="$t('Basic Usage')" v-model="show4"></aui-switch>
    </aui-group>
  
    <aui-group>
      <aui-switch :title="$t('Menu as tips')" v-model="show3"></aui-switch>
      <aui-switch :title="$t('Slot: header')" v-model="show6"></aui-switch>
      <aui-switch :title="$t('Prevent auto closing')" v-model="show8"></aui-switch>
    </aui-group>
    <aui-actionsheet v-model="show4" :menus="menus1" :close-on-clicking-mask="false" show-cancel @click-mask="console('on click mask')"></aui-actionsheet>
  
    <aui-actionsheet v-model="show1" :menus="menus1" @click-menu="click"></aui-actionsheet>
  
    <aui-actionsheet v-model="show2" :menus="menus2" @click-menu="click" show-cancel></aui-actionsheet>
  
    <aui-actionsheet v-model="show3" :menus="menus3" @click-menu="click" @click-menu-delete="onDelete" show-cancel></aui-actionsheet>
  
    <aui-actionsheet v-model="show5" :menus="menus5" show-cancel @click-menu="click5"></aui-actionsheet>
  
    <aui-actionsheet v-model="show6" :menus="menus1">
      <p slot="header" v-html="$t('Actionsheet header')"></p>
    </aui-actionsheet>
  
    <aui-actionsheet v-model="show7" :menus="menu7" theme="android" @click-menu="click">
    </aui-actionsheet>
    <aui-toast v-model="showSuccess">{{ $t('Deleted~') }}</aui-toast>
  
    <div v-transfer-dom>
      <aui-actionsheet v-model="show8" :menus="menus8" @click-menu="demo8doClose" :close-on-clicking-mask="false" :close-on-clicking-menu="false">
      </aui-actionsheet>
    </div>
  </div>
</template>



<script>

export default {
  data() {
    return {
      show1: false,
      menus1: {
        menu1: this.$t('Share to friends'),
        menu2: this.$t('Share to timeline')
      },
      show2: false,
      menus2: {
        menu1: this.$t('Take Photo'),
        menu2: this.$t('Choose from photos')
      },
      show3: false,
      show4: false,
      show5: false,
      show6: false,
      show7: false,
      show8: false,
      menus5: [{
        label: this.$t('Actionsheet header'),
        type: 'info'
      }, {
        label: 'Primary',
        type: 'primary',
        value: 'primary',
        otherProp: 'hey'
      }, {
        label: 'Warn',
        type: 'warn'
      }, {
        label: 'Disabled',
        type: 'disabled'
      }, {
        label: 'Default'
      }],
      menu7: {
        menu1: '北京烤鸭',
        menu2: '陕西油泼面',
        menu3: '西安肉夹馍'
      },
      showSuccess: false,
      menus3: {
        'title.noop': 'Actionsheet header',
        delete: '<span style="color:red">Delete</span>'
      },
      menus8: {
        menu1: this.$t('Close me'),
        menu2: this.$t('Close me')
      }
    }
  },
  methods: {
    demo8doClose() {
      this.$aui.loading.show({
        text: 'processing'
      })
      setTimeout(() => {
        this.$aui.loading.hide()
        this.show8 = false
      }, 1000)
    },
    console(msg) {
      console.log(msg)
    },
    click(key) {
      console.log(key)
    },
    click5(key, item) {
      console.log(key, item)
    },
    onDelete() {
      this.showSuccess = true
    }
  }
}
</script>

<style>
.popup0 {
  padding-bottom: 15px;
  height: 200px;
}

.popup1 {
  width: 100%;
  height: 100%;
}
</style>

```


#### Github Issue