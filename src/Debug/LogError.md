# Debug.LogError

将错误消息记录到控制台（红色）

## 定义

```csharp
public static void LogError (object message, Object context); 
```

| 参数名     | 类型     | 必要  | 说明                    |
|:------- |:------ |:--- |:--------------------- |
| message | object | 是   | 字符串或对象，将被转换为字符串表示进行显示 |
| context | Object | 否   | 此消息应用到的对象             |

## 示例

```csharp
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    public Rigidbody myRigidbody;

    private void Start()
    {
        if (myRigidbody == null)
        {
            // 将会以红色文本显示
            Debug.LogError("未找到 Rigidbody");
        }
    }
}
```
