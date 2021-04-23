# Unreal LiveStreaming Camera

_Plugin for live-streaming direct from Unreal Engine at runtime_


This plugin enables you to live-stream a video output from Unreal Engine at runtime without the computational overhead/ latency of capture cards/ NDI.

We recommend that you use it with our [Spout2 receiver plugin for OBS](https://github.com/Off-World-Live/obs-spout2-source-plugin) in order to live-stream to different internet locations or to record to video.

It can also be used to output video to any programme using a SPOUT receiver (Resolume, Notch, TouchDesigner etc. see full list [here](https://spout.zeal.co/)

The plugin is compatible with DX11 and DX12 APIs and so can be used for streaming ray-traced scenes.

[Video tutorials for using the camera`s various special features can be found here](https://www.youtube.com/playlist?list=PLElT6SIg9JnBal5zWDEAVo_l-5TaEhD2J)


## Installation

### Download the Plugin:



1. If via a file download link download and unzip the downloaded plugin.
2. If via the Unreal marketplace, select the project for the plugin and it will automatically appear in your `Plugins` folder.

### Adding the Plugin to your Unreal Project

1. Ensure that all instances of your Unreal Project are closed.
2. If you do not have any Plugins installed in your project then create a new `Plugins` folder in your `Project` folder and copy the unzipped plugin inside.
3. If you already have Plugins in your project then open the `Plugins` folder to find the '**OWL_LivestreamingCamera`folder and copy it into the existing `Plugins` folder in your Project.



<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image1.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image1.png "image_tooltip")




4. When installed correctly, the folder structure should read [Myproject]/Plugins/OWL_LivestreamingCamera.]

### Downloading OBS (for streaming the output from Unreal Engine)

1. Install OBS Studio [https://obsproject.com/download](https://obsproject.com/download)
2. Install our `Spout2 Source Plugin for OBS Studio (64bit)`: [https://github.com/Off-World-Live/obs-spout2-source-plugin/releases](https://github.com/Off-World-Live/obs-spout2-source-plugin/releases)


## Using the Virtual Camera in Unreal

1. Open your Unreal Engine Project and, in the `Place Actors/ Modes` window, search for `OWLLivestreamingCamera`
2. Select this item and drop it into your Unreal viewport.



<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image2.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image2.jpg "image_tooltip")




3. At runtime (when you press play) the camera will automatically start streaming to your desired output programme.



<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image3.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image3.jpg "image_tooltip")




4. You can add as many cameras to your level/ scene as you like. Performance will be relative to your graphics card capacity and output resolution.



<p id="gdcalert4" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image4.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert5">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image4.png "image_tooltip")



## Camera Properties (Found in the Unreal Details Panel)

### `Camera Name`

*   You can set each camera name as you would like it to appear as a source in output programmes (OBS/ Spout etc).



<p id="gdcalert5" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image5.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert6">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image5.jpg "image_tooltip")




*   In the case of multiple cameras each must be named differently to ensure separation in output programmes (OBS/ Spout etc).



<p id="gdcalert6" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image6.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert7">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image6.jpg "image_tooltip")


### `Stream Resolution`

Stream resolution can be customised in the camera details panel. 



<p id="gdcalert7" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image7.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert8">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image7.png "image_tooltip")


Automatic available streaming resolutions are:

| Resolution | 16:9 |
| -----------|------|
| 240p |  426x240 |
| 360p |  640x360 |
| 480p | 854x480 |
| 720p | 1280x720 |
| 1080p | 1920x1080 |
| 1440p/ 2k | 2560x1440 |
| 4k | 3840x2160 |



## [Alpha Channel Output](https://www.youtube.com/watch?v=RtiiQR5GIxw&lc=UgwF6h4RMSI8hQn5O2p4AaABAg)

> _[Watch a  tutorial on this](https://www.youtube.com/watch?v=RtiiQR5GIxw&lc=UgwF6h4RMSI8hQn5O2p4AaABAg)_

N.B. You can only select _Actors _to appear in the alpha channel. This method does not work with _Components _or _Instance Meshes_.


1. In `Project Settings` in your Editor, find `Enable alpha channel support` in `Engine - Rendering/ Postprocessing` and set it to `AllowThroughTonemapper`.



<p id="gdcalert8" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image8.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert9">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image8.png "image_tooltip")




2. Select your OWL LivestreamingCamera in World Outliner and in it`s Details panel find the section called `Scene Capture` and:
    1. Set `Consider Unrendered Opaque Pixel as Fully Translucent` to `True`
    2. Set `Primitive Render Mode` to `Use ShowOnly List`
    3. Go to the `Show Only Actors` list and create an array element for each actor you want to send in your alpha channel (you can select these either from the drop down list or using the picker in your viewport).



<p id="gdcalert9" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image9.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert10">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image9.png "image_tooltip")




3. If you don`t have a `Post Process Volume` in your scene then [follow these instructions](https://subscription.packtpub.com/book/game_development/9781784391966/4/ch04lvl1sec24/adding-post-process) to add one. Then:
    4. Select your `Post Process Volume` in `World Outliner`.
    5. In its `Details Panel` go to `Rendering Features`/ `Post Process Materials`/ `Array`. 
    6. Add a new array element and select `Asset reference` from the drop down.
    7. Use the arrow next to the array element you have added to select `M_OwlAlpha`.



<p id="gdcalert10" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image10.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert11">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image10.png "image_tooltip")




    8.  (If this doesn`t appear in your list, go to `Content Browser`/  `View Options`/ `Show Plugin Content` and then repeat.
4. In 

<p id="gdcalert11" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image11.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert12">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image11.png "image_tooltip")
OBS (or your SPOUT receiver programme) (for a guide on how to stream to OBS more generally please see below):
    9. Click on your SPOUT2 Source.
    10. In the pop-up window for `Composite Mode` select `Premultiplied Alpha`.
    11. You should now see the `Actors` you have selected in Unreal as an alpha channel in OBS/ your SPOUT receiver programme.



<p id="gdcalert12" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image12.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert13">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image12.png "image_tooltip")



## [SPOUT to Unreal Receiver (DX12 Compatible)](https://www.youtube.com/watch?v=eRuxlOgTN9E)

> _[Watch a tutorial on this](https://www.youtube.com/watch?v=eRuxlOgTN9E)_

Adding the SPOUT receiver to your scene:



1. Open your Unreal Engine Project and, in the `Place Actors/ Modes` window, search for `OWLSpout Receiver`.
2. Drag and drop a new receiver into your scene for each SPOUT input you need (you can add multiple into a single scene).



<p id="gdcalert13" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image13.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert14">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image13.png "image_tooltip")


Create a Render Texture to receive the SPOUT input:



1. In Content Browser add a new Render Target by selecting: Add/Import-> Materials & Textures -> Render Target.
2. Give your Render Target a name so you can identify it later.



<p id="gdcalert14" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image14.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert15">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image14.png "image_tooltip")


Connect your SPOUT input to your Render Target:



1. Select your SPOUT Receiver in World Outliner.
2. In the Details panel for your SPOUT Receiver go to Off World Live SPOUT Receiver Settings and:
    1. Click `Receiver Active` to `True`
    2. Select your Render Target from the drop-down list `Render Target`
    3. Input the exact name of your SPOUT sender (as it is called in your external SPOUT sender programme) into the Receiver Name field.



<p id="gdcalert15" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image15.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert16">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image15.png "image_tooltip")


Create a material from your Render Texture and add it elements in your level:



1. Right click on your SPOUT Render Target in Content Browser (which you previously created above) and choose `Create Material`.



<p id="gdcalert16" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image16.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert17">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image16.png "image_tooltip")




2. Drag the newly created material (which will be called the same as your Render Target) onto the element/s in your level on which you would like to show your video texture.



<p id="gdcalert17" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image17.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert18">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image17.png "image_tooltip")



## CPU Usage in Unreal



*   In Editor Preferences in Unreal Engine, please ensure that the box below is unticked. 
*   Without this, you may find that your stream slows down when you have OBS rather than Unreal running in the foreground on your computer.



<p id="gdcalert18" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image18.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert19">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image18.png "image_tooltip")



## Delivering to SPOUT

The camera can be used to output to any SPOUT receiver and converts DX12 textures to DX11 so they are compatible with SPOUT (so ray-tracing can be used):



*   To test with SPOUT you can [download the SPOUT receiver here](https://leadedge.github.io/spout-download.html).
*   You need to ensure that the GPU running the SPOUT receiver program is the same as the GPU running Unreal Engine.
*   To do so, click the `Spout Receiver` programme included in the SPOUT download folder and select the correct GPU from the drop down menu.
*   You also need to ensure that whatever programmes you are sharing the video texture with are also running on the same GPU. [You can use the guide here](https://www.itechtics.com/use-specific-gpu/#:~:text=Click%20on%20Graphics%20Settings.,run%20on%20a%20dedicated%20GPU.).



<p id="gdcalert19" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image19.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert20">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image19.png "image_tooltip")



## Delivering to OBS

First, please [follow the instructions for installing the](https://docs.google.com/document/d/1jPyk8CN7-zeqZnV8f6GvZfuCs2_x1qDbmZRGIL4eI8g) [Spout to OBS plugin](https://docs.google.com/document/d/1jPyk8CN7-zeqZnV8f6GvZfuCs2_x1qDbmZRGIL4eI8g) 


## Technical Considerations

### System Requirements

*   Operating System: Windows 8 or later
*   For ray-tracing, RTX (or other compatible cards) are required. Please see more information [here](https://docs.unrealengine.com/en-US/Engine/Rendering/RayTracing/index.html).
*   Your Windows SDK should be updated to the latest version. Please use Visual Studio to check this (it should be at least above version 19XXX)


## Copyright

Copyright © 2021 Off World Live Limited. All rights reserved.
