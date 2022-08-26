# GameObject.GetComponentInChildren

返回游戏对象（`GameObject`）及其子对象中第一个指定类型的组件，如果没有则返回 `null`。



## 定义

```csharp
public Component[] GetComponentsInChildren(Type type, bool includeInactive = false);
```

| 参数名          | 类型 | 必要 | 说明                                                     |
| --------------- | ---- | ---- | -------------------------------------------------------- |
| type            | Type | 是   | 要检索的组件类型                                         |
| includeInactive | bool | 否   | 是否检索不活动对象，默认否<br />（预制体是不活动的对象） |

