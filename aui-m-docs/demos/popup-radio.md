<!-- ---
nav: zh-CN
--- -->


### PopupRadio

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/popup-radio" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-group>
      <aui-popup-radio title="options"
                   :options="options1"
                   v-model="option1"
                   defaultSortStyle="color:red"></aui-popup-radio>
    </aui-group>
  
    <aui-group>
      <aui-popup-radio title="options"
                   :options="options2"
                   v-model="option2"
                   placeholder="placeholder"></aui-popup-radio>
    </aui-group>

    <aui-group>
      <aui-popup-radio title="options-dialog"
                  :show-dialog="true"
                   :options="options2"
                   v-model="option2"
                   placeholder="placeholder"></aui-popup-radio>
    </aui-group>
  
    <aui-group>
      <aui-popup-radio title="options"
                   :options="options3"
                   v-model="option3">
        <p slot="popup-header"
           class="aui-1px-b demo3-slot">Please select</p>
      </aui-popup-radio>
    </aui-group>
  
    <aui-group>
      <aui-popup-radio title="readonly"
                   readonly
                   :options="options3"
                   v-model="option4">
        <p slot="popup-header"
           class="aui-1px-b demo3-slot">Please select</p>
      </aui-popup-radio>
    </aui-group>
  
    <aui-group>
      <aui-popup-radio title="slot:each-item"
                   :options="options3"
                   v-model="option5">
        <template slot-scope="props"
                  slot="each-item">
          <p>
            custom item <img src="http://dn-placeholder.qbox.me/110x110/FF2D55/000"
                 class="aui-radio-icon"> {{ props.label }}
            <br>
            <span style="color:#666;">{{ props.index + 1 }} another line</span>
          </p>
        </template>
      </aui-popup-radio>
    </aui-group>
  
  </div>
</template>

<script>
export default {
  data() {
    return {
      option1: "A",
      options1: ["A", "B", "C"],
      option2: "",
      options2: [
        {
          key: "A",
          value: "label A"
        },
        {
          key: "B",
          value: "label B"
        }
      ],
      option3: "C",
      options3: ["A", "B", "C"],
      option4: "B",
      option5: "B"
    };
  }
};
</script>

<style scoped>
.demo3-slot {
  text-align: center;
  padding: 8px 0;
  color: #888;
}
</style>
```


#### Github Issue