<!-- ---
nav: zh-CN
--- -->


### AuiTable

---

#### 演示

 <div style="width:377px;height:667px;display:inline-block;border:1px dashed #ececec;border-radius:5px;overflow:hidden;">
   <iframe src="https://afexteam.github.io/aui-m-demo/#/component/aui-table" width="375" height="667" border="0" frameborder="0"></iframe>
 </div>

#### demo 代码

<p class="tip">下面的$t是Demo的i18n使用的翻译函数，一般情况下可以直接使用字符串。另外，下面代码隐藏了i18n标签部分的代码。</p>

``` html
<template>
  <div>
    <aui-load-more tip="default" :show-loading="false" background-color="#fbf9fe"></aui-load-more>
    <div style="padding:0 15px;">
      <aui-table>
        <thead>
          <tr>
            <th>Product</th>
            <th>Price</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Apple</td>
            <td>$1.25</td>
          </tr>
          <tr>
            <td>Banana</td>
            <td>$1.20</td>
          </tr>
        </tbody>
      </aui-table>
    </div>
    <div>
      <aui-load-more tip="cell-bordered=false" :show-loading="false" background-color="#fbf9fe"></aui-load-more>
      <aui-table :cell-bordered="false" style="background-color:#fff;">
        <thead>
          <tr>
            <th>Product</th>
            <th>Price</th>
            <th>Quantity</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Apple</td>
            <td>$1.25</td>
            <td> x 1</td>
          </tr>
          <tr>
            <td>Banana</td>
            <td>$1.20</td>
            <td> x 2</td>
          </tr>
        </tbody>
      </aui-table>

      <aui-load-more tip="content-bordered=false" :show-loading="false" background-color="#fbf9fe"></aui-load-more>

      <aui-table :cell-bordered="false" :content-bordered="false" style="background-color:#fff;">
        <thead>
          <tr style="background-color: #F7F7F7">
            <th>Product</th>
            <th>Price</th>
            <th>Quantity</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Apple</td>
            <td>$1.25</td>
            <td> x 1</td>
          </tr>
          <tr>
            <td>Banana</td>
            <td>$1.20</td>
            <td> x 2</td>
          </tr>
        </tbody>
      </aui-table>
      </div>
      <div style="padding:15px;">
        <aui-load-more tip="full-bordered" :show-loading="false" background-color="#fbf9fe"></aui-load-more>
        <aui-table full-bordered style="background-color:#fff;">
          <thead>
            <tr>
              <th>Product</th>
              <th>Price</th>
              <th>Quantity</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>Apple</td>
              <td colspan="2">$1.25 x 10</td>
            </tr>
            <tr>
              <td>Banana</td>
              <td>$1.20</td>
              <td>x 08</td>
            </tr>
          </tbody>
        </aui-table>
    </div>
  </div>
</template>

<script>

export default {
 
}
</script>
```


#### Github Issue