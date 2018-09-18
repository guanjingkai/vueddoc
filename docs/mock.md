# Mock
vued 自带mcok，配置文件在 src/mock 下
mock的使用规则 参考mock.js 官网即可

一个mock的举例
```javascript
Mock.mock('http://api.meituan.com/shopList', 'get', {
  'code': 200, 
  'msg': 'success',
  'data|20': [{
    'merchant_id': '@integer(17000000,18000000)',
    'shop_name': '@cword(4)(@city())店',
    'open_service': {
      'open_api': '@integer(1,1)',
      'qrcode': '@integer(0,1)',
      'white_box': '@integer(0,1)',
      'black_box': '@integer(0,1)',
      'pos': '@integer(0,1)'
    },
    'business_licence': '@cword(5)' + '餐饮有限公司',
    'mcc|1': ['餐饮', '生鲜', '奶茶'],
    'belong_custom|1': ['呷哺呷哺', '田老师', '喜茶'],
    'belong_isv|1': ['屏芯', '天子星', '美团收银'],
    'shop_address': '@city(true)'
  }]
})
```

mockjs 文档 https://github.com/nuysoft/Mock/wiki