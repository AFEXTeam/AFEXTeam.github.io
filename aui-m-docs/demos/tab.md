<!-- ---
nav: zh-CN
--- -->


### Tab

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/tab" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-tab>
      <aui-tab-item selected @item-click="onItemClick">已发货</aui-tab-item>
      <aui-tab-item @item-click="onItemClick">未发货</aui-tab-item>
      <aui-tab-item @item-click="onItemClick">全部订单</aui-tab-item>
    </aui-tab>
    <br/>
    <br/>
    <aui-tab bar-position="top">
      <aui-tab-item selected @item-click="onItemClick">已发货</aui-tab-item>
      <aui-tab-item @item-click="onItemClick">未发货</aui-tab-item>
      <aui-tab-item @item-click="onItemClick">全部订单</aui-tab-item>
    </aui-tab>
    <br/>
    <br/>
    <aui-divider>手动切换</aui-divider>
    <aui-tab v-model="index01" prevent-default @on-before-index-change="switchaui-tabItem">
      <aui-tab-item selected>已发货</aui-tab-item>
      <aui-tab-item>未发货</aui-tab-item>
      <aui-tab-item>全部订单</aui-tab-item>
    </aui-tab>
    <br/>
    <br/>
    <aui-divider>定义bar固定宽度</aui-divider>
    <aui-tab :line-width="1" custom-bar-width="60px">
      <aui-tab-item selected>已发货</aui-tab-item>
      <aui-tab-item>未发货</aui-tab-item>
      <aui-tab-item>全部订单</aui-tab-item>
    </aui-tab>
    <br/>
    <br/>
    <aui-divider>使用函数定义bar宽度</aui-divider>
    <aui-tab :line-width="1" :custom-bar-width="getBarWidth">
      <aui-tab-item selected>AA</aui-tab-item>
      <aui-tab-item>AAAA</aui-tab-item>
      <aui-tab-item>AAAAAAA</aui-tab-item>
    </aui-tab>
    <br/>
    <br/>
    <br/>
    <aui-divider>{{ $t('set bar-active-color')}}</aui-divider>
    <aui-tab bar-active-color="#668599" :line-width="1">
        <aui-tab-item>已发货</aui-tab-item>
        <aui-tab-item selected>未发货</aui-tab-item>
        <aui-tab-item>全部订单</aui-tab-item>
        <aui-tab-item>全部订单</aui-tab-item>
        <aui-tab-item>全部订单</aui-tab-item>
      </aui-tab>
  
    <br/>
    <br/>
    <br/>
    <aui-divider>different active class</aui-divider>
    <aui-tab :animate="false">
      <aui-tab-item active-class="active-6-1">已发货</aui-tab-item>
      <aui-tab-item active-class="active-6-2" selected>未发货</aui-tab-item>
      <aui-tab-item active-class="active-6-3">全部订单</aui-tab-item>
    </aui-tab>
    <br/>
    <br/>
    <br/>
    <aui-divider>no animation</aui-divider>
    <aui-tab :animate="false">
      <aui-tab-item>已发货</aui-tab-item>
      <aui-tab-item selected>未发货</aui-tab-item>
      <aui-tab-item>全部订单</aui-tab-item>
    </aui-tab>
    <br/>
    <br/>
    <br/>
    <aui-divider>disabled</aui-divider>
    <aui-tab>
      <aui-tab-item selected>A</aui-tab-item>
      <aui-tab-item>B</aui-tab-item>
      <aui-tab-item disabled>Disabled</aui-tab-item>
    </aui-tab>
    <br/>
    <br/>
    <br/>
    <aui-divider>aui-tab-item badge</aui-divider>
    <aui-tab>
      <aui-tab-item selected badge-label="1">收到的消息</aui-tab-item>
      <aui-tab-item badge-background="#38C972" badge-color="#fff" badge-label="2">发出的消息</aui-tab-item>
    </aui-tab>
    <br/>
    <br/>
    <br/>
    <aui-divider>scroll</aui-divider>
    <aui-tab>
      <aui-tab-item v-for="n in 8" :key="n" :selected="n===1">已发货{{ n }}</aui-tab-item>
    </aui-tab>
    <br/>
    <br/>
    <br/>
    <aui-divider>scroll threshold</aui-divider>
    <aui-tab :scroll-threshold="5">
      <aui-tab-item v-for="n in 5" :key="n" :selected="n===1">已发货{{ n }}</aui-tab-item>
    </aui-tab>
    <br/>
    <br/>
    <br/>
    <div>
       <aui-tab :line-width=2 active-color='#fc378c' v-model="index">
        <aui-tab-item class="vux-center" :selected="demo2 === item" v-for="(item, index) in list2" @click="demo2 = item" :key="index">{{item}}</aui-tab-item>
      </aui-tab>
      <aui-swiper v-model="index" height="100px" :show-dots="false">
        <aui-swiper-item v-for="(item, index) in list2" :key="index">
          <div class="aui-tab-aui-swiper vux-center">{{item}} Container</div>
        </aui-swiper-item>
      </aui-swiper>
    </div>
  
    <br/>
    <div class="box">
      <aui-button @click.native="index=0" :disabled="index === 0" type="primary">go to 0</aui-button>
      <aui-button @click.native="index=1" :disabled="index === 1" type="primary">go to 1</aui-button>
  
      <aui-button @click.native="addaui-tab" :disabled="list2.length === 5" type="primary">Add tab item</aui-button>
      <aui-button @click.native="removeTab" :disabled="list2.length <= 2" type="primary">Remove tab item</aui-button>
      <aui-button @click.native="next" type="primary">Active next current: {{index}}</aui-button>
      <aui-button @click.native="prev" type="primary">Active prev current: {{index}}</aui-button>
    </div>
  
    <br/>
    <br/>
    <aui-tab :line-width="2">
      <aui-tab-item :selected="demo3 === item" v-for="(item, index) in list3" :class="{'vux-1px-r': index===0}" @click="demo3 = item" :key="index">{{item}}</aui-tab-item>
    </aui-tab>
    <br/>
    <br/>
    <br/>
    <aui-sticky scrollBox="aui_view_box_body" :check-sticky-support="false" :offset="46">
      <aui-tab :line-width=1>
        <aui-tab-item :selected="demo4 === item" v-for="(item, index) in list4" @click="demo4 = item" :key="index">{{item}}</aui-tab-item>
      </aui-tab>
    </aui-sticky>
    <br v-for="i in 40">
  </div>
