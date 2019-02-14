---
nav: zh-CN
---


### AuiInput

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/aui-input" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>

    <aui-group title="禁用内置验证及显示成功或者错误样式">
      <aui-input title="禁用验证" placeholder="0.00" :showkeyboard='true' :reserve-bits="3" novalidate :icon-type="iconType" :show-clear="false" @blur="onBlur" placeholder-align="right"></aui-input>
    </aui-group>
    <div style="padding:15px;">
      <aui-button @click.native="iconType = 'success'" type="primary"> set success</aui-button>
      <aui-button @click.native="iconType = 'error'" type="primary"> set error</aui-button>
      <aui-button @click.native="iconType = ''" type="primary"> set empty</aui-button>
    </div>
    <aui-group title="自动获取焦点">
      <aui-input title="自动获取焦点" :auto="true" placeholder="I'm placeholder"></aui-input>
    </aui-group>
    <aui-group title="is-type传入function">
      <aui-input title="必须输入2333" :is-type="be2333" placeholder="I'm placeholder"></aui-input>
    </aui-group>

    <aui-group title="mask">
      <aui-input title="手机号码格式化" mask="999 9999 9999" v-model="maskValue" :max="13" is-type="china-mobile"></aui-input>
      <aui-cell title="value" :value="maskValue"></aui-cell>
      <aui-input title="(99) 9-99" mask="(99) 9-99" v-model="maskValue2" :max="9"></aui-input>
    </aui-group>

    <aui-group title="使用icon代替title">
      <aui-input title="必须输入2333" :is-type="be2333" placeholder="I'm placeholder">
        <img slot="label" style="padding-right:10px;display:block;" src="http://dn-placeholder.qbox.me/110x110/FF2D55/000" width="24" height="24">
      </aui-input>
    </aui-group>

    <aui-group title="max is alias to maxlength">
      <aui-input title='max=5' :max="5" @change="change" v-model="maxValue"></aui-input>
    </aui-group>

    <aui-group title="debounce = 1000">
      <aui-input title='debounce' :debounce="500" @change="change" v-model="debounceValue"></aui-input>
    </aui-group>

    <aui-group title="disabled">
      <aui-input title='value' disabled v-model="disabledValue"></aui-input>
    </aui-group>

    <aui-group title="set type = tel">
      <aui-input title='value' type="tel"></aui-input>
    </aui-group>

    <aui-group title="html title">
      <aui-input label-width="4em" :title='`<span style="${style}">hello</span>`' placeholder="I'm placeholder"></aui-input>
    </aui-group>
    <div style="padding:15px;">
      <aui-button @click.native="style = 'color:red;'" type="primary">set red</aui-button>
      <aui-button @click.native="style = 'color:green'" type="primary">set green</aui-button>
      <aui-button @click.native="style = 'color:#000'" type="primary">set default</aui-button>
    </div>

    <aui-group title="Default">
      <aui-input title="message" placeholder="I'm placeholder"></aui-input>
    </aui-group>

    <aui-group title="不显示清除按钮">
      <aui-input title="message" required placeholder="I'm placeholder" :show-clear="false" autocapitalize="characters" :error-message="errorMessage"></aui-input>
    </aui-group>

    <aui-group title="focus事件">
      <aui-input title="focus-handler" placeholder="focus me!" :show-clear="true" @focus="onFocus"></aui-input>
    </aui-group>

    <aui-group title="set is-type=china-name">
      <aui-input title="姓名" name="username" placeholder="请输入姓名" is-type="china-name"></aui-input>
    </aui-group>

    <aui-group title="set keyboard=number and is-type=china-mobile">
      <aui-input title="手机号码" name="mobile" placeholder="请输入手机号码" keyboard="number" is-type="china-mobile"></aui-input>
    </aui-group>

    <aui-group title="set is-type=email">
      <aui-input title="邮箱" name="email" placeholder="请输入邮箱地址" is-type="email"></aui-input>
    </aui-group>

    <aui-group title="set min=2 and max=5">
      <aui-input title="2-5个字符" placeholder="" :min="2" :max="5"></aui-input>
    </aui-group>

    <aui-group title="确认输入">
      <aui-input title="请输入6位数字" type="text" placeholder="" v-model="password" :min="6" :max="6" @change="change"></aui-input>
      <aui-input title="请确认6位数字" v-model="password2" type="text" placeholder="" :equal-with="password"></aui-input>
    </aui-group>

    <aui-group title="enter事件">
      <aui-input title="输入完成后回车" type="text" placeholder="" v-model="enterText" @enter="onEnter"></aui-input>
    </aui-group>

    <aui-group title="验证码" class="aui-cells_form">
      <aui-input title="验证码" class="aui-cell_vcode">
        <img slot="right" class="aui-vcode-img" src="https://i.loli.net/2017/09/18/59bf7f32425d5.jpg">
      </aui-input>
      <aui-input title="发送验证码" class="aui-vcode">
        <aui-button slot="right" type="primary" mini>发送验证码</aui-button>
      </aui-input>
    </aui-group>

    <aui-group title="check if value is valid when required===true">
      <aui-input title="message" placeholder="I'm placeholder" ref="input01" required></aui-input>
      <aui-cell title="click to get valid value" :value="'$valid value:' + valid1" @click.native="getValid1"></aui-cell>
    </aui-group>

    <aui-group title="check if value is valid when required===false">
      <aui-input title="message" placeholder="I'm placeholder" :required="false" ref="input02" @click.native="getValid2"></aui-input>
      <aui-cell title="click to get valid value" :value="'$valid value:' + valid2" @click.native="getValid2"></aui-cell>
    </aui-group>

  </div>
</template>

<script>

export default {

  data() {
    return {
      password: '123465',
      password2: '',
      enterText: '',
      valid1: false,
      valid2: false,
      iconType: '',
      be2333: function(value) {
        return {
          valid: value === '2333',
          msg: 'Must be 2333'
        }
      },
      style: '',
      disabledValue: 'hello',
      debounceValue: '',
      maxValue: '',
      maskValue: '13545678910',
      maskValue2: '',
      errorMessage: "错误哦"
    }
  },
  methods: {
    getValid1() {
      this.valid1 = this.$refs.input01.valid
    },
    getValid2() {
      this.valid2 = this.$refs.input02.valid
    },
    change(val) {
      console.log('on change', val)
    },
    onBlur(val) {
      console.log('on blur', val)
    },
    onFocus(val, $event) {
      console.log('on focus', val, $event)
    },
    onEnter(val) {
      console.log('click enter!', val)
    }
  }
}
</script>
<style lang="less" scoped>
.red {
  color: red;
}

.green {
  color: green;
}

.aui-cell_vcode {
  padding-top: 0;
  padding-right: 0;
  padding-bottom: 0;
}

.aui-vcode-img {
  margin-left: 5px;
  height: 44px;
  vertical-align: middle;
}

.aui-vcode-btn {
  display: inline-block;
  height: 44px;
  margin-left: 5px;
  padding: 0 0.6em 0 0.7em;
  border-left: 1px solid #e5e5e5;
  line-height: 44px;
  vertical-align: middle;
  font-size: 17px;
  color: #3cc51f;
  button& {
    background-color: transparent;
    border-top: 0;
    border-right: 0;
    border-bottom: 0;
    outline: 0;
  }
  &:active {
    color: desaturate(#3cc51f, 30%);
  }
}

.aui-cells_form {
  .aui-cell__ft {
    font-size: 0;
  }
  .aui-icon-warn {
    display: none;
  }
  input,
  textarea,
  label[for] {
    -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
  }
}
</style>

```


#### Github Issue