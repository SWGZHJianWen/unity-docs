# Physics.Raycast

检测是否有任何碰撞体重叠在定义的**射线**上

## 定义

```csharp
public static bool Raycast(
    Vector3 origin,
    Vector3 direction,
    float maxDistance = Mathf.Infinity,
    int layerMask = DefaultRaycastLayers,
    QueryTriggerInteraction queryTriggerInteraction = QueryTriggerInteraction.UseGlobal
);
```



| 参数名                  | 类型                    | 必要 | 说明                                                         |
| ----------------------- | ----------------------- | ---- | ------------------------------------------------------------ |
| origin                  | Vector3                 | 是   | 世界坐标系中射线起始点                                       |
| direction               | Vector3                 | 是   | 射线方向                                                     |
| maxDistance             | float                   | 否   | 射线最大距离，默认 `Mathf.Infinity`，即无限                  |
| layerMask               | int                     | 否   | 层级蒙版，设定后只检测此层级中的物体是否相交                 |
| queryTriggerInteraction | QueryTriggerInteraction | 否   | 指定该查询是否触发触发器，默认 `QueryTriggerInteraction.UseGlobal`<br />`QueryTriggerInteraction.UseGlobal`：使用 `Physics.queriesHitTriggers` 设置<br />`QueryTriggerInteraction.Ignore`：忽略<br />`QueryTriggerInteraction.Colide`：触发 |
