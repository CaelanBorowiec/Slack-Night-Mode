

# Slack Night Mode (tweaked)

Clone / Fork of [laCour/slack-night-mode](https://github.com/laCour/slack-night-mode) with fixes for minor things that annoy me.

## Changes

- [x] Fix white gradient at the bottom of code boxes

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
