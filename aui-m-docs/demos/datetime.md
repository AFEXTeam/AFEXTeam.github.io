<!-- ---
nav: zh-CN
--- -->


### Datetime

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/datetime" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <div style="padding:15px;">
      <aui-button type="primary" plain @click.native="showPlugin">{{ $t('Used as a plugin') }}</aui-button>
    </div>
  
    <div style="padding:15px;">
      <aui-button type="primary" plain @click.native="showPluginAndroid">{{ $t('Used as a plugin dialog theme(Hide in 2s)') }}</aui-button>
    </div>
  
    <aui-group :title="$t('default format: YYYY-MM-DD')">
      <aui-datetime
        v-model="value1"
        @change="change"
        :title="$t('Birthday')"
        @cancel="log('cancel')"
        @confirm="log('confirm')"
        @hide="log('hide', $event)"></aui-datetime>
    </aui-group>
  
    <aui-group :title="$t('custom minute list: every 15 minutes')">
      <aui-datetime v-model="minuteListValue" format="YYYY-MM-DD HH:mm" :minute-list="['00', '15', '30', '45']" @change="change" :title="$t('Birthday')"></aui-datetime>
    </aui-group>
  
    <aui-group :title="$t('custom hour list')">
      <aui-datetime v-model="hourListValue" format="YYYY-MM-DD HH:mm" :hour-list="['09', '10', '11', '12', '13', '14', '15', '16']" :minute-list="['00', '15', '30', '45']" @change="change" :title="$t('Birthday')"></aui-datetime>
    </aui-group>
  
    <aui-group title="readonly">
      <aui-datetime v-model="valueReadonly" :readonly="readonly" @change="change" :title="$t('Birthday')"></aui-datetime>
    </aui-group>
  
    <div style="padding:15px">
      <aui-button type="primary" plain @click.native="readonly = !readonly">toggle readonly</aui-button>
    </div>
  
    <aui-group :title="$t('format display value')">
      <aui-datetime v-model="formatValue" :display-format="formatValueFunction" defaultFooterStyle="color:red" @change="change" :title="$t('Birthday')"></aui-datetime>
    </aui-group>
  
    <div style="padding:15px;">
      <aui-button type="primary" @click.native="formatValue = '2017-11-11'">{{ $t('set value: 2017-11-11') }}</aui-button>
    </div>
  
    <aui-group :title="$t('Limit hours')">
      <aui-datetime v-model="limitHourValue" format="YYYY-MM-DD HH:mm" :min-hour=9 :max-hour=18 @change="change" :title="$t('Limit hours')" :inline-desc="$t('09-18')"></aui-datetime>
    </aui-group>
  
    <aui-group :title="$t('set start-date and end-date') + ' 2015-11-11 ~ 2017-10-11'">
      <aui-datetime v-model="limitHourValue" :start-date="startDate" :end-date="endDate" format="YYYY-MM-DD HH:mm" @change="change" :title="$t('start time')"></aui-datetime>
    </aui-group>
  
    <div style="padding:15px;">
      <aui-button @click.native="reRender" type="primary">2016-11-11 ~ 2018-10-11</aui-button>
    </div>

    <aui-group :title="$t('Set end-date only') + ' 2017-10-11'">
      <aui-datetime v-model="onlySetEndDateValue" :end-date="onlySetEndDate" format="YYYY-MM-DD HH:mm" @change="change" :title="$t('Start time')"></aui-datetime>
    </aui-group>

    <aui-group :title="$t('format') + ':' + format">
      <aui-datetime v-model="value2" :format="format" @change="change" :title="$t('start time')"></aui-datetime>
    </aui-group>
  
    <div style="padding:15px;">
      <aui-button type="primary" @click.native="toggleFormat">{{ $t('toggle format') }}</aui-button>
    </div>
  
    <aui-group :title="$t('Placeholder')">
      <aui-datetime v-model="value3" default-selected-value="2017-06-18 13" format="YYYY-MM-DD HH" :placeholder="$t('Please select')" @change="change" :title="$t('start time')"></aui-datetime>
    </aui-group>
  
    <aui-group :title="$t('set default-selected-value to 2017-11-11')">
      <aui-datetime v-model="value3_1" default-selected-value="2017-11-11" format="YYYY-MM-DD" :placeholder="$t('Please select')" @change="change" :title="$t('start time')" :inline-desc="`current value: ${value3_1}`"></aui-datetime>
    </aui-group>
  
    <aui-group :title="$t('set min-year and max-year')">
      <aui-datetime v-model="value4" :placeholder="$t('Please select')" :min-year=2000 :max-year=2016 format="YYYY-MM-DD HH:mm" @change="change" :title="$t('years after 2000')"></aui-datetime>
    </aui-group>
  
    <aui-group :title="$t('prop:compute-hours-function')">
      <aui-datetime format="YYYY-MM-DD HH" v-model="computeHoursValue" :compute-hours-function="computeHoursFunction" :title="$t('Birthday')" @change="change"></aui-datetime>
    </aui-group>

    <aui-group :title="$t('prop:compute-days-function')">
      <aui-datetime format="YYYY-MM-DD HH" v-model="computeDaysValue" :compute-days-function="computeDaysFunction" :title="$t('Birthday')" @change="change"></aui-datetime>
    </aui-group>
  
    <aui-group :title="$t('specified template text in Chinese')">
      <aui-datetime v-model="value5" :placeholder="$t('Please select')" :min-year=2000 :max-year=2016 format="YYYY-MM-DD HH:mm" @change="change" :title="$t('Chinese')" year-row="{value}年" month-row="{value}月" day-row="{value}日" hour-row="{value}点" minute-row="{value}分" confirm-text="完成" cancel-text="取消"></aui-datetime>
    </aui-group>
  
    <aui-group :title="$t('show center button and clear the value')">
      <aui-datetime v-model="value6" @change="change" :title="$t('Birthday')" clear-text="clear" @clear="clearValue"></aui-datetime>
    </aui-group>
  
    <aui-group :title="$t('show center button to set date to today')">
      <aui-datetime v-model="value7" @change="change" :title="$t('Birthday')" clear-text="today" @clear="setToday"></aui-datetime>
    </aui-group>
  
    <aui-group :title="$t('custom trigger slot')">
      <aui-datetime v-model="value7" @change="change" :title="$t('Birthday')" clear-text="today" @clear="setToday">
        <aui-button>{{$t('Click me')}}</aui-button>
      </aui-datetime>
    </aui-group>
    <aui-group :title="$t('required')">
      <aui-datetime v-model="value8" :title="$t('Required')" clear-text="clear" @clear="clearValue8" :required="true"></aui-datetime>
    </aui-group>
  
    <aui-group :title="$t('use prop:show.sync(vue^2.3) to control visibility')">
      <aui-datetime v-model="value9" @change="change" :title="$t('Birthday')" :show.sync="visibility"></aui-datetime>
    </aui-group>
    <div style="padding:15px;">
      <aui-button type="primary" plain @click.native="visibility = false">显示</aui-button>
    </div>
  </div>
