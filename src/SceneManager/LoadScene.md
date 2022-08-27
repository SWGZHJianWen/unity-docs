# SceneManager.LoadScene

按照 Build Settings 中的名称或索引加载场景。

## 定义

```csharp
public static void LoadScene (int sceneBuildIndex, SceneManagement.LoadSceneMode mode= LoadSceneMode.Single);
```

| 参数名          | 类型          | 必要 | 说明                                                         |
| --------------- | ------------- | ---- | ------------------------------------------------------------ |
| sceneBuildIndex | int           | 是   | 场景的索引（在 `Build Settings` ）                           |
| mode            | LoadSceneMode | 否   | 加载场景的方式，默认为单模式<br>单模式（销毁当前场景）：`LoadSceneMode.Single`<br>附加模式（不销毁当前场景）：`LoadSceneMode.Additive` |

```csharp
public static void LoadScene (string sceneName, SceneManagement.LoadSceneMode mode= LoadSceneMode.Single);
```

| 参数名    | 类型          | 必要 | 说明                                                         |
| --------- | ------------- | ---- | ------------------------------------------------------------ |
| sceneName | string        | 是   | 场景的名称或路径                                             |
| mode      | LoadSceneMode | 否   | 加载场景的方式，默认为单模式<br>单模式（销毁当前场景）：`LoadSceneMode.Single`<br>附加模式（不销毁当前场景）：`LoadSceneMode.Additive` |

```csharp
public static SceneManagement.Scene LoadScene (int sceneBuildIndex, SceneManagement.LoadSceneParameters parameters);
```

| 参数名          | 类型                | 必要 | 说明                               |
| --------------- | ------------------- | ---- | ---------------------------------- |
| sceneBuildIndex | int                 | 是   | 场景的索引（在 `Build Settings` ） |
| parameters      | LoadSceneParameters | 是   | 用于加载场景的各种参数             |

```csharp
public static SceneManagement.Scene LoadScene (string sceneName, SceneManagement.LoadSceneParameters parameters);
```

| 参数名          | 类型                | 必要 | 说明                   |
| --------------- | ------------------- | ---- | ---------------------- |
| sceneBuildIndex | int                 | 是   | 场景的名称或路径       |
| parameters      | LoadSceneParameters | 是   | 用于加载场景的各种参数 |

## 示例
