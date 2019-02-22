<!-- ---
nav: zh-CN
--- -->


### Loading

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/loading" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
      <aui-switch :title="$t('Toggle')" v-model="show1" @change="show1change"></aui-switch>
    </aui-group>
    <div v-transfer-dom>
      <aui-loading :show="show1" :text="text1"></aui-loading>
    </div>
    <div style="padding: 15px;">
     <aui-button @click.native="showLoading" type="primary">{{ $t('show loading') }}</aui-button>
    </div>
    <div style="padding: 15px;">
      <aui-button @click.native="showDelayLoading" type="primary">{{ $t('Show delay loading') }}</aui-button>
    </div>
  </div>
</template>



<script>

export default {
  data () {
    return {
      show1: false,
      text1: 'Processing'
    }
  },
  methods: {
    showLoading () {
      this.$aui.loading.show({
        text: 'Loading'
      })
      setTimeout(() => {
        this.$aui.loading.hide() 
      }, 2000)
    },
    showDelayLoading () {
      this.$aui.loading.show({
        text: 'Loading',
        delay: 1e3
      })
      setTimeout(() => {
        this.$aui.loading.hide()
      }, 2000)
    },
    show1change (val) {
      if (val) {
        tick(0, (percent) => {
          if (percent === 100) {
            this.show1 = false
            return
          }
          this.text1 = `${percent}%`
        })
      }
    }
  }
}

function tick (i, cb) {
  setTimeout(function () {
    i++
    cb(i)
    if (i < 100) {
      tick(i, cb)
    }
  }, 10)
}
</script>

```


#### Github Issue