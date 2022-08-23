# Physics.CheckSphere

检测是否有任何碰撞体重叠在定义的球体上。

## 定义

```csharp
public static bool CheckSphere(
    Vector3 position,
    float radius,
    int layerMask = DefaultRaycastLayers,
    QueryTriggerInteraction queryTriggerInteraction = QueryTriggerInteraction.UseGlobal
);
```

## 参数

| 参数名                  | 类型                    | 必要 | 说明                                         |
| ----------------------- | ----------------------- | ---- | -------------------------------------------- |
| position                | Vector3                 | 是   | 球体中心坐标                                 |
| radius                  | float                   | 是   | 球体半径                                     |
| layerMask               | int                     | 否   | 层级蒙版，设定后只检测此层级中的物体是否相交 |
| queryTriggerInteraction | QueryTriggerInteraction | 否   | 指定该查询是否应该命中触发器                 |

## 示例

```csharp
using UnityEngine;

[RequireComponent(typeof(AudioSource))]
public class ExampleScript : MonoBehaviour
{
    private AudioSource _audioSource;
    private void Start()
    {
        _audioSource = GetComponent<AudioSource>();
    }

    private void Update()
    {
        
        if (Physics.CheckSphere(transform.position, 3.0f))
        {
            _audioSource.Play();
        }
    }
}
```