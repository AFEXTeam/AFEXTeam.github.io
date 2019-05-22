在App.vue文件中的input需要绑定v-keyboard=”‘englishOnly’”自定义指令（或者v-keyboard=”‘englishOnlyNumber’”更改为默认为数字键盘）
```js
<template>
    <div id='app'>
        <input type="text" v-keyboard="'englishOnlyNumber'">
    </div>
</template>
```

main.js中：
```js
import {ScreenKeyboard, ScreenKeyboardManagerJS,inkRecognitionHandler} from "ab-plugin-keyboard";
import 'ab-plugin-keyboard/keyboard.css';
Vue.use(ScreenKeyboard);
```

keyboard插件也支持国际化，需要在main.js中进行配置
```js

import VueI18n from 'vue-i18n'
import zh from '../@agree/aui-web/lib/locale/lang/zh-CN.js'; // 根据locale文件夹所在的位置引入语言包
import en from '../@agree/aui-web/lib/locale/lang/en.js';

import {ScreenKeyboard, ScreenKeyboardManagerJS,inkRecognitionHandler} from "ab-plugin-keyboard";
import 'ab-plugin-keyboard/keyboard.css';

Vue.use(VueI18n);
// 准备翻译的语言环境信息
const messages = {
  'zh-CN': zh,
  'en': en
}

// 通过选项创建 VueI18n 实例
const i18n = new VueI18n({
  locale: 'zh-CN', // 设置地区
  messages
})

Vue.use(ScreenKeyboard, {
    i18n: (key, value) => i18n.t(key, value)
});


// 组件内部切换语言
// this.$i18n.locale = 'zh-CN';
this.$i18n.locale = 'en';
```