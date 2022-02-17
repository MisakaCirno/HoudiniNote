# Geometry（几何）

[Geometry (sidefx.com)](https://www.sidefx.com/docs/houdini/model/index.html)

How Houdini represents geometry and how to create and edit it.
==胡迪尼如何表示几何，以及如何创建和编辑几何。==

***

## UNDERSTANDING（理解）

- [Working with objects（处理对象）](https://www.sidefx.com/docs/houdini/basics/objects.html)
【[[object.html_Working with objects]]】
    
- [Primitives（基元）](https://www.sidefx.com/docs/houdini/model/primitives.html)
    
- [Points and vertices（点和顶点）](https://www.sidefx.com/docs/houdini/model/points.html)
    
- [Geometry attributes（几何属性）](https://www.sidefx.com/docs/houdini/model/attributes.html "Describes how Houdini represents geometry using details, primitives, points, vertices, and attributes.")  
 Describes how Houdini represents geometry using details, primitives, points, vertices, and attributes.
==描述胡迪尼如何使用细节、基元、点、顶点和属性表示几何。==
    
- [Groups（组）](https://www.sidefx.com/docs/houdini/model/groups.html)
    
- [Volumes（体积）](https://www.sidefx.com/docs/houdini/model/volumes.html)

## MODELING（建模）

- [Create geometry（创建几何）](https://www.sidefx.com/docs/houdini/model/create.html)
    
- [Edit geometry（编辑几何）](https://www.sidefx.com/docs/houdini/model/edit.html)
    
- [Edit components（编辑组件）](https://www.sidefx.com/docs/houdini/model/edit_points.html)
    
- [Reselect geometry（重新选择几何）](https://www.sidefx.com/docs/houdini/model/reselect.html "In Houdini you can not only edit the parameters of a surface node, you can reselect the geometry the operation applies to.")
In Houdini you can not only edit the parameters of a surface node, you can reselect the geometry the operation applies to.
==在胡迪尼中，你不仅可以编辑曲面节点的参数，还可以重新选择所适用的几何。==

- [Box up modeling（基于多边形建模）](https://www.sidefx.com/docs/houdini/model/box_up_modeling.html)
    
- [Curve up modeling（基于曲线建模）](https://www.sidefx.com/docs/houdini/model/curve_up_modeling.html)
    
- [Mirror geometry across a symmetry plane（在对称平面上镜像几何）](https://www.sidefx.com/docs/houdini/model/mirror.html)
    
- [Repair polygonal models（修复多边形模型）](https://www.sidefx.com/docs/houdini/model/repair_polys.html)
    
- [Snapping, construction plane, and alignment（捕捉、构造面与对齐）](https://www.sidefx.com/docs/houdini/model/aids.html)
    
- [Trim NURBS surfaces（修建NURBS曲面）](https://www.sidefx.com/docs/houdini/model/trim_nurbs.html)

## TERRAIN（地形）

- [Building terrain with height fields（用高度场构建地形）](https://www.sidefx.com/docs/houdini/model/heightfields.html "How to use Houdini’s height field tools to generate realistic terrain.")
How to use Houdini’s height field tools to generate realistic terrain.
==如何使用胡迪尼高度场工具来生成真实的地形。==
    
- [Realistic terrain with heightfields（用高度场构建真实的地形）](https://www.sidefx.com/docs/houdini/model/terrain_workflow.html "A heuristic workflow using the heightfield tools, based on experience generating realistic-looking terrain.")
A heuristic workflow using the heightfield tools, based on experience generating realistic-looking terrain.
根据生成逼真地形的经验，启发式的高度场工具使用流程。
	
## FRACTURING（碎裂）
See [Destruction](https://www.sidefx.com/docs/houdini/destruction/index.html "How to break different types of materials.")
==详见破坏==

## NEXT STEPS（更进一步）
- [Import geometry from other objects（从其他对象中导入几何）](https://www.sidefx.com/docs/houdini/model/object_merge.html)

- [Create, edit, and use Null objects（创建、编辑并使用空对象）](https://www.sidefx.com/docs/houdini/model/nulls.html)

- [Geometry appearance editor（几何外观编辑器）](https://www.sidefx.com/docs/houdini/model/appearance.html "The appearance editor mode of the data tree pane lets you edit various controls for object viewport/rendered appearance in one place.")
The appearance editor mode of the data tree pane lets you edit various controls for object viewport/rendered appearance in one place.
数据树窗格的外观编辑器模式可以让你在一个地方编辑对象视口/渲染外观的各种控制。

- [Locking geometry nodes（锁定几何节点）](https://www.sidefx.com/docs/houdini/model/lock_nodes.html)

## GURU LEVEL（大师级）
- [Packed primitives（打包基元）](https://www.sidefx.com/docs/houdini/model/packed.html)

- [Looping in geometry networks（几何网络中的循环）](https://www.sidefx.com/docs/houdini/model/looping.html)

- [Compiled blocks（编辑块）](https://www.sidefx.com/docs/houdini/model/compile.html "You can mark a chain of compilable SOPs as a compiled block which can execute much faster in parallel.")
You can mark a chain of compilable SOPs as a compiled block which can execute much faster in parallel.
==你可以将一个可编译的SOPs链标记为一个编译块，这样可以更快地执行。==

- [Programmatic geometry with verbs（动态程序化几何）](https://www.sidefx.com/docs/houdini/model/verbs.html "Many geometry (SOP) nodes allow you to use them in Python scripts to generate geometry programmatically.")
Many geometry (SOP) nodes allow you to use them in Python scripts to generate geometry programmatically.
==许多几何（SOP）节点允许你在Python脚本中使用他们，并用编程的方式生成几何。==

- [Primitive Parametric Spaces (Implicit UVs)（基元参数空间（隐式UVs））](https://www.sidefx.com/docs/houdini/model/primitive_spaces.html)

- [Speed vs. reproducibility in Math Kernel Library（数学内核库的速度与可重复性）](https://www.sidefx.com/docs/houdini/model/mkl.html "Some nodes use a library that gives a speed boost for floating-point operations but can make the output vary between different computers. You can control how much the library tries to guarantee reproducible results.")
Some nodes use a library that gives a speed boost for floating-point operations but can make the output vary between different computers. You can control how much the library tries to guarantee reproducible results.
==一些节点使用了库，以追求对浮点运算的速度提升，但这会导致在不同的计算机上输出有所不同。你可以调整该库在多大程度上保证结果的可重复性。==

## See also（扩展阅读）
- [Interface basics（界面基础）](https://www.sidefx.com/docs/houdini/basics/index.html)
- [Copying and instancing（复制与实例化）](https://www.sidefx.com/docs/houdini/copy/index.html)
- [Surface nodes（曲面节点）](https://www.sidefx.com/docs/houdini/nodes/sop/index.html)