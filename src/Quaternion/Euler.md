# Quaternion.Euler

将欧拉角转换为四元数

## 定义

```csharp
public static Quaternion Euler (float x, float y, float z);
```

| 参数名 | 类型    | 必要  | 说明      |
|:--- |:----- |:--- |:------- |
| x   | float | 是   | X 轴旋转度数 |
| y   | float | 是   | Y 轴旋转度数 |
| z   | float | 是   | Z 轴旋转度数 |

```csharp
public static Quaternion Euler (Vector euler);
```

| 参数名   | 类型      | 必要  | 说明                 |
|:----- |:------- |:--- |:------------------ |
| euler | Vector3 | 是   | 表示 X、Y、Z 三轴旋转度数的向量 |

```admonish
```csharp
using UnityEngine;

public class Example : MonoBehaviour
{
    private void Start()
    {
        var rotationX = 0;
        var rotationY = 30;
        var rotationZ = 0;
        var rotationVector = new Vector3(rotationX, rotationY, rotationZ);

        var rotation = Quaternion.Euler(rotationX, rotationY, rotationZ);
        var rotation = Quaternion.Euler(rotationVector);
    }
}
```