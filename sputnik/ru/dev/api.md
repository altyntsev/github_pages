---
layout: page
title: sputnik
---
# FastAPI
## Version: 0.1.0

### /project/new

#### POST
##### Summary:

Save project

##### Description:


        Description: Save project to database
        

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /project/list

#### GET
##### Summary:

Project list

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /project/info

#### GET
##### Summary:

Project info

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| project_id | query |  | Yes | integer |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /task/list

#### GET
##### Summary:

Task list

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /task/run

#### POST
##### Summary:

Run processing

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /proc/list

#### GET
##### Summary:

Processing list

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| project_id | query |  | Yes | integer |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /meta/list

#### GET
##### Summary:

Scenes metadata for date

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| project_id | query |  | Yes | integer |
| date | query |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /meta/dates

#### GET
##### Summary:

Date list of available metadata

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| project_id | query |  | Yes | integer |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /rgb/list

#### GET
##### Summary:

Scenes metadata for date

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| project_id | query |  | Yes | integer |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /rgb/tile/{project_id}/{product_id}/{z}/{x}/{y}

#### GET
##### Summary:

Get tile

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| project_id | path |  | Yes | integer |
| product_id | path |  | Yes | string |
| z | path |  | Yes | integer |
| x | path |  | Yes | integer |
| y | path |  | Yes | integer |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/bounds

#### GET
##### Summary:

Bounds

##### Description:

Return the bounds of the COG.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| url | query | Dataset URL | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return dataset's bounds. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/info

#### GET
##### Summary:

Info

##### Description:

Return dataset's basic info.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| url | query | Dataset URL | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return dataset's basic info. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/info.geojson

#### GET
##### Summary:

Info Geojson

##### Description:

Return dataset's basic info as a GeoJSON feature.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| url | query | Dataset URL | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return dataset's basic info as a GeoJSON feature. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/statistics

#### GET
##### Summary:

Statistics

##### Description:

Create image from a geojson feature.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| max_size | query | Maximum image size to read onto. | No | integer |
| height | query | Force output image height. | No | integer |
| width | query | Force output image width. | No | integer |
| categorical | query | Return statistics for categorical dataset. | No | boolean |
| c | query | List of values for which to report counts. | No | [  ] |
| p | query | List of percentile values. | No | [ integer ] |
| histogram_bins | query |  Defines the number of equal-width bins in the given range (10, by default).  If bins is a sequence (comma `,` delimited values), it defines a monotonically increasing array of bin edges, including the rightmost edge, allowing for non-uniform bin widths.  link: https://numpy.org/doc/stable/reference/generated/numpy.histogram.html          | No | string |
| histogram_range | query |  Comma `,` delimited range of the bins.  The lower and upper range of the bins. If not provided, range is simply (a.min(), a.max()).  Values outside the range are ignored. The first element of the range must be less than or equal to the second. range affects the automatic bin computation as well.  link: https://numpy.org/doc/stable/reference/generated/numpy.histogram.html          | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return dataset's statistics. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

#### POST
##### Summary:

Geojson Statistics

##### Description:

Get Statistics from a geojson feature or featureCollection.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| max_size | query | Maximum image size to read onto. | No | integer |
| height | query | Force output image height. | No | integer |
| width | query | Force output image width. | No | integer |
| categorical | query | Return statistics for categorical dataset. | No | boolean |
| c | query | List of values for which to report counts. | No | [  ] |
| p | query | List of percentile values. | No | [ integer ] |
| histogram_bins | query |  Defines the number of equal-width bins in the given range (10, by default).  If bins is a sequence (comma `,` delimited values), it defines a monotonically increasing array of bin edges, including the rightmost edge, allowing for non-uniform bin widths.  link: https://numpy.org/doc/stable/reference/generated/numpy.histogram.html          | No | string |
| histogram_range | query |  Comma `,` delimited range of the bins.  The lower and upper range of the bins. If not provided, range is simply (a.min(), a.max()).  Values outside the range are ignored. The first element of the range must be less than or equal to the second. range affects the automatic bin computation as well.  link: https://numpy.org/doc/stable/reference/generated/numpy.histogram.html          | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return dataset's statistics. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/tiles/{TileMatrixSetId}/{z}/{x}/{y}@{scale}x.{format}

#### GET
##### Summary:

Tile

##### Description:

