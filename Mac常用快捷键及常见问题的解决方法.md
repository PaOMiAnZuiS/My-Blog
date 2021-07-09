---
layout: default

---

# Mac常用快捷键及常见问题的解决方法：

## 常用快捷键：

#### 截图篇：

Command + Shift + 3：截取当前整个屏幕，并保存到桌面

Command + Shift + Control + 3：截取当前整个屏幕，并复制到剪切板，可直接粘贴

Command + Shift + 4：截取所选框内屏幕，并保存到桌面

Command + Shift + Control + 4：截取所选框内屏幕，并复制到剪切板，可直接粘贴



Command + Shift + G：跳转至指定位置（可用于访问usr/local）



## 常见问题：

- **相信大家对这张图并不陌生，那么如何获取相应权限呢？**

  

  ![image-20210708163706862](./resource/img/无权限.png)

  1. 在当前文件夹位置打开终端
  
  2. 在终端中输入 

     ```
     sudo chmod 775 filename
     ```
  
     (filename就是文件夹或者文件的名字)
  
  现在就有权限打开该文件夹了。

[back](./)

