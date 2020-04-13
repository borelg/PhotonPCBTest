# PhotonPCB
Method that employ Anycubic Photon DLP printer for the creation of printed circuit boards (PCB)

1. PCB design



![PCB_kicad](https://user-images.githubusercontent.com/37478033/75089867-71ee8d00-555d-11ea-81ba-53a5a5169133.png)

I used KiCad to design the desired PCB.


2. Plot svg (negative & mirrored)

![plot_svg_window](https://user-images.githubusercontent.com/37478033/75089919-da3d6e80-555d-11ea-9b6e-0d40b6db9175.png)

I exported the svg file of the design selecting the NEGATIVE and MIRRORED option. The result follows:

![SVG_result](https://user-images.githubusercontent.com/37478033/75089949-415b2300-555e-11ea-86a9-fd28bfb975dc.png)

3. Obtain PNG from svg

File -> Document Property:
According to https://github.com/Photonsters/anycubic-photon-docs the print area is 68.04(W)mm x 120.96(H)mm, thus we should create a new document that has the same size.

File -> Import:
Select the .svg file that was the output of your PCB design software.
Then, adjustthe position of your PCB on the page.

File -> Export as PNG image:
Export the entire page and define the resolution of the resultant PNG image to be compliant with Photon's resolution: 2560x1440 pixels.



4. PNG to photon file

5. Exposition & etching
