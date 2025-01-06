# ARRI-REVEAL-OCIO-Config
Based on the [LogC4 LUT Package](https://www.arri.com/en/learn-help/learn-help-camera-system/technical-downloads) I have created a minimal OCIO config of ARRI REVEAL for full CG projects. This is **the ARRI ALEXA 35 Workflow** in its most minimalistic and simple form:
* Inputs (textures) are in "linear"
* Rendering and Nuke working space are also in "linear"
* View Transform is for Rec.1886 display

There is no need to go wide gamut or do anything complex to **craft beautiful images**. Enjoy!

# Image Examples
<p>
    <img ![hue_sweep_arri_reveal] width="144" height="81" src="https://github.com/user-attachments/assets/39e5a786-d7e7-4744-8f65-99eb1bf9cd0c" >  
    <img ![photographic_scene_arri_reveal] width="144" height="81" src="https://github.com/user-attachments/assets/32afdea2-cbbf-4860-a893-b5fff8454a34" >
    <img ![light_sabers_arri_reveal] width="144" height="81" src="https://github.com/user-attachments/assets/41a879a9-89ec-4da9-be51-d87508c73375" >
    <img ![lego_sailors_arri_reveal] width="144" height="81" src="https://github.com/user-attachments/assets/a4a0b29e-79f8-48e2-99c0-130d8c637a83" >
    <img ![louise_concert_arri_reveal] width="144" height="81" src="https://github.com/user-attachments/assets/2861828c-6a43-4e86-bf1f-25685641bb0d" >
</p>

Original files (encoded in "linear-AP0") are available [here](https://www.dropbox.com/scl/fo/fhzx0bcwcjylek1oz7kjc/ACGfmi0EHeufVOQPZLvvk7w?rlkey=53cp61955hbns8x46j6cf8k55&e=1&dl=0).

# About the config
* Reference color space is XYZ which is the base of all colourimetry
* All matrixes have been generated using [colour-science](https://www.colour-science.org/apps/) with CAT02
* "linear" stands for "linear_bt.709"
* "cineonlog_rec709" can be used for a matte-painting workflow in Photoshop
* "logc4_arriwg4" is the shaper space. It can be used for color timing and some log operations (such as sharpen)
* Substance_painter roles were set following [this page](https://mrlixm.github.io/blog/substance-painter-color-management/)
* An inverse of the View Transform has been provided even though it is not perfect
* Please note that the inverted LUT was not ARRI-originated (I respected the naming convention from [this guide](https://www.arri.com/resource/blob/294602/67ddc229fc77f6f27551fc2613302dfc/arri-lut-naming-convention-logc4-and-logc3-guideline-en-data.pdf))
* One may easily add several colorspaces or displays for HDR output if needed (such as "p3_d65_pq")

# Looks
* 87 looks from the [ARRI Look Library](https://www.arri.com/en/learn-help/learn-help-camera-system/tools/arri-look-library-app) have been added to the config
* **BUT** you will have to download them from [this link](https://www.filmlight.ltd.uk/support/customer-login/colourspaces/colourspaces.php)
* The use of Looks is highly recommended with ARRI REVEAL
* To use one of the looks, you need to combine it with a View. Like this for instance:

```- !<View> {name: ARRI REVEAL Vibrant, colorspace: ARRI REVEAL - Rec.709 - 2.4 Gamma, looks: 5210 Vibrant}```

# Other available Color Management Workflows
| Name                                                                                             | Author               | Release date |              Observations                             |
|:---:                                                                                             |         :---:        |      :---:   |                 :---:                                 |
| [ARRI K1S1](https://www.arri.com/en/learn-help/learn-help-camera-system/tools/lut-generator)     | Harald Brendel       | 2011         | THE most used LUT on the planet (ARRI Alexa workflow) |
| [Filmic](https://github.com/sobotka/filmic-blender)                                              | Troy Sobotka         | 2017         | Original Blender Color Management used on [this movie](https://www.youtube.com/watch?v=uf3ALGKgpGU) |
| [RED IPP2](https://support.red.com/hc/en-us/articles/360041467533-RED-LUT-Downloads)             | Graeme Natress       | 2017         | RED Image Processing Pipeline explained [here](https://www.red.com/red-tech/image-processing-pipeline-ipp2) |
| [ACES](https://github.com/AcademySoftwareFoundation/OpenColorIO-Config-ACES/releases)            | AMPAS                | 2021         | Color Encoding System developed by the Academy |
| [Sony Venice](https://sonycine.com/resources/luts/)                                              | Sony / Picture Shop  | 2022         | LUT files made in partnership with [Picture Shop](https://www.pictureshop.com/) |
| [Tony](https://github.com/h3r2tic/tony-mc-mapface)                                     | Tomasz Stachowiak    | 2023         | A cool-headed display transform |
| [AgX Blender](https://github.com/EaryChow/AgX)                                                   | Eary Chow            | 2023         | Blender Color Management used on [this video game](https://www.youtube.com/watch?v=mVjBRZqajYY) |
| [TCAMv3](https://www.filmlight.ltd.uk/support/customer-login/colourspaces/colourspaces.php)      | Daniele Siragusano   | 2024         | Baselight Color Management Workflow explained [here](https://youtu.be/DL4n6LErMbw?t=325) |
| [AgX SB2383](https://github.com/sobotka/SB2383-Configuration)                                    | Troy Sobotka         | 2024         | Minimal AgX OCIO Config using Linear BT.709 |
| [JP-2499](https://github.com/jedypod/JP2499)                                                     | JP Zambrano          | 2024         | A popular picture formation pipeline described [here](https://www.liftgammagain.com/forum/index.php?threads/2499-drt-an-alternative-picture-formation-pipeline.18639/) |
| [Open DRT](https://github.com/jedypod/open-display-transform)                                    | Jed Smith            | 2024         | State-of-the-art Color Management Workflow |
