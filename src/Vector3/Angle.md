# Vector3.Angle

计算两向量间角度

## 定义

```csharp
public static float Angle(Vector3 from, Vector3 to);
```

## 参数

| 参数名 | 类型    | 必要 | 说明     |
| ------ | ------- | ---- | -------- |
| from   | Vector3 | 是   | 源向量   |
| to     | Vector3 | 是   | 目标向量 |

## 示例

```csharp
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    public Transform target;
    
    private bool IsAiming()
    {
        var playerTransform = transform;
        var targetDir = target.position - playerTransform.position;
        var angle = Vector3.Angle(targetDir, playerTransform.forward);
        return angle < 5.0f;
    }
}
```

