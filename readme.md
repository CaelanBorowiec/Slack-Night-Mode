



# Slack Night Mode (tweaked)

Clone / Fork of [laCour/slack-night-mode](https://github.com/laCour/slack-night-mode) to make it more purple and add fixes for minor things that annoy me.

## Changes

- [x] Fix white gradient at the bottom of code boxes
- [x] Add purple border over the About panel
- [x] Changed hamburger menu to purple
- [x] Changed links to light purple
- [x] Updated day dividers to purple

## Setup
### Slack v4
[Instructions](https://www.reddit.com/r/Slack/comments/cdonno/is_there_a_working_dark_theme_for_slack_400_on/eu4vqnv/) via Reddit user fadenrv:
1. Install [7-Zip](https://www.7-zip.org/), and [Asar7z](http://www.tc4shell.com/en/7zip/asar/).
2. Exit Slack fully.
3. Open `%LocalAppData%\slack\app-4.0.0\resources\app.asar` with 7-Zip.
4. Edit `\dist\ssb-interop.bundle.js` to add the following code:
```javascript
document.addEventListener('DOMContentLoaded', function() {    
  fetch('https://raw.githubusercontent.com/CaelanBorowiec/Slack-Night-Mode/dev/css/raw/black.css')    
  .then(function(response) {
    return response.text();
  })
  .then(function(css) {
    const style = document.createElement('style');
    style.innerHTML = css;
    document.head.appendChild(style);
  });
});
document.addEventListener('DOMContentLoaded', function() {
  $.ajax({
    url: 'https://raw.githubusercontent.com/CaelanBorowiec/Slack-Night-Mode/dev/css/raw/black.css',
    success: function(css) {
      $("<style></style>").appendTo('head').html(css);
    }
  });
});
```
5. Finally save ssb-interop.bundle.js and update it in the archive.
6. Start Slack.

### Slack v3
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
