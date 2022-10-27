# Debug.LogWarning

将警告消息记录到控制台（黄色）

## 定义

```csharp
public static void LogWarning (object message, Object context);
```

| 参数名     | 类型     | 必要  | 说明                    |
| ------- | ------ | --- | --------------------- |
| message | object | 是   | 字符串或对象，将被转换为字符串表示进行显示 |
| context | Object | 否   | 此消息应用到的对象             |

## 示例

```csharp
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    public float gravity;

    private void Start()
    {
        if (gravity < 0)
        {
            // 将会以黄色文本显示
            Debug.LogWarning("重力大小为负数");
        }
    }
}
```
