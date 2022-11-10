# GameObject.AddComponent

向游戏对象（`GameObject`）添加组件

## 定义

```csharp
public Component AddComponent(string className);
```

| 参数名       | 类型     | 必要  | 说明   |
|:--------- |:------ |:--- |:---- |
| className | string | 是   | 组件类名 |

```csharp
public Component AddComponent(Type componentType);
```

| 参数名           | 类型   | 必要  | 说明   |
|:------------- |:---- |:--- |:---- |
| componentType | Type | 是   | 组件类型 |

```cs
public T AddComponent<T>();
```

| 参数名 | 类型  | 必要  | 说明   |
|:--- |:--- |:--- |:---- |
| T   | 泛型  | 是   | 组件类型 |
