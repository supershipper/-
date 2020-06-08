# 认证的Icons展示

> 考虑到后期，除了个人是否实名认证，会加做公司是否认证，和是否是VIP船东/货主，所以单独做了一个组件来展示。目前组件的后三个已经做好样式，但是被注释掉没有放出来


## 示例
![示例](../img/identifyIcos.jpg)

## 参数
|  字段   | 默认值  |  类型  | 说明 |
|  ----  | ----  |  ----  | ----  |
| realName  | "0" | String | 是否个人认证("0"-未认证 "1"-已认证)  |
| enterpriseCer  | "0" | String | 是否企业认证  ("0"-未认证 "1"-已认证)|




## 示例用法

```json
{
	"usingComponents": {
        "c-identify-icos":"../component/identifyIcos/identifyIcos"
	}
}
```

```wxml
    <c-identify-icos class="flex1" realName="{{realName}}" enterpriseCer="{{enterpriseCer}}"></c-identify-icos>
```

```js
Page({
    data:{
        realName:"0",
        enterpriseCer:"1",
    },
	
})
```
