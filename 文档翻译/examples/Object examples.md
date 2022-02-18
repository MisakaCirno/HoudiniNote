# Object examples

[Object examples (sidefx.com)](https://www.sidefx.com/docs/houdini/examples/nodes/obj/index.html)

***

## Agent Cam（代理摄像机）

[CrowdPov（群众视角）](https://www.sidefx.com/docs/houdini/examples/nodes/obj/agentcam/CrowdPov.html)
Example for [Agent Cam](https://www.sidefx.com/docs/houdini/nodes/obj/agentcam.html) object node

This example demonstrates how the agent cam can be assigned to a crowd agent to give you the point of view from someone in a crowd simulation.
==这个例子演示了如何将代理摄像机分配给人群代理，让你在看到人群模拟中某个人的视角。==
>创建模拟人群，然后设置为其中某一个人的视角。
>![[Pasted image 20220218145704.png|400]]

## Environment Light（环境光）

[PortalBox（入口箱子）](https://www.sidefx.com/docs/houdini/examples/nodes/obj/envlight/PortalBox.html) 
Example for [Environment Light](https://www.sidefx.com/docs/houdini/nodes/obj/envlight.html) object node

This example shows how to create a portal light using window geometry. A box is modeled and then split into 2 SOPs - one representing windows and the other walls. The walls are rendered, while the windows are used to specify the portal for an environment light. Toggle on and off the portal to see the render quality difference while rendering in the Render View.
==这个例子演示了如何使用窗户几何体来创建一个门灯。创建一个盒子的模型，然后分割成两个SOPs，一个代表窗户，另一个代表墙壁。墙壁被渲染，而窗户被用来指定环境光的入口。在渲染视图中，切换入口的开启和关闭以查看渲染质量的差异。==
>一个盒子，盒子上有一些开口，开口被设置为光源。
>![[Pasted image 20220218152540.png|400]]

## Extract Transform（提取变换）

[extracttransform（提取变换）](https://www.sidefx.com/docs/houdini/examples/nodes/obj/extractgeo/extracttransform.html) 
Example for [Extract Transform](https://www.sidefx.com/docs/houdini/nodes/obj/extractgeo.html) object node

This example shows how to parent geometry to a moving piece of geometry that is defined by a prebaked .bgeo sequence.
==这个例子演示了如何将几何体作为另一个移动的几何体的父级，这个几何体是由一个预先烘焙的.bgeo序列定义的。==
>效果是将一个物体的位移信息复制给另一个物体。
>![[Pasted image 20220218153208.png|400]]

## Light（灯光）

[TransparentShadows（透明阴影）](https://www.sidefx.com/docs/houdini/examples/nodes/obj/hlight/TransparentShadows.html)
Example for [Light](https://www.sidefx.com/docs/houdini/nodes/obj/hlight.html) object node

This example shows how to configure transparent shadows with deep shadow maps. The scene includes a transparent grid which casts a shadow on the scene. The renderer used is micropolygon rendering.
==这个例子演示了如何用深度阴影贴图配置透明阴影。该场景包括一个透明的网格，它在场景上投下了阴影。使用的渲染器是micropolygon。==
>光透过带颜色的半透明网格后落下带颜色的投影。
>![[Pasted image 20220218153511.png|400]]

## Indirect Light（间接光照）

[IndirectLightBox（间接光盒）](https://www.sidefx.com/docs/houdini/examples/nodes/obj/indirectlight/IndirectLightBox.html)
Example for [Indirect Light](https://www.sidefx.com/docs/houdini/nodes/obj/indirectlight.html) object node

This example shows how to set up the indirectlight object for indirect diffuse lighting. The scene consists of a box that has been extruded several times, containing a light source and the camera. The light has been placed so that all light reaching the camera must bounce more than once inside the scene before reaching the camera. The indirectlight object is configured to generate 1000000 photons. To visualize the photon map, change the rendering mode on the light to “Direct Global Photon Map”. To adjust the sampling quality, modify the pixel samples or ray samples on the mantra ROP. The rendering engine used in this example is PBR.
==这个例子展示了间接漫反射光设置间接光对象。场景由一个被挤出了几次的盒子，一个光源和一个摄像机组成。光源的放置使得所有光线在进入相机之前，都必须在场景中反弹一次以上。间接光对象被设置为产生100万个光子。为了使光子图可视化，将灯光的渲染模式改为“Direct Global Photon Map”。要调整采样质量，可以修改mantra ROP上的像素采样或光线采样。本例中使用的渲染引擎是PBR。==
>类似于室内场景的光线多次反弹的效果
>![[Pasted image 20220218153852.png|400]]

[TubeCaustic（管道聚焦）](https://www.sidefx.com/docs/houdini/examples/nodes/obj/indirectlight/TubeCaustic.html)
Example for [Indirect Light](https://www.sidefx.com/docs/houdini/nodes/obj/indirectlight.html) object node

This example shows how to set up the indirectlight object for caustic photon map generation and also how light masks and photon targets should be used. The scene consists of a reflective tube and a point and environment light. Each light has a corresponding indirectlight to generate caustics, with the light mask configured to allow the light to generate photons only from the specified light. The photon target is used to ensure that photons are only sent toward the reflective tube. The mantra ROP will produce deep raster planes for the direct_diffuse component on a per-light basis, showing the diffuse illumination from the two lights and the caustics split into separate planes.
==这个例子展示了如何设置间接光对象以生成聚焦光子图，以及如何使用光照遮罩及光子目标。该场景由一个反射管、一个点光源和环境光组成。每个光源都有一个相应的间接光来生成聚焦，光照遮罩是为了只让特定的光源中生成光子。光子目标用于确保光子只向反射管发射。mantra ROP将在每个光的基础上为direct_diffuse组件生成有深度的光栅平面，显示两盏灯的漫反射光和聚焦分割成单独的平面。==
>内容是一个玻璃圆台在光照下的折射阴影效果。
>![[Pasted image 20220218145008.png|400]]

## Path（路径）

[PathPathcvWorm（蠕虫路径）](https://www.sidefx.com/docs/houdini/examples/nodes/obj/path/PathPathcvWorm.html)
Example for [Path](https://www.sidefx.com/docs/houdini/nodes/obj/path.html) object node

This example shows a use for the Path and Pathcv nodes. These Path CV’s can be rotated greater than 360. They also have an initial twist function under the controls tab. This can be useful for creating a quick spine.
==这个例子展示了Path和Pathcv节点的作用。这些路径CV的旋转幅度可以大于360度。它们在控制选项卡下也有一个初始的扭转功能。这对于快速创建一个脊柱是很有用的。==
>类似于一条蠕虫扭曲的效果。
>![[Pasted image 20220218154115.png|400]]

## Rivet（铆钉）

[RivetWaveform（铆钉在波浪上）](https://www.sidefx.com/docs/houdini/examples/nodes/obj/rivet/RivetWaveform.html)
Example for [Rivet](https://www.sidefx.com/docs/houdini/nodes/obj/rivet.html) object node

In this example, a Waveform deformer is applied to a grid. A Rivet is then attached to the surface of the grid, and then parented to a sphere.
==在这个例子中，网格被赋予了一个波浪变形器。而一个铆钉被附加在网格的表面上，并在铆钉上添加了一个球体。==
>类似于波浪起伏的效果，球会贴在平面上。
>![[Pasted image 20220218155236.png|400]]

## Sticky（粘性）

[StickyDonut（粘性甜甜圈）](https://www.sidefx.com/docs/houdini/examples/nodes/obj/sticky/StickyDonut.html)
Example for [Sticky](https://www.sidefx.com/docs/houdini/nodes/obj/sticky.html) object node

In this example, a donut is stuck to an animated sticky object on the surface of a grid.
==在这个例子中，一个甜甜圈被站在一个动画粘性对象的网格表面上。==
>大概是模拟移动中的阻力效果。
>![[Pasted image 20220218155902.png|400]]

## Switcher（切换器）

[switchcamera（切换相机）](https://www.sidefx.com/docs/houdini/examples/nodes/obj/switcher/switchcamera.html)
Example for [Switcher](https://www.sidefx.com/docs/houdini/nodes/obj/switcher.html) object node

In this example, we demonstrate how a switcher node can be used to switch the view between two cameras and then used by the render node to output the scene.
==在这个例子中，我们演示了如何使用切换器节点来在两个相机之间切换视图，然后用渲染节点来输出场景。==
>场景中有两个相机，在播放动画的中间切换为另一个相机。
>![[Pasted image 20220218160203.png|400]]

## /nodes/vop/surfacemodel（曲面模型）

[RainbowGeometryLight（彩虹几何体灯光）](https://www.sidefx.com/docs/houdini/examples/nodes/obj/hlight/RainbowGeometryLight.html)
This example highlights several features:

- Geometry area lights
- Attenuation ramp controls
- Surface model specular layers
- ==几何区域光==
- ==斜坡控制衰减==
- ==表面模型镜面层==

The example consists of a geometry light based on a wireframe of nurbs curves. The attenuation on the light uses colored keys, allowing for different light colors to be produced at different distances from the light. The ground plane shader uses a surface model with two specular components - one wide component and another narrower glossy component to give a multi-layered appearance.
==这个例子包括了一个基于nurbs曲线线框的几何体灯光。灯光的衰减使用彩色键，这允许在距离灯光不同的地方产生不同的灯光颜色。地面的着色器使用了具有两个镜面组件的表面模型——一个宽的和另一个较窄的光滑组件，以获得一个多层次的外观。==
>彩虹效果。
>![[Pasted image 20220218160456.png|400]]