<!-- ---
nav: zh-CN
--- -->


### Confirm

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/confirm" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
      <aui-switch :title="$t('Toggle')" v-model="show"></aui-switch>
    </aui-group>
    <aui-group>
      <aui-switch :title="$t('Toggle_show_input')" v-model="show3"></aui-switch>
    </aui-group>
    <aui-group>
      <aui-switch :title="$t('Set default input value')" v-model="show5"></aui-switch>
    </aui-group>
    <aui-group>
      <aui-switch :title="$t('Toggle_android')" v-model="show2"></aui-switch>
    </aui-group>
    <aui-group>
      <aui-switch :title="$t('closeOnConfirm=false')" v-model="show4"></aui-switch>
    </aui-group>
    <div v-transfer-dom>
      <aui-confirm v-model="show" :title="$t('confirm deleting the item')" @cancel="onCancel" @confirm="onConfirm" @show="onShow" @hide="onHide">
        <p style="text-align:center;">{{ $t('Are you sure?') }}</p>
      </aui-confirm>
    </div>
    <br>
    <div v-transfer-dom>
      <aui-confirm v-model="show3" show-input :title="$t('confirm deleting the item')" @cancel="onCancel" @confirm="onConfirm" @show="onShow" @hide="onHide">
      </aui-confirm>
    </div>
    <br>
    <div v-transfer-dom>
      <aui-confirm v-model="show3" show-input :title="$t('confirm deleting the item')" :input-attrs="{type: 'number'}" @cancel="onCancel" @confirm="onConfirm" @show="onShow" @hide="onHide">
      </aui-confirm>
    </div>
    <br>
    <div v-transfer-dom>
      <aui-confirm v-model="show5" show-input ref="confirm5" :title="$t('confirm deleting the item')" @cancel="onCancel" @confirm="onConfirm5" @show="onShow5" @hide="onHide">
      </aui-confirm>
    </div>
    <br>
    <div v-transfer-dom>
      <aui-confirm v-model="show2" :title="$t('confirm deleting the item')" theme="android" @cancel="onCancel" @confirm="onConfirm" @show="onShow" @hide="onHide">
        <p style="text-align:center;">{{ $t('I miss u sunyi') }}</p>
      </aui-confirm>
    </div>
    <br>
    <div v-transfer-dom>
      <aui-confirm v-model="show4" :close-confirm="false" :title="$t('confirm deleting the item')" @confirm="onConfirm4">
        <p style="text-align:center;">{{ $t('Are you sure?') }}</p>
      </aui-confirm>
    </div>
    <br>
    <div style="padding:15px;">
      <aui-button @click.native="showPlugin" type="primary">{{ $t('Show') }}</aui-button>
    </div>
    <div style="padding:15px;">
      <aui-button @click.native="showPlugin2" type="primary">{{ $t('Plugin usage') }}</aui-button>
    </div>
    <div style="padding:15px;">
      <aui-button @click.native="showPlugin3" type="primary">插件形式调用promt</aui-button>
    </div>
  </div>
</template>



<script>
export default {
  data() {
    return {
      show: false,
      show2: false,
      show3: false,
      show4: false,
      show5: false
    }
  },
  methods: {
    onCancel() {
      console.log('on cancel')
    },
    onConfirm(msg) {
      console.log('on confirm')
      if (msg) {
        alert(msg)
      }
    },
    onConfirm4() {
      console.log('on confirm')
      this.$aui.loading.show({
        transition: '',
        text: 'processing'
      })
      setTimeout(() => {
        this.$aui.loading.hide()
        this.show4 = false
      }, 1000)
    },
    onHide() {
      console.log('on hide')
    },
    onShow() {
      console.log('on show')
    },
    onShow5() {
      this.$refs.confirm5.setInputValue('default')
    },
    onConfirm5(value) {
      this.$refs.confirm5.setInputValue('')
      this.$aui.toast.text('input value: ' + value)
    },
    showPlugin() {
      this.$aui.confirm.show({
        title: 'Title',
        content: 'Content',
        onShow() {
          console.log('plugin show')
        },
        onHide() {
          console.log('plugin hide')
        },
        onCancel() {
          console.log('plugin cancel')
        },
        onConfirm() {
          console.log('plugin confirm')
        }
      })
    },
    showPlugin2() {
      this.showPlugin()
    },
    showPlugin3() {
      const _this = this
      this.$aui.confirm.prompt('123', {
        title: 'Title',
        onShow() {
          console.log('promt show')
          _this.$aui.confirm.setInputValue('set input value')
        },
        onHide() {
          console.log('prompt hide')
        },
        onCancel() {
          console.log('prompt cancel')
        },
        onConfirm(msg) {
          alert(msg)
        }
      })
    }
  }
}
</script>

```


#### Github Issue