---
up:
  - "[[Computer Graphics]]"
  - "[[wgpu]]"
  - "[[Pipeline]]"
tags: 
aliases:
  - primitive state
  - primitive
  - primitive states
date: 2023-11-18
---

> [!NOTE] this explanation is based specifically on [[Rust|Rust's]] struct 'PrimitiveState'.
# Primitive State
Defines how the [[vertices]] will be assembled and [[Rasterization| rasterized]] within a [[Pipeline|Graphic Pipeline]]

## Primitive Topologies
These are the different patterns in which vertices can be assembled to form an image.
- `PointList`: Each vertex is an individual point.
- LineList`: Each pair of vertices forms a separate line.
- LineStrip`: A continuous series of connected lines, where each line shares a vertex with the next.
- TriangleList`: Each group of three vertices forms a separate triangle.
- `TriangleStrip`: A series of connected triangles, where each new triangle shares two vertices with the previous triangle.


<!-- TODO: so far the `strip_index_format` is not that relevant, if I ever use it in the future, I will come back here to define it -->

## Front Face
is a rule that determines the front orientation of a triangle, there are 2 definitions:
- `Ccw` (counter-clockwise): The front face of triangles is defined by the vertices ordered counter-clockwise.
- `Cw` (clockwise): The front is defined by the vertices ordered clockwise.
## CullMode
After knowing which face is the front face, here we decide which of the faces will be rendered, these are the following possible options:

- `Back`: The back faces of the triangles are not rendered.
- Front`: The front faces are not rendered.
- None`: Both faces are rendered.

## Front Face and Cull Mode example:
Imagine you have a triangle formed by three points in space:

- Point A: (0,0,0).
- Point B: (1,0,0,0)
- Point C: (0,1,0)

If you list these points in your code in the order A -> B -> C, and you look at the triangle from a position where this order appears counterclockwise, then you are looking at the front of the triangle. If `FrontFace` is set to `Ccw`, then the front of the triangle is visible, and if `CullMode` is set to `Back`, the back face will not be rendered.

If you were to go around this triangle and see the points in clockwise order, then you would be looking at the back face. If `CullMode` is `Back`, this view of the triangle would not be rendered.

## Polygon Mode
defines how the primitives (triangles for example) are drawn. The options are:
- `Fill`: Triangles are filled completely.
- Line`: Only the edges of the triangles are drawn.
- Point`: Only the vertices are drawn.

## unclipped_depth (boolean option)
Defines whether to do [[clipping]] or not.

## Conservative (boolean option)
is a rasterization technique that ensures that all pixels that a triangle could cover are rendered, useful for certain optimizations. 
<!-- TODO: research more to have this concept separated out in another note -->



