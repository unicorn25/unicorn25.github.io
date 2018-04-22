---
layout: post
title: Tips of UnityEditor.EditorWindow
date: 2018-4-22
author: Sam
---


### 前言
本文默认讲的是 Unity3D 中，关于 UnityEditor.EditorWindow 的编码技巧。

---
### Tips

1. 进度条

```
//进度条展示
string s = progress * 100 + "%";
EditorUtility.DisplayProgressBar("进度", s, progress);

//加载完毕，记得关闭进度条（重要）
EditorUtility.ClearProgressBar();
```

2. EditorWindow 窗口大小设置

```
EditorWindow ew = EditorWindow.GetWindow(typeof(FightCompareEditor));
ew.minSize = new Vector2(700, 900);
ew.maxSize = new Vector2(800, 1000);
```

3. label字体颜色、字体大小设置

```
var _labelStyle = new GUIStyle(EditorStyles.label);
_labelStyle.normal.textColor = Color.red;
_labelStyle.fontSize = 20;

GUILayout.Label("第一步", _labelStyle);
```

4. 画一条水平的虚线

```
void drawline(Color c)
{
    _colorStyle.normal.textColor = c;
    int len = Screen.width / 6;

    EditorGUILayout.BeginHorizontal();

    for (int i = 0; i < len; i++)
        GUILayout.Label("┅", _colorStyle);

    EditorGUILayout.EndHorizontal();
}
```

5. 异步日志打印

```
class Logger
{
    string _log = null;
    uint _timeCount = 0;

    Color _color = Color.black;
    readonly GUIStyle _style = new GUIStyle(EditorStyles.boldLabel);

    object _locker = new object();

    /// <summary>
    /// invoke in OnGUI
    /// </summary>
    public void showUILog()
    {
        if (_log != null)
        {
            _style.normal.textColor = _color;
            GUILayout.Label(_log, _style);

            if (_timeCount++ > 500) _log = null;
        }
    }

    public void Log(string log)
    {
        Log(log, Color.black);
    }

    public void Log(string log, Color cc)
    {
        lock (_locker)
        {
            _log = log;
            _color = cc;
            _timeCount = 0;
        }
    }
}
```

