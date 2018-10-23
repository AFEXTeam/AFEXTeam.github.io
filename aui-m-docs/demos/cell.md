---
nav: zh-CN
---


### Cell

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/cell" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
      <aui-cell :title="$t('My Account')"
            :value="$t('Protected')"
            @click.native="onClick"></aui-cell>
      <aui-cell :title="$t('Money')"
            @click.native="onClick"
            :is-loading="!money"
            :value="money"></aui-cell>
      <aui-cell :title="$t('Withdraw')"
            disabled
            is-link></aui-cell>
    </aui-group>
  
    <aui-group :title="$t('use is-link to show arrow')">
      <aui-cell is-link>
        <span slot="title"
              style="color:green;"><span style="vertical-align:middle;">{{ $t('Important News') }}</span>
        <aui-badge value="1"></aui-badge>
        </span>
      </aui-cell>
      <aui-cell :title="$t('Notifications')"
            :titleClass="classTitle"
            is-link></aui-cell>
      <aui-cell :title="$t('Privacy')"
            is-link></aui-cell>
      <aui-cell :title="$t('General')"
            is-link>
        <img slot="icon"
             width="20"
             style="display:block;margin-right:5px;"
             src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAC4AAAAuCAMAAABgZ9sFAAAAVFBMVEXx8fHMzMzr6+vn5+fv7+/t7e3d3d2+vr7W1tbHx8eysrKdnZ3p6enk5OTR0dG7u7u3t7ejo6PY2Njh4eHf39/T09PExMSvr6+goKCqqqqnp6e4uLgcLY/OAAAAnklEQVRIx+3RSRLDIAxE0QYhAbGZPNu5/z0zrXHiqiz5W72FqhqtVuuXAl3iOV7iPV/iSsAqZa9BS7YOmMXnNNX4TWGxRMn3R6SxRNgy0bzXOW8EBO8SAClsPdB3psqlvG+Lw7ONXg/pTld52BjgSSkA3PV2OOemjIDcZQWgVvONw60q7sIpR38EnHPSMDQ4MjDjLPozhAkGrVbr/z0ANjAF4AcbXmYAAAAASUVORK5CYII=">
      </aui-cell>

    </aui-group>
      <aui-group label-width="5em" title="align-items">
      <aui-cell primary="content" title="default" value="long long long longlong longlong longlong longlong longlong longlong longlong longlong long"></aui-cell>
      <aui-cell title="flex-start" align-items="flex-start" value="long long long longlong longlong longlong longlong longlong longlong longlong longlong long"></aui-cell>
    </aui-group>

    <aui-group :title="$t('Collapse')">
      <aui-cell :title="$t('Title 001')"
            is-link
            :border-intent="false"
            :arrow-direction="showContent001 ? 'up' : 'down'"
            @click.native="showContent001 = !showContent001"></aui-cell>
  
      <template v-if="showContent001">
        <aui-cell-box :border-intent="false"
                  class="sub-item"
                  is-link>content 001</aui-cell-box>
        <aui-cell-box class="sub-item"
                  is-link>content 001</aui-cell-box>
        <aui-cell-box class="sub-item"
                  is-link>content 001</aui-cell-box>
      </template>
  
      <aui-cell :title="$t('Title 002')"
            is-link
            :border-intent="false"
            :arrow-direction="showContent002 ? 'up' : 'down'"
            @click.native="showContent002 = !showContent002"></aui-cell>
  
      <template v-if="showContent002">
        <aui-cell-form-preview :border-intent="false"
                           :list="list"></aui-cell-form-preview>
      </template>
  
      <aui-cell :title="$t('Title 003')"
            is-link
            :border-intent="false"
            :arrow-direction="showContent003 ? 'up' : 'down'"
            @click.native="showContent003 = !showContent003"></aui-cell>
  
      <template v-if="showContent003">
        <aui-cell-box :border-intent="false"
                  class="sub-item">I'm content 003</aui-cell-box>
      </template>
  
      <aui-cell :title="$t('Animated')"
            is-link
            :border-intent="false"
            :arrow-direction="showContent004 ? 'up' : 'down'"
            @click.native="showContent004 = !showContent004"></aui-cell>
  
      <p class="slide"
         :class="showContent004?'animate':''">blablabla...
        <br/>blablabla...
        <br/>blablabla...
        <br/>blablabla...</p>
  
    </aui-group>
  
    <aui-group>
      <aui-cell :title="$t('Notifications')"
            :value="$t('Enabled')"></aui-cell>
    </aui-group>
  
    <aui-group :title="$t('use slot for complexed content')">
      <aui-cell :title="$t('slot content')">
        <div>
          <span style="color: green">{{$t('Hi, Im Aui.')}}</span>
        </div>
      </aui-cell>
    </aui-group>
  
    <aui-group :title="$t('isLink is set to true when link exists')">
      <aui-cell :title="$t('Go to Radio Demo')"
            link="/component/radio"
            inline-desc='link="/component/radio"'></aui-cell>
      <aui-cell :title="$t('Go to Demo')"
            :link="{path:'/demo'}"
            inline-desc=':link={path:"/demo"}'></aui-cell>
      <aui-cell :title="$t('http link')"
            link="http://www.agree.com.cn"
            inline-desc='link="http://www.agree.com.cn"'></aui-cell>
    </aui-group>
  </div>
</template>



<script>
export default {
  mounted() {
    setTimeout(() => {
      this.money = -1024
    }, 2000)
  },
  methods: {
    onClick() {
      console.log('on click')
    }
  },
  data() {
    return {

      list: [{
        label: 'Apple',
        value: '3.29'
      }, {
        label: 'Banana',
        value: '1.04'
      }, {
        label: 'Fish',
        value: '8.00'
      }],
      money: null,
      showContent001: false,
      showContent002: false,
      showContent003: false,
      showContent004: false,
      classTitle: 'titleClass'
    }
  }
}
</script>

<style scoped>
.titleClass {
  color: red
}

.sub-item {
  color: #888;
}

.slide {
  padding: 0 20px;
  overflow: hidden;
  max-height: 0;
  transition: max-height .5s cubic-bezier(0, 1, 0, 1) -.1s;
}

.animate {
  max-height: 9999px;
  transition-timing-function: cubic-bezier(0.5, 0, 1, 0);
  transition-delay: 0s;
}
</style>

```


#### Github Issue