<p align="right">
  <img src="https://img.shields.io/badge/extruded-yes-blue.svg?style=flat-square" alt="64-bit" />
</p>

# PointDensityGridLayer

The PointDensityGridLayer renders a grid heatmap based on an array of points.
It takes the constant size all each cell, projects points into cells. The color 
and height of the cell is scaled by number of points it contains. Grid layer 
at the moment only works with COORDINATE_SYSTEM.LNG_LAT.


<div align="center">
  <img height="300" src="/demo/src/static/images/point-density-grid.gif" />
</div>

    import {PointDensityGridLayer} from 'deck.gl';

Inherits from all [Base Layer](/docs/layers/base-layer.md) properties.


## Layer-specific Properties

##### `cellSize` (Number, optional)

- Default: `1000`

Size of each cell in meters

##### `colorDomain` (Array, optional)

- Default: `[min(count), max(count)]`

Color scale domain, default is set to the range of point counts in each cell.

##### `colorRange` (Array, optional)

- Default: <img src="/demo/src/static/images/colorbrewer_YlOrRd_6.png"/></a>

Cell color ranges as an array of colors formatted as `[255, 255, 255]`. Default is colorbrewer `6-class YlOrRd`.

##### `elevationDomain` (Array, optional)

- Default: `[0, max(count)]`

Elevation scale domain, default is set to the range of point counts in each cell.

#### `elevationRange` (Array, optional)

- Default: `[0, 10]`

Elevation scale range

##### `extruded` (Boolean, optional)

- Default: `true`

Whether to enable cell elevation. Cell elevation scale by count of points in each cell. 
If se to false, all cell will be flat.

##### `getPosition` (Function, optional)

- Default: `object => object.position`

Method called to retrieve the position of each point.

##### `lightSettings` (Object, optional) **EXPERIMENTAL**

This is an object that contains light settings for extruded polygons.
Be aware that this prop will likely be changed in a future version of deck.gl.