---
nav: zh-CN
---


### Uploader

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="http://192.9.200.185:50003/aui-m/#/component/uploader" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-uploader height="100px" width="200px" :uploadImage="img"  @onChange="uploader"></aui-uploader>
    <!-- <aui-divider>没有封装组件，引入样式使用</aui-divider>
    <div class="aui-uploader" style="padding:15px;">
      <div class="aui-uploader__hd">
          <p class="aui-uploader__title">图片上传</p>
          <div class="aui-uploader__info">0/2</div>
      </div>
      <div class="aui-uploader__bd">
          <ul class="aui-uploader__files" id="uploaderFiles">
              <li class="aui-uploader__file" style="background-image:url(https://static.vux.li/uploader_bg.png)"></li>
              <li class="aui-uploader__file" style="background-image:url(https://static.vux.li/uploader_bg.png)"></li>
              <li class="aui-uploader__file" style="background-image:url(https://static.vux.li/uploader_bg.png)"></li>
              <li class="aui-uploader__file aui-uploader__file_status" style="background-image:url(https://static.vux.li/uploader_bg.png)">
                  <div class="aui-uploader__file-content">
                      <i class="aui-icon-warn"></i>
                  </div>
              </li>
              <li class="aui-uploader__file aui-uploader__file_status" style="background-image:url(https://static.vux.li/uploader_bg.png)">
                  <div class="aui-uploader__file-content">50%</div>
              </li>
          </ul>
          <div class="aui-uploader__input-box">
              <input id="uploaderInput" class="aui-uploader__input" type="file" accept="image/*" multiple />
          </div>
      </div>
    </div> -->
  </div>
</template>

<script>
export default {
  data(){
    return{
    img:""

    }
  },
  methods: {
    uploader(value) {
      // this.img = value
      // var xhr = new XMLHttpRequest();
      // xhr.open("POST", "http://httpbin.org/post", true);

      // xhr.onreadystatechange = function(e) {
      //   console.log("进度：" + e.target.readyState);
      //   if (e.target.readyState == 4) {
      //     console.log("成功");
      //   }
      // };
      // // xhr.onprogress = function(e) {
      // //   console.log("onprogress：" + e.target);
      // // };
      // xhr.send(value);
    }
  }
};
</script>

<style lang="less">
// @import '../../theme-default/weui/widget/aui-uploader/index.less';
</style>

```


#### Github Issue