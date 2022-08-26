# Transform.Rotate

旋转物体

## 定义

```csharp
public void Rotate(Vector3 eulers, Space relativeTo = Space.Self);
```

| 参数名     | 类型    | 必要 | 说明                                                   |
| ---------- | ------- | ---- | ------------------------------------------------------ |
| eulers     | Vector3 | 是   | 表示旋转的欧拉角                                       |
| relativeTo | Space   | 否   | 相对局部坐标或世界坐标<br />默认 `Space.Self` 局部坐标 |

```csharp
public void Rotate(float xAngle, float yAngle, float zAngle, Space relativeTo = Space.Self);
```

| 参数名     | 类型  | 必要 | 说明                                                   |
| ---------- | ----- | ---- | ------------------------------------------------------ |
| xAngle     | float | 是   | X 轴旋转角度                                           |
| yAngle     | float | 是   | Y 轴旋转角度                                           |
| zAngle     | float | 是   | Z 轴旋转角度                                           |
| relativeTo | Space | 否   | 相对局部坐标或世界坐标<br />默认 `Space.Self` 局部坐标 |

```csharp
public void Rotate(Vector3 axis, float angle, Space relativeTo = Space.Self);
```

| 参数名     | 类型    | 必要 | 说明                                                   |
| ---------- | ------- | ---- | ------------------------------------------------------ |
| axis       | Vector3 | 是   | 旋转所绕轴                                             |
| angle      | float   | 是   | 旋转角度                                               |
| relativeTo | Space   | 否   | 相对局部坐标或世界坐标<br />默认 `Space.Self` 局部坐标 |

## 示例

