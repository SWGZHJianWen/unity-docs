# Vector3.Distance

计算两点间距离。

## 定义

```csharp
public static float Distance(Vector3 a, Vector3 b);
```

| 参数名 | 类型      | 必要  | 说明  |
|:--- |:------- |:--- |:--- |
| a   | Vector3 | 是   | a 点 |
| b   | Vector3 | 是   | b 点 |

```admonish example
~~~csharp
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    public Transform target;

    private bool IsClose()
    {
        if (!target) return false;
        var distance = Vector3.Distance(transform.position, target.position);
        return distance < 10.0f;
    }
}
~~~
```
