# NavMeshAgent.SetDestination

设置或更新目的地

## 定义

```csharp
public bool SetDestination (Vector3 target);
```

| 参数名    | 类型      | 必要  | 说明    |
|:------ |:------- |:--- |:----- |
| target | Vector3 | 是   | 目的地坐标 |

~~~admonish example title="示例"

```csharp
using UnityEngine;
using UnityEngine.AI;

public class ExampleScript : MonoBehaviour
{
    public NavMeshAgent myNavMeshAgent;
    public Camera myCamera;

    private void Start()
    {
        myNavMeshAgent = GetComponent<NavMeshAgent>();
    }

    private void Update()
    {
        if (Input.GetMouseButtonDown(0))
        {
            SetDestinationToMousePosition();
        }
    }

    private void SetDestinationToMousePosition()
    {
        var ray = myCamera.ScreenPointToRay(Input.mousePosition);
        if (Physics.Raycast(ray, out var hit))
        {
            myNavMeshAgent.SetDestination(hit.point);
        }
    }
}
```
~~~