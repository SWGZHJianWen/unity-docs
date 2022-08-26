# Transform.Translate

改变物体位置

## 定义

```csharp
public void Translate(Vector3 translation, Space relativeTo = Space.Self);
```

| 参数名      | 类型    | 必要 | 说明                                                   |
| ----------- | ------- | ---- | ------------------------------------------------------ |
| translation | Vector3 | 是   | 移动方向和大小                                         |
| relativeTo  | Space   | 否   | 相对局部坐标或世界坐标<br />默认 `Space.Self` 局部坐标 |

```csharp
public void Translate(float x, float y, float z, Space relativeTo = Space.Self);
```

| 参数名     | 类型  | 必要 | 说明                                                   |
| ---------- | ----- | ---- | ------------------------------------------------------ |
| x          | float | 是   | X 轴移动大小                                           |
| y          | float | 是   | Y 轴移动大小                                           |
| z          | float | 是   | Z 轴移动大小                                           |
| relativeTo | Space | 否   | 相对局部坐标或世界坐标<br />默认 `Space.Self` 局部坐标 |

