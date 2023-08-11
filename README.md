# mic-mutebar

This app show microphone status as simple bar.

https://user-images.githubusercontent.com/19714/143683255-60b38e79-803d-4a6a-802c-09d35c3b9f28.mp4

This bar can be moved to anywhere.

## Installation

1. Download [latest binary](https://github.com/azu/mic-mutebar/releases/latest)
2. Open app

:warning: This app is not signed. So, OS show warning about it.

Additional installation steps on macOS:

1. Select `mic-mutebar.app`
2. Open context menu and Click "Open"

## Usage

When microphone is muted:

![](./docs/img/muted.png)

When microphone is inputing:

![](./docs/img/inputing.png)

## Tips

### Toggle mute/unmute

You can toggle mute/unmute by AppleScript.

```applescript
set micVolume to toggleMic()
display notification micVolume with title "Mic"
tell application "mic-mutebar.app" to activate
return micVolume

on toggleMic()
	set inputVolume to input volume of (get volume settings)
	if inputVolume <= 5 then
		set inputVolume to 100
		set micVal to "🔈"
	else
		set inputVolume to 0
		set micVal to "🔇"
	end if
	set volume input volume inputVolume
	return micVal
end toggleMic
```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## License

MIT
