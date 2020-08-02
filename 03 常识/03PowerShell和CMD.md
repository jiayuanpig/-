# cmd

## 用途
cmd是command的缩写.即命令提示符(CMD),可以运行DOS命令

Windows系统中给操作员在DOS窗口下对计算机进行一些文本式的操作或用于测试，调试计算机用


## 常见命令

- 使用上下方向键，翻看使用过的命令
- 补全功能:tab
- 要使用反斜杠'\'，不要使用正斜杠'/'
- 帮助查看DOS命令:help
- 查看命令的属性:命令 + /?
- 清除屏幕:cls

文件,路径问题：
- 若存在空格，应使用双引号将路径引起来
- 文件及目录名中不能包含下列任何字符：\ / : * ? " < > |
- 进入某盘，例如	D:
- 跳转到某一路径: cd + 路径名
- 查看目录文件:dir
- 创建/删除目录: md/rd 目录名
- 复制/移动文件:copy/move 路径\文件名 路径\文件名
- 删除文件(不能删目录):del 文件名

补充:
- 查看本机ip:ipconfig
- 测试网络是否畅通:ping ip


# PowerShell

PowerShell可以看作是cmd的升级版,PowerShell基于面向对象的，更为易用，可以说是分分钟秒杀cmd

PowerShell推出了一个功能强大的命令叫做cmdlet,所有的cmdlet命令都遵循动词-名词这样语法结构

- 查找powershell命令:get-command
- 查看命令的具体使用:Get-Help –Name 操作名
- 命令主要包括:get-,set-,write-

详细参考:[Windows PowerShell基本语法及常用命令](https://blog.csdn.net/Mr_Pang/article/details/50571866)



