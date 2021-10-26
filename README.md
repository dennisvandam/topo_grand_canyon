# Contour Map - Grand Canyon - Bright Angel

## Description

Create a layered topographic contour map. Each layer reflects a topographic change in the map to create a true 3 dimensional effect. Started with a section of the Grand Canyon based on the amount of elevation change over a short distance (i.e. the walls are steep).

## Final Pics

![Pic 1](images/small/IMG_6919.JPG)

![Pic 2](images/small/IMG_6920.JPG)

![Pic 3](images/small/IMG_6921.JPG)

![Pic 4](images/small/IMG_6922.JPG)

See the images directory for larger pictures.

## Notes

- Initially tried converting PDF maps into SVG files. The process generated image files. A bitmap to vector conversion on those generated many separate files to be linked together. Abandoned this approach.

- Found a great writeup at theshamblog (see link below). It describes the process of pulling GIS information and breaking it up using QGIS mapping software.

- QGIS works on data that creates topographic contour lines across the entire map. I used it to create topographic maps and then generate an SVG for each elevation level. I color coded each elevation path for visual separation and then used Inkscape to separate each topo into its own file.

- I used recycled white paper stock, cereal boxes, and some Trex decking scraps. It used a surprising number of layers so it burned up quite a few pieces of cardboard box. I think the only thing I purchased for this was some glue.

- The frames were made of some leftover Trex decking material. I used the CNC to route out a precise frame but that process took a lot of time. I'd probably use another type of framing on future runs to avoid the need for the CNC to construct the frame.

- I made two versions of this concurrently by cutting two versions (white/brown) of each layer.  If you look closely at the pictures you can see that the layer colors alternate differently. 

## References
- https://theshamblog.com/making-a-laser-cut-topo-map-the-design-phase/
- Software
  - https://inkscape.org/
  - https://www.qgis.org/en/site/forusers/alldownloads.html#debian-ubuntu
  - https://snapmaker.com/product/snapmaker-2/downloads
- Data
  - http://www.webgis.com/terr_pages/AZ/dem1/coconino.html
    - Used the *Bright Angel Point* file
  - https://www.pickatrail.com/topo-map/b/7.5x7.5/bright-angel-point-az.html

## Materials
- Single layer card stock
  - White layers
  - Weight: 
- Sides of cardboard cereal boxes
  - Brown layers
  - Material is *~ 0.5mm* thick but can be irregular
- Piece of cutoff Trex decking
  - Used for the backing frame
  - Routed out profile and cut to size afterwards
- Small nails for registration pins
- Glue

## Software and Tooling:
- QGIS software (free - see references)
- InkScape (free - see references)
- SnapMaker Luban (free - see references)
- SnapMaker A350 with 1600mW laser to cut each layer.
- SnapMaker A350 with CNC cutter to create backing frame.

## Process
- Install QGIS software
- Download GIS file
- Load in QGIS and break into layers
- Open in Inkscape and reprocess
  - For each layer
    - Create a new layer
    - Select a color
    - Select all same color
    - Select *group* for each one to avoid losing color information
    - Move groups to their own layer
  - For Background
    - Create separate layer
    - Add rectangle around entire box
    - Add calibration circles that should appear in each layer.
- Create files with SnapMaker Luban (verion 3.15)
  - Background layer contains outline an calibration holes
  - Each layer file contains topographic paths

## Machine Settings:
- For full cut
  - 2 passes
  - 0.6mm per cut (default)
  - 300mm / minute
- Sequence
  - Cut layer first
  - Cut background second to avoid fallout
