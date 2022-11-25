# Debug.DrawLine

绘制一条直线

## 定义

```csharp
public static void DrawLine (Vector3 start, Vector3 end, Color color= Color.white, float duration= 0.0f, bool depthTest= true);
```

| 参数名       | 类型      | 必要  | 说明                     |
|:--------- |:------- |:--- |:---------------------- |
| start     | Vector3 | 是   | 直线起始点（世界空间中）           |
| end       | Vector3 | 是   | 直线结束点（世界空间中）           |
| color     | Color   | 否   | 直线颜色，默认黄色              |
| duration  | float   | 否   | 直线的可见时间，单位秒，默认 `0`，即一帧 |
| depthTest | bool    | 否   | 直线是否会被遮挡，默认是           |

~~~admonish example title="示例"

```csharp
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    private void Start()
    {
        // 从原点绘制一条 5 单位长度的白线，持续 2.5 秒
        Debug.DrawLine(Vector3.zero, new Vector3(5, 0, 0), Color.white, 2.5f);
    }

    private float q = 0.0f;

    private void FixedUpdate()
    {
        // 从原点画一条 5 单位长度的彩色线，一直显示
        Color color = new Color(q, q, 1.0f);
        Debug.DrawLine(Vector3.zero, new Vector3(0, 5, 0), color);
        q = q + 0.01f;

        if (q > 1.0f)
        {
            q = 0.0f;
        }
    }
}
```
~~~