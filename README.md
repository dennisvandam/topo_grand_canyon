# Contour Map

## Description

Cutout a topographic contour map of the Grand Canyon.  Each layer of the cutout reflects a topographic change in the map.  

Found a great writeup at theshamblog link listed below.  Describes the process of pulling GIS information and breaking it up using QGIS software.

## Notes
- Tried converting downloaded PDF versions of maps to vectors but that generated image files.  Could do a bitmap to vector conversion on those but it generated disparate files to be linked together.  QGIS works on a data set that creates topographic paths across the entire map.  It then has the ability to generate an SVG with individual paths.  By color coding those paths per elevation, you can use Inkscape to separate each topo into its own file.

## Type
- Laser cutter

## References
- https://theshamblog.com/making-a-laser-cut-topo-map-the-design-phase/
- https://www.qgis.org/en/site/forusers/alldownloads.html#debian-ubuntu
- http://www.webgis.com/terr_pages/AZ/dem1/coconino.html
  - Used the *Bright Angel Point* file
- https://www.pickatrail.com/topo-map/b/7.5x7.5/bright-angel-point-az.html

## Files
- [xxx.svg](xxx.svg) <img src="xxx.svg" alt="xxx" width="100"/>

## Material
- Single layer card stock
- Sides of cardboard cereal boxes
- Material is *~ 0.5mm* thick but not always regular

## Tooling:
- SnapMaker with 1600mW laser.

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
