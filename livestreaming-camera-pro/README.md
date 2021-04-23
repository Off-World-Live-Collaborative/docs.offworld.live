# Unreal Engine Livestreaming Toolkit


This plugin enables you to manage sending and receiving multiple real-time video inputs/outputs to/from Unreal Engine in-Editor or at Runtime to/ from [any SPOUT compatible programme](https://spout.zeal.co/) including [OBS Studio (64bit)](https://github.com/Off-World-Live/obs-spout2-source-plugin)

It is compatible with all significant Unreal creative tools including (but not limited to): Cinecam, Composure, DLSS, Virtual Camera plugin, Livelink etc.

SPOUT allows Windows users to share video feeds between programmes running on the same GPU with no computational overhead, compression or latency, making it the best way to stream realtime-video from a single machine.

For any support or further questions, [please get in touch on our discord channel.](https://discord.gg/2PaMtnK)


## Download

### Unreal Plugin

1. You will receive an email invitation to download the plugin. Click the link and you will be taken to the registration/ download page.
![Alpha Email](./images/alphaemail.jpg)
2. You will be asked if you want to accept the plugin invitation.
![Accept Invite](./images/acceptinvite.jpg)
3. Please accept 

### OBS-to-SPOUT Plugin

In order to stream the output from Unreal Engine to the Internet:

1. [Install OBS Studio](https://obsproject.com/download)
2. Install our [Spout2 Source Plugin for OBS Studio (64bit).](https://github.com/Off-World-Live/obs-spout2-source-plugin/releases) 
3. See [Installation guide here](https://docs.google.com/document/d/1jPyk8CN7-zeqZnV8f6GvZfuCs2_x1qDbmZRGIL4eI8g)


## Installation

### Add the Plugin to your Unreal Project


1. Ensure that all instances of your Unreal project are closed and that you are connected to the internet.
2. If you do not have any `Plugins` installed in your project then create a new `Plugins` folder in your `Project` folder and copy the unzipped plugin inside.
![Creating the plugin directory](./images/CreatePluginDir.jpg)
3. If you already have `Plugins` in your project then open the `Plugins` folder to find the `OWLLivestreamingToolkit` folder and copy it into the existing `Plugins` folder in your `Project`.
![Copy the plugin folder](./images/CopyPluginFolder.jpg)
4. When installed correctly, the folder structure should read `Project`/Plugins/OWLLivestreamingToolkit.
5. Open your Unreal project and you will see an `Off World Live` icon above your viewport. Click it and you will be taken to login.
![Off World Icon](./images/login.jpg)
6. You will be taken to the browser to login.
![Off World Icon](./images/signin.jpg) 
7. Validate your login and you will be returned to Unreal.
![Off World Icon](./images/validated.jpg)


## Toolkit Overview

There are three main components to the toolkit:
1. The `Spout Sender Manager` which allows you to live-stream any Unreal `Render Target` from Unreal via `Spout`.
2. The `Spout Receiver Manager` which allows you to receive any real-time video feeds from `Spout` in Unreal.
3. The `OWL Cinecam` which allows you to output an Unreal `Cinecam` to a `Render Target` for use either with the `Spout Sender Manager` or in other Unreal processes.


## Spout Sender Manager

### Overview

- The `Spout Sender Manager` is an Unreal `Actor` that you use to manage different real-time Spout video ouputs from Unreal. 
- It allows you to output any `Render Target` from Unreal to Spout (such as those from `OWL Cinecam`, `Composure` or `Virtual Camera Plugin`)
- It works both `in-Editor` and `at-Runtime` and can be controlled through `Blueprints`.

### Installation
- Please install as follows:

1. Find the `OWLSpoutSenderManager` `Actor` in the `Place Actors`panel and drag it into your scene.
![Select Spout Sender Actor](./images/spoutsenderactorselect.jpg)
2. In `World Outliner`select `OWLSpoutSenderManager`so it opens in your `Details` panel.
![Spout Sender Details Panel](./images/spoutsenderdetails.jpg)
3. In your `Details` panel add a `Spout Sender` `Array Element` and click the arrow in the right hand corner to open the `Array Element` showing its `Members` (there are 4). 
![Spout Sender Array](./images/senderarray.jpg)
You need to:
 
    a.  Name your `Sender` and `Standalone Sender` as this is what your video feeds will be called in OBS/ your Spout receiver programme.
    b. Select/ create a `Render Target` by clicking the drop down (this can be from your `OWL Cinecam` as configured below or from another Unreal output.) 
    c. Click the `Active` box to begin sending to Spout.
 ![Render Target](./images/rendertarget.jpg)
4. To stream multiple cameras, just add additional `Array Elements`.
5. You can use the `Active` tick-box to manage which cameras are rendering simultaneously and so reduce computational load.


## Spout Receiver Manager

### Overview

- The `Spout Receiver Manager` is an Unreal `Actor` that you use to manage different real-time Spout video inputs to Unreal. 
- Inputs are managed as  `Render Targets` in the same way as the `Spout Sender`
- You need to create a `Material` from your `Render Target` to add the video input to `Actors` in your scene (explained below).
- It works both `in-Editor` and `at-Runtime` and can be controlled through `Blueprints`.

### Installation
- Please install as follows:

1. Find the `OWLSpoutReceiverManager` `Actor` in the `Place Actors`panel and drag it into your scene.  
![Spout Receiver Manager](images/spoutreceiver.jpg "image_tooltip")
2. In `World Outliner`select `OWLSpoutReceiverManager`so it opens in your `Details` panel.
3. In your `Details` panel add a `Spout Receiver` `Array Element` and click the arrow in the right hand corner to open the `Array Element` showing its `Members` (there are 3). 
![Spout Receiver Details Panel](./images/receiverarray.jpg)
4. To receive your video input/s you need to:
    a. In `Content Browser` add a new `Render Target` by selecting: `Add/Import`> `Materials & Textures` > `Render Target`.
![Add new Render Target](images/addrendertarget.jpg "image_tooltip")
    b. Give your `Render Target` a name so you can identify it from the drop-down list in the `Spout Sender` `Array`
 ![Name new Render Target](images/namerendertarget.jpg "image_tooltip")
    c. Go back to your `Spout Receiver Manager` `Details` panel and select your newly added `Render Target` in your `Spout Receiver` `Array`
![Select Render Target](images/selectrendertarget.jpg "image_tooltip")
    d. Input the name of your `Spout Sender` video-feed. This needs to be **EXACTLY** the same as your `Spout Sender` in your external program otherwise it will not appear.
    e. Click the `Active` box to begin receiving the video-feed from your external `Spout Sender` (you should automatically see your input in the `Render Target` thumbnail.)
![Spout Receiver Thumbnail](images/senderthumbnail.jpg)
5. To add your video input/s to elements in your scene you need to:
    a. Create a `Material` from your `Render Target`: Right click on the `Render Target` you created in `Content Browser` (step 4.a) and choose `Create Material`.
![Create Material](images/rendermaterial.jpg)
    b. Drag the newly created `Material` (which will be called the same as your `Render Target`) onto the elements in your level.
![Drag Material](images/dragmaterial.jpg)
6. To receive multiple input feeds, just add additional `Array Elements`.
7. You can use the `Active` tick-box to manage which inputs are rendering simultaneously and so reduce computational load.

## OWL Cinecam

### Overview

- The `OWL Cinecam` is a modified Unreal `Cinecam` that outputs to a `Render Target` and so can be used with our `Spout Sender Manager`to stream video from the `Cinecam` to `Spout`.
- It includes all normal `Cinecam` features in addition to certain `Scene Capture` features like `Alpha`and `Resolution`(see details below).

### Installation
- Please install as follows:
1. Find the `OWLCine Cam Capture` `Actor` in the `Place Actors` panel and drag it into your scene.
![OWL Cinecam](images/owlcinecamactor.jpg)
2. In `World Outliner`select `OWLCine Cam Capture`so it opens in your `Details` panel.
![OWL Cinecam Details](images/cinecamdetails.jpg)
3. In your `Details` panel, create a `Render Target` to receive the video feed from your `OWL Cinecam` by clicking the dropdown next to `Texture Target` and selecting `Render Target`.
![OWL Cinecam Details](images/cinecamrendertarget.jpg) 
4. Name your `Render Target` so that you can select it from the drop down list.
![OWL Cinecam Render Target Name](images/rendertargetname.jpg) 
5. You will now see your `Render Target` connected to your `OWL Cinecam`
![OWL Cinecam Render Target Complete](images/cinerender.jpg) 


### Features

- The `OWL Cinecam` combines features from the Unreal `Cinecam` and `Scene Capture 2D` to create a streaming camera that benefits from the features and rendering pipeline of `Cinecam`.


#### Render Texture Target:
  
- You can select the `Render Texture Target` that you want to attach to the `OWL Cinecam` using the drop-down as described above in `OWL Cinecam` step 3.
- You can create multiple `Render Targets` and use `Blueprints` to switch between then as required.

#### Resolution/ Aspect Ratio:

- The `OWL Cinecam` has both a `Resolution` and an `Aspect Ratio`.
 ![Resolution and Aspect Ratio](images/resolutionaspect.jpg) 
- The `Aspect Ratio` is controlled through the standard `Cinecam` `Filmback` settings in the `Details` panel and changes the size of the `Render Target`.
- The `Resolution` is locked to the `Aspect Ratio` so you can only increase/ decrease the `Y-Value` (which will automatically set the correct proportionate `X-Value`). 
- To disconnect `Resolution` from `Aspect Ratio` you can untick `Constrain Aspect Ratio` in the `Camera Options` section of the `Details` panel. N.B. this will create a distorted output.
![Constrain Ratio](images/constrain.jpg) 


#### Render Target Clear Color/ Gamma

- The `Render Target` `Gamma` is exposed in the `Details` panel and set to 2.2 as this is the optimal colour setting for streaming.  
- The `Clear Colour` settings can be used to change the default colour of the `Render Texture`  (e.g. if you want to send a green screen background for keying in `OBS Studio`).
![Clear Colour/ Gamma](images/clearcolour.jpg) 

#### Pause Rendering:

-   This enables you to `Pause Rendering` on the `OWL Cinecam` which is useful for saving GPU power when using live-editing.
-   This will stream a static/ paused image if `Pause Rendering` is selected in the `OWL Cinecam` `Details` panel and `Active` is selected in the `Spout Sender Manager` (for that `OWL Cinecam`). This is useful if you want to see the viewport of your different cameras but only render a live video-feed from a single camera at a time).
![Pause Rendering](images/pauserendering.jpg) 

#### Use Show Only/ Hidden Actors:


-   `Show Only` is used to select specific `Actors` to appear in an alpha channel output.
-   `Hidden Actors` can be used to select `Actors` in your scene and stop them from being rendered into your output.
-  Both require a post-process volume (see full guide below).
![Show Only/ Hidden Actors](images/showhide.jpg) 

#### Max View Distance Override:

*   This can be used to cull distant objects from a reflection.
![Max Distance](images/maxview.jpg) 

#### Standard Cinecam Features:

*   The `OWL Cinecam` also includes the following standard `Cinecam` features which can be used to select properties such as `Aspect Ratio` and `Depth of Field`:
    *   `Filmback`
    *   `Lens Settings`
    *   `Focus Settings`
    *   `Focal Length`
    *   `Aperture`
    *   `Lookat tracking settings`
    *  `Horizontal Field of View`
![Cinecam Features](images/cinecamfeatures.jpg) 


### Depth of Field


- The `OWL Cinecam` includes all the of the `Depth of Field` capabilities from the Unreal `Cinecam` which are split across the `Current Camera Settings` and `Post Process` sections.
- For more information about `Depth of Field` [please see the Unreal guidelines here](https://docs.unrealengine.com/en-US/RenderingAndGraphics/PostProcessEffects/DepthOfField/CinematicDOFMethods/index.html)


### Post Processing

The `OWL Cinecam` uses the `Viewport` rendering pipeline from Unreal and so can take advantage of `Temporal Anti-Aliasing`, `TAA Motion Blur` and `TAA Upsampling`.
-   All of these can be disabled via the tick-boxes in the `OWL Cinecam` details panel.
-   All other post-process settings are as standard for the `OWL Cinecam`.
![Post Process](images/postprocess.jpg)

### Alpha Channel Output


You can select specific `Actors` to show/ hide (but only `Actors`, not `Components` or `Instance Meshes`) using the `Hidden Actors` and `Show Only Actors` `Arrays` as follows:

1. Go to `Project Settings` in your `Editor`
 ![Project Settings](images/projectsettings.jpg)
2. find `Enable alpha channel support` in `Engine - Rendering/ Postprocessing` and set it to `AllowThroughTonemapper` (you will be asked to restart your level).
![Allow Tonemapper](images/allowtonemapper.jpg)
3. If you don’t have a `Post Process Volume` in your scene then [follow these instructions](https://subscription.packtpub.com/book/game_development/9781784391966/4/ch04lvl1sec24/adding-post-process) to add one. Then:
    a. Select your `Post Process Volume` in `World Outliner`.
    b. In its `Details` panel go to `Rendering Features`/ `Post Process Materials`/ `Array`.
    c. Add a new `Array element` and select `Asset reference` from the drop down.
    d. Search for and select `M_OwlAlpha`.
    ![OWLAlpha](images/owlalpha.jpg)
    e. If `M_OwlAlpha` doesn’t appear in your list, go to `Content Browser`>  `View Options`> `Show Plugin Content` and then repeat.
4. Click on the `OWL Cinecam` in the `World Outliner` and go to its `Details` panel.
    a. Using the `Hidden Actors` or `Show Only Actors` arrays select the `Actors` that you would like to show/ hide.
    b. You can do this from the drop down list or using the picker to the left of the drop down list.
    c. If you want to `Show Only Actors` then you need to also tick the `Use Show Only List` tick box.
    ![Show/Hide](images/showhidelist.jpg)
5. In `OBS Studio` (or your `Spout` receiver programme):
    a. Click on your `SPOUT2 Capture` `Source`.
    b. In the pop-up window for `Composite Mode` select `Premultiplied Alpha`.
    ![OBS Alpha](images/obsalpha.jpg)
    c. You should now see the `Actors` you have selected in Unreal as an alpha channel in `OBS Studio`/ your `Spout` receiver programme.
    ![OBS Alpha View](images/obsalphaview.jpg)


## DLSS & OWL Cinecam

`DLSS` works with the `OWL CineCam` in all game targets (`PIE`, `Standalone`, `Packaged`) but not `in-Editor` (because of the `DLSS` implementation). You can configure it as follows:
1. Ensure that you have the latest NVIDIA GeForce drivers [here](https://www.nvidia.com/drivers)
2. Set up `DLSS` in your level by watching a [tutorial like this](https://www.youtube.com/watch?v=4JkHE48YptA)
3. Use blueprints to set up a toggle for DLSS at runtime such as this: 
![DLSS](images/dlss.png)


## Composure
- `Composure` is Unreal's native plugin for chromakeying elements in your scene.
- You can output your `Composure` `Render Target` through the `Spout Sender Manager` as follows:
1. Follow the Unreal `Composure` guide [here](https://docs.unrealengine.com/en-US/WorkingWithMedia/Composure/QuickStart/index.html) (or a similar video guide).
2. Once you have created your `Composure` select your `Media Plate` in `World Outliner`and in the `Details` panel go to `Output` section and add a new `Array Element`.
![Output](images/output.jpg)
3. In your `Array Element` for `Output Pass` please select `Render Target Compositing Output` from the drop down.
![RTCOutput](images/rtcoutput.jpg)
4. Create a new `Render Target` following the instructions as above (in the `OWL Cinecam` section).
![CompRTarget](images/comprtarget.jpg)
5. Name your `Output` and ensure it is `Enabled`
![CompNamed](images/compnamed.jpg)
5. Now if you go to your `Spout Sender Manager`you can create a new `Array Element` using your new `Render Target` for your `Composure` output and stream it wherever you like.
![CompSender](images/compspoutsender.jpg)

## Unreal Virtual Camera/ LiveLink
- The Unreal `Virtual Camera`allows you to control your `OWL Cinecam` from an external device. 
- You can output from your Unreal Virtual Camera through the `Spout Sender Manager` as follows:
1. 

## Testing Spout

### Delivering to Spout

The `Spout Sender Manager` converts DX12 textures to DX11 so they are compatible with `Spout`:

-   You can test`Spout`by downloading the demo[ `Spout` sender/ receiver ](https://leadedge.github.io/spout-download.html).
-   [Use the guide here](https://www.itechtics.com/use-specific-gpu/#:~:text=Click%20on%20Graphics%20Settings.,run%20on%20a%20dedicated%20GPU.) to ensure that the programs you are sharing the video texture between are running on the same GPU. 
-   You also need to ensure that the programmes you are sharing between are also in `High Performance` mode if your computer has any performance throttling (this can be common on laptops).

### Delivering to OBS


First, please [follow the instructions for installing the](https://docs.google.com/document/d/1jPyk8CN7-zeqZnV8f6GvZfuCs2_x1qDbmZRGIL4eI8g) [Spout to OBS plugin](https://docs.google.com/document/d/1jPyk8CN7-zeqZnV8f6GvZfuCs2_x1qDbmZRGIL4eI8g) 


## Optimisation 

### GPU Usage Optimisation


### CPU Usage Optimisation

*   In Editor Preferences in Unreal Engine, please ensure that the box below is unticked. 
*   Without this, you may find that your stream slows down when you have OBS rather than Unreal running in the foreground on your computer.


## Technical Considerations


### System Requirements


*   Operating System: Windows 8 or later
*   For ray-tracing, RTX (or other compatible cards) are required. Please see more information [here](https://docs.unrealengine.com/en-US/Engine/Rendering/RayTracing/index.html).
*   Your Windows SDK should be updated to the latest version. Please use Visual Studio to check this (it should be at least above version 19XXX)


## Copyright


Copyright © 2021 Off World Live Limited. All rights reserved.