# Working with objects（处理对象）

[Working with objects (sidefx.com)](https://www.sidefx.com/docs/houdini/basics/objects.html)

****
## Overview（概述）
Objects are the top level representations of things in the scene. They have location, rotation, and scale in world space.
==对象是场景中事物的最高级别的代表。它们在世界空间中具有位置、旋转和比例。==

## Geometry containers and surface nodes（几何容器和表面节点）
Models in Houdini are represented by [Geometry objects](https://www.sidefx.com/docs/houdini/nodes/obj/geo.html "Container for the geometry operators (SOPs) that define a modeled
 object.") at the scene level. Inside a geometry container object, [geometry nodes](https://www.sidefx.com/docs/houdini/nodes/sop/index.html "Geometry nodes live inside Geo objects and generate geometry.") define the geometry of the object. The geometry container object lets you translate (move, rotate, and/or scale) and shade the entire object, as opposed to individual surfaces inside the object.
==胡迪尼中的模型是由场景级别的几何对象表示的。在一个几何容器对象内，由几何节点定义了对象的几何形状。几何容器对象可以让您变换（移动、旋转和缩放）和隐藏整个对象，而不是对象内的单独的表面。==

When you use the [shelf tools](https://www.sidefx.com/docs/houdini/shelf/index.html "How to use and customize the icons on the shelf at the top of the main window.") Houdini will create geometry containers with surface nodes inside for you. For example, clicking the _Sphere_ tool on the shelf creates a new container named `object_sphere1`, with a [sphere surface node](https://www.sidefx.com/docs/houdini/nodes/sop/sphere.html "Creates a sphere or ovoid surface.") inside named `sphere1` that defines the sphere geometry.
==当您使用工具架时，胡迪尼会为你创建内部有有曲面节点的几何容器。例如，点击工具架上的 _Sphere_ 工具，就会创建一个名为 `object_sphere1`的新容器，里面有一个名为`sphere1`的球体曲面节点，定义了球体的几何形状。==

Note that the object container and the surface nodes inside each have their own parameters. In some cases, the functionality of the parameters might seem to overlap at first. With only one sphere inside the sphere node’s **Center** parameter, which sets the sphere’s location, has the same effect as the container object’s **Translate** parameter, which moves the entire object. Similarly, the container object’s **Scale** parameter sets the size of the entire object, while the sphere node’s **Radius** parameter sets the size of the sphere inside.
==请注意，对象容器和里面的曲面节点都有自己的参数。在某些情况下，参数的功能一开始可能会出现重叠的情况。在内部只有一个球体的情况下，球体节点的**Center**参数（设置球体的位置）与容器对象的**Translate**参数（移动整个对象）具有相同的效果。同样地，容器对象的**Scale**参数设置整个对象的大小，而球体节点的**Radius**参数设置里面的球体大小。==

** Moving between the container object and the surface nodes inside（在容器对象和内部曲面节点之间移动）**
讲的是操作，略过。

## Transforming objects vs. surfaces（对比变换物体与变换曲面）
Keep in mind that the normal unit of transformation (moving, rotating, and scaling) is the _object_. Transforming surfaces at the Geometry level (for example, using the [Transform surface node](https://www.sidefx.com/docs/houdini/nodes/sop/xform.html "The Transform operation transforms the source geometry in object space using a transformation matrix.")) is more accurately _deformation_, and can potentially take much longer for Houdini to calculate than just transforming static object geometry at the scene level.
==请记住，变换（移动、旋转和缩放）的正常单元是_对象_。在几何级别的曲面上进行变换（例如使用变换曲面节点）是更准确的_变形_，相比于对于变换场景级别的静态几何对象来说，这可能会让胡迪尼花费更多的时间去计算。==

This is not to say that transforming at the geometry level is bad: often you _need_ an object’s shape to deform over time. However, you should remember to look for opportunities to accomplish your goals by transforming objects before you look at transforming surfaces, because the former is more efficient.
==这并不是说在几何级别上进行变换是不好的：往往你会_需要_一个物体的形状随着时间而改变。但是，你应该记住，当你考虑对曲面进行变换之前，先尝试寻找机会通过变换对象来达到你的目标，因为这样的效率更高。==

## Parenting（创建父子关联）
#翻译问题
Parenting makes a child object’s transformations (moves, rotations, and scales) relative to those of a parent object.
==创建父子关联可以使一个子对象的变换（移动、旋转和缩放）是相对于父对象的。==

Connecting the output of object A to the input of object B makes object A the _parent_ of object B. For example, to view the scene from the point of view of a particular object, you can parent the camera to the POV object so the camera transforms with the object.
==将对象A的输出连接到对象B的输入，会使对象A成为对象B的_父级_。例如，为了从某个特定的视角来观察创场景中的对象，你可以将相机作为POV对象的子级，这样摄像机就会随着对象的变换而变换。【不确定】==

❀
**Note（注意）**
In computer graphics, we say that we “parented” B to A. This might seem backwards, but that’s the way it is.
==在计算机图形学中，我们说将“parented” B to A。这可能看起来很反常，但是事情就是这样的。==
❀

An object which is _parented to_ (that is, the child of) another object inherits the transformations of the parent object. Moving or rotating the parent moves/rotates the child as well.
==一个对象如果是另一个对象的子节点，它就会继承父对象的变换。移动或旋转父对象，也会移动/旋转子对象。==

You can also put objects inside an object subnetwork (use the [tab menu](https://www.sidefx.com/docs/houdini/basics/tabmenu.html) to create a Subnet node at the object level). All objects inside the subnetwork inherit the transform of the subnet’s parent, if any.
==你也可以把对象放在一个对象子网络中（使用Tab菜单在对象层级创建一个子网络节点）。如果子网络有父对象的话，那么子网络内所有对象都会继承父对象的变换。==

Some other information is inherited from parent objects besides transformations. For example, motion blur can be inherited from a parent object. If the rendering parameters are not enabled for an object, they will be inherited from the parent object.
==除了变换之外，还有一些信息也是从父对象那里继承的。例如，运动模糊可以从父对象中继承。如果一个对象的渲染参数没有被启用，它们也将从父对象中继承。==

Each object can have only one parent, however the [Blend object](https://www.sidefx.com/docs/houdini/nodes/obj/blend.html "Switches or blends between the transformations of several input objects.") lets you blend between the transforms of multiple parents.
==每个对象只能有一个父对象，但混合对象可以让你在多个父对象的变换之间进行混合。==

#### How to
讲的是操作，略过。

#### Keep position and child compensation（保持位置与子节点补偿）
When you parent an object, its transforms become relative to the parent. This means the object might jump to a new position/rotation in the scene. From then on, changes to the parent will affect the position of the child, and changes to the child’s transforms will be relative to the parent.
==当你为一个对象添加父对象时，它的变换是相对于父对象的。这意味着该对象可能会在场景中跳到一个新的位置或改变朝向。从那时起，对父对象的改变将影响到子对象的位置，而对子对象的变换是相对于父对象的。==

There are two settings that can change these behaviors.
- Keep position when parenting
If you turn this on, when you parent an object, Houdini automatically modifies its transforms so it maintains its old position and rotation.

- Child compensation
If you turn this on, when you move a parent object, Houdini automatically modifies the transforms of its children so they keep their positions (instead of moving relative to the parent).

==有两种设置可以改变这些行为。==
- ==保持建立关系之前的位置==
==如果你打开了这个选项，当你为一个对象添加父对象时，胡迪尼会自动改变它的变换，使其保持原来的位置和朝向。==
- ==子节点补偿==
==如果你打开了这个选项，当你移动一个父对象时，胡迪尼会自动修改其子对象的变换，使它们保持相应的位置（而不是相对于父对象移动）。==

You can change both settings on individual objects, or turn them on or off globally in the “Objects and Geometry” page of the main preferences.
==你可以为单个对象设置这两个参数，或在主偏好设置中的“Objects and Geometry”页面为全局设置它们。==


