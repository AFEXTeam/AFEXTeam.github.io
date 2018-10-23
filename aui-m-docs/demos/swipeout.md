---
nav: zh-CN
---


### Swipeout

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/swipeout" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <div class="aui-1px-t">
  
      <aui-swipeout>
  
        <aui-swipeout-item @close="handleEvents('close')"
                       @open="handleEvents('open')"
                       transition-mode="follow">
          <div slot="right-menu">
            <aui-swipeout-button @click.native="onButtonClick('fav')"
                             type="primary">{{$t('Yes')}}</aui-swipeout-button>
            <aui-swipeout-button @click.native="onButtonClick('delete')"
                             type="warn">{{$t('Right')}}</aui-swipeout-button>
          </div>
          <div slot="content"
               class="demo-content aui-1px-t">
            {{$t('JavaScript is the best language')}}
          </div>
        </aui-swipeout-item>
  
        <aui-swipeout-item :threshold=".5"
                       underlay-color="#ccc">
          <div slot="right-menu">
            <aui-swipeout-button @click.native="onButtonClick('fav')"
                             background-color="#336DD6">{{$t('Fav')}}</aui-swipeout-button>
            <aui-swipeout-button @click.native="onButtonClick('delete')"
                             background-color="#D23934">{{$t('Delete')}}</aui-swipeout-button>
          </div>
          <div slot="content"
               class="demo-content aui-1px-tb">
            {{$t('threshold = 0.5')}}
          </div>
        </aui-swipeout-item>
  
        <aui-swipeout-item :disabled="disabled"
                       ref="swipeoutItem"
                       :right-menu-width="210"
                       :sensitivity="15">
          <div slot="right-menu">
            <aui-swipeout-button @click.native="onButtonClick('fav')"
                             type="primary"
                             :width="70">{{$t('Fav')}}</aui-swipeout-button>
            <aui-swipeout-button @click.native="onButtonClick('delete')"
                             type="warn"
                             :width="70">{{$t('Delete')}}</aui-swipeout-button>
            <aui-swipeout-button @click.native="onButtonClick('ignore')"
                             type="default"
                             :width="70">{{$t('Ignore')}}</aui-swipeout-button>
          </div>
  
          <div slot="left-menu">
            <aui-swipeout-button @click.native="onButtonClick('fav')"
                             type="primary">{{$t('Fav')}}</aui-swipeout-button>
            <aui-swipeout-button @click.native="onButtonClick('delete')"
                             type="warn">{{$t('Delete')}}</aui-swipeout-button>
          </div>
  
          <div slot="content"
               class="demo-content aui-1px-b">
            {{$t('now ' + (disabled ? 'disabled' : 'enabled'))}}
          </div>
        </aui-swipeout-item>
  
      </aui-swipeout>
    </div>
  
    <div style="padding:15px;">
      <aui-button @click.native="disabled = false"
                type="primary"
                :disabled="!disabled">{{ $t('set Enabled') }}</aui-button>
      <aui-button @click.native="disabled = true"
                type="warn"
                :disabled="disabled">{{ $t('set Disabled') }}</aui-button>
      <aui-button @click.native="$refs.swipeoutItem.open('left')"
                type="primary">{{ $t('open left menu') }}</aui-button>
      <aui-button @click.native="$refs.swipeoutItem.open('right')"
                type="primary">{{ $t('open right menu') }}</aui-button>
      <aui-button @click.native="$refs.swipeoutItem.close()"
                type="warn">{{ $t('close menu') }}</aui-button>
    </div>
  
    <br>
    <aui-group-title>use aui-1px to style items</aui-group-title>
    <aui-swipeout class="aui-1px-tb">
      <aui-swipeout-item transition-mode="follow"
                     v-for="i in 3"
                     :key="i">
        <div slot="right-menu">
          <aui-swipeout-button type="primary">{{$t('Yes')}}</aui-swipeout-button>
          <aui-swipeout-button type="warn">{{$t('Right')}}</aui-swipeout-button>
        </div>
        <div slot="content"
             :class="{'aui-1px-b': i !== 3, 'aui-1px-t': i === 1}"
             style="padding:12px;">{{ $t('JavaScript is the best language') }}</div>
      </aui-swipeout-item>
    </aui-swipeout>
    <br>
    <br>
  </div>
</template>



<script>
export default {

  methods: {
    onButtonClick(type) {
      alert('on button click ' + type)
    },
    handleEvents(type) {
      console.log('event: ', type)
    }
  },
  data() {
    return {
      disabled: false
    }
  }
}
</script>

<style lang="less">
.demo-content {
  padding: 10px 10px;
}
</style>

```


#### Github Issue