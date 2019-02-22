<!-- ---
nav: zh-CN
--- -->


### Toast

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/toast" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <div style="padding:15px;">
      <aui-button @click.native="showPosition('top')" type="primary">Top</aui-button>
      <aui-button @click.native="showPosition('middle')" type="primary">Middle</aui-button>
      <aui-button @click.native="showPosition('bottom')" type="primary">Bottom</aui-button>
      <aui-button @click.native="showPosition('')" type="primary">Default</aui-button>  
    </div>

    <aui-toast v-model="showPositionValue" type="text" :time="800" is-show-mask text="Hello World" :position="position">{{ $t('Basic Usage') }}</aui-toast>
    <aui-group>
      <aui-switch :title="$t('Basic Usage')" v-model="show1"></aui-switch>
      <aui-switch :title="$t('type:text')" v-model="show2"></aui-switch>
      <aui-switch :title="$t('type:cancel')" v-model="show3"></aui-switch>
      <aui-switch :title="$t('type:warn')" v-model="show4"></aui-switch>
      <aui-switch :title="$t('time:1s')" v-model="show5"></aui-switch>
      <aui-switch :title="$t('long text')" v-model="show6"></aui-switch>
    </aui-group>

    <aui-toast v-model="show1" @hide="onHide">{{ $t('Basic Usage') }}</aui-toast>
    <aui-toast v-model="show2" type="text">{{$t('success')}}</aui-toast>
    <aui-toast v-model="show3" type="cancel">{{$t('type:cancel')}}</aui-toast>
    <aui-toast v-model="show4" type="warn">{{$t('type:warn')}}</aui-toast>
    <aui-toast v-model="show5" :time="1000">{{$t('time:1s')}}</aui-toast>
    <aui-toast v-model="show6" type="text" width="20em">{{$t('show me code')}}</aui-toast>

    <aui-group :title="$t('prop:text')">
      <aui-switch :title="$t('type:success')" v-model="show7"></aui-switch>
      <aui-switch :title="$t('type:text')" v-model="show8"></aui-switch>
    </aui-group>

    <aui-toast v-model="show7" text="Hello World"></aui-toast>
    <aui-toast v-model="show8" type="text" text="Hello World"></aui-toast>

    <aui-group :title="$t('As a plugin(>=v0.1.3)')">
      <aui-switch :title="$t('default')" v-model="show9" @change="onChange"></aui-switch>
    </aui-group>

    <div style="padding:15px;">
      <aui-button type="primary" @click.native="$aui.toast.text('How are you~', 'top')">use text function</aui-button> 
    </div>
  </div>
</template>



<script>
export default {
  
  methods: {
    showPosition (position) {
      this.position = position
      this.showPositionValue = true
    },
    onHide () {
      console.log('on hide')
    },
    onChange (val) {
      const _this = this
      if (val) {
        this.$aui.toast.show({
          text: 'Hello World',
          onShow () {
            console.log('Plugin: I\'m showing')
          },
          onHide () {
            console.log('Plugin: I\'m hiding')
            _this.show9 = false
          }
        })
      } else {
        this.$aui.toast.hide()
      }
    }
  },
  data () {
    return {
      show1: false,
      show2: false,
      show3: false,
      show4: false,
      show5: false,
      show6: false,
      show7: false,
      show8: false,
      show9: false,
      position: 'default',
      showPositionValue: false
    }
  }
}
</script>

```


#### Github Issue