# Rigidbody.AddForce

对刚体施加力

## 定义

| 参数名 | 类型      | 必要 | 说明                                                         |
| ------ | --------- | ---- | ------------------------------------------------------------ |
| force  | Vector3   | 是   | 世界坐标下表示力方向和大小的矢量                             |
| mode   | ForceMode | 否   | 施加力的模式，默认 `ForceMode.Force`<br />`ForceMode.Force`：利用刚体的质量向刚体添加一个连续的力<br />`ForceMode.Acceleration`：向刚体添加一个连续的加速度，忽略它的质量<br />`ForceMode.Impulse`：利用刚体的质量向刚体添加一个瞬时的力<br />`ForceMode.VelocityChange`：给刚体添加一个瞬时的加速度，忽略它的质量 |

