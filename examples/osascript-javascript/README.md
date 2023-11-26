# osascript Javascript (MacOS)

```
// osascript -e 'on run argv' \
//           -e 'do shell script (item 1 of argv) with administrator privileges' \
//           -e 'end run' \
//           "$jre $args"
```

AppleScript Translates to Js most time with camelHumpCase

```
// #!/usr/bin/osascript -l JavaScript

const app = Application.currentApplication();
/**
If you look in the StandardAdditions.sdef.

Menubar menu: Windows -> Library
Double click on: StandardAdditions
Change the dropdown to Javascript.
You will see that many of the script command change to the camelHump syntax
 */
app.includeStandardAdditions = true;

app.doShellScript('ls',{administratorPrivileges:true})

// var Safari = new Application("/Applications/Safari.app");

Safari.activate();
Safari.windows[0].currentTab = Safari.windows[0].tabs[Safari.windows[0].tabs.push(Safari.Tab({url:"data:text/html;"}))];
Safari.windows[0].currentTab.doJavaScript("");

// const terminal = new Application("/Applications/Safari.app");
// terminal.activate();
// // terminal.execCommand()
// // terminal.script()
```
