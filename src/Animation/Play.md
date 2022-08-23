# Animation.Play

## 定义

```csharp
public bool Play (PlayMode mode= PlayMode.StopSameLayer);
```

```csharp
public bool Play (string animation, PlayMode mode= PlayMode.StopSameLayer);
```

## 参数

| 参数名    | 类型     | 必要 | 说明                                                         |
| --------- | -------- | ---- | ------------------------------------------------------------ |
| animation | string   | 否   | 动画名称，不指定则播放默认动画                               |
| mode      | PlayMode | 否   | 播放模式，默认为 `StopSameLayer`<br>`StopSameLayer`：播放前停止在相同层启动的所有动画<br>`StopAll`：播放前x停止使用此组件启动的所有动画 |

