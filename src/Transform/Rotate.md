# Transform.Rotate

旋转物体

## 定义

```csharp
public void Rotate(Vector3 eulers, Space relativeTo = Space.Self);
```

| 参数名        | 类型      | 必要  | 说明                                                                      |
|:---------- |:------- |:--- |:----------------------------------------------------------------------- |
| eulers     | Vector3 | 是   | 表示旋转的欧拉角                                                                |
| relativeTo | Space   | 否   | 相对的坐标系，默认 `Space.Self`<br />`Space.Self`：局部坐标系<br />`Space.World`：世界坐标系 |

```csharp
public void Rotate(float xAngle, float yAngle, float zAngle, Space relativeTo = Space.Self);
```

| 参数名        | 类型    | 必要  | 说明                                                                      |
|:---------- |:----- |:--- |:----------------------------------------------------------------------- |
| xAngle     | float | 是   | X 轴旋转角度                                                                 |
| yAngle     | float | 是   | Y 轴旋转角度                                                                 |
| zAngle     | float | 是   | Z 轴旋转角度                                                                 |
| relativeTo | Space | 否   | 相对的坐标系，默认 `Space.Self`<br />`Space.Self`：局部坐标系<br />`Space.World`：世界坐标系 |

```csharp
public void Rotate(Vector3 axis, float angle, Space relativeTo = Space.Self);
```

| 参数名        | 类型      | 必要  | 说明                                                                      |
|:---------- |:------- |:--- |:----------------------------------------------------------------------- |
| axis       | Vector3 | 是   | 旋转所绕轴                                                                   |
| angle      | float   | 是   | 旋转角度                                                                    |
| relativeTo | Space   | 否   | 相对的坐标系，默认 `Space.Self`<br />`Space.Self`：局部坐标系<br />`Space.World`：世界坐标系 |

## 示例

该示例代码创建了两个不同的立方体：红色立方体按照局部座标系 `Space.Self` 旋转；绿色立方体按照世界座标系 `Space.World` 旋转。

通过改变面板中的 `xAngle`、`yAngle`、`zAngle` 控制旋转角度。

```csharp
using UnityEngine;


public class ExampleScript : MonoBehaviour
{
    public float xAngle, yAngle, zAngle;

    private GameObject _cube1, _cube2;

    private void Awake()
    {
        _cube1 = GameObject.CreatePrimitive(PrimitiveType.Cube);
        _cube1.transform.position = new Vector3(0.75f, 0.0f, 0.0f);
        _cube1.transform.Rotate(90.0f, 0.0f, 0.0f, Space.Self);
        _cube1.GetComponent<Renderer>().material.color = Color.red;
        _cube1.name = "Self";

        _cube2 = GameObject.CreatePrimitive(PrimitiveType.Cube);
        _cube2.transform.position = new Vector3(-0.75f, 0.0f, 0.0f);
        _cube2.transform.Rotate(90.0f, 0.0f, 0.0f, Space.World);
        _cube2.GetComponent<Renderer>().material.color = Color.green;
        _cube2.name = "World";
    }

    private void Update()
    {
        cube1.transform.Rotate(xAngle, yAngle, zAngle, Space.Self);
        cube2.transform.Rotate(xAngle, yAngle, zAngle, Space.World);
    }
}
```