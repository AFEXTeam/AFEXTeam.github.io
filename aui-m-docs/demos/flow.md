<!-- ---
nav: zh-CN
--- -->


### Flow

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/flow" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-flow>
      <aui-flow-state flowStateImg='../../theme-default/assets/flowConfirm/agree.png'  flowStateConfirmImg="../../theme-default/assets/flowConfirm/through.svg" state="1"
                  title="已付款"
                  is-done></aui-flow-state>
      <aui-flow-line is-done></aui-flow-line>
  
      <aui-flow-state state="2" is-done>
        <span slot="title">{{ $t('Shipped') }}</span>
      </aui-flow-state>
      <aui-flow-line tip="进行中"></aui-flow-line>
  
      <aui-flow-state state="3"
                  title="待收货"></aui-flow-state>
      <aui-flow-line></aui-flow-line>
  
      <aui-flow-state state="4"
                  title="完成"></aui-flow-state>
    </aui-flow>
  
    <aui-flow>
      <aui-flow-state title="已付款"
                  is-done></aui-flow-state>
      <aui-flow-line is-done
                 :line-span="15"></aui-flow-line>
  
      <aui-flow-state title="已发货"
                  is-done></aui-flow-state>
      <aui-flow-line is-done
                 :line-span="30"></aui-flow-line>
  
      <aui-flow-state title="待收货"
                  is-done></aui-flow-state>
      <aui-flow-line tip="进行中"
                 tip-direction="bottom"
                 :line-span="45"
                 :process-span="60"></aui-flow-line>
  
      <aui-flow-state title="完成"></aui-flow-state>
    </aui-flow>
  
    <aui-flow orientation="vertical"
          style="height:250px;">
      <aui-flow-state state="1"
                  title="已付款"
                  is-done></aui-flow-state>
      <aui-flow-line is-done></aui-flow-line>
  
      <aui-flow-state state="2"
                  title="已发货"
                  is-done></aui-flow-state>
      <aui-flow-line tip="进行中"></aui-flow-line>
  
      <aui-flow-state state="3"
                  title="待收货"></aui-flow-state>
      <aui-flow-line></aui-flow-line>
  
      <aui-flow-state state="4"
                  title="完成"></aui-flow-state>
    </aui-flow>
  
    <aui-flow orientation="vertical"
          style="height:200px;">
      <aui-flow-state state="1"
                  title="已付款"
                  is-done></aui-flow-state>
      <aui-flow-line is-done
                 :line-span="15"></aui-flow-line>
  
      <aui-flow-state state="2"
                  title="已发货"
                  is-done></aui-flow-state>
      <aui-flow-line :line-span="30"></aui-flow-line>
  
      <aui-flow-state state="3"
                  title="待收货"></aui-flow-state>
      <aui-flow-line :line-span="45"></aui-flow-line>
  
      <aui-flow-state state="4"
                  title="完成"></aui-flow-state>
    </aui-flow>
  
  </div>
</template>

<script>

export default {
}
</script>
<style>
  .flowStateImg{
    width:15px;
    height:15px;
  }
  .confirmImgClass{
     
    top: 10px;
    display: block;
    position: absolute;
  }
</style>
```


#### Github Issue