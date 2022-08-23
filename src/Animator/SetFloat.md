# Animator.SetFloat

设置浮点参数。

## 定义

```csharp
public void SetFloat(string name, float value, float dampTime, float deltaTime);
```

```csharp
public void SetFloat(int id, float value, float dampTime, float deltaTime);
```

## 参数

| 参数名    | 类型   | 必要             | 说明                 |
| --------- | ------ | ---------------- | -------------------- |
| name      | string | 与 `id` 二选一   | 参数名称             |
| id        | int    | 与 `name` 二选一 | 参数 ID              |
| value     | float  | 是               | 新的参数值           |
| dampTime  | float  | 否               | 阻尼器总时间         |
| deltaTime | float  | 否               | 基于阻尼器的增量时间 |
