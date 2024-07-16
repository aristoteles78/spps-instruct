# Spatial functions

Spatial functions can be used with geospatial data. For example, they allow you to calculate the distances between two points, the area of a polygon, and so on.

There can also be situations that require a merge of multiple geospatial data sets that are based on a spatial predicate (within, close to, and so on), which can be done through a merge condition.

## Notes

These spatial functions don't apply to three-dimensional data. If you import three-dimensional data into a flow, only the first two dimensions are used by these functions. The z-axis values are ignored.
Geospatial functions aren't supported.

## Table 1. CLEM spatial functions

| Function                      | Return Type | Description                                                                                                                                                                                                                         |
| ----------------------------- | ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `close_to(SHAPE, SHAPE, NUM)` | Boolean     | Tests whether 2 shapes are within a certain DISTANCE of each other. If a projected coordinate system is used, DISTANCE is in meters. If no coordinate system is used, it is an arbitrary unit.                                      |
| `crosses(SHAPE, SHAPE)`       | Boolean     | Tests whether 2 shapes cross each other. This function is suitable for 2 linestring shapes, or 1 linestring and 1 polygon.                                                                                                          |
| `overlap(SHAPE, SHAPE)`       | Boolean     | Tests whether there is an intersection between 2 polygons and that the intersection is interior to both shapes.                                                                                                                     |
| `within(SHAPE, SHAPE)`        | Boolean     | Tests whether the entirety of SHAPE1 is contained within a POLYGON.                                                                                                                                                                 |
| `area(SHAPE)`                 | Real        | Returns the area of the specified POLYGON. If a projected system is used, the function returns meters squared. If no coordinate system is used, it is an arbitrary unit. The shape must be a POLYGON or a MULTIPOLYGON.             |
| `num_points(SHAPE, LIST)`     | Integer     | Returns the number of points from a point field (MULTIPOINT) which are contained within the bounds of a POLYGON. SHAPE1 must be a POLYGON or a MULTIPOLYGON.                                                                        |
| `distance(SHAPE, SHAPE)`      | Real        | Returns the distance between SHAPE1 and SHAPE2. If a projected coordinate system is used, the function returns meters. If no coordinate system is used, it is an arbitrary unit. SHAPE1 and SHAPE2 can be any geo measurement type. |
