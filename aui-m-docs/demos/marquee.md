<!-- ---
nav: zh-CN
--- -->


### Marquee

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/marquee" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-divider>{{ $t('Default usage') }}</aui-divider>
    <aui-marquee>
      <aui-marquee-item v-for="i in 5" :key="i" @click.native="onClick(i)" class="align-middle">hello world {{i}}</aui-marquee-item>
    </aui-marquee>
    <br>
    <aui-divider>{{ $t('Used in a cell')}}</aui-divider>
    <aui-group>
      <aui-cell :title="$t('News')">
        <aui-marquee>
          <aui-marquee-item v-for="i in 5" :key="i" @click.native="onClick(i)">{{ $t('JavaScript is the best language')}} {{i}}</aui-marquee-item>
        </aui-marquee>
      </aui-cell>
    </aui-group>
    <br>
    <aui-divider>{{ $t('Async data')}}</aui-divider>
    <aui-marquee>
      <aui-marquee-item v-for="i in asyncCount" :key="i" @click.native="onClick(i)" class="align-middle">hello world {{i}}</aui-marquee-item>
    </aui-marquee>
  </div>
</template>



<script>

export default {
  mounted () {
    setTimeout(() => {
      this.asyncCount = 5
    }, 1000)
  },
  methods: {
    onClick (i) {
      console.log(i)
    }
  },
  data () {
    return {
      asyncCount: 0
    }
  }
}
</script>

<style scoped>
.align-middle {
  text-align: center;
}
</style>
```


#### Github Issue