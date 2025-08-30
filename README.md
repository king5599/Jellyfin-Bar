# Jellyfin-Media-Bar - 中文说明
## 闲鱼推广

如需NAS、影视库、服务器运维等问题解决，可在闲鱼搜索：**网络运维老师傅**  


**重要更新 — 目前仅维护全屏版，普通CSS版暂不更新（仍可用，待全屏版稳定后再考虑）。**

全屏版已适配多种屏幕尺寸，遇到显示问题请提交bug报告，附带设备型号及横竖屏信息。

鸣谢 [BobHasNoSoul](https://github.com/BobHasNoSoul) 的 [jellyfinfeatured](https://github.com/BobHasNoSoul/jellyfin-featured) 及 [SethBacon](https://forum.jellyfin.org/u-sethbacon)、[TedHinklater](https://github.com/tedhinklater) 的 [Jellyfin-Featured-Content-Bar](https://github.com/tedhinklater/Jellyfin-Featured-Content-Bar)。

本项目在原有基础上优化了代码、提升了加载速度和安全性。推荐配合 [Zombie主题](https://github.com/MakD/zombie-release) 使用。

> **安装前请备份你的 index.html 文件！**

---

## 使用方法

1. 下载本项目的 `index.html` 文件到本地目录。
2. 替换 Jellyfin 的 web 目录下的 `index.html` 文件。
   - Docker 用户可通过挂载本地目录实现：
     ```shell
     docker run -d \
       -v /你的本地目录/index.html:/jellyfin/jellyfin-web/index.html \
       ...其它参数...
       jellyfin/jellyfin
     ```
3. 强制刷新浏览器页面（Ctrl+Shift+R）两次。

---

## 自定义展示列表
！！未找到avatars，没有验证是否可行，目前只能随机
1. 在 `avatars` 文件夹下新建 `list.txt` 文件。
2. 第一行为列表名称。
3. 第二行起每行一个条目ID。例如：
   ```
   我的片单
   ItemID1
   ItemID2
   ItemID3
   ```
4. 保存后刷新页面即可生效。

---

## 卸载方法

恢复原始 `index.html` 文件或删除替换的内容即可。

---



---
# Jellyfin-Media-Bar - Now with Play Now Function

**IMP UPDATE — We have dropped support for the normal CSS version (for now). _(It still works, but there will be no further updates till the fullscreen mode is stabilized)_** 

The fullscreen version has a new look (in beta), and support for different screen sizes has been added. For any visual goof-ups, please open a bug report, including the device being used and whether it is encountered in portrait or landscape mode.


Thanks to the Man, the Legend [BobHasNoSoul](https://github.com/BobHasNoSoul) for his work on the [jellyfinfeatured](https://github.com/BobHasNoSoul/jellyfin-featured) and [SethBacon](https://forum.jellyfin.org/u-sethbacon) and [TedHinklater](https://github.com/tedhinklater) for their take on the [Jellyfin-Featured-Content-Bar](https://github.com/tedhinklater/Jellyfin-Featured-Content-Bar). 

Here I present my version with some code improvements, loading optimizations, and security enhancements. Works best with the [Zombie theme](https://github.com/MakD/zombie-release) (_Shameless Plug_ `@import url(https://cdn.jsdelivr.net/gh/MakD/zombie-release@latest/zombie_revived.css);`, visit the repo for more color schemes).


> <ins>**Before Installing, please take a backup of your index.html file**<ins>

<details>
<summary> Desktop Layout </summary>
  
![Jellyfin Desktop Layout](https://raw.githubusercontent.com/MakD/Jellyfin-Media-Bar/refs/heads/main/img/Jelly-Web%20-%20Fullscreen%20Mode.png)
  
</details>

<details>

<summary> Mobile Layout </summary>
  
![Jellyfin Mobile Layout](https://raw.githubusercontent.com/MakD/Jellyfin-Media-Bar/refs/heads/main/img/Jelly-Mobile-Fullscreen.png)

</details>


# Prepping the files
<details>
  
<summary>index.html</summary>

  1. Navigate to your `jellyfin-web` folder and search for the file index.html. (you can use any code editor, just remember to open with administrator privileges.
  2. Search for `</head>`
  3. Just before the `</head>`, plug the below code
```
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/king5599/Jellyfin-Bar@latest/slideshowpure.css" />
    <script async src="https://cdn.jsdelivr.net/gh/king5599/Jellyfin-Bar@latest/slideshowpure.js"></script>
```
</details>

And that is it. Hard refresh your web page (CTRL+Shift+R) twice, and Profit!

# Want a Custom List to be showcased instead of random items??

No worries this got you covered. 

## Steps

1. Create a `list.txt` file inside your `avatars` folder.
2. In line 1 give your list a name.
3. Starting line 2, paste the item IDs you want to be showcased, one ID per line. For Example :

```
Awesome Playlist Name
ItemID1
ItemID2
ItemID3
ItemID4
ItemID5
```
The next time it loads, it will display these items.

# Uninstall the Bar

<details>
  
<summary> Roll Back </summary>

Restore the `index.html` file / remove the lines added and you are good to go!!!

</details>


## License

[![Custom: DBAD License](https://img.shields.io/badge/License-Don't_Be_A_Dick-red)](LICENSE)


This project is licensed under a DBAD license prohibiting any commercial use or redistribution.  
All modifications must be contributed back to this repository.  
Attribution to the original author (MakD) is required in any use or derivative work.

Please take a look at the [LICENSE](LICENSE) file for full terms.
