# Time.time

游戏自启动以来的时间（秒）。

## 定义

```csharp
public static float time;
```

~~~admonish example title="示例"

与 [Time.deltaTime](./deltaTime.md) 中的示例不同，此处使用 `Time.time` 实现了一个新的倒数计时器，并且可以控制计数间隔

```csharp
using UnityEngine;
using UnityEngine.UI;

public class ExampleScript : MonoBehaviour
{
    public float timeStart = 60f;
    public Text textBox;
    public Text startBtnText;
    public float interval = 3f; // 间隔

    private float _nextTick;
    private bool _timerActive;

    private void Start()
    {
        textBox.text = timeStart.ToString("00");
    }

    private void Update()
    {
        if (!_timerActive || Time.time < _nextTick) return;
        timeStart -= interval;
        _nextTick = Time.time + interval;
        textBox.text = timeStart <= 0 ? "Over" : timeStart.ToString("00");
    }

    public void TimerButton()
    {
        _timerActive = !_timerActive;
        startBtnText.text = _timerActive ? "Pause" : "Start";
    }
}
```
~~~