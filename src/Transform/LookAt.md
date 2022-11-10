# Transform.LookAt

面向某一物体或坐标（旋转变换，使向前矢量指向 `target` 或者 `worldPosition`）

## 定义

```csharp
public void LookAt(Transform target, Vector3 worldUp = Vector3.up);
```

| 参数名     | 类型        | 必要  | 说明                 |
|:------- |:--------- |:--- |:------------------ |
| target  | Transform | 是   | 指向的对象              |
| worldUp | Vector3   | 否   | 指定向上方向的向量，默认世界 Y 轴 |

```csharp
public void LookAt (Vector3 worldPosition, Vector3 worldUp = Vector3.up);
```

| 参数名           | 类型        | 必要  | 说明                 |
|:------------- |:--------- |:--- |:------------------ |
| worldPosition | Transform | 是   | 要对准的点              |
| worldUp       | Vector3   | 否   | 指定向上方向的向量，默认世界 Y 轴 |

## 示例

相机看向物体：

```csharp
using UnityEngine;


public class ExampleClass : MonoBehaviour
{
    public Transform target;

    private void Update()
    {
        // 旋转相机，使其每帧都看向 target
        transform.LookAt(target);

        // 同上，但设置向上方向的向量为 Vector3.left，相机将会被转向侧面
        transform.LookAt(target, Vector3.left);
    }
}
```

看向某一点：

```csharp
using UnityEngine;


public class ExampleClass : MonoBehaviour
{
    public Transform target;

    private void Update()
    {
        // 看向世界座标系中的 (0, 0, 0)
        transform.LookAt(Vector3.zero);
    }
}
```