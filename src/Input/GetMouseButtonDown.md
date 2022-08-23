# Input.GetMouseButtonDown

鼠标按下的**那一帧**返回 `true`

## 定义

```csharp
public static bool GetMouseButtonDown(int button);
```

## 参数

| 参数名 | 类型 | 必要 | 说明                                                         |
| ------ | ---- | ---- | ------------------------------------------------------------ |
| button | int  | 是   | 按键对应数字<br>`0`：鼠标左键<br>`1`：鼠标右键<br>`2`：鼠标中键 |

## 示例

```csharp
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    private void Update()
    {
		if (Input.GetMouseButton(0))
            Debug.Log("鼠标左键处于按下状态");

        if (Input.GetMouseButtonDown(0))
            Debug.Log("已按下鼠标左键");

        if (Input.GetMouseButtonUp(0))
            Debug.Log("已抬起鼠标左键");
    }
}
```