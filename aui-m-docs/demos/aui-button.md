<!-- ---
nav: zh-CN
--- -->


### AuiButton

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/aui-button" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
        <aui-divider>iOS Gradients(v2.7.4)</aui-divider>
    <aui-box gap="10px 10px">
      <aui-button :gradients="['#1D62F0', '#19D5FD']">iOS Gradients</aui-button>
      <aui-button :gradients="['#A644FF', '#FC5BC4']">iOS Gradients</aui-button>
      <aui-button :gradients="['#FF2719', '#FF61AD']">iOS Gradients</aui-button>
      <aui-button :gradients="['#6F1BFE', '#9479DF']">iOS Gradients</aui-button>
      <aui-button :gradients="['#FF5E3A', '#FF9500']">iOS Gradients</aui-button>
    </aui-box>
    <aui-divider>default</aui-divider>
    <aui-box gap="10px 10px">
      <aui-button>submit</aui-button>
      <aui-button type="primary">primary</aui-button>
      <aui-button type="warn">Delete</aui-button>
  
      <aui-divider>link</aui-divider>
      <aui-button type="primary"
                link="/demo">Go to demo list</aui-button>
      <aui-button type="default"
                link="BACK">Back</aui-button>
  
      <aui-divider>native type</aui-divider>
      <aui-button type="primary"
                native-type="button">submit</aui-button>
      <aui-button type="warn"
                native-type="reset">reset</aui-button>
  
      <aui-divider>loading</aui-divider>
      <aui-button type="default"
                loading>submit</aui-button>
      <aui-button type="primary"
                loading>submit</aui-button>
      <aui-button type="warn"
                loading>submit</aui-button>
  
      <aui-divider>mini</aui-divider>
      <aui-button mini>submit</aui-button>
      <aui-button mini
                type="primary">primary</aui-button>
      <aui-button mini
                type="warn">Delete</aui-button>
      <br>
      <aui-button mini
                plain>submit</aui-button>
      <aui-button mini
                plain
                type="primary">primary</aui-button>
  
      <aui-divider>plain</aui-divider>
      <aui-button plain>submit</aui-button>
      <aui-button plain
                type="primary">primary</aui-button>
  
      <aui-divider>you can custom styles</aui-divider>
      <aui-button plain
                type="primary"
                style="border-radius:99px;">primary</aui-button>
      <aui-button plain
                type="primary"
                class="custom-primary-red">primary</aui-button>
  
      <aui-divider>disabled</aui-divider>
      <aui-button disabled>disable submit</aui-button>
      <aui-button type="primary"
                disabled>disable primary</aui-button>
      <aui-button type="warn"
                disabled>disable Delete</aui-button>
  
      <aui-button mini disabled>disable mini submit</aui-button>
      <aui-button mini type="primary" disabled>disable mini primary</aui-button>
      <aui-button mini type="warn" disabled>disable mini Delete</aui-button>

      <aui-button plain disabled>disable plain</aui-button>
      <aui-button plain type="primary" disabled>disable plain primary</aui-button>

      <aui-divider>use :text and :disabled</aui-divider>
      <aui-button :text="submit001"
                :disabled="disable001"
                @click.native="processButton001"
                type="primary"></aui-button>
  
      <aui-divider>combined with flexbox</aui-divider>
      <aui-flexbox>
        <aui-flexbox-item>
          <aui-button type="primary">primary</aui-button>
        </aui-flexbox-item>
        <aui-flexbox-item>
          <aui-button type="warn">Delete</aui-button>
        </aui-flexbox-item>
      </aui-flexbox>
      <aui-divider>combined with flexbox</aui-divider>
      <aui-flexbox>
        <aui-flexbox-item>
          <aui-button type="default">default</aui-button>
        </aui-flexbox-item>
        <aui-flexbox-item>
          <aui-button type="primary">primary</aui-button>
        </aui-flexbox-item>
        <aui-flexbox-item>
          <aui-button type="warn">Delete</aui-button>
        </aui-flexbox-item>
      </aui-flexbox>
  
    </aui-box>
  
  </div>
</template>

<script>

export default {

  methods: {
    change(value) {
      console.log('change:', value)
    },
    processButton001() {
      this.submit001 = 'processing'
      this.disable001 = true
    }
  },
  data() {
    return {
      submit001: 'click me',
      disable001: false
    }
  }
}
</script>

<style lang="less">
.custom-primary-red {
  border-radius: 99px!important;
  border-color: #CE3C39!important;
  color: #CE3C39!important;
  &:active {
    border-color: rgba(206, 60, 57, 0.6)!important;
    color: rgba(206, 60, 57, 0.6)!important;
    background-color: transparent;
  }
}
</style>

```


#### Github Issue