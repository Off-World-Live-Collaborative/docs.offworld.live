# SPOUT OBS Plugin 
_Plugin for adding SPOUT as an input source in OBS Studio_

[This plugin](https://github.com/Off-World-Live/obs-spout2-source-plugin) creates a SPOUT video intput source in OBS for shared textures from any SPOUT sender program (Resolume, Notch, TouchDesigner, [Unreal Engine](https://offworld.live/livestreaming-camera) etc. - see full list [here](https://spout.zeal.co/)).

Previously the only way to import shared textures from SPOUT was via the DirectShow SpoutCam interface or by screen-capturing the full-screen output of the SpoutReceiver program. The SpoutCam is limited to standard webcam resolutions and capped at 1920x1080 and capturing the SpoutReceiver is both inefficient and limited by your current screen resolution.

This plugin enables high resolution capture and enables you to retain control of the sender program interface while simultaneously sending video.

A video tutorial for installing the plugin in OBS [can be found here](https://www.youtube.com/watch?v=-AcauTS1V8k)


## Installation

*   Go to the plugin [Releases Page](https://github.com/Off-World-Live/obs-spout2-source-plugin/releases)
*   Download the latest windows installer.
*   Run the installer (accepting installation from untrusted source)
*   Select the OBS directory if not the default install location

### Manual Installation

*   If you are unable to run the installer, download the release zip file OBS_SPOUT2_Plugin_Build_xxx.zip from the [Releases Page](https://github.com/Off-World-Live/obs-spout2-source-plugin/releases)
*   Extract the entire contents into your OBS directory
*   Verify that win-spout.dll is in the dir &lt;obs-install>\obs-plugins\64bit

## Using the Plugin

> OBS needs to be using the same GPU as the SPOUT sender for texture sharing to work

*   Certain laptops might not do this by default (you will see the source in OBS but the input will be black. 
*   If so, [you can change your OBS settings here](https://obsproject.com/wiki/Laptop-Troubleshooting)

Once you are ready to live-stream your content, open OBS and add `Spout2 Capture` to your `Sources` as follows:

1. Add Source:

    1. At the bottom of the `Sources` window click the `+` icon which will show you a list of all possible input sources.
    2. From this list, select `Spout 2 Capture`.
    3. This will open a window called `Create/Select Source`. Ensure that `Create new` is selected here and press `OK`. You can also rename the Source if you like.

2. Select `Source` properties:

    1. A window will open called `Properties for Spout2 Capture` (or whatever you have renamed your Source). Ensure that: 
    2. Spout Sender is set to the name of your input video feed (by default)
    3. Composite mode is set to `Opaque`
    4. Pull time for new sender is left as the default option.
    5. Click `OK`.

3. Resize Output:

    1. Right click the image/ video inside the main window
    2. From the menu list that appears, select `Resize Output (source size)`.
    3. In the window that appears called `Resize Output (source size)` select `Yes` (to the question `Do you want to continue`).

## Output
### Streaming from OBS to Internet Locations

1. In OBS click `Settings` in the bottom right hand corner and in the `Settings` window click `Stream`.
2. In the `Stream` section, select from the `Service` dropdown menu where you would like to stream to.
3. Follow the instructions of your selected streaming platform (including acquiring a stream key) and paste the stream key into the `Stream Key` box.
4.  Click `Apply` to close the `Settings` window and return to the main OBS window.
5. When you are ready to stream from OBS select `Start Streaming` in the bottom right hand corner.

Setting recommendations for streaming 4K to YouTube:



1. Ensure that you are using the `NVEnc` video encoder (in the output tab).
2. Enable `Advanced Settings` and set the bit rate to at least 30000 Kbs - (ie 30Mbs) with CBR.
3. Ensure that the keyframe interval is not 0. 4 seems to be a good interval for YouTube.

### Minimum Internet Upload Speeds


| Resolution / Framerate | Min Rec. Bandwidth |
| ---- | ---|
| 1080px/ 30fps | +7.5 mbps |
| 2k/ 1440px/ 30fps |  +15mbps |
| 4k/ 30fps | +25mpbs |

## Copyright

Copyright © 2021 Off World Live Limited. All rights reserved.
