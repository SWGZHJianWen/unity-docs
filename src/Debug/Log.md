# Debug.Log

将普通消息记录到控制台（白色）

## 定义

```csharp
public static void Log (object message, Object context);
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
    private void Start()
    {
        // 输出游戏对象的名字，将会以灰色文本显示
        Debug.Log(gameObject.name);

        // 将会转换为字符串表示进行显示
        Debug.Log(gameObject);

        // 支持富文本.
        Debug.Log("<color=red>Alert: </color>Test rich text");
    }
}
```
