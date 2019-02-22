<!-- ---
nav: zh-CN
--- -->


### Popup

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/popup" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
      <aui-switch title="Default popup" v-model="show"></aui-switch>
      <aui-switch title="Full popup" v-model="show1"></aui-switch>
      <aui-switch title="Multi popup (first)" v-model="show3"></aui-switch>
      <aui-switch title="Mask disable" v-model="show5"></aui-switch>
      <aui-switch title="Popup address" v-model="show6"></aui-switch>
      <aui-switch title="default max-height=100%" v-model="show12"></aui-switch>
      <aui-switch title="set max-height=50%" v-model="show13"></aui-switch>
    </aui-group>
  
    <div v-transfer-dom>
      <aui-popup v-model="show" @hide="log('hide')" @show="log('show')">
        <div class="popup0">
          <aui-group>
            <aui-switch title="Another XSwitcher" v-model="show"></aui-switch>
            <aui-switch title="Show Toast" v-model="showToast"></aui-switch>
          </aui-group>
        </div>
      </aui-popup>
    </div>
  
    <aui-toast v-model="showToast">You did it!</aui-toast>
  
    <div v-transfer-dom>
      <aui-popup v-model="show1" height="100%">
        <div class="popup1">
          <aui-group>
            <aui-switch title="Another XSwitcher" v-model="show1"></aui-switch>
          </aui-group>
        </div>
      </aui-popup>
    </div>
  

  
    <div v-transfer-dom>
      <aui-popup v-model="show3">
        <div class="popup2">
          <aui-group>
            <aui-switch title="Multi Popup (first)" v-model="show3"></aui-switch>
            <aui-switch title="Multi Popup (second)" v-model="show4"></aui-switch>
          </aui-group>
          this is the first popup
        </div>
      </aui-popup>
    </div>
  
    <div v-transfer-dom>
      <aui-popup v-model="show4">
        <div class="popup2">
          <aui-group>
            <aui-switch title="Multi Popup (second)" v-model="show4"></aui-switch>
          </aui-group>
          this is the second popup
        </div>
      </aui-popup>
    </div>
  
    <div v-transfer-dom>
      <aui-popup v-model="show5" :hide-on-blur=false>
        <div class="popup2">
          <aui-group>
            <aui-switch title="Mask disable" v-model="show5"></aui-switch>
          </aui-group>
          The mask cannot be clicked!
        </div>
      </aui-popup>
    </div>
  
    <div v-transfer-dom>
      <aui-popup v-model="show6">
        <div class="popup1">
          <aui-group>
            <aui-switch title="Popup address" v-model="show6"></aui-switch>
          </aui-group>
          <aui-group>
            <!-- <aui-address :title="title6" v-model="value6" :list="addressData" placeholder="请选择地址" inline-desc="可以设置placeholder" :popup-style="{zIndex: 502}"></aui-address> -->
          </aui-group>
        </div>
      </aui-popup>
    </div>
  
    <aui-group>
      <aui-switch title="transparent background" v-model="show7"></aui-switch>
    </aui-group>
  
    <div v-transfer-dom>
      <aui-popup v-model="show7" height="270px" is-transparent>
        <div style="width: 95%;background-color:#fff;height:250px;margin:0 auto;border-radius:5px;padding-top:10px;">
          <aui-group>
            <aui-cell title="Product" value="Donate"></aui-cell>
            <aui-cell title="Total" value="$10.24"></aui-cell>
          </aui-group>
          <div style="padding:20px 15px;">
            <aui-button type="primary">Pay</aui-button>
            <aui-button @click.native="show7 = false">Cancel</aui-button>
          </div>
        </div>
      </aui-popup>
    </div>
  
    <aui-group title="set position">
      <aui-switch title="left(100% width)" v-model="show8"></aui-switch>
      <aui-switch title="right" v-model="show9"></aui-switch>
      <aui-switch title="top(no mask)" v-model="show10"></aui-switch>
      <aui-switch title="bottom" v-model="show11"></aui-switch>
    </aui-group>
  
    <div v-transfer-dom>
      <aui-popup v-model="show8" position="left" width="100%">
        <div class="position-horizontal-demo">
          <span class="aui-close" @click="show8 = false"></span>
        </div>
      </aui-popup>
    </div>
  
    <div v-transfer-dom>
      <aui-popup v-model="show9" position="right">
        <div style="width:200px;">
        </div>
      </aui-popup>
    </div>
  
    <div v-transfer-dom>
      <aui-popup v-model="show10" position="top" :show-mask="false">
        <div class="position-vertical-demo">
          I'm on top. Hide in 1s.
        </div>
      </aui-popup>
    </div>
  
    <div v-transfer-dom>
      <aui-popup v-model="show11" position="bottom">
        <div class="position-vertical-demo">
          I'm on bottom.
        </div>
      </aui-popup>
    </div>
  
    <div v-transfer-dom>
      <aui-popup v-model="show12" position="bottom">
        <aui-group>
          <aui-cell v-for="i in 20" :key="i" :title="i"></aui-cell>
        </aui-group>
        <div style="padding: 15px;">
          <aui-button @click.native="show12 = false" plain type="primary"> Close Me </aui-button>
        </div>
      </aui-popup>
    </div>
  
    <div v-transfer-dom>
      <aui-popup v-model="show13" position="bottom" max-height="50%">
        <aui-group>
          <aui-cell v-for="i in 20" :key="i" :title="i"></aui-cell>
        </aui-group>
        <div style="padding: 15px;">
          <aui-button @click.native="show13 = false" plain type="primary"> Close Me </aui-button>
        </div>
      </aui-popup>
    </div>
  
  </div>
</template>

<script>
import {ChinaAddressData} from '../../src/utils'
export default {
  data() {
    return {
      addressData: ChinaAddressData,
      show: false,
      show1: false,
      show2: false,
      show3: false,
      show4: false,
      show5: false,
      show6: false,
      title6: '默认空的',
      value6: [],
      show7: false,
      showToast: false,
      show8: false,
      show9: false,
      show10: false,
      show11: false,
      show12: false,
      show13: false
    }
  },
  methods: {
    log(str) {
      console.log(str)
    }
  },
  watch: {
    show10(val) {
      if (val) {
        setTimeout(() => {
          this.show10 = false
        }, 1000)
      }
    }
  }
}
</script>

<style lang="less" scoped>
@import '../../theme-default/components/common/close.less';

.popup0 {
  padding-bottom: 15px;
  height: 200px;
}

.popup1 {
  width: 100%;
  height: 100%;
}

.popup2 {
  padding-bottom: 15px;
  height: 400px;
}

.position-vertical-demo {
  background-color: #ffe26d;
  color: #000;
  text-align: center;
  padding: 15px;
}

.position-horizontal-demo {
  position: relative;
  height: 100%;
  .aui-close {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateX(-50%) translateY(-50%) scale(4);
    color: #000;
  }
}
</style>

```


#### Github Issue