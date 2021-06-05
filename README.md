# Contour Map

## Description

Create a layered topographic contour map. Each layer reflects a topographic change in the map to create a true 3 dimensional effect. Started with a section of the Grand Canyon based on the amount of elevation change over a short distance (i.e. the walls are steep).

## Notes
- Initially tried converting downloaded PDF versions of maps into SVG files but that generated image files.  A bitmap to vector conversion on those generated disparate files to be linked together.

- With a little searching, I found a great writeup at theshamblog (see link below). It describes the process of pulling GIS information and breaking it up using QGIS mapping software.

- QGIS works on a data set that creates topographic paths across the entire map. It can create topographic maps and then generate an SVG for each individual path. I color coded each elevation path and used Inkscape to separate each topo into its own file.

- I used recycled some white paper stock, cereal boxes, and some Trex decking I had lying around. It uses a surprising number of layers so it burned up quite a few old pieces of cardboard box.

## Project Type
- Laser cutter

## References
- https://theshamblog.com/making-a-laser-cut-topo-map-the-design-phase/
- https://www.qgis.org/en/site/forusers/alldownloads.html#debian-ubuntu
- http://www.webgis.com/terr_pages/AZ/dem1/coconino.html
  - Used the *Bright Angel Point* file
- https://www.pickatrail.com/topo-map/b/7.5x7.5/bright-angel-point-az.html

## Files
- [xxx.svg](xxx.svg) <img src="xxx.svg" alt="xxx" width="100"/>

## Materials
- Single layer card stock (white)
- Sides of cardboard cereal boxes
- Material is *~ 0.5mm* thick but can be irregular
- Piece of cutoff Trex decking for the backing frames
- Some small nails for registration pins

## Tooling:
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
