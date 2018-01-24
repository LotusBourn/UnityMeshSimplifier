# UnityMeshSimplifier
Mesh simplification for [Unity](https://unity3d.com/). The project is written entirely in C# and released under the MIT license.

## Compatibility
These scripts have been tested and confirmed working with Unity 2017.2 and Unity 2017.3

## Installation into Unity project
1. Copy the contents of this repository into a folder named *UnityMeshSimplifier* in your Assets directory within your Unity project.
2. You are done!

## How do I use this?
```c#
float quality = 0.5f;
var meshSimplifier = new UnityMeshSimplifier.MeshSimplifier();
meshSimplifier.Initialize(sourceMesh);
meshSimplifier.SimplifyMesh(quality);
var destMesh = meshSimplifier.ToMesh();
```

or

```c#
float quality = 0.5f;
var meshSimplifier = new UnityMeshSimplifier.MeshSimplifier();
meshSimplifier.Vertices = vertices;
meshSimplifier.AddSubMeshTriangles(indices);
meshSimplifier.SimplifyMesh(quality);
var newVertices = meshSimplifier.Vertices;
var newIndices = meshSimplifier.GetSubMeshTriangles(0);
```

## Fast Quadric Mesh Simplification Algorithm
UnityMeshSimplifier is based on the [Fast Quadric Mesh Simplification](https://github.com/sp4cerat/Fast-Quadric-Mesh-Simplification) algorithm, completely rewritten in C#.