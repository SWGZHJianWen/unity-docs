# CharacterController.SimpleMove

传入表示各方向移动**速度**的 Vector3 类型参数 `speed`，使物体移动。

其中 Y 轴会被忽略，重力自动应用。

返回角色物体是否在地面上。

## 定义

```csharp
public bool SimpleMove(Vector3 speed);
```

| 参数名   | 类型      | 必要  | 说明                             |
|:----- |:------- |:--- |:------------------------------ |
| speed | Vector3 | 是   | 各方向移动速度，单位为 `units/s`，Y 轴会被忽略。 |

## 示例

简单的人物控制器，左右键旋转，前后键移动。

```csharp
using UnityEngine;

[RequireComponent(typeof(CharacterController))]
public class ExampleScript : MonoBehaviour
{
    public float moveSpeed = 2.0f; // 移动速度
    public float rotateSpeed = 2.0f; // 旋转速度

    private CharacterController _controller;

    private void Start()
    {
        _controller = GetComponent<CharacterController>();
    }

    private void Update()
    {
        // 旋转
        transform.Rotate(0, Input.GetAxis("Horizontal") * rotateSpeed, 0);

        // 前进后退
        var forward = transform.TransformDirection(Vector3.forward);
        var curSpeed = moveSpeed * Input.GetAxis("Vertical");
        _controller.SimpleMove(forward * curSpeed);
    }
}
```