# MacScriptEdit

# 重要资料
[官方API](https://developer.apple.com/library/archive/releasenotes/InterapplicationCommunication/RN-JavaScriptForAutomation/Articles/Introduction.html)  

解决大部分疑难问题 [JXA-Cookbook](https://github.com/JXA-Cookbook/JXA-Cookbook)  

[一些例子](https://gist.github.com/heckj/5b7bb332463a762639e179a37ea3a216)  

# js如何检查UI子组件
https://stackoverflow.com/questions/33232154/javascript-automation-click-download-button-in-itunes/33274695#33274695
```
// Get an array of all UI elements in iTunes window.
uiElems = Application("System Events").applicationProcesses['iTunes']
           .windows[0].entireContents()

// Find all buttons whose description contains 'Get'.
btns = uiElems.filter(function(el) { 
  try {
    return el.role() == 'AXButton' 
           &&
           el.description().match(/\bGet\b/)
  } catch (e) {}
})

// Click on the 1st button found.
btns[0].click()
```


# js 如何获取Nams
https://stackoverflow.com/questions/26301681/listing-all-the-files-in-a-folder-using-javascript-for-automation-on-yosemite
```
set myPath to POSIX file "/usr"
tell application "Finder" to name of every item of item myPath
--> {"X11", "X11R6", "bin", "lib", "libexec", "local", "sbin", "share", "standalone"}

myPath = Path('/usr')
Application('Finder').folders.byName(myPath.toString()).items.name()
// Error -1728: Can't get object.
```

# js 如何获取指定属性
https://mikebian.co/scripting-macos-with-javascript-automation/

