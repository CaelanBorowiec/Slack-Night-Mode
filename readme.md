
# Slack Night Mode (tweaked)

Clone / Fork of [laCour/slack-night-mode](https://github.com/laCour/slack-night-mode) with fixes for minor things that annoy me.

## Changes

- [ ] Fix white gradient at the bottom of code boxes

## Notes

### How to enable Slack Dev Tools
**Powershell:**

    [System.Environment]::SetEnvironmentVariable('SLACK_DEVELOPER_MENU', 'true', 'Process')
    & $env:LOCALAPPDATA\slack\slack.exe