</template>



<script>
export default {
  data() {
    return {
      readonly: true,
      minuteListValue: "2017-06-12 09:00",
      hourListValue: "2017-06-12 09:00",
      format: "YYYY-MM-DD HH:mm",
      value1: "2015-11-12",
      valueReadonly: "2015-11-12",
      value2: "",
      value3: "",
      value3_1: "",
      value4: "",
      value5: "",
      value6: "2016-08-18",
      value7: "",
      value8: "",
      limitHourValue: "",
      startDate: "2015-11-11",
      endDate: "2017-10-11",
      formatValue: "2017-10-11",
      formatValueFunction(val) {
        return val.replace(/-/g, "$");
      },
      value9: "",
      visibility: false,
      computeHoursValue: "",
      computeDaysValue: "",
      computeHoursFunction(date, isToday, generateRange) {
        if (isToday) {
          return generateRange(new Date().getHours(), 23);
        } else {
          return generateRange(0, 23);
        }
      },
      computeDaysFunction(options, generateRange) {
        return [options.month]; // if current month is n, days are [n]
      },
      onlySetEndDate: "2017-10-11",
      onlySetEndDateValue: ""
    };
  },
  methods: {
    log(str1, str2 = "") {
      console.log(str1, str2);
    },
    showPluginAndroid() {
      this.$aui.datetime.show({
        showDialog: true,
        cancelText: "取消",
        confirmText: "确定",
        format: "YYYY-MM-DD HH",
        value: "2017-05-20 18",
        onConfirm(val) {
          console.log("plugin confirm", val);
        },
        onShow() {
          console.log("plugin show");
        },
        onHide() {
          console.log("plugin hide");
        }
      });
    },
    showPlugin() {
      this.$aui.datetime.show({
        showDialog: false,
        cancelText: "取消",
        confirmText: "确定",
        format: "YYYY-MM-DD HH",
        value: "2017-05-20 18",
        onConfirm(val) {
          console.log("plugin confirm", val);
        },
        onShow() {
          console.log("plugin show");
        },
        onHide() {
          console.log("plugin hide");
        }
      });
    },
    toggleFormat() {
      this.format =
        this.format === "YYYY-MM-DD HH:mm" ? "YYYY-MM-DD" : "YYYY-MM-DD HH:mm";
    },
    reRender() {
      this.startDate = "2016-11-11";
      this.endDate = "2018-10-11";
    },
    change(value) {
      console.log("change", value);
    },
    clearValue(value) {
      this.value6 = "";
    },
    clearValue8(value) {
      this.value8 = "";
    },
    setToday(value) {
      let now = new Date();
      let cmonth = now.getMonth() + 1;
      let day = now.getDate();
      if (cmonth < 10) cmonth = "0" + cmonth;
      if (day < 10) day = "0" + day;
      this.value7 = now.getFullYear() + "-" + cmonth + "-" + day;
      console.log("set today ok");
    }
  }
};
</script>

<style scoped lang="less">
.center {
  padding-top: 10px;
  padding-left: 15px;
  color: green;
}
</style>

```


#### Github Issue