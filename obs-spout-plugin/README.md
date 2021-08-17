# Spout Plugin for OBS Studio

This plugin creates a `Spout` video input source in `OBS Studio` from any Spout sender [program](https://spout.zeal.co/) and a `Spout` output video texture from your `OBS` canvas.

It enables high resolution, zero-compression, zero-latency, zero-computational overhead video capture and so is better than `NDI`, capture cards, screen capture or the `DirectShow` `SpoutCam` interface.

It enables you to send video in the background while retaining full control of your `Spout` sender/ receiver program viewport.

A video tutorial for installing the plugin can be found [here.](https://www.youtube.com/watch?v=-AcauTS1V8k)

For support, [please get in touch on our `Discord` channel.](https://discord.gg/2PaMtnK)

N.B. This plugin only works for video sharing on a single GPU. For sharing over the network you will need to use a solution like [`NDI`](https://www.ndi.tv/sdk/).*

## Installation

### Installer

-   Go to the plugin [`Releases Page`.](https://github.com/Off-World-Live/obs-spout2-source-plugin/releases)
-   Download the `Windows` `Installer` for your version of `OBS Studio`.
![Installer Page](images/installer.jpg) 
-   Double-click the downloaded `Installer` and select `Run Anyway`.
![Run Anyway](images/runanyway.jpg)
- Run the `Installer` `widget`.
![Widget](images/widget.jpg)
- Agree to the open-source `License` [(GNU GPL)]
![License](images/license.jpg) 
-   Select the `OBS Studio` directory if not the default install location.
![Install Location](images/installlocation.jpg)

## Receiving Spout into OBS

Open `OBS` and add `Spout2 Capture` to your `Sources` as follows:

1. Add `Source`:
    1. At the bottom of the `Sources` window click the `+` icon which will show you a list of all possible input sources.
    2. From this list, select `Spout 2 Capture`.
    3. This will open a window called `Create/Select Source`. Ensure that `Create new` is selected here and press `OK`. You can also rename the Source if you like.
![Spout2 Source](images/spoutsource.jpg)
2. Double-click the `Source` to open its `Properties`:
    1. Select your `Spout Sender` from the available list. These will be named as in the program you are sending your `Spout` feed from.
    2. Composite mode is set to `Opaque` unless you want an `alpha` output.
    3. Pull time for new sender is left as the default option.
    4. Click `OK` to return to the main `OBS` page.
![Spout2 Properties](images/spoutproperties.jpg)
3. Resize Output:
    1. Right click the image/ video inside the main window
    2. From the menu list that appears, select `Resize Output (source size)`.
    3. In the window that appears called `Resize Output (source size)` select `Yes` (to the question `Do you want to continue`.    
    ![Spout2 Resize](images/resize.jpg)
    4. Your `output` window should now be the same as your `Source` size.
    ![Spout2 Resized](images/resized.jpg)

## Sending Spout from OBS

- There are two ways of sending Spout from OBS:
1. Via a `Filter`: 
    - This lets you send any active `OBS` `Source` to Spout.
    - You can manage your inputs and outputs in a single version of OBS.
    - You can output as many simultaneous video feeds as you like (you just add a new filter for each feed). 
    - This is the best way to output from OBS.
2. Via `Tools`:
    - This lets you send your current `OBS` canvas. 
    - It locks `OBS` so you can't use it for any other purpose.)

### OBS Filter Output

1. Open `OBS`, select the `Source` you want to output, ensure that it is active (the 'eye' logo is lit) and that it is highlighted with the mouse and then click `Filters`: 
![Spout2 Output](images/obsfilters.jpg)
2. In the new window that appears add a new `Spout Filter` for that `Source` using the '+' icon in the bottom left of the screen: 
![Spout2 Output](images/addobsfilter.jpg)
3. Change the default name to the name your need for your `Spout` output so you can recognise it in your `Spout` receiver program: 
![Spout2 Output](images/filtername.jpg)
4. Go to your `Spout` receiver program and select the output you have created in `OBS` and it will automatically appear:
![Spout2 Output](images/filterreceiver.jpg)
5. You can create as many simultaneous outputs as you like, each one will be a different `Filter` for the `OBS` `Source` you want to output. 
6. N.B. a `Source` doesn't have to show on your `OBS` canvas (it can behind the canvas/ video feed you want to stream to the internet for example) but it has to be selected (the eye icon is lit) in order to output to `Spout`.


### OBS Tools Output

1. Open `OBS` go to `Tools` and select `Spout Output Settings`
![Spout2 Output](images/spoutoutputtools.jpg)
2. In the pop-up input the name you would like for your `Spout` output and click `Start`. (While you are outputting your `OBS` viewport will be locked)
![Spout2 Output Yes](images/spoutoutputyes.jpg)
3. Create a `Spout` receiver in your desired program, select the name of your sender as you input above and you will now receive the video stream from `OBS`.
![Spout2 Output Receiver](images/spoutreceiverexample.jpg)

## Streaming/ Recording from OBS

### Recording

- Once you have `resized` your output as above, you can use the `Start Recording` option to immediately record your input video feed to file.
 ![Recordings](images/recording.jpg)
 - To find your `recordings` go to `File`>`Show Recordings` and it will open the folder in which they have been saved.
 ![Show Recordings](images/showrecordings.jpg)

### Streaming

1. In OBS click `Settings` in the bottom right hand corner.
![Settings](images/settings.jpg)
2. In the `Settings` window click `Stream`.
![Stream](images/stream.jpg)
2. In the `Stream` section, select from the `Service` dropdown menu where you would like to stream to.
3. Follow the instructions of your selected streaming platform (including acquiring a stream key) and paste the stream key into the `Stream Key` box.
![YouTube](images/youtube.jpg)
4.  Click `Apply` to close the `Settings` window and return to the main OBS window.
5. When you are ready to stream from OBS select `Start Streaming` in the bottom right hand corner.
![Start Streaming](images/streamstart.jpg)

### 4K Streaming
1. In `Settings` go to `Output` and for `Output Mode` select `Advanced`
    1. Under `Encoder` select`NVEnc`.
    2. Under `Rate Control` select `CBR`
    2. Set the `Bit Rate` to at least 30000 Kbs - (ie 30Mbs).
    3. Ensure that the `Keyframe Interval` is not 0. (4 seems to be a good interval for `YouTube`.)
![Advanced Settings](images/advanced.jpg)

### Minimum Internet Upload Speeds

- You should increase the `Bitrate` as explained above to minimise compression for higher resolution outputs.

| Resolution / Framerate | Min Rec. Bandwidth |
| ---- | ---|
| 1080px/ 30fps | +7.5 mbps |
| 2k/ 1440px/ 30fps |  +15mbps |
| 4k/ 30fps | +25mpbs |

## Troubleshooting Spout

- There will always be a `Spout Sender` which is the program outputting the video and a `Spout Receiver`, in this case `OBS`.
- If your video feed does not automatically appear in `OBS` it is normally because either `Sender` or `Receiver` has an issue.
- You can troubleshoot `Spout` using the tips below:
    1. Download the demo `Spout` sender/ receiver [here](https://leadedge.github.io/spout-download.html) to see whether it is the `Sender` program or the `Receiver` program that is not working with `Spout`.
    2. Ensure that `OBS` and your other program are running on the same `GPU` (this is an issue with some laptops). To deal with this:
    3. Check `Windows` `Task Manager` to see which `GPU` your programs are running on - [guide here](https://www.digitalcitizen.life/7-ways-launch-task-manager-windows-8/)
    4. [Use the guide here](https://www.itechtics.com/use-specific-gpu/#:~:text=Click%20on%20Graphics%20Settings.,run%20on%20a%20dedicated%20GPU.) to force your program to use a specific GPU.
    5.  Ensure that the programmes you are sharing between are also in `High Performance` mode if your computer has any performance throttling (this can be common on laptops).
    6. For outputs to `OBS` on certain laptops you may also need to change your `OBS` settings [here.](https://obsproject.com/wiki/Laptop-Troubleshooting)
    7. For any other issues [contact us on Discord.](https://discord.gg/2PaMtnK)



## Copyright

Copyright © 2021 Off World Live Limited. All rights reserved.
