# OnTriggerEnter

当物体**刚碰撞**另一个物体时被调用。

## 定义

```csharp
private void OnTriggerEnter(Collider other)
```

| 参数名 | 类型     | 说明                                   |
| ------ | -------- | -------------------------------------- |
| other  | Collider | 该碰撞中涉及的其他碰撞体（`Collider`） |

## 示例

```csharp
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    public float health = 10f;

    private void OnTriggerEnter(Collider other)
    {
        switch (other.tag)
        {
            case "Red":
                health -= 2f;
                break;
            case "Green":
                health += 1f;
                break;
        }
    }
}
```