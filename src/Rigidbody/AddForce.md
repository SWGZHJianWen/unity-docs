# Rigidbody.AddForce

对刚体施加力

## 定义

```csharp
public void AddForce (Vector3 force, ForceMode mode = ForceMode.Force);
```

| 参数名   | 类型        | 必要  | 说明                                                                                                                                                                                                                        |
|:----- |:--------- |:--- |:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| force | Vector3   | 是   | 世界坐标下表示力方向和大小的矢量                                                                                                                                                                                                          |
| mode  | ForceMode | 否   | 施加力的模式，默认 `ForceMode.Force`<br />`ForceMode.Force`：利用刚体的质量向刚体添加一个连续的力<br />`ForceMode.Acceleration`：向刚体添加一个连续的加速度，忽略它的质量<br />`ForceMode.Impulse`：利用刚体的质量向刚体添加一个瞬时的力<br />`ForceMode.VelocityChange`：给刚体添加一个瞬时的加速度，忽略它的质量 |

```csharp
public void AddForce (float x, float y, float z, ForceMode mode = ForceMode.Force);
```

| 参数名  | 类型        | 必要  | 说明                                                                                                                                                                                                                        |
|:---- |:--------- |:--- |:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| x    | float     | 是   | 沿世界 x 轴的力大小                                                                                                                                                                                                               |
| y    | float     | 是   | 沿世界 y 轴的力大小                                                                                                                                                                                                               |
| z    | float     | 是   | 沿世界 z 轴的力大小                                                                                                                                                                                                               |
| mode | ForceMode | 否   | 施加力的模式，默认 `ForceMode.Force`<br />`ForceMode.Force`：利用刚体的质量向刚体添加一个连续的力<br />`ForceMode.Acceleration`：向刚体添加一个连续的加速度，忽略它的质量<br />`ForceMode.Impulse`：利用刚体的质量向刚体添加一个瞬时的力<br />`ForceMode.VelocityChange`：给刚体添加一个瞬时的加速度，忽略它的质量 |

## 示例

使用表示力方向和大小的矢量：

```csharp
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    public Rigidbody myRigidbody;
    public float myThrust = 20f;

    private void Start()
    {
        myRigidbody = GetComponent<Rigidbody>();
    }

    void FixedUpdate()
    {
        if (Input.GetButton("Jump"))
        {
            // 对这个物体施加向上的力
            myRigidbody.AddForce(transform.up * myThrust);
        }
    }
}
```

指定 `x`、`y`、`z`各轴的大小：

```csharp
using UnityEngine;

public class Example : MonoBehaviour
{
    public Rigidbody myRigidbody;
    public float myThrust = 10f;

    private void Start()
    {
        myRigidbody = GetComponent<Rigidbody>();

        // 给物体一个沿 z 轴方向的瞬时力
        myRigidbody.AddForce(0, 0, myThrust, ForceMode.Impulse);
    }
}
```

   
