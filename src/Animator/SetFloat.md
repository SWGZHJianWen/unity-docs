# Animator.SetFloat

设置浮点参数。

## 定义

```csharp
public void SetFloat(string name, float value, float dampTime, float deltaTime);
```

| 参数名    | 类型   | 必要             | 说明                 |
| --------- | ------ | ---------------- | -------------------- |
| name      | string | 是               | 参数名称             |
| value     | float  | 是               | 新的参数值           |
| dampTime  | float  | 否               | 阻尼器总时间         |
| deltaTime | float  | 否               | 基于阻尼器的增量时间 |


```csharp
public void SetFloat(int id, float value, float dampTime, float deltaTime);
```

| 参数名    | 类型   | 必要             | 说明                 |
| --------- | ------ | ---------------- | -------------------- |
| id        | int    | 是               | 参数 ID              |
| value     | float  | 是               | 新的参数值           |
| dampTime  | float  | 否               | 阻尼器总时间         |
| deltaTime | float  | 否               | 基于阻尼器的增量时间 |
