# Vector3.Normalize

对向量进行标准化，使其方向保持不变，但长度变为 1.0，这个过程也称为归一化。

## 定义

```csharp
public static Vector3 Normalize(Vector3 value);
```

| 参数名   | 类型      | 必要  | 说明     |
|:----- |:------- |:--- |:------ |
| value | Vector3 | 是   | 待归一化向量 |

```admonish example
~~~csharp
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    public Transform target;

    private void Update()
    {
        var direction = target.position - transform.position;
        direction.Normalize();
        transform.Translate(direction * Time.deltaTime);
    }
}
~~~
```
