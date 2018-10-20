# ab-manager-validator

输入校验，对输入的内容进行验证。

1.引入

```js
import { ValidatorManager } from "ab-manager-validator";
```

2.使用：

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

| 参数     | 类型 | 说明 |
| -------- | --- | --- |
| "required"(可选) | string | 只能是"required"，表示“必输”，不设置表示“不必输” |
| test(可选) | regex | 正则表达式，表示验证规则 |
| errorMsg(可选) | string | 不满足验证提示的错误信息 |