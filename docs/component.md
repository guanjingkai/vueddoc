# 组件
### CommonTable
基于iView Table组件封装的业务组件，适用于中后台列表页面

组件vue文件位置
```javascript
vued/table
```
props

|参数|描述|
|--------|--------|
|api|当前列表数据源，请求的api接口|
|searchConfig|搜索条件|
|tableColumns|列表列|
|fixedHeight|table绝对高度|
|tableData|table数据，若没有api，则优先使用tableData|

searchConfig
```javascript
searchConfig: {
        vip_id: {
          title: "会员ID",
          key: "vip_id",
          type: "input",
          width: 100,
          value: ""
        }
}
```
|参数|描述|
|--------|--------|
|title|表头|
|key|需要和API的检索条件保持一致|
|type|控件类型，具体看下面|
|width|控件宽度|
|value|默认值|

type
```javascript
searchConfig: {
       //input
        vip_id: {
          title: "会员ID",
          key: "vip_id",
          type: "input",
          width: 100,
          value: ""
        },
        //select
        payTools: {
          title: "渠道",
          key: "payType",
          type: "select",
          data: [
            { key: "weixin", value: "微信" },
            { key: "Alipay", value: "支付宝" },
            { key: "card", value: "实体卡" }
          ],
          width: 100,
          value: ""
        },
        //date-time 时间区间
        payType:{
          title:'有效期',
          key:'payType',
          type:'date-time',
          width:180,
          value:''
        }   
}
```
### CommonForm
组件vue文件位置
```javascript
vued/form
```