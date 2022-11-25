# Resources.Load

加载指定路径（资源文件夹中）的资产。

## 定义

```csharp
public static T Load(string path);
```

| 参数名  | 类型     | 必要  | 说明   |
|:---- |:------ |:--- |:---- |
| path | string | 是   | 资产路径 |

~~~admonish example title="示例"

```csharp
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    private void Start()
    {
        // 加载一个文本文件 (Assets/Resources/Text/textFile01.txt)
        var textFile = Resources.Load<TextAsset>("Text/textFile01");

        // 加载一个 JSON 文件 (Assets/Resources/Text/jsonFile01.json)
        var jsonTextFile = Resources.Load<TextAsset>("Text/jsonFile01");
        // 然后使用 JsonUtility.FromJson<T>() 来反序列化 JSON 文本文件

        // 加载一个材质 (Assets/Resources/Textures/texture01.png)
        var texture = Resources.Load<Texture2D>("Textures/texture01");

        // 加载一个精灵对象 (Assets/Resources/Sprites/sprite01.png)
        var sprite = Resources.Load<Sprite>("Sprites/sprite01");

        // 加载一段音频 (Assets/Resources/Audio/audioClip01.mp3)
        var audioClip = Resources.Load<AudioClip>("Audio/audioClip01");
    }
}
```
~~~

## 补充

~~~admonish info title="注意事项"
1. 用 `Resources` 加载的资源，只能位于 `Assets/Resources/` 文件夹下。
2. 传入路径用 `/` 表示子文件夹
3. `Resources` 加载资源的相关代码最好在打开场景时进行加载。
4. `Resources` 加载资源的方式时只读的，在游戏打包后就无法对文件内容进行修改。
5. 游戏打包导出时，`Resources` 目录下的文件，不论是否在游戏中使用，都会被打包到游戏中增加体积，因此应该尽量控制 `Resources` 目录下的文件数量
~~~