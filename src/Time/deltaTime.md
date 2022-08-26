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