# PhotonPCB
Method that employ Anycubic Photon DLP printer for the creation of printed circuit boards (PCB)

**1. PCB design**

![PCB_kicad](https://user-images.githubusercontent.com/37478033/75089867-71ee8d00-555d-11ea-81ba-53a5a5169133.png)

I used KiCad to design the desired PCB.


**2. Plot svg (negative & mirrored)**

![plot_svg_window](https://user-images.githubusercontent.com/37478033/75089919-da3d6e80-555d-11ea-9b6e-0d40b6db9175.png)

I exported the svg file of the design selecting the NEGATIVE and MIRRORED option. The result follows:

![SVG_result](https://user-images.githubusercontent.com/37478033/75089949-415b2300-555e-11ea-86a9-fd28bfb975dc.png)

**3. Obtain PNG from svg**

File -> Document Property:
According to https://github.com/Photonsters/anycubic-photon-docs the print area is 68.04(W)mm x 120.96(H)mm, thus I should create a new document that has the same size. Plus, I should set the background of the page to be black. **Remember to set the alpha channel to 100% as well.**

![doc_prop_black](https://user-images.githubusercontent.com/37478033/79127203-c1a14600-7da1-11ea-9c02-c70e7add4096.png)

File -> Import:
Select the .svg file that was the output of your PCB design software.
Then, adjust the position of your PCB on the page.

![pcb_positioned](https://user-images.githubusercontent.com/37478033/79127252-d978ca00-7da1-11ea-8c85-79df5953d06b.png)

File -> Export as PNG image:
Export the **entire page** and define the resolution of the resultant PNG image to be compliant with Photon's resolution: 1440x2560 pixels.

![export_menu](https://user-images.githubusercontent.com/37478033/79127282-e7c6e600-7da1-11ea-9f67-60978a7e526c.png)

I have now the PNG image of your PCB with the correct resolution.

<img src="https://user-images.githubusercontent.com/37478033/79127299-f1e8e480-7da1-11ea-9a43-abaf57ec5708.png" height="50%" width="50%">

**4. PNG to photon file**

In this step I will exploit a slightly modified version of PhotonCpp [https://github.com/0x3f00/PhotonCpp].

I build the software according to my environment (MSVC project for Windows and Makefile for Linux and MacOS X).

The usage of the software is the following:

Usage: PngToPhoton <input-1440x2560.png> <output.photon> <exposure_time_in_seconds>

Example: ./PngToPhoton exported_pcb.png pcb_to_be_exposed.photon 900

(The previous command will generate a photon file with 1 bottom layer that has an exposure time of 900 seconds.)

**5. Exposition**

Now the photon file is ready to be transfered to an USB key and executed in my Photon printer.

(I removed the bed and the resin tank)

<img src="https://user-images.githubusercontent.com/37478033/79127700-a8e56000-7da2-11ea-921d-26ac4ca52938.jpg" height="50%" width="50%">

<img src="https://user-images.githubusercontent.com/37478033/79127773-c286a780-7da2-11ea-90d0-2a7a230e06bb.jpg" height="50%" width="50%">

<img src="https://user-images.githubusercontent.com/37478033/79129209-172b2200-7da5-11ea-8294-c7b2306e723e.jpg" height="50%" width="50%">

<img src="https://user-images.githubusercontent.com/37478033/79129255-2dd17900-7da5-11ea-9d1a-489cbe07b956.jpg" height="50%" width="50%">

**6. Final Result**

![photo5809687521704129714](https://user-images.githubusercontent.com/37478033/79129836-2f4f7100-7da6-11ea-855c-aff59486c1bb.jpg)
