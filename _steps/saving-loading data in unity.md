---
layout: post
title: Unity3D 本地持久化存取数据方法
date: 2018-03-08
author: Sam
---


### Unity3D 本地持久化存取数据方法 

* 存：将数据用 JsonUtility、Newtonsoft.Json 等格式化为 string(json)，然后存入到 PlayerPrefs
* 取：逆操作**存**即可。

**注意：**

>* PlayerPrefs 只支持int，string，float三种数据类型的写读，因此宜存取简单的游戏数据，如玩家设置信息等。
>* 详见 [PlayerPrefs 官方文档](https://docs.unity3d.com/ScriptReference/PlayerPrefs.html)

### 示例：

**Data class**

```
[Serializable]
public class Save
{
    public List<int> ID = new List<int>();
    public List<int> Amounts = new List<int>();
    public int extra = 0;
    public float highScore = 0;
}
```

**Save Data**

```
void Save()
{
    Save saveData = new Save();
    saveData.extra = 99;
    saveData.highScore = 40;

    //Convert to Json
    string jsonData = JsonUtility.ToJson(saveData);
    //Save Json string
    PlayerPrefs.SetString("MySettings", jsonData);
    PlayerPrefs.Save();
}
```

**Load Data**

```
void Load()
{
    //Load saved Json
    string jsonData = PlayerPrefs.GetString("MySettings");
    //Convert to Class
    Save loadedData = JsonUtility.FromJson<Save>(jsonData);

    //Display saved data
    Debug.Log("Extra: " + loadedData.extra);
    Debug.Log("High Score: " + loadedData.highScore);
}
```