# StreamLink-Local-Extension
A local browser extension for click-and-play video streaming using Ace Stream and TorrServer, with a built-in theater player and HLS support.
# StreamLink Local Extension

**Click. Play. Enjoy.**

StreamLink Local Extension is a browser extension designed to make video streaming easier through a built-in theater player, with support for Ace Stream and TorrServer backends.

The project focuses on local playback, convenient video launching, and HLS streaming support.

## Features

- **Built-in theater player** for watching video directly in the browser.
- **Ace Stream support** for compatible streaming URLs, including HLS.
- **TorrServer support** for streaming torrent-based video.
- **HLS playback** for compatible `.m3u8` streams.
- **Right-click playback options** for supported links.
- **Direct playback** for compatible video formats.
- **GStreamer HLS support** through TorrServer for compatible transcoding workflows.
- **Local-first design** using locally running playback services.

## Requirements

Depending on the playback method, you may need:

- Microsoft Edge or another compatible Chromium-based browser.
- Ace Stream for streams that use the Ace Stream backend.
- TorrServer running locally for TorrServer playback.
- GStreamer configured in TorrServer when using its GStreamer HLS functionality.

Not every stream or video format is compatible with every playback method. Performance depends on the source, format, backend configuration, and hardware.

## Installation

1. Download or clone this repository.
2. Extract the extension files into a folder on your PC.
3. Open your browser's extensions page:
   - **Microsoft Edge:** `edge://extensions`
   - **Google Chrome:** `chrome://extensions`
4. Enable **Developer mode**.
5. Select **Load unpacked**.
6. Choose the folder containing the extension's `manifest.json` file.
7. Start the relevant local playback backend when required.

Keep the extension folder in its chosen location while using the extension.

## Using StreamLink

1. Open a website containing a supported video, stream, magnet link, or torrent link.
2. Use the available StreamLink playback option or right-click menu where supported.
3. Choose the appropriate playback route.
4. Enjoy the video in the theater player.

Some websites may obscure or restrict access to playback links, and certain torrent or stream links may require additional handling.

## Local Services

StreamLink can use locally running playback services, such as Ace Stream and TorrServer.

TorrServer commonly uses a local web interface and API at:

`http://127.0.0.1:8090`

The actual address and port may differ depending on your configuration.

Some video formats, including certain HEVC or HDR files, may require additional transcoding support. GStreamer configuration and hardware capabilities can affect playback quality.

## Privacy and Network Use

The local extension is designed to work with local playback backends. Those backends may communicate with other peers or streaming sources as part of their normal operation.

Review the extension source code and configure each backend according to your own privacy and security requirements. Do not expose local playback services to public networks unless you understand the security implications.

## Troubleshooting

**The extension does not appear in the browser**

- Confirm that Developer mode is enabled.
- Select the correct extension folder containing `manifest.json`.
- Review any errors shown on the browser extensions page.

**Video does not play**

- Confirm that the relevant backend is running.
- Check that the playback URL and video format are supported.
- Try another compatible stream or playback route.

**Audio plays but video does not**

- The video codec may not be supported by the current browser playback route.
- Check the TorrServer and GStreamer configuration when using HLS transcoding.

**A torrent link fails**

- Confirm that the link is valid and supported.
- Some websites provide links in formats that require additional handling.

## Project Status

This project is developed and tested for local use. Compatibility varies by website, stream source, video format, browser, and backend configuration.

Contributions, bug reports, and suggestions are welcome.

## Disclaimer

Users are responsible for ensuring that they have the right to access and stream the content they use with this software and for complying with applicable laws and service terms.

---

***StreamLink Local Extension — Click. Play. Enjoy.***
