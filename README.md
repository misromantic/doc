##### <a href="#模板标题">模板标题</a>
##### <a href="#一、轮播广告">一、轮播广告</a>

### <a name="模板标题">模板标题</a>
URL
---
``` 
/api/banner
```
参数
---
```
{}
```
返回
---
```
{
  "data": {},
  "message": "查询成功",
  "stateCode": 101
}
```

### <a name="一、轮播广告">一、轮播广告</a>
URL
---
``` 
/api/banner
```
参数
---
```
{
  type: 轮播类型  1-首页
}
```
返回
---
```
{
  "data": {
    "informations": [{
      "link": "http://www.yidianchina.com/netauction/auction/15266468.html?utm_source=12ZWP26",
      "picture": "http://***/assets/upload/image/b34faeb07cd6b80758baf5b85c5b303b.jpg",
      "pictureId": 15761515
    }, {
      "link": "http://www.yidianchina.com/netauction/auction/15152626.html?utm_source=12XYYJD",
      "picture": "http://***/assets/upload/image/c6d7f207bb639508f864314c3cb3de29.jpg",
      "pictureId": 15536825
    }, {
      "link": "http://***/#/news/detail/9308911?utm_source=12ZS",
      "picture": "http://picture1.yidianchina.com/assets/upload/image/61a04238272c15316c86dcc23d87797a.jpg",
      "pictureId": 15216380
    }]
  },
  "stateCode": 101
}
```




