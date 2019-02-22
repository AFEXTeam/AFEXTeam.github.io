<!-- ---
nav: zh-CN
--- -->


### Search

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/search" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <!-- <img src="../assets/demo/filter_bg.jpg"
         style="width: 100%"> -->
    <aui-search @result-click="resultClick"
            @change="getResult"
            :results="results"
            v-model="value"
            position="absolute"
            auto-scroll-to-top
            top="46px"
            @focus="onFocus"
            @cancel="onCancel"
            @submit="onSubmit"
            ref="search"></aui-search>
    <aui-group>
      <aui-cell title="keyword">{{value}}</aui-cell>
    </aui-group>

    <div style="padding:15px;">
      <aui-button @click.native="setFocus"
                type="primary">set focus</aui-button>
    </div>
    <aui-group>
      <aui-cell title="static position demo"
            is-link
            link="/component/search-static"></aui-cell>
    </aui-group>
  </div>
</template>

<script>

export default {
  methods: {
    setFocus() {
      this.$refs.search.setFocus()
    },
    resultClick(item) {
      window.alert('you click the result item: ' + JSON.stringify(item))
    },
    getResult(val) {
      console.log('change', val)
      this.results = val ? getResult(this.value) : []
    },
    onSubmit() {
      this.$refs.search.setBlur()
      this.$aui.toast.show({
        type: 'text',
        position: 'top',
        text: 'on submit'
      })
    },
    onFocus() {
      console.log('on focus')
    },
    onCancel() {
      console.log('on cancel')
    }
  },
  data() {
    return {
      results: [],
      value: 'test'
    }
  }
}

function getResult(val) {
  let rs = []
  for (let i = 0; i < 20; i++) {
    rs.push({
      title: `${val} result: ${i + 1} `,
      other: i
    })
  }
  return rs
}
</script>

```


#### Github Issue