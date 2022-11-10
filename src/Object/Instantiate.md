# Object.Instantiate

克隆 `original` 对象并返回此克隆。

## 定义

```csharp
public static Object Instantiate(
    Object original,
    Transform parent,
    bool instantiateInWorldSpace
);
```

| 参数名                     | 类型        | 必要  | 说明                               |
|:----------------------- |:--------- |:--- |:-------------------------------- |
| original                | Object    | 是   | 要克隆的现有对象                         |
| parent                  | Transform | 否   | 新对象的父对象                          |
| instantiateInWorldSpace | bool      | 否   | `true`：相对于世界空间<br>`false`：相对于父对象 |

```csharp
public static Object Instantiate(
    Object original,
    Vector3 position,
    Quaternion rotation,
    Transform parent
);
```

| 参数名      | 类型         | 必要  | 说明       |
|:-------- |:---------- |:--- |:-------- |
| original | Object     | 是   | 要克隆的现有对象 |
| position | Vector3    | 是   | 新对象的位置   |
| rotation | Quaternion | 是   | 新对象的旋转   |
| parent   | Transform  | 否   | 新对象的父对象  |

## 示例

```csharp
using UnityEngine;

public class Example : MonoBehaviour
{
    public GameObject prefab;
    void Start()
    {
        for (var i = 0; i < 10; i++)
        {
            Instantiate(prefab, new Vector3(i * 2.0f, 0, 0), Quaternion.identity);
        }
    }
}
```