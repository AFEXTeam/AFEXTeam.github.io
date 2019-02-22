<!-- ---
nav: zh-CN
--- -->


### Drawer

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/drawer" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div style="height:100%;">
    <div v-transfer-dom>
      <aui-loading v-model="isLoading"></aui-loading>
    </div>
    <div v-transfer-dom>
      <aui-actionsheet :menus="menus" v-model="showMenu" @click-menu="changeLocale"></aui-actionsheet>
    </div>

    <aui-drawer
    width="200px;"
    :show.sync="drawerVisibility"
    :show-mode="showModeValue"
    :placement="showPlacementValue"
    :drawer-style="{'background-color':'#35495e', width: '200px'}">

      <!-- drawer content -->
      <div slot="drawer">
        <aui-group title="showMode">
          <aui-radio v-model="showMode" :options="['push', 'overlay']" @change="onShowModeChange"></aui-radio>
        </aui-group>
        <aui-group title="placement">
          <aui-radio v-model="showPlacement" :options="['left', 'right']" @change="onPlacementChange"></aui-radio>
        </aui-group>
      </div>

      <!-- main content -->
      <aui-view-box ref="viewBox" body-padding-top="46px" body-padding-bottom="55px">
        
        <aui-header slot="header"
        style="width:100%;position:absolute;left:0;top:0;z-index:100;"
        :showBack="leftOptions"
        :showMore="true"
        :title="title"
        :transition="headerTransition"   
        @click-more="onClickMore">
          <span v-if="route.path === '/' || route.path === '/component/drawer'" slot="overwrite-left" @click="drawerVisibility = !drawerVisibility">
            <img src="../assets/drag.png" style="width:35px;height:35px;position:relative;display:inline-block;margin-top:-8px;"/>
          </span>
        </aui-header>
        
        <!-- remember to import BusPlugin in main.js if you use components: aui-img and sticky -->
        <transition
        @after-enter="$aui.bus && $aui.bus.$emit('aui:after-view-enter')" 
        :name="'aui-pop-' + (direction === 'forward' ? 'in' : 'out')">
          <router-view class="router-view"></router-view>
        </transition>

      </aui-view-box>
    </aui-drawer>
  </div>
</template>

<script>
import { mapState, mapActions } from 'vuex'
export default {
  methods: {
    onShowModeChange (val) {
      /** hide drawer before changing showMode **/
      this.drawerVisibility = false
      setTimeout(one => {
        this.showModeValue = val
      }, 400)
    },
    onPlacementChange (val) {
      /** hide drawer before changing position **/
      this.drawerVisibility = false
      setTimeout(one => {
        this.showPlacementValue = val
      }, 400)
    },
    onClickMore () {
      this.showMenu = true
    },
    changeLocale (locale) {
      this.$i18n.set(locale)
      this.$locale.set(locale)
    },
    ...mapActions([
      'updateDemoPosition'
    ])
  },
  mounted () {
    this.handler = () => {
      if (this.path === '/demo') {
        this.box = document.querySelector('#demo_list_box')
        this.updateDemoPosition(this.box.scrollTop)
      }
    }
  },
  beforeDestroy () {
    this.box && this.box.removeEventListener('scroll', this.handler, false)
  },
  watch: {
    path (path) {
      if (path === '/component/demo') {
        this.$router.replace('/demo')
        return
      }
      if (path === '/demo') {
        setTimeout(() => {
          this.box = document.querySelector('#demo_list_box')
          if (this.box) {
            this.box.removeEventListener('scroll', this.handler, false)
            this.box.addEventListener('scroll', this.handler, false)
          }
        }, 1000)
      } else {
        this.box && this.box.removeEventListener('scroll', this.handler, false)
      }
    }
  },
  computed: {
    ...mapState({
      route: state => state.route,
      path: state => state.route.path,
      deviceready: state => state.app.deviceready,
      demoTop: state => state.aui.demoScrollTop,
      isLoading: state => state.aui.isLoading,
      direction: state => state.aui.direction
    }),
    isShowBar () {
      if (/component/.test(this.path)) {
        return true
      }
      return false
    },
    leftOptions () {
      return  this.route.path !== '/'
    },
    headerTransition () {
      return this.direction === 'forward' ? 'aui-header-fade-in-right' : 'aui-header-fade-in-left'
    },
    componentName () {
      if (this.route.path) {
        const parts = this.route.path.split('/')
        if (/component/.test(this.route.path) && parts[2]) return parts[2]
      }
    },
    isDemo () {
      return /component|demo/.test(this.route.path)
    },
    isTabbarDemo () {
      return /tabbar/.test(this.route.path)
    },
    title () {
      if (this.route.path === '/') return 'Home'
      if (this.route.path === '/project/donate') return 'Donate'
      if (this.route.path === '/demo') return 'Demo list'
      return this.componentName ? `Demo/${this.componentName}` : 'Demo/~~'
    }
  },
  data () {
    return {
      showMenu: false,
      menus: {
        'language.noop': '<span class="menu-title">Language</span>',
        'zh-CN': '中文',
        'en': 'English'
      },
      drawerVisibility: false,
      showMode: 'push',
      showModeValue: 'push',
      showPlacement: 'left',
      showPlacementValue: 'left'
    }
  }
}
</script>

```


#### Github Issue