# iTorrent neo

An iOS torrent client with Files app support, updated for iPhone Duo.

> [!NOTE]
> iTorrent neo is a fork of [**iTorrent**](https://github.com/XITRIX/iTorrent) by [XITRIX](https://github.com/XITRIX) (Daniil Vinogradov). Nearly all of the app is their work. This fork is not affiliated with or endorsed by XITRIX. For the original app, official builds, and support, visit the [iTorrent repository](https://github.com/XITRIX/iTorrent). If you find the app useful, consider [supporting XITRIX on Patreon](https://www.patreon.com/xitrix).

## What's different in neo

- Built against the iOS 27.1 SDK and tested on iPhone Duo, folded and unfolded, in Split View and in landscape
- Its own bundle ID and app group, so it installs alongside the original iTorrent
- Build fixes for Xcode 27, using forks of [LibTorrent-Swift](https://github.com/enjoyerofslop/LibTorrent-Swift) and [MVVMFoundation](https://github.com/enjoyerofslop/MVVMFoundation)

## Features

From the original iTorrent:

- Background downloading
- Live Activity and Dynamic Island progress
- Built-in VLC player with AirPlay and Picture in Picture
- Sequential download, so you can watch while downloading
- Add torrents from the Share menu, magnet links, or a URL
- Store and share files through the Files app
- Choose which files in a torrent to download
- Download-finished notifications
- WebDAV server
- RSS feeds

Languages: English, German, Italian, Polish, Russian, Spanish, and Simplified Chinese.

## Building from source

There are no prebuilt releases of iTorrent neo yet.

Requirements: Xcode 27.1 with the iOS 27.1 SDK, and [Homebrew](https://brew.sh).

```bash
git clone --recurse-submodules https://github.com/enjoyerofslop/iTorrent-neo.git
cd iTorrent-neo
brew install boost cmake
./Submodules/LibTorrent-Swift/make.sh
```

Then:

1. Add a `GoogleService-Info.plist` from your own [Firebase](https://firebase.google.com) project at `iTorrent/Core/Assets/`. The build needs this file.
2. Open `iTorrent.xcworkspace`, not the `.xcodeproj`.
3. If you aren't building with the iTorrent neo team, set your own team under Signing & Capabilities, and change `APPLICATION_ID` in `iTorrent/Core/Assets/iTorrent.xcconfig` and the app group in the entitlements files.
4. Select the `iTorrent` scheme and build.

## Privacy

The app includes Firebase Analytics and Crashlytics. Any usage statistics and crash reports go to the Firebase project set in your `GoogleService-Info.plist`.

## Libraries used

- [LibTorrent](https://github.com/arvidn/libtorrent)
- [OpenSSL](https://github.com/krzyzanowskim/OpenSSL)
- [SwiftVLC](https://github.com/harflabs/SwiftVLC)
- [MvvmFoundation](https://github.com/XITRIX/MVVMFoundation)
- [CombineCocoa](https://github.com/XITRIX/CombineCocoa)
- [SWXMLHash](https://github.com/drmohundro/SWXMLHash)
- [MarqueeText](https://github.com/joekndy/MarqueeText)
- [MarqueeLabel](https://github.com/cbpowell/MarqueeLabel)
- [GCDWebServer](https://github.com/XITRIX/GCDWebServer)
- [Firebase](https://github.com/firebase/firebase-ios-sdk)

## License

MIT. iTorrent is Copyright (c) 2024 XITRIX (Vinogradov Daniil), and this fork keeps the original license. See [LICENSE.txt](LICENSE.txt).
