# Debug.DrawLine

绘制一条直线

## 定义

```csharp
public static void DrawLine (Vector3 start, Vector3 end, Color color= Color.white, float duration= 0.0f, bool depthTest= true);
```

| 参数名    | 类型    | 必要 | 说明                                     |
| --------- | ------- | ---- | ---------------------------------------- |
| start     | Vector3 | 是   | 直线起始点（世界空间中）                 |
| end       | Vector3 | 是   | 直线结束点（世界空间中）                 |
| color     | Color   | 否   | 直线颜色，默认黄色                       |
| duration  | float   | 否   | 直线的可见时间，单位秒，默认 `0`，即一帧 |
| depthTest | bool    | 否   | 直线是否会被遮挡，默认是                 |