Create map tile from a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| z | path | TMS tiles's zoom level | Yes | integer |
| x | path | TMS tiles's column | Yes | integer |
| y | path | TMS tiles's row | Yes | integer |
| scale | path |  | Yes | integer |
| format | path |  | Yes | [ImageType](#imagetype) |
| TileMatrixSetId | path |  | Yes | [TileMatrixSetName](#tilematrixsetname) |
| buffer | query | Buffer on each side of the given tile. It must be a multiple of `0.5`. Output **tilesize** will be expanded to `tilesize + 2 * tile_buffer` (e.g 0.5 = 257x257, 1.0 = 258x258). | No | number |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/tiles/{TileMatrixSetId}/{z}/{x}/{y}@{scale}x

#### GET
##### Summary:

Tile

##### Description:

Create map tile from a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| z | path | TMS tiles's zoom level | Yes | integer |
| x | path | TMS tiles's column | Yes | integer |
| y | path | TMS tiles's row | Yes | integer |
| scale | path |  | Yes | integer |
| TileMatrixSetId | path |  | Yes | [TileMatrixSetName](#tilematrixsetname) |
| format | query | Output image type. Default is auto. | No | [ImageType](#imagetype) |
| buffer | query | Buffer on each side of the given tile. It must be a multiple of `0.5`. Output **tilesize** will be expanded to `tilesize + 2 * tile_buffer` (e.g 0.5 = 257x257, 1.0 = 258x258). | No | number |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/tiles/{TileMatrixSetId}/{z}/{x}/{y}.{format}

#### GET
##### Summary:

Tile

##### Description:

Create map tile from a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| z | path | TMS tiles's zoom level | Yes | integer |
| x | path | TMS tiles's column | Yes | integer |
| y | path | TMS tiles's row | Yes | integer |
| format | path |  | Yes | [ImageType](#imagetype) |
| TileMatrixSetId | path |  | Yes | [TileMatrixSetName](#tilematrixsetname) |
| scale | query | Tile size scale. 1=256x256, 2=512x512... | No | integer |
| buffer | query | Buffer on each side of the given tile. It must be a multiple of `0.5`. Output **tilesize** will be expanded to `tilesize + 2 * tile_buffer` (e.g 0.5 = 257x257, 1.0 = 258x258). | No | number |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/tiles/{TileMatrixSetId}/{z}/{x}/{y}

#### GET
##### Summary:

Tile

##### Description:

Create map tile from a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| z | path | TMS tiles's zoom level | Yes | integer |
| x | path | TMS tiles's column | Yes | integer |
| y | path | TMS tiles's row | Yes | integer |
| TileMatrixSetId | path |  | Yes | [TileMatrixSetName](#tilematrixsetname) |
| scale | query | Tile size scale. 1=256x256, 2=512x512... | No | integer |
| format | query | Output image type. Default is auto. | No | [ImageType](#imagetype) |
| buffer | query | Buffer on each side of the given tile. It must be a multiple of `0.5`. Output **tilesize** will be expanded to `tilesize + 2 * tile_buffer` (e.g 0.5 = 257x257, 1.0 = 258x258). | No | number |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/tiles/{z}/{x}/{y}@{scale}x.{format}

#### GET
##### Summary:

Tile

##### Description:

Create map tile from a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| z | path | TMS tiles's zoom level | Yes | integer |
| x | path | TMS tiles's column | Yes | integer |
| y | path | TMS tiles's row | Yes | integer |
| scale | path |  | Yes | integer |
| format | path |  | Yes | [ImageType](#imagetype) |
| buffer | query | Buffer on each side of the given tile. It must be a multiple of `0.5`. Output **tilesize** will be expanded to `tilesize + 2 * tile_buffer` (e.g 0.5 = 257x257, 1.0 = 258x258). | No | number |
| TileMatrixSetId | query | TileMatrixSet Name (default: 'WebMercatorQuad') | No | [TileMatrixSetName](#tilematrixsetname) |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/tiles/{z}/{x}/{y}@{scale}x

#### GET
##### Summary:

Tile

##### Description:

Create map tile from a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| z | path | TMS tiles's zoom level | Yes | integer |
| x | path | TMS tiles's column | Yes | integer |
| y | path | TMS tiles's row | Yes | integer |
| scale | path |  | Yes | integer |
| format | query | Output image type. Default is auto. | No | [ImageType](#imagetype) |
| buffer | query | Buffer on each side of the given tile. It must be a multiple of `0.5`. Output **tilesize** will be expanded to `tilesize + 2 * tile_buffer` (e.g 0.5 = 257x257, 1.0 = 258x258). | No | number |
| TileMatrixSetId | query | TileMatrixSet Name (default: 'WebMercatorQuad') | No | [TileMatrixSetName](#tilematrixsetname) |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/tiles/{z}/{x}/{y}.{format}

#### GET
##### Summary:

Tile

##### Description:

Create map tile from a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| z | path | TMS tiles's zoom level | Yes | integer |
| x | path | TMS tiles's column | Yes | integer |
| y | path | TMS tiles's row | Yes | integer |
| format | path |  | Yes | [ImageType](#imagetype) |
| scale | query | Tile size scale. 1=256x256, 2=512x512... | No | integer |
| buffer | query | Buffer on each side of the given tile. It must be a multiple of `0.5`. Output **tilesize** will be expanded to `tilesize + 2 * tile_buffer` (e.g 0.5 = 257x257, 1.0 = 258x258). | No | number |
| TileMatrixSetId | query | TileMatrixSet Name (default: 'WebMercatorQuad') | No | [TileMatrixSetName](#tilematrixsetname) |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/tiles/{z}/{x}/{y}

#### GET
##### Summary:

Tile

##### Description:

Create map tile from a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| z | path | TMS tiles's zoom level | Yes | integer |
| x | path | TMS tiles's column | Yes | integer |
| y | path | TMS tiles's row | Yes | integer |
| scale | query | Tile size scale. 1=256x256, 2=512x512... | No | integer |
| format | query | Output image type. Default is auto. | No | [ImageType](#imagetype) |
| buffer | query | Buffer on each side of the given tile. It must be a multiple of `0.5`. Output **tilesize** will be expanded to `tilesize + 2 * tile_buffer` (e.g 0.5 = 257x257, 1.0 = 258x258). | No | number |
| TileMatrixSetId | query | TileMatrixSet Name (default: 'WebMercatorQuad') | No | [TileMatrixSetName](#tilematrixsetname) |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/{TileMatrixSetId}/tilejson.json

#### GET
##### Summary:

Tilejson

##### Description:

Return TileJSON document for a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| TileMatrixSetId | path |  | Yes | [TileMatrixSetName](#tilematrixsetname) |
| tile_format | query | Output image type. Default is auto. | No | [ImageType](#imagetype) |
| tile_scale | query | Tile size scale. 1=256x256, 2=512x512... | No | integer |
| minzoom | query | Overwrite default minzoom. | No | integer |
| maxzoom | query | Overwrite default maxzoom. | No | integer |
| buffer | query | Buffer on each side of the given tile. It must be a multiple of `0.5`. Output **tilesize** will be expanded to `tilesize + 2 * tile_buffer` (e.g 0.5 = 257x257, 1.0 = 258x258). | No | number |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return a tilejson |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/tilejson.json

#### GET
##### Summary:

Tilejson

##### Description:

Return TileJSON document for a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| tile_format | query | Output image type. Default is auto. | No | [ImageType](#imagetype) |
| tile_scale | query | Tile size scale. 1=256x256, 2=512x512... | No | integer |
| minzoom | query | Overwrite default minzoom. | No | integer |
| maxzoom | query | Overwrite default maxzoom. | No | integer |
| buffer | query | Buffer on each side of the given tile. It must be a multiple of `0.5`. Output **tilesize** will be expanded to `tilesize + 2 * tile_buffer` (e.g 0.5 = 257x257, 1.0 = 258x258). | No | number |
| TileMatrixSetId | query | TileMatrixSet Name (default: 'WebMercatorQuad') | No | [TileMatrixSetName](#tilematrixsetname) |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return a tilejson |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/{TileMatrixSetId}/WMTSCapabilities.xml

#### GET
##### Summary:

Wmts

##### Description:

OGC WMTS endpoint.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| TileMatrixSetId | path |  | Yes | [TileMatrixSetName](#tilematrixsetname) |
| tile_format | query | Output image type. Default is png. | No | [ImageType](#imagetype) |
| tile_scale | query | Tile size scale. 1=256x256, 2=512x512... | No | integer |
| minzoom | query | Overwrite default minzoom. | No | integer |
| maxzoom | query | Overwrite default maxzoom. | No | integer |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/WMTSCapabilities.xml

#### GET
##### Summary:

Wmts

##### Description:

OGC WMTS endpoint.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| tile_format | query | Output image type. Default is png. | No | [ImageType](#imagetype) |
| tile_scale | query | Tile size scale. 1=256x256, 2=512x512... | No | integer |
| minzoom | query | Overwrite default minzoom. | No | integer |
| maxzoom | query | Overwrite default maxzoom. | No | integer |
| TileMatrixSetId | query | TileMatrixSet Name (default: 'WebMercatorQuad') | No | [TileMatrixSetName](#tilematrixsetname) |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/point/{lon},{lat}

#### GET
##### Summary:

Point

##### Description:

Get Point value for a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| lon | path | Longitude | Yes | number |
| lat | path | Latitude | Yes | number |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return a value for a point |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/preview.{format}

#### GET
##### Summary:

Preview

##### Description:

Create preview of a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| format | path |  | Yes | [ImageType](#imagetype) |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| max_size | query | Maximum image size to read onto. | No | integer |
| height | query | Force output image height. | No | integer |
| width | query | Force output image width. | No | integer |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/preview

#### GET
##### Summary:

Preview

##### Description:

Create preview of a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| format | query | Output image type. Default is auto. | No | [ImageType](#imagetype) |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| max_size | query | Maximum image size to read onto. | No | integer |
| height | query | Force output image height. | No | integer |
| width | query | Force output image width. | No | integer |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/crop/{minx},{miny},{maxx},{maxy}/{width}x{height}.{format}

#### GET
##### Summary:

Part

##### Description:

Create image from part of a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| minx | path | Bounding box min X | Yes | number |
| miny | path | Bounding box min Y | Yes | number |
| maxx | path | Bounding box max X | Yes | number |
| maxy | path | Bounding box max Y | Yes | number |
| format | path |  | Yes | [ImageType](#imagetype) |
| height | path |  | Yes | integer |
| width | path |  | Yes | integer |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| max_size | query | Maximum image size to read onto. | No | integer |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/crop/{minx},{miny},{maxx},{maxy}.{format}

#### GET
##### Summary:

Part

##### Description:

Create image from part of a dataset.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| minx | path | Bounding box min X | Yes | number |
| miny | path | Bounding box min Y | Yes | number |
| maxx | path | Bounding box max X | Yes | number |
| maxy | path | Bounding box max Y | Yes | number |
| format | path |  | Yes | [ImageType](#imagetype) |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| max_size | query | Maximum image size to read onto. | No | integer |
| height | query | Force output image height. | No | integer |
| width | query | Force output image width. | No | integer |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/crop/{width}x{height}.{format}

#### POST
##### Summary:

Geojson Crop

##### Description:

Create image from a geojson feature.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| format | path |  | Yes | [ImageType](#imagetype) |
| height | path |  | Yes | integer |
| width | path |  | Yes | integer |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| max_size | query | Maximum image size to read onto. | No | integer |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/crop.{format}

#### POST
##### Summary:

Geojson Crop

##### Description:

Create image from a geojson feature.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| format | path |  | Yes | [ImageType](#imagetype) |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| max_size | query | Maximum image size to read onto. | No | integer |
| height | query | Force output image height. | No | integer |
| width | query | Force output image width. | No | integer |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /cog/crop

#### POST
##### Summary:

Geojson Crop

##### Description:

Create image from a geojson feature.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| format | query | Output image type. Default is auto. | No | [ImageType](#imagetype) |
| url | query | Dataset URL | Yes | string |
| bidx | query | Dataset band indexes | No | [ integer ] |
| expression | query | rio-tiler's band math expression | No | string |
| nodata | query | Overwrite internal Nodata value | No |  |
| unscale | query | Apply internal Scale/Offset | No | boolean |
| resampling | query | Resampling method. | No | [ResamplingName](#resamplingname) |
| max_size | query | Maximum image size to read onto. | No | integer |
| height | query | Force output image height. | No | integer |
| width | query | Force output image width. | No | integer |
| rescale | query | comma (',') delimited Min,Max range. Can set multiple time for multiple bands. | No | [ string ] |
| color_formula | query | rio-color formula (info: https://github.com/mapbox/rio-color) | No | string |
| colormap_name | query | Colormap name | No | [ColorMapName](#colormapname) |
| colormap | query | JSON encoded custom Colormap | No | string |
| return_mask | query | Add mask to the output data. | No | boolean |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return an image. |
| 422 | Validation Error |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### /

#### GET
##### Summary:

Root

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |

##### Security

| Security Schema | Scopes |
| --- | --- |
| HTTPBasic | |

### Models


#### BandStatistics

Image statistics

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| min | number |  | Yes |
| max | number |  | Yes |
| mean | number |  | Yes |
| count | number |  | Yes |
| sum | number |  | Yes |
| std | number |  | Yes |
| median | number |  | Yes |
| majority | number |  | Yes |
| minority | number |  | Yes |
| unique | number |  | Yes |
| histogram | [ [  ] ] |  | Yes |
| valid_percent | number |  | Yes |
| masked_pixels | number |  | Yes |
| valid_pixels | number |  | Yes |

#### BoundingBox

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| left |  |  | Yes |
| bottom |  |  | Yes |
| right |  |  | Yes |
| top |  |  | Yes |

#### Bounds

Dataset Bounding box

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| bounds | [  ] |  | Yes |

#### ColorMapName

An enumeration.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| ColorMapName |  | An enumeration. |  |

#### Feature

Feature Model

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| type | string |  | No |
| geometry |  |  | No |
| properties | object |  | No |
| id | string |  | No |
| bbox |  |  | No |

#### FeatureCollection

FeatureCollection Model

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| type | string |  | No |
| features | [ [Feature](#feature) ] |  | Yes |
| bbox |  |  | No |

#### FeatureCollection_Union_geojson_pydantic.geometries.Point__geojson_pydantic.geometries.MultiPoint__geojson_pydantic.geometries.LineString__geojson_pydantic.geometries.MultiLineString__geojson_pydantic.geometries.Polygon__geojson_pydantic.geometries.MultiPolygon___StatisticsInGeoJSON_

FeatureCollection Model

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| type | string |  | No |
| features | [ [Feature_Union_geojson_pydantic.geometries.Point__geojson_pydantic.geometries.MultiPoint__geojson_pydantic.geometries.LineString__geojson_pydantic.geometries.MultiLineString__geojson_pydantic.geometries.Polygon__geojson_pydantic.geometries.MultiPolygon___StatisticsInGeoJSON_](#feature_union_geojson_pydantic.geometries.point__geojson_pydantic.geometries.multipoint__geojson_pydantic.geometries.linestring__geojson_pydantic.geometries.multilinestring__geojson_pydantic.geometries.polygon__geojson_pydantic.geometries.multipolygon___statisticsingeojson_) ] |  | Yes |
| bbox |  |  | No |

#### Feature_Polygon__Info_

Feature Model

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| type | string |  | No |
| geometry | [Polygon](#polygon) |  | No |
| properties | [Info](#info) |  | No |
| id | string |  | No |
| bbox |  |  | No |

#### Feature_Union_geojson_pydantic.geometries.Point__geojson_pydantic.geometries.MultiPoint__geojson_pydantic.geometries.LineString__geojson_pydantic.geometries.MultiLineString__geojson_pydantic.geometries.Polygon__geojson_pydantic.geometries.MultiPolygon___StatisticsInGeoJSON_

Feature Model

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| type | string |  | No |
| geometry |  |  | No |
| properties | [StatisticsInGeoJSON](#statisticsingeojson) |  | No |
| id | string |  | No |
| bbox |  |  | No |

#### HTTPValidationError

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| detail | [ [ValidationError](#validationerror) ] |  | No |

#### ImageType

Available Output image type.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| ImageType | string | Available Output image type. |  |

#### Info

Dataset Info.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| bounds | [  ] |  | Yes |
| minzoom | integer |  | Yes |
| maxzoom | integer |  | Yes |
| band_metadata | [ [  ] ] |  | Yes |
| band_descriptions | [ [  ] ] |  | Yes |
| dtype | string |  | Yes |
| nodata_type | [NodataTypes](#nodatatypes) |  | Yes |
| colorinterp | [ string ] |  | No |
| scale | number |  | No |
| offset | number |  | No |
| colormap | object |  | No |

#### LineString

LineString Model

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| coordinates | [  ] |  | Yes |
| type | string |  | No |

#### MetaRes

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| project_id | integer |  | Yes |
| scene_id | string |  | Yes |
| date | string |  | Yes |
| border | binary |  | Yes |
| filename | string |  | Yes |
| xg0 | number |  | Yes |
| xg1 | number |  | Yes |
| yg0 | number |  | Yes |
| yg1 | number |  | Yes |
| border_gj | string |  | Yes |

#### MultiLineString

MultiLineString Model

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| coordinates | [ [  ] ] |  | Yes |
| type | string |  | No |

#### MultiPoint

MultiPoint Model

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| coordinates | [  ] |  | Yes |
| type | string |  | No |

#### MultiPolygon

MultiPolygon Model

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| coordinates | [ [ [  ] ] ] |  | Yes |
| type | string |  | No |

#### NodataTypes

rio-tiler Nodata types.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| NodataTypes | string | rio-tiler Nodata types. |  |

#### Polygon

Polygon Model

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| coordinates | [ [  ] ] |  | Yes |
| type | string |  | No |

#### ProcRes

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| event_id | integer |  | Yes |
| status | string |  | No |
| result | string |  | No |
| params |  |  | No |
| task_id | integer |  | Yes |
| ctime | dateTime |  | Yes |
| proc_id | integer |  | Yes |
| task | string |  | No |
| title | string |  | No |
| scripts | [ [ScriptRes](#scriptres) ] |  | No |

#### Project

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| project_id | integer |  | Yes |
| login | string |  | Yes |
| name | string |  | Yes |
| start_date | string |  | No |
| end_date | string |  | No |
| border | string |  | Yes |

#### ResamplingName

An enumeration.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| ResamplingName |  | An enumeration. |  |

#### SchemeEnum

TileJSON scheme choice.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| SchemeEnum | string | TileJSON scheme choice. |  |

#### ScriptRes

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| proc_id | integer |  | Yes |
| iscript | integer |  | Yes |
| name | string |  | Yes |
| status | string |  | No |
| result | string |  | No |

#### StatisticsInGeoJSON

Statistics model in geojson response.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| statistics | object |  | Yes |

#### Task

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| name | string |  | Yes |
| descr | string |  | Yes |

#### TileJSON

TileJSON model.

Based on https://github.com/mapbox/tilejson-spec/tree/master/2.2.0

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| tilejson | string |  | No |
| name | string |  | No |
| description | string |  | No |
| version | string |  | No |
| attribution | string |  | No |
| template | string |  | No |
| legend | string |  | No |
| scheme | [SchemeEnum](#schemeenum) |  | No |
| tiles | [ string ] |  | Yes |
| grids | [ string ] |  | No |
| data | [ string ] |  | No |
| minzoom | integer |  | No |
| maxzoom | integer |  | No |
| bounds | [ number ] |  | No |
| center | [  ] |  | No |

#### TileMatrixSetName

An enumeration.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| TileMatrixSetName |  | An enumeration. |  |

#### ValidationError

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| loc | [  ] |  | Yes |
| msg | string |  | Yes |
| type | string |  | Yes |

#### geojson_pydantic__geometries__Point

Point Model

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| coordinates |  |  | Yes |
| type | string |  | No |

#### meta__dates__Res

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| dates | [ string ] |  | Yes |

#### meta__list__Res

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| metas | [ [MetaRes](#metares) ] |  | Yes |

#### proc__list__Res

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| procs | [ [ProcRes](#procres) ] |  | Yes |

#### project__info__Res

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| project_id | integer |  | Yes |
| login | string |  | Yes |
| name | string |  | Yes |
| start_date | string |  | No |
| end_date | string |  | No |
| border | string |  | Yes |
| border_gj | string |  | Yes |

#### project__list__Res

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| projects | [ [Project](#project) ] |  | Yes |

#### project__new__Params

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| name | string |  | Yes |
| start_date | string |  | No |
| end_date | string |  | No |
| border | string |  | Yes |

#### project__new__Res

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| project_id | integer |  | Yes |

#### rgb__list__Res

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| product_ids | [ string ] |  | Yes |

#### task__list__Res

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| tasks | [ [Task](#task) ] |  | Yes |

#### task__run__Params

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| task | string |  | Yes |
| title | string |  | Yes |
| project_id | integer |  | Yes |
| params |  |  | No |

#### task__run__Res

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| event_id | integer |  | Yes |

#### titiler__core__models__responses__Point

Point model.

response model for `/point` endpoints

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| coordinates | [ number ] |  | Yes |
| values | [ number ] |  | Yes |