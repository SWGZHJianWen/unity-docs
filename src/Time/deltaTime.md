# Time.deltaTime

上一帧到当前帧的时间间隔（秒）

## 定义

```csharp
public static float deltaTime;
```

## 示例

倒数计时器，按下按钮即可从 60 秒倒数，再次点击按钮可以暂停。

```csharp
using UnityEngine;
using UnityEngine.UI;

public class ExampleScript : MonoBehaviour
{
    public float timeStart = 60f;
    public Text textBox;
    public Text startBtnText;

    private bool _timerActive;

    private void Start()
    {
        textBox.text = timeStart.ToString("00");
    }

    private void Update()
    {
        if (!_timerActive) return;
        timeStart -= Time.deltaTime;
        textBox.text = timeStart <= 0 ? "Over" : timeStart.ToString("00");
    }

    public void TimerButton()
    {
        _timerActive = !_timerActive;
        startBtnText.text = _timerActive ? "Pause" : "Start";
    }
}
```

## 补充

### 应用

1. 使用每帧时间累加，来进行游戏计数。

2. 让运动的物体，在相同的时间内保持平均的速度进行运动（引入增量时间；将数值乘以 `Time.deltaTime` 后，，可使得此内人在 `Update()` 中执行时，无论游戏的帧率是多少，结果依然在分布上与时间有关。）