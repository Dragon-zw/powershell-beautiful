# powershell-beautiful
配置一个漂亮的Windows Powershell 

前提条件需要 Windows Powershell 在 v7 版本以上。可以去相应的 GitHub 下载

相关链接：

https://aka.ms/PSWindows

https://github.com/PowerShell/PowerShell/releases/

```powershell
Install-Module oh-my-posh -Scope CurrentUser -SkipPublisherCheck
Install-Module posh-git -Scope CurrentUser

# 需要有管理员权限
Install-Module -Name PSReadLine -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck
# Install-Module : 找不到与参数名称“AllowPrerelease”匹配的参数。
# 解决方法：
Install-Module -Name PackageManagement -Repository PSGallery -Force
Install-Module -Name PowerShellGet -Repository PSGallery -Force
```

参考资料：https://ohmyposh.dev/docs

notepad.exe $PROFILE

设置 profile

```powershell
Import-Module posh-git
Import-Module oh-my-posh
Set-PoshPrompt -Theme robbyrussel
```

# 安装字体

```SH
# 安装字体的介绍
https://ohmyposh.dev/docs/installation/fonts

# 下载相应的字体压缩包进行解压即可
https://www.nerdfonts.com/font-downloads
# 再根据官网的引导步骤进行操作
```

基于CascadiaCode的一个Nerd Font的字体补充库，里面包括了很多图标，这里推荐使用它。

- [CascadiaCode.zip](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/CascadiaCode.zip)

![image](https://img2022.cnblogs.com/blog/375390/202207/375390-20220715220632146-6859336.png)

- 推荐下载完成之后，将 VSCode 软件的字体进行设置为 "CaskaydiaCove Nerd Font"，可以参考 VSCode 的配置文件内容

```json
{
  "redhat.telemetry.enabled": true,
  "explorer.confirmDragAndDrop": false,
  "liveServer.settings.donotShowInfoMsg": true,
  "code-runner.runInTerminal": true,
  "terminal.integrated.enableBell": true,
  "security.workspace.trust.untrustedFiles": "open",
  "editor.suggestSelection": "first",
  "vsintellicode.modify.editor.suggestSelection": "choseToUpdateConfiguration",
  "files.exclude": {
    "**/.classpath": true,
    "**/.project": true,
    "**/.settings": true,
    "**/.factorypath": true
  },
  "explorer.confirmDelete": false,
  "bracketPairColorizer.depreciation-notice": false,
  "vsicons.dontShowNewVersionMessage": true,
  "tabnine.experimentalAutoImports": true,
  "diffEditor.codeLens": true,
  "editor.fontFamily": "'CaskaydiaCove Nerd Font' ,'Cascadia Code' ,'Source Code Pro',Consolas, 'Courier New', monospace",
  "editor.fontLigatures": false,
  "files.autoSave": "afterDelay",
  "files.autoGuessEncoding": true,
  "workbench.list.smoothScrolling": true,
  "editor.cursorSmoothCaretAnimation": "on",
  "editor.smoothScrolling": true,
  "editor.cursorBlinking": "smooth",
  "editor.mouseWheelZoom": true,
  "editor.formatOnPaste": true,
  "editor.formatOnType": true,
  "editor.formatOnSave": true,
  "editor.wordWrap": "on",
  "editor.guides.bracketPairs": true,
  //"editor.bracketPairColorization.enabled": true, (此设置vscode在较新版本已默认开启)
  "editor.suggest.snippetsPreventQuickSuggestions": false,
  "editor.acceptSuggestionOnEnter": "smart",
  "editor.suggestSelection": "recentlyUsed",
  "window.dialogStyle": "custom",
  "debug.showBreakpointsInOverviewRuler": true,
  "terminal.integrated.enableMultiLinePasteWarning": false,
  "cSpell.language": "cn",
  "git.enableSmartCommit": true,
  "git.autofetch": true,
  "[python]": {
    "editor.formatOnType": true
  },
  "CodeGPT.query.language": "Chinese",
  "settingsSync.ignoredExtensions": [
    "ms-ceintl.vscode-language-pack-zh-hans"
  ],
  "window.commandCenter": false,
  "workbench.colorTheme": "Default Dark+ Experimental",
  "workbench.iconTheme": "material-icon-theme",
  "git.openRepositoryInParentFolders": "always",
  "editor.fontSize": 14
```




# 安装文件图标库

```powershell
Install-Module -Name Terminal-Icons -Repository PSGallery
```

# 使用图标

```powershell
Import-Module -Name Terminal-Icons
```

![image](https://img2022.cnblogs.com/blog/375390/202207/375390-20220715220824185-141637806.png)

# 命令行自动补全和提示

```powershell
Set-PSReadlineKeyHandler -Key Tab -Function MenuComplete
```
