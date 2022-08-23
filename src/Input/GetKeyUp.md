# Input.GetKeyUp

键盘抬起的**那一帧**返回 `true`

## 定义

```csharp
public static bool GetKeyUp(string name);
```

```csharp
public static bool GetKeyUp(KeyCode key);
```

## 参数

| 参数名 | 类型    | 必要             | 说明                                               |
| ------ | ------- | ---------------- | -------------------------------------------------- |
| name   | string  | 与 `key` 二选一  | 按键对应代码，详见 [按键名称表](#按键名称表)       |
| key    | KeyCode | 与 `name` 二选一 | 按键对应字符串名称，详见 [按键代码表](#按键代码表) |

## 示例

```csharp
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    public float number = 0.0f;
    
    private void Update()
    {
        if (Input.GetKeyDown("up"))
        {
            number += 1.0f;
            Debug.Log(number);
        }
        else if (Input.GetKeyDown("down"))
        {
            number -= 1.0f;
            Debug.Log(number);
        }
    }
}
```