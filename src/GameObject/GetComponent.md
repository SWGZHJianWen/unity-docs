# GameObject.GetComponent

返回游戏对象（`GameObject`）的第一个指定类型组件，如果没有则返回 `null`。

## 定义

```csharp
public Component GetComponent(Type type);
```

| 参数名 | 类型 | 必要 | 说明             |
| ------ | ----- | ---- | ---------------- |
| type   | Type  | 是  | 要检索的组件类型 |


```csharp
public Component GetComponent(string type);
```

| 参数名 | 类型 | 必要 | 说明             |
| ------ | ----- | ---- | ---------------- |
| type   | string | 是  | 要检索的组件类型 |

```csharp
public T GetComponent<T>();
```

泛型版本

## 示例

```csharp
```

