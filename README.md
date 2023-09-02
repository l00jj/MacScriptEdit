# MacScriptEdit

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
