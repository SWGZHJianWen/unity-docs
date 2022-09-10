# OnTriggerStay

当物体**持续碰撞**另一个物体时被调用。

## 定义

```csharp
private void OnTriggerEnter(Collider other)
```

| 参数名 | 类型     | 说明                                   |
| ------ | -------- | -------------------------------------- |
| other  | Collider | 该碰撞中涉及的其他碰撞体（`Collider`） |

## 示例

演示了 [OnTriggerEnter](./OnTriggerEnter.md)、[OnTriggerStay](./OnTriggerStay.md)、[OnTriggerExit](./OnTriggerExit.md) 的基本用法。

碰到红色(`Red` 标签)扣血，碰到绿色（`Green` 标签）回复，在紫色（`Purple` 标签）里中毒，在黄色（`Yellow` 标签）里减速。

```csharp
using System;
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    public float health = 10f;
    public float speed = 2f;
    private float _totalTime;
    
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

    private void OnTriggerStay(Collider other)
    {
        if (other.CompareTag("Purple"))
        {
            _totalTime += Time.deltaTime;
            if (_totalTime >= 1f)
            {
                health -= 0.5f;
                _totalTime = 0f;
            }
        }
        else if (other.CompareTag("Yellow"))
        {
            speed = 1f;
        }
    }

    private void OnTriggerExit(Collider other)
    {
        if (other.CompareTag("Yellow"))
        {
            speed = 2f;
        }
    }
} 
```