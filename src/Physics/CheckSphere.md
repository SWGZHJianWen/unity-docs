# Physics.CheckSphere

检测是否有任何碰撞体重叠在定义的**球体**上 

## 定义

```csharp
public static bool CheckSphere(
    Vector3 position,
    float radius,
    int layerMask = DefaultRaycastLayers,
    QueryTriggerInteraction queryTriggerInteraction = QueryTriggerInteraction.UseGlobal
);
```

| 参数名                     | 类型                      | 必要  | 说明                                                                                                                                                                                                                |
|:----------------------- |:----------------------- |:--- |:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| position                | Vector3                 | 是   | 球体中心坐标                                                                                                                                                                                                            |
| radius                  | float                   | 是   | 球体半径                                                                                                                                                                                                              |
| layerMask               | int                     | 否   | 层级蒙版，设定后只检测此层级中的物体是否相交                                                                                                                                                                                            |
| queryTriggerInteraction | QueryTriggerInteraction | 否   | 指定该查询是否触发触发器，默认 `QueryTriggerInteraction.UseGlobal`<br />`QueryTriggerInteraction.UseGlobal`：使用 `Physics.queriesHitTriggers` 设置<br />`QueryTriggerInteraction.Ignore`：忽略<br />`QueryTriggerInteraction.Colide`：触发 |

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