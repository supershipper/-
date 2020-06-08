# 给货主打电话

> 叫这个名字是因为之前进入并使用小程序不需要绑定手机号，但是要打电话的话需要绑定手机号，所以做了一个验证的区分，展示绑定手机号和未绑定手机号的不同界面样式。并在未绑定的时候点击，会触发绑定手机号的流程。

> **特别注意：现在的版本要求进入立马绑定手机号，否则无法使用任何功能，所以该文档仅做参考，该组件在当前版本并未做维护**


## 参数
|  字段   | 默认值  |  类型  | 说明 |
|  ----  | ----  |  ----  | ----  |
| isAuth  | false | Boolean | 是否绑定手机号  |

## 事件
|  事件名   | 携带参数  |  类型  | 说明 |
|  ----  | ----  |  ----  | ----  |
| authsuccess  | - | - | 完成绑定手机号  |

## 插槽
|  名字    | 说明 |
|  ----  |  ----  |
| unauthorized  |  未绑定时展示样式  |
| authorized  |  已绑定时展示样式  |

## 示例用法

```json
{
	"usingComponents": {
		"c-call-gooder": "../component/callGooder/callGooder"
	}
}
```

```wxml
<c-call-gooder bind:authsuccess="authSuccess" is-auth="{{isAuth}}">
    <view slot="unauthorized">
        <view catchtap='toAuth' >我要投保</view>
    </view>
    <view slot="authorized">
        <view catchtap='todo'>我要投保</view>
    </view>
</c-call-gooder>
```

```js
Page({
    data: {
		isAuth:false,
	},
    authSuccess() {
        this.setData({
            isAuth: true,
        });
    },
})
```
