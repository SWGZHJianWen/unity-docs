# Time.deltaTime

上一帧到当前帧的时间间隔（秒）

## 定义

```csharp
public static float deltaTime;
```

## 示例

```csharp
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    private const float WaitTime = 5.0f;
    private float _timer;
    
    private void Update()
    {
        _timer += Time.deltaTime;
        if (_timer > WaitTime)
        {
            Debug.Log("等待完成");
            _timer -= WaitTime;
        }
        else
        {
            Debug.Log($"已等待{_timer}秒...");
        }
    }
}
```