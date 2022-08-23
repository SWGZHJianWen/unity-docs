# Animator.SetInteger

设置整型参数。

## 定义

```csharp
public void SetInteger(string name, int value);
```

```csharp
public void SetInteger(int id, int value);
```

## 参数

| 参数名 | 类型   | 必要             | 说明       |
| ------ | ------ | ---------------- | ---------- |
| name   | string | 与 `id` 二选一   | 参数名称   |
| id     | int    | 与 `name` 二选一 | 参数 ID    |
| value  | int    | 是               | 新的参数值 |
