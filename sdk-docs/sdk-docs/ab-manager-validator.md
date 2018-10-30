# ab-manager-validator@校验管理

输入校验，对输入的内容进行验证。

1.引入

```js
import { ValidatorManager } from "ab-manager-validator";
```

2.基本用法：

```js
<template>
    <valid-template property="phone">
        <aui-input v-model="phone"></aui-input>
    </valid-template>
</template>

<script>
import { ValidatorManager } from "ab-manager-validator";

export default {
  mixins: [ValidatorManager],
  validators: {
    phone: [
      "required",
      {
        test: /^((13[0-9])|(14[5|7])|(15([0-3]|[5-9]))|(18[0,5-9]))\d{8}$/g,
        errorMsg: "请输入正确的手机号类型"
      }
    ]
  },
  data() {
      return {
          phone: ''
      }
  }
  // ...
}
</script>
```

3.修改校验规则

```js
this.$setValidate(validateName, validateRule[, symbol]);
```

**例：**

```js
<script>
// ...
methods: {
  setValidate() {
    this.$setValidate('phone', {
      required: false,
      test: function(value) {
        if(value > 1000) {
          return true;
        }
      }
    }, false);
  }
}
// ...
</script>
```

> 此处由于`symbol`为`false`，只更新原有规则的`required`以及`test`；如果改为`true`，则全部替换原有规则，所以`errorMsg`为空，将使用默认值。

4.设置默认校验规则

step1:
```js
// 定义规则
/* @/common/manager/validator-manager/defualt-rules.js */
let defaultRules = {
    idCard: ['required'],
    email: {
        test: /.+@.+\..+/g,
        errMsg: '请输入正确的邮箱类型'
    }
};

export {
    defaultRules
}
```

step2:
```js
// 增加规则
import { Rules } from 'ab-manager-validator'
import { defaultRules } from '@/common/manager/validator-manager/defualt-rules.js'
Rules.add(defaultRules);
```

step3:
```js
// 使用规则
import { Rules } from 'ab-manager-validator'

export default {
    validators: {
        idCard: Rules.idCard,
        email: [
          'required',
          Rules.email
        ]
    }
}
```

**注：**`step2`可在`main.js`中将一次性将定义好的规则统一添加到默认规则中。

| 参数     | 类型 | 说明 | 默认值 |
| -------- | --- | --- | --- |
| "required"(可选) | string | 只能是"required"，表示“必输”，不设置表示“不必输” | - |
| test(可选) | regex | 正则表达式，表示验证规则 | - |
| errorMsg(可选) | string | 不满足验证提示的错误信息 | "必输项" |
| validateName | string | 修改规则的变量名 | - |
| validateRule | object | 规则信息 | - |
| symbol(可选) | boolean | 是否整体替换原有规则 | true |

**参数`validateRule`中的字段：**

| 参数     | 类型 | 说明 | 默认值 |
| -------- | --- | --- | --- |
| required | boolean | 是否必输 | - |
| test | regexp/function | 校验规则 | - |
| errorMsg | string | 错误提示信息 | - |