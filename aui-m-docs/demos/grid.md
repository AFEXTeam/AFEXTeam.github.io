---
nav: zh-CN
---


### Grid

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/grid" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group-title>2 columns</aui-group-title>
    <aui-grid>
      <aui-grid-item :label="$t('Grid')" v-for="i in 2" :key="i">
        <img slot="icon" src="../assets/grid_icon.png">
      </aui-grid-item>
    </aui-grid>
    <aui-group-title>3 columns</aui-group-title>
    <aui-grid :show-lr-borders="false" :show-vertical-dividers="false">
      <aui-grid-item link="/component/cell" :label="$t('Go to Cell')">
        <img slot="icon" src="../assets/grid_icon.png">
      </aui-grid-item>
      <aui-grid-item :link="{ path: '/component/cell'}" :label="$t('Go to Cell')">
        <img slot="icon" src="../assets/grid_icon.png">
      </aui-grid-item>
      <aui-grid-item link="/component/cell" @on-item-click="onItemClick">
        <img slot="icon" src="../assets/grid_icon.png">
        <span slot="label">{{ $t('Go to Cell') }}</span>
      </aui-grid-item>
    </aui-grid>
    <aui-group-title>4 columns</aui-group-title>
    <aui-grid :show-lr-borders="false">
      <aui-grid-item :label="$t('Grid')" v-for="i in 4" :key="i">
        <img slot="icon" src="../assets/grid_icon.png">
      </aui-grid-item>
    </aui-grid>
    <aui-group-title> {{ $t('Custom content') }} </aui-group-title>
    <aui-grid :show-vertical-dividers="false">
      <aui-grid-item v-for="i in 5" :key="i">
        <span class="grid-center">{{i}}</span>
      </aui-grid-item>
    </aui-grid>
    <aui-group-title> {{ $t('Custom col') }} </aui-group-title>
    <aui-grid :cols="3" :show-lr-borders="false">
      <aui-grid-item v-for="i in 6" :key="i">
        <span class="grid-center">{{i}}</span>
      </aui-grid-item>
    </aui-grid>
  </div>
</template>



<script>

export default {
  methods: {
    onItemClick () {
      console.log('on item click')
    }
  }
}
</script>

<style scoped>
.grid-center {
  display: block;
  text-align: center;
  color: #666;
}
.aui-grid {
  background-color: #fff;
}
</style>

```


#### Github Issue