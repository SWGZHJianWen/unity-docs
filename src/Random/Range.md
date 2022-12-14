# Random.Range

返回区间内一个随机数值。

`int` 类型时区间左闭右开，`float` 类型时区间左闭右闭。

## 定义

```csharp
public static int Range(int minInclusive, int maxInclusive);
```

| 参数名          | 类型  | 必要  | 说明  |
|:------------ |:--- |:--- |:--- |
| minInclusive | int | 是   | 最小值 |
| maxInclusive | int | 是   | 最大值 |

```csharp
public static float Range(float minInclusive, float maxInclusive);
```

| 参数名          | 类型    | 必要  | 说明  |
|:------------ |:----- |:--- |:--- |
| minInclusive | float | 是   | 最小值 |
| maxInclusive | float | 是   | 最大值 |


~~~admonish example title="示例"
点击按钮后，随机在 `([-10 ~ 10], 0, [-10 ~ 10])` 的位置生成物体

```csharp
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    public GameObject prefab;

    void OnGUI()
    {
        if (GUI.Button(new Rect(10, 10, 100, 50), "Instantiate!"))
        {
            var position = new Vector3(Random.Range(-10.0f, 10.0f), 0, Random.Range(-10.0f, 10.0f));
            Instantiate(prefab, position, Quaternion.identity);
        }
    }
}
```
~~~