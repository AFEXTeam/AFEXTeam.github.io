<!-- ---
nav: zh-CN
--- -->


### Step

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/step" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div style="width: 95%;margin: 0 auto;">
    <br>
    <div>
      <aui-step v-model="step1" background-color='#fbf9fe'>
        <aui-step-item :title="$t('step 1')" description="step 1"></aui-step-item>
        <aui-step-item :title="$t('step 2')" description="step 2"></aui-step-item>
        <aui-step-item :title="$t('step 3')" description="step 3"></aui-step-item>
      </aui-step>
    </div>
    <aui-hr></aui-hr>
    <div>
      <aui-step v-model="step2" background-color='#fbf9fe' gutter="20px">
        <aui-step-item :title="$t('done')"></aui-step-item>
        <aui-step-item :title="$t('processing')"></aui-step-item>
        <aui-step-item :title="$t('end')"></aui-step-item>
      </aui-step>
      <div class="btn_wrap">
        <aui-button type="primary" @click.native="nextStep">{{ $t('next step') }}</aui-button>
      </div>
    </div>
  </div>
</template>



<script>

export default {
  data () {
    return {
      step1: 1,
      step2: 0
    }
  },
  methods: {
    nextStep () {
      this.step2 ++
    }
  }
}
</script>

<style lang="less">
.btn_wrap {
  padding: 0 1rem;
  margin-top: 2rem;
}
</style>

```


#### Github Issue