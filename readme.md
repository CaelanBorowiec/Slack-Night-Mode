


# Slack Night Mode (tweaked)

Clone / Fork of [laCour/slack-night-mode](https://github.com/laCour/slack-night-mode) with fixes for minor things that annoy me.

## Changes

- [x] Fix white gradient at the bottom of code boxes

## Setup
On Windows, edit
`%LocalAppData%\slack\app-3.4.3\resources\app.asar.unpacked\src\static\ssb-interop.js`
and add the following at the bottom of the file:
```javascript
document.addEventListener('DOMContentLoaded', function () {
   $.ajax({
      url: 'https://raw.githubusercontent.com/CaelanBorowiec/Slack-Night-Mode/dev/css/raw/black.css',
      success: function (css) {
         $("<style></style>").appendTo('head').html(css);
      }
   });
});

```

## Notes

### Enable Slack Dev Tools
```powershell
# Powershell
[System.Environment]::SetEnvironmentVariable('SLACK_DEVELOPER_MENU', 'true', 'Process')
& $env:LOCALAPPDATA\slack\slack.exe

```

### Open Slack Dev Tools
* Control + Alt + I (Windows)
* Cmd + Alt + I (MacOS)
