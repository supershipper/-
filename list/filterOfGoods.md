# 货盘筛选项

> 包含起始港海域 货量范围 预载时间



## 示例
![示例](../img/filterOfGoods.jpg)



## 事件
|  事件名   | 携带参数  |  类型  | 说明 |
|  ----  | ----  |  ----  | ----  |
| selectDone  | ↓ | {} | 选择完成  |
|             | startDate | String | 起始日期  |
|             | endDate | String | 截止日期  |
|             | minTon | Number | 最小货量  |
|             | maxTon | Number | 最大货量  |
|             | seaAreaId | Number | 起始港海域Id  |
|    closed   | - | - | 关闭panel  |


## 插槽
|  名字    | 说明 |
|  ----  |  ----  |
| 默认插槽  |  点击插槽会打开该modal  |


## 示例用法

```json
{
	"usingComponents": {
        "c-filter-goods": "../component/filterOfGoods/filterOfGoods"
	}
}
```

```wxml
    <c-filter-goods bind:selectDone='filterGoods' bind:closed='closed'>
        <text>筛选</text>
    </c-filter-goods>
```

```js
Page({
    filterGoods(e){
        let filterData=e.detail;
        this.setData({
            "SeaAreaId":filterData.seaAreaId,
            "MinCargo":filterData.minTon,
            "MaxCargo":filterData.maxTon,
            "MinLoadDate":filterData.startDate,
            "MaxLoadDate":filterData.endDate
        })
    },
    closed(){
        //todo..
    }
})
```
