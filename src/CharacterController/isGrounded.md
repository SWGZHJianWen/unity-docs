# CharacterController.isGrounded

判断物体是否在地面上，但只有在移动中才进行检测。（在最后的移动中是否触地）

## 定义

```csharp
public bool isGrounded;
```

## 示例

这是对 [CharacterController.Move](./Move.md) 中示例的补充，添加了跳跃功能。

由于使用 [Move](./Move.md) 而不是 [SimpleMove](./SimpleMove.md)，所以需要自己处理重力。

```csharp
using System;
using UnityEngine;

[RequireComponent(typeof(CharacterController))]
public class ExampleScript : MonoBehaviour
{
    public float moveSpeed = 2.0f; // 移动速度
    public float gravity = 9.8f; // 重力大小
    public float jumpHeight = 2f; // 跳跃高度
    public float sensitivity = 2f; // 鼠标灵敏度
    
    private CharacterController _controller;
    private float _ySpeed; // Y 轴速度

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
        
        // 跳跃
        switch (_controller.isGrounded)
        {
            case true when Input.GetKeyDown(KeyCode.Space):
                _ySpeed = (float) Math.Sqrt(2 * gravity * jumpHeight);
                break;
            case true:
                _ySpeed = 0;
                break;
            case false:
                _ySpeed -= gravity * Time.deltaTime; // 重力
                break;
        }
        motion += transform.up * _ySpeed;
        
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

## 其他

上述示例也许并不好用，因为 `isGround` 只有角色移动时（调用 `SimpleMove` 或 `Move`时）才会进行检测，并且 `CharacterController` 的 `Skin Width` 也会对其影响。

所以建议自己实现地面检测功能，方法有多种，其中使用