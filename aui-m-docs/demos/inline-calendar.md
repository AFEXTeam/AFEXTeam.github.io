---
nav: zh-CN
---


### InlineCalendar

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/inline-calendar" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-inline-calendar ref="calendar" 
    @change="onChange" 
    @view-change="onViewChange" 
    class="inline-calendar-demo" 
    :show.sync="show" 
    v-model="value" 
    start-date="2016-04-01" 
    end-date="2038-12-12" 
    :range="range" 
    :show-last-month="showLastMonth" 
    :show-next-month="showNextMonth" 
    :highlight-weekend="highlightWeekend" 
    :return-six-rows="return6Rows" 
    :hide-header="hideHeader" 
    :hide-week-list="hideWeekList" 
    :disable-month="true"
    :replace-text-list="replaceTextList" 
    :weeks-list="weeksList" 
    :render-function="buildSlotFn" 
    :disable-past="disablePast"   
    :disable-future="disableFuture"
    :disable-weekend="disableWeekend"
    :disable-date-function="disableDateFunction">
    </aui-inline-calendar>

    <aui-group>
      <aui-cell title="current value" :value="value"></aui-cell>
      <aui-cell title="start date" value="2016-04-01"></aui-cell>
      <aui-cell title="end date" value="2018-05-30"></aui-cell>
    </aui-group>

 
    <div style="margin: 15px;">
      <aui-button type="primary" @click.native="$refs.calendar.switchViewToToday()">switchViewToToday</aui-button>
      <aui-button type="primary" @click.native="$refs.calendar.switchViewToMonth(2017, 12)">switchViewToMonth(2017, 12)</aui-button>
      <aui-button type="primary" @click.native="$refs.calendar.switchViewToMonth(2018, 10)">switchViewToMonth(2018, 10)</aui-button>
      <aui-button type="primary" @click.native="$refs.calendar.switchViewToCurrentValue()">switchViewToCurrentValue</aui-button>
    </div>
  
    <aui-group title="control days" style="margin-top: 30px;">
      <aui-switch v-model="disablePast" title="Disable Past"></aui-switch>
      <aui-switch v-model="disableFuture" title="Disable Future"></aui-switch>
      <aui-switch v-model="disableWeekend" title="Disable Weekend"></aui-switch>
      <aui-switch v-model="showLastMonth" title="Show Last Month"></aui-switch>
      <aui-switch v-model="showNextMonth" title="Show Next Month"></aui-switch>
      <aui-switch v-model="return6Rows" inline-desc="if not, the calendar's height would change" title="Always show 6 rows"></aui-switch>
      <aui-switch v-model="highlightWeekend" title="highlight weekend"></aui-switch>
      <aui-cell title="current value" :value="value"></aui-cell>
    </aui-group>
    <aui-group title="control navs">
      <aui-switch v-model="hideHeader" title="Hide header"></aui-switch>
      <aui-switch v-model="hideWeekList" title="Hide week list"></aui-switch>
      <aui-switch v-model="changeWeeksList" title="Change weeks list"></aui-switch>
    </aui-group>
    <aui-group title="replace text">
      <aui-switch v-model="replace" title="Replace date text"></aui-switch>
    </aui-group>
    <br>
    <div style="margin: 15px;">
      <aui-button type="primary" @click.native="value='2020-11-11'">Set time to 2020-11-11</aui-button>
      <aui-button type="primary" @click.native="value='2020-11-22'">Set time to 2020-11-22</aui-button>
      <aui-button type="primary" @click.native="value='2016-08-09'">Set time to 2016-08-09</aui-button>
      <aui-button type="primary" @click.native="value='TODAY'">Set time to today</aui-button>
      <aui-button type="primary" @click.native="value='2016-06-05'">Set time to 2016-06-05</aui-button>
    </div>
    <br>
    <aui-group title="custom every day cell">
      <aui-switch v-model="useCustomFn" inline-desc="Add red dot for dates with 8" title="add custom contents in day cell"></aui-switch>
    </aui-group>

    <br>

    <aui-divider>We can render a list of calendars order by month</aui-divider>
    <aui-group>
      <aui-cell title="current value" :value="listValue"></aui-cell>
    </aui-group>
    <br>
  </div>
</template>

<script>
export default {
  methods: {
    onChange(val) {
      console.log("change", val);
    },
    onViewChange(val, count) {
      console.log("on view change", val, count);
    }
  },
  data() {
    return {
      show: true,
      value: "",
      listValue: "",
      range: false,
      showLastMonth: true,
      showNextMonth: true,
      highlightWeekend: false,
      return6Rows: true,
      hideHeader: false,
      hideWeekList: false,
      replaceTextList: {
            TODAY: "今"
          },
      replace: false,
      changeWeeksList: false,
      weeksList: [],
      useCustomFn: false,
      buildSlotFn: () => "",
      disablePast: false,
      disableFuture: false,
      disableFuture: false,
      disableWeekend: false,
      disableDateFunction (date) {
        if (date.formatedDate === '2017-10-16') {
          return true
        }
      }
    };
  },
  watch: {
    replace(val) {
      this.replaceTextList = val
        ? {
            TODAY: "今"
          }
        : {};
    },
    useCustomFn(val) {
      this.buildSlotFn = val
        ? (line, index, data) => {
            return /8/.test(data.date)
              ? '<div style="font-size:12px;text-align:center;"><span style="display:inline-block;width:5px;height:5px;background-color:red;border-radius:50%;"></span></div>'
              : '<div style="height:19px;"></div>';
          }
        : () => "";
    },
    changeWeeksList(val) {
      this.weeksList = val
        ? ["日", "一", "二", "三", "四", "五", "六 "]
        : ["Su", "Mo", "Tu", "We", "Th", "Fr", "Sa"];
    }
  }
};
</script>

<style lang="less" scoped>
.inline-calendar-demo {
  background: rgba(255, 255, 255, 0.9);
}
</style>

```


#### Github Issue