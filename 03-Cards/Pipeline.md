---
up:
  - "[[Computer Graphics]]"
  - "[[WebGPU]]"
  - "[[wgpu]]"
tags: 
aliases:
  - pipeline
  - pipelines
date: 2023-11-18
---
> [!NOTE] this explanation is based on the [[Rust]] struct *`RenderPipelineDescriptor`*. 
# Pipeline
A series of steps that a graphics [[API]] (such as [[wgpu]]) uses to convert [[vertices]] into an on-screen image.

High-level steps:

1. **Vertex Fetching**: Vertices are loaded from buffers.
2. **Vertex Shading**: Vertices are processed by a vertex [[vertex shader]].
3. **Primitive Assembly**: Vertices are assembled into geometric [[Primitive State|primitive]] (such as triangles).
4. **Rasterization**: The [[Primitive State|primitives]] are converted into pixels.
5. **Fragment Shading**: Pixels are processed by a [[fragment shader]] to produce colors. 
6. **Blending and Output**: Colors are blended in the [[framebuffer]].
