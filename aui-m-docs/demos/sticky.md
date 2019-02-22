<!-- ---
nav: zh-CN
--- -->


### Sticky

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/sticky" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <br/>
    <br/>
    <div class="space-btn" @click="spaceChange">显示间隔</div>
    <div class="space" v-if="showSpace">间隔</div>
    <div style="height:44px;">
      <aui-sticky scroll-box="aui_view_box_body" ref="sticky" :offset="46" :check-sticky-support="false">
        <aui-tab :line-width="1">
          <aui-tab-item selected>正在正映</aui-tab-item>
          <aui-tab-item>即将上映</aui-tab-item>
        </aui-tab>
      </aui-sticky>
    </div>
    <p v-for="i in 100">{{i}}
      <br>
    </p>
  </div>
</template>

<script>

export default {
  data() {
    return {
      showSpace: false
    }
  },
  methods: {
    spaceChange() {
      this.showSpace = !this.showSpace
      this.$nextTick(() => {
        this.$refs.sticky.bindSticky()
      })
    }
  }
}
</script>
<style scoped>
.space-btn {
  padding: 5px 0;
  margin: 10px;
  text-align: center;
  border: 1px red solid;
}

.space {
  padding: 30px 0;
  margin: 10px;
  text-align: center;
  border: 1px green solid;
}
</style>

```


#### Github Issue