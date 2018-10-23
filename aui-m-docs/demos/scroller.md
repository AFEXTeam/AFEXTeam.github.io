---
nav: zh-CN
---


### Scroller

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/scroller" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
      <aui-cell is-link title="pullup" link="/component/pullup">Pullup</aui-cell>
      <aui-cell is-link title="pulldown" link="/component/pulldown">Pulldown</aui-cell>
      <aui-cell is-link title="pulldownpullup" link="/component/pulldown-pullup">PulldownPullup</aui-cell>
    </aui-group>

    <aui-divider>{{ $t('A Horizontal Scroller without Scrollbar') }}</aui-divider>
    <aui-scroller lock-y :scrollbar-x=false>
      <div class="box1">
        <div class="box1-item" v-for="i in 7"><span>{{' ' + i + ' '}}</span></div>
      </div>
    </aui-scroller>

    <aui-divider>{{ $t('A Horizontal Scroller with Scrollbar') }}</aui-divider>
    <aui-scroller lock-y scrollbar-x>
      <div class="box1">
        <div class="box1-item" v-for="i in 7"><span>{{' ' + i + ' '}}</span></div>
      </div>
    </aui-scroller>

    <aui-divider>{{ $t('A Horizontal Scroller without bounce effect') }}</aui-divider>
    <aui-scroller lock-y scrollbar-x :bounce=false>
      <div class="box1">
        <div class="box1-item" v-for="i in 7"><span>{{' ' + i + ' '}}</span></div>
      </div>
    </aui-scroller>

    <aui-divider>{{ $t('A Vertical Scroller') }} scrollTop: {{scrollTop}}</aui-divider>
    <aui-scroller lock-x height="200px" @scroll="onScroll" ref="scrollerEvent">
      <div class="box2">
        <p v-for="i in 80">placeholder {{i}}</p>
      </div>
    </aui-scroller>

    <aui-button type="primary" @click.native="$refs.scrollerEvent.reset({top:0})">reset</aui-button>

    <aui-divider>{{ $t('event:scroll-bottom') }} </aui-divider>
    <aui-scroller lock-x height="200px" @scroll-bottom="onScrollBottom" ref="scrollerBottom" :scroll-bottom-offst="200">
      <div class="box2">
        <p v-for="i in bottomCount">placeholder {{i}}</p>
        <aui-load-more tip="loading"></aui-load-more>
      </div>
    </aui-scroller>

    <aui-divider>{{ $t('A Vertical Scroller with scrollbar') }}</aui-divider>
    <aui-scroller lock-x scrollbar-y height="200px" ref="scroller">
      <div class="box2">
        <p v-for="i in 20" v-if="showList1">placeholder {{ i + '' + i }}</p>
        <p v-for="i in 10" v-if="!showList1">placeholder {{ i }}</p>
        <aui-button style="margin:10px 0;" type="primary" @click.native="onClickButton">{{ $t('Button') }}</aui-button>
        <aui-group>
          <aui-cell @click.native="onCellClick" title="Title" value="Value"></aui-cell>
        </aui-group>
      </div>
    </aui-scroller>
    <aui-button @click.native="changeList" type="primary">{{ $t('show another list') }}</aui-button>
  </div>
</template>



<script>

export default {
  data () {
    return {
      showList1: true,
      scrollTop: 0,
      onFetching: false,
      bottomCount: 20
    }
  },
  mounted () {
    this.$nextTick(() => {
      this.$refs.scrollerEvent.reset({top: 0})
    })
    this.$nextTick(() => {
      this.$refs.scrollerBottom.reset({top: 0})
    })
  },
  methods: {
    onScrollBottom () {
      if (this.onFetching) {
        // do nothing
      } else {
        this.onFetching = true
        setTimeout(() => {
          this.bottomCount += 10
          this.$nextTick(() => {
            this.$refs.scrollerBottom.reset()
          })
          this.onFetching = false
        }, 2000)
      }
    },
    onScroll (pos) {
      this.scrollTop = pos.top
    },
    onCellClick () {
      window.alert('cell click')
    },
    onClickButton () {
      window.alert('click')
    },
    changeList () {
      this.showList1 = false
      this.$nextTick(() => {
        this.$refs.scroller.reset({
          top: 0
        })
      })
    }
  }
}
</script>

<style scoped>
.box1 {
  height: 100px;
  position: relative;
  width: 1490px;
}
.box1-item {
  width: 200px;
  height: 100px;
  background-color: #ccc;
  display:inline-block;
  margin-left: 15px;
  float: left;
  text-align: center;
  line-height: 100px;
}
.box1-item:first-child {
  margin-left: 0;
}
.box2-wrap {
  height: 300px;
  overflow: hidden;
}
</style>

```


#### Github Issue