</template>



<script>
const list = () => ['精选', '美食', '电影', '酒店', '外卖']

export default {
  data () {
    return {
      index01: 0,
      list2: list(),
      demo2: '美食',
      list3: ['收到的消息', '发出的消息'],
      demo3: '收到的消息',
      list4: ['正在放映', '即将上映'],
      demo4: '即将上映',
      demoDisabled: 'A',
      index: 0,
      getBarWidth: function (index) {
        return (index + 1) * 22 + 'px'
      }
    }
  },
  methods: {
    switchTabItem (index) {
      console.log('before-index-change', index)
      this.$aui.loading.show({
        text: 'loading'
      })
      setTimeout(() => {
        this.$vux.loading.hide()
        this.index01 = index
      }, 1000)
    },
    onItemClick (index) {
      console.log('on item click:', index)
    },
    addTab() {
      if (this.list2.length < 5) {
        this.list2 = list().slice(0, this.list2.length + 1)
      }
    },
    removeTab() {
      if (this.list2.length > 1) {
        this.list2 = list().slice(0, this.list2.length - 1)
      }
    },
    next () {
      if (this.index === this.list2.length - 1) {
        this.index = 0
      } else {
        ++this.index
      }
    },
    prev () {
      if (this.index === 0) {
        this.index = this.list2.length - 1
      } else {
        --this.index
      }
    }
  }
}
</script>

<style lang="less" scoped>
.box {
  padding: 15px;
}
.active-6-1 {
  color: rgb(252, 55, 140) !important;
  border-color: rgb(252, 55, 140) !important;
}
.active-6-2 {
  color: #04be02 !important;
  border-color: #04be02 !important;
}
.active-6-3 {
  color: rgb(55, 174, 252) !important;
  border-color: rgb(55, 174, 252) !important;
}
.aui-tab-aui-swiper {
  background-color: #fff;
  height: 100px;
}
</style>

```


#### Github Issue