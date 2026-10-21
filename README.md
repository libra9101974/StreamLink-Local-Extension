# StreamLink-Local-Extension
A local browser extension for click-and-play video streaming, including **magnet links and `.torrent` files**, using Ace Stream and TorrServer with a built-in theater player and HLS support.

# StreamLink Local Extension

**Click. Play. Enjoy.**

StreamLink Local Extension is a local browser extension designed to make video playback easier. It can open supported **magnet links and `.torrent` links/files** through its available playback routes and play compatible streams in the built-in theater player. It supports TorrServer for torrent-based video, Ace Stream for compatible streams, and HLS playback for supported formats.

The goal is a simple **click-and-play experience**: use the StreamLink playback option or right-click menu on a supported magnet or torrent link, choose the available playback route, and watch in the theater player. TorrServer can stream a torrent by its info hash or magnet link; compatible files can use direct playback, while supported GStreamer HLS workflows can help with formats such as HEVC/H.265 that browsers may not play reliably.

Playback depends on the website exposing a usable link, the local backend being running and configured, and the media format being supported. Some sites obscure torrent links or require additional handling, so not every link is guaranteed to work.

## Features

- **Built-in theater player** for watching video directly in the browser.
- **Magnet-link playback** for supported magnet links, including TorrServer streaming routes.
- **`.torrent` link/file playback** through supported StreamLink playback options; some websites may require additional handling.
- **TorrServer support** for streaming torrent-based video from a magnet link or torrent info hash.
- **Ace Stream support** for compatible streaming URLs, including HLS.
- **HLS playback** for compatible `.m3u8` streams.
- **Right-click playback options** for supported magnet, torrent, and video links.
- **Direct playback** for compatible video formats.
- **GStreamer HLS support** through TorrServer for compatible remuxing/transcoding workflows.
- **Local-first design** using locally running playback services.

## Requirements

Depending on the playback method, you may need:

- Microsoft Edge or another compatible Chromium-based browser.
- Ace Stream for streams that use the Ace Stream backend.
- TorrServer running locally for TorrServer playback.
- GStreamer configured in TorrServer when using its GStreamer HLS functionality.

Not every stream or video format is compatible with every playback method. Performance depends on the source, format, backend configuration, and hardware.
## *Required Software*

*StreamLink Local Extension uses local playback software to handle supported streaming sources. Depending on the playback method, you may need one or both of the following.*

### *TorrServer — Recommended*

*TorrServer provides local torrent streaming. The GStreamer-enabled build adds HLS playback and transcoding support, which can help with MKV, HEVC/H.265 and other formats that do not play smoothly in a browser.*

***Download:** [Official TorrServer releases](https://github.com/YouROK/TorrServer/releases)*

#### *Windows installation and GStreamer setup*

1. *Download the **GStreamer-enabled Windows 64-bit build** named `TorrServer-gst-windows-amd64.exe` from the official releases page, if available. A standard TorrServer executable does not provide the GStreamer endpoints required for this feature.*

2. *Run the executable and open the local TorrServer interface at [http://127.0.0.1:8090](http://127.0.0.1:8090).*

3. *Open **Settings** and enable **PRO mode**.*

4. *Open the **GStreamer** tab. If this tab is missing, check that you downloaded the GStreamer-enabled build.*

5. *Configure the GStreamer options as needed, then click **Save GStreamer Settings**.*

#### *Recommended starting settings*

*These are a starting point based on a working StreamLink setup, not universal requirements:*

- ***GStreamer:** Enabled and available.*
- ***GStreamer path:** `C:\Program Files\gstreamer\1.0\mingw_x86_64` when using a separately installed MinGW x86_64 runtime. Embedded builds may not need this.*
- ***HDR to SDR:** Enable for HDR sources when tone mapping is supported and needed.*
- ***Hardware acceleration / Use GPU:** Enable only if supported by your system; otherwise use software encoding.*
- ***H.265/HEVC transcoding:** Enable if the source needs conversion for browser playback.*
- ***x264 ultrafast:** Enable if CPU transcoding is struggling to keep up.*
- ***Video bitrate:** Start around `30000` kbps for high-quality video; `50000` kbps worked well in our test, but requires more bandwidth and processing capacity.*

***Important:** Higher bitrate does not automatically mean smoother playback. Adjust it to match your hardware and connection. GStreamer runtime requirements vary by build, so follow the official documentation if the runtime or plugins are missing.*

### *Ace Stream — Alternative*

*Ace Stream is an alternative playback engine supported by StreamLink.*

***Download:** [Official Ace Stream Windows installation guide](https://wiki.acestream.media/Install_Windows)*

*Install and start Ace Stream if you want to use its playback features.*

### *Notes*

- *TorrServer and Ace Stream are separate applications; they are not bundled with StreamLink.*
- *Compatible files may play directly without transcoding. GStreamer HLS is useful when a file needs remuxing or transcoding.*
- *Playback depends on the media format, backend configuration, hardware and network conditions.*
- *Download software only from the official project sources linked above.*

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

1. Open a website containing a supported video, stream, magnet link, or `.torrent` link.
2. Use the available StreamLink playback option or right-click a supported magnet/torrent link.
3. Choose the appropriate playback route. TorrServer must be running for TorrServer playback; Ace Stream must be running for Ace Stream playback.
4. StreamLink opens the supported source in its built-in theater player.

**Magnet links and torrent links are supported playback sources**, but success depends on the link format, the website, the backend, and media compatibility. Some sites obscure torrent URLs, and some `.torrent` links may need additional handling. A torrent may also need time to start buffering before video appears.

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

##  Support StreamLink

If you enjoy using StreamLink and want to support its development, you can make a voluntary donation through PayPal.

[![Donate with PayPal](https://img.shields.io/badge/Donate%20with-PayPal-0070BA?logo=paypal&logoColor=white)](https://www.paypal.com/donate/?hosted_button_id=8FDKK4PYCL3CU)

Every contribution is appreciated. Thank you for supporting the project!

***StreamLink Local Extension — Click. Play. Enjoy.***

