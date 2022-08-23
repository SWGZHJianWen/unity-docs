# Animator.SetBool

设置布尔参数。

## 定义

```csharp
public void SetBool(string name, bool value);
```

```csharp
public void SetBool(int id, bool value);
```

## 参数

| 参数名 | 类型   | 必要             | 说明       |
| ------ | ------ | ---------------- | ---------- |
| name   | string | 与 `id` 二选一   | 参数名称   |
| id     | int    | 与 `name` 二选一 | 参数 ID    |
| value  | bool   | 是               | 新的参数值 |
