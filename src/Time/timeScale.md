# Time.timeScale

时间流逝速度缩放。

默认为 `1`，大于 `1` 加速，小于 `1` 减速，`0` 表示暂停，负值被忽略。

可用于慢动作效果或加速效果。

## 定义

```csharp
public static float timeScale;
```

## 示例

对 [Time.deltaTime](./deltaTime.md) 中示例的补充，添加了一个滑块控制时间的流逝速度。

```csharp
using UnityEngine;
using UnityEngine.UI;

public class ExampleScript : MonoBehaviour
{
    public float timeStart = 60f;
    public Text textBox;
    public Text startBtnText;
    public Slider timeScaleSlider;

    private bool _timerActive;

    private void Start()
    {
        textBox.text = timeStart.ToString("00");
        timeScaleSlider.minValue = 0.5f;
        timeScaleSlider.maxValue = 2;
        timeScaleSlider.value = 1;
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

    public void TimeScaleSliderChanged()
    {
        Time.timeScale = timeScaleSlider.value;
    }
}
```