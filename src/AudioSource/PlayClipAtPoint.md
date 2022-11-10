# AudioSource.PlayClipAtPoint

在世界空间中指定位置播放音频剪辑（`AudioClip`）

## 定义

```csharp
public static void PlayClipAtPoint (AudioClip clip, Vector3 position, float volume= 1.0F);
```

| 参数名   | 类型      | 必要 | 说明                     |
|:-------- |:--------- |:---- |:------------------------ |
| clip     | AudioClip | 是   | 要播放的音频剪辑         |
| position | Vector3   | 是   | 世界空间中发出声音的位置 |
| volume   | float     | 否   | 音量，默认 `1.0`         |

