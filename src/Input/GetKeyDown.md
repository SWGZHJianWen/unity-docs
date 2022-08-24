# Input.GetKeyDown

键盘按下的**那一帧**返回 `true`

## 定义

```csharp
public static bool GetKeyDown(string name);
```

| 参数名 | 类型   | 必要 | 说明                                                         |
| ------ | ------ | ---- | ------------------------------------------------------------ |
| name   | string | 是   | 按键对应代码，详见 [附录 #按键名称表](./appendix.md#按键名称表) |

```csharp
public static bool GetKeyDown(KeyCode key);
```

| 参数名 | 类型    | 必要 | 说明                                                         |
| ------ | ------- | ---- | ------------------------------------------------------------ |
| key    | KeyCode | 是   | 按键对应字符串名称，详见 [附录 #按键代码表](./appendix.md#按键代码表) |

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