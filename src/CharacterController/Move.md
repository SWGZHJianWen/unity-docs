# CharacterController.Move

传入表示各方向移动**增量值**的 Vector3 类型参数 `motion`，使物体移动。

与 [SimpleMove](./SimpleMove.md) 不同的是，它是增量值而不是速度，且可以控制 Y 轴。

## 定义

```csharp
public CollisionFlags Move(Vector3 motion);
```

## 参数

| 参数名 | 类型    | 必要 | 说明                   |
| ------ | ------- | ---- | ---------------------- |
| motion | Vector3 | 是   | 各方向移动的绝对增量值 |

## 示例

一个简单的第一人称控制器

```csharp
using UnityEngine;

[RequireComponent(typeof(CharacterController))]
public class ExampleScript : MonoBehaviour
{
    public float moveSpeed = 2.0f; // 移动速度
    public float sensitivity = 2f; // 鼠标灵敏度
    
    private CharacterController _controller;
    private float _ySpeed;

    private void PlayerRotate()
    {
        var mouseX = Input.GetAxis("Mouse X") * sensitivity;
        transform.Rotate(Vector3.up * mouseX);
    }

    private void PlayerMove()
    {
        var motion =
            transform.right * Input.GetAxis("Horizontal") +
            transform.forward * Input.GetAxis("Vertical");
        motion *= moveSpeed;

        _controller.Move(motion * Time.deltaTime);
    }
    
    private void Start()
    {
        _controller = GetComponent<CharacterController>();
    }

    private void Update()
    {
        PlayerRotate();
        PlayerMove();
    }
}
```
