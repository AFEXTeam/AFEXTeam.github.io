<!-- ---
nav: zh-CN
--- -->


### Timeline

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/timeline" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
	<div class="timeline-demo">
		<aui-timeline>
			<aui-timeline-item>
				<h4 class="recent">【广东】 广州市 已发出</h4>
				<p class="recent">2016-04-17 12:00:00</p>
			</aui-timeline-item>
			<aui-timeline-item>
				<h4> 申通快递员 广东广州 收件员 xxx 已揽件</h4>
				<p>2016-04-16 10:23:00</p>
			</aui-timeline-item>
			<aui-timeline-item>
				<h4> 商家正在通知快递公司揽件</h4>
				<p>2016-04-15 9:00:00</p>
			</aui-timeline-item>
		</aui-timeline>
		<aui-timeline>
			<aui-timeline-item v-for="(i, index) in count" :key="index">
				<h4 :class="[i === 0 ? 'recent' : '']">Timeline Node {{i + 1}}</h4>
				<p :class="[i === 0 ? 'recent' : '']">index {{i + 1}}</p>
			</aui-timeline-item>
		</aui-timeline>
    <aui-button type="primary" @click.native="count = 6"> Set to 6 nodes</aui-button>
    <aui-button type="primary" @click.native="count = 3"> Set to 3 nodes</aui-button>
	</div>
</template>

<script>

export default {
  
  data () {
    return {
      count: 3
    }
  }
}
</script>

<style lang="less">
.timeline-demo {
	p {
		color: #888;
		font-size: 0.8rem;
	}
	h4 {
		color: #666;
		font-weight: normal;
	}
	.recent {
		color: rgb(4, 190, 2)
	}
}
</style>

```


#### Github Issue