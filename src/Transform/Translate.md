# Transform.Translate

改变物体位置

## 定义

```csharp
public void Translate(Vector3 translation, Space relativeTo = Space.Self);
```

| 参数名         | 类型      | 必要  | 说明                                                                      |
|:----------- |:------- |:--- |:----------------------------------------------------------------------- |
| translation | Vector3 | 是   | 移动方向和大小                                                                 |
| relativeTo  | Space   | 否   | 相对的坐标系，默认 `Space.Self`<br />`Space.Self`：局部坐标系<br />`Space.World`：世界坐标系 |

```csharp
public void Translate(float x, float y, float z, Space relativeTo = Space.Self);
```

| 参数名        | 类型    | 必要  | 说明                                                                      |
|:---------- |:----- |:--- |:----------------------------------------------------------------------- |
| x          | float | 是   | X 轴移动大小                                                                 |
| y          | float | 是   | Y 轴移动大小                                                                 |
| z          | float | 是   | Z 轴移动大小                                                                 |
| relativeTo | Space | 否   | 相对的坐标系，默认 `Space.Self`<br />`Space.Self`：局部坐标系<br />`Space.World`：世界坐标系 |

## 示例

指定向量进行移动

```csharp
using UnityEngine;
using System.Collections;


public class ExampleClass : MonoBehaviour
{
    private void Update()
    {
        // 让物体沿自身 z 轴移动，每秒一个单位长度
        transform.Translate(Vector3.forward * Time.deltaTime);

        // 让物体沿世界方向向上移动，每秒一个单位长度
        transform.Translate(Vector3.up * Time.deltaTime, Space.World);
    }
}
```

指定各轴大小进行移动

```csharp
using UnityEngine;
using System.Collections;


public class ExampleClass : MonoBehaviour
{
    private void Update()
    {
        // 让物体沿自身 z 轴移动，每秒一个单位长度
        transform.Translate(0, 0, Time.deltaTime);

        // 让物体沿世界方向向上移动，每秒一个单位长度
        transform.Translate(0, Time.deltaTime, 0, Space.World);
    }
}
```

除了 `Space.Self` 和 `Spcae.World` 还可以使用例如 `Camera.main.transform` 来实现相对座标系的移动。

```csharp
using UnityEngine;
using System.Collections;


public class ExampleClass : MonoBehaviour
{
    private void Update()
    {
        // 让物体向相机右侧移动，每秒一个单位长度
        transform.Translate(Time.deltaTime, 0, 0, Camera.main.Transform);
    }
}
```