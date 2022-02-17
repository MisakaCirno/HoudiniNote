# Solaris

[Solaris (sidefx.com)](https://www.sidefx.com/docs/houdini/solaris/index.html)

Solaris is the umbrella name for Houdini’s scene building, layout, lighting, and rendering tools based on the Universal Scene Description (USD) framework.
==Solaris是胡迪尼基于通用场景描述（USD）框架的场景构建、布局、光照和渲染工具的总称。==

**This is a WORK IN PROGRESS.**
==**这是一个正在完成的项目**==

---

## USD
- [USD Basics（USD基础）](https://www.sidefx.com/docs/houdini/solaris/usd.html "Introduces a number of USD concepts, and how they relate to Houdini’s USD support.")
Introduces a number of USD concepts, and how they relate to Houdini’s USD support.
==介绍一些USD的概念以及它们与胡迪尼提供的USD之间的关系。==

- [How LOPs work（LOPs如何工作）](https://www.sidefx.com/docs/houdini/solaris/about_lops.html "How Solaris LOP (lighting operator) nodes work to generate/modify USD.")
How Solaris LOP (lighting operator) nodes work to generate/modify USD.
==介绍Solaris LOP（光照操作）节点是如何生成/修改USD的。==

- [Solaris user interface（Solaris的用户界面）](https://www.sidefx.com/docs/houdini/solaris/ui.html "Guide to using the user interface to interact with LOP networks and USD data.")
Guide to using the user interface to interact with LOP networks and USD data.
==使用户界面与LOP网络及USD数据互通的指南。==

- [Primitive Matching Patterns（基元匹配模式）](https://www.sidefx.com/docs/houdini/solaris/pattern.html "How to use the USD primitive matching syntax.")
How to use the USD primitive matching syntax.
==如何使用USD的基元匹配语法。==

- [LOPS and USD Glossary（LOPs和USD术语）](https://www.sidefx.com/docs/houdini/solaris/glossary.html)

- [Solaris scene viewer（Solaris场景查看器）](https://www.sidefx.com/docs/houdini/solaris/view.html "Describes the differences/enhancements in the Solaris viewer compared to the Houdini object/SOP viewer.")
Describes the differences/enhancements in the Solaris viewer compared to the Houdini object/SOP viewer.
==介绍了Solaris查看器与Houdini中对象和SOP查看器的区别与改进。==

- [Using VEX With USD（在USD中使用VEX）](https://www.sidefx.com/docs/houdini/solaris/vex.html)

- [Writing out USD（编写USD）](https://www.sidefx.com/docs/houdini/solaris/output.html)

 
## GEOMETRY（几何）
- [Importing SOP geometry into USD（将SOP几何导入至USD中）](https://www.sidefx.com/docs/houdini/solaris/sop_import.html "Details of how Houdini converts SOP geometry to USD, and how you can control the process.")
Details of how Houdini converts SOP geometry to USD, and how you can control the process.
==详细介绍了胡迪尼如何将SOP几何转换为USD，以及如何控制这个过程。==

- [Component Builder（组件生成器）](https://www.sidefx.com/docs/houdini/solaris/component_builder.html "The Component Builder tool puts down a network snippet for creating a USD model from SOPs, with support for materials, variants, payloads, and layering.")
The Component Builder tool puts down a network snippet for creating a USD model from SOPs, with support for materials, variants, payloads, and layering.
==组件生成器会生成一个网络片段，用于从SOPs中创建USD模型，并支持材质、变量、负载和层级。==
  

## LAYOUT（布局）
- [Edit node（编辑节点）](https://www.sidefx.com/docs/houdini/nodes/lop/edit.html "Interactively transforms prims in the viewer. Can use physics collisions to position props realistically.")
Interactively transforms prims in the viewer. Can use physics collisions to position props realistically.
==在查看器中交互式地变换基元。可以使用物理学碰撞来真实地定位道具。==

- [Layout node（布局节点）](https://www.sidefx.com/docs/houdini/nodes/lop/layout.html "Provides tools for populating a scene with instanced USD assets. You can place individual components, paint/scatter components in different ways using customizable brushes, and edit existing instances.")
Provides tools for populating a scene with instanced USD assets. You can place individual components, paint/scatter components in different ways using customizable brushes, and edit existing instances.
==提供了用实例化USD资产来填充场景的工具。你可以放置单独的组件，使用自定义笔刷以不同的方式绘制或散布组件，并编辑现有的实例。==

- [Custom Layout Brushes（自定义布局笔刷）](https://www.sidefx.com/docs/houdini/solaris/layout_brush.html "How to create layout brush digital assets you can use to customize the behavior of the Layout LOP.")
How to create layout brush digital assets you can use to customize the behavior of the Layout LOP.
==如何创建可以用来定制LOP布局行为的布局笔刷数字资产。==

## SHADING（渲染）
- [Shader Framework（渲染框架）](https://www.sidefx.com/docs/houdini/solaris/shader_framework.html "Describes the Solaris shading framework, including shader node translation to USD primitives.")
Describes the Solaris shading framework, including shader node translation to USD primitives.
介绍了Solaris的渲染框架，包括渲染节点如何转换为USD基元。

- [Using MaterialX with Karma（使用Karma的MaterialX）](https://www.sidefx.com/docs/houdini/solaris/materialx.html "Houdini has VOP node equivalents of the MaterialX shader nodes. You can build a shader network using these nodes, or import an existing MaterialX shader, and use them with Karma (Houdini’s USD renderer).")
Houdini has VOP node equivalents of the MaterialX shader nodes. You can build a shader network using these nodes, or import an existing MaterialX shader, and use them with Karma (Houdini’s USD renderer).
胡迪尼有相当于MaterialX渲染节点的VOP节点。你可以使用这些节点建立一个渲染网络，或者导入一个现有的MaterialX渲染器，并将它们用于Karma（胡迪尼的USD渲染器）。

- [/solaris/materialx_nodes（MaterialX节点）](https://www.sidefx.com/docs/houdini/solaris/materialx_nodes.html)


## KARMA RENDERING（Karma渲染）
- [Karma](https://www.sidefx.com/docs/houdini/solaris/karma.html "Houdini’s Physically Based USD Renderer.")
Houdini’s Physically Based USD Renderer.
胡迪尼基于物理的USD渲染器。

- [Karma XPU alpha preview（Karma XPU alpha预览）](https://www.sidefx.com/docs/houdini/solaris/karma_xpu.html)

- [Setting up custom AOVs in Karma（在Karma中设置自定义的AOVs）](https://www.sidefx.com/docs/houdini/solaris/karma_aovs.html)

- [Cryptomatte（隐蔽性）](https://www.sidefx.com/docs/houdini/solaris/cryptomatte.html "How to generate image maps associating each pixel in the image with the object name and/or material in the original source scene.")
How to generate image maps associating each pixel in the image with the object name and/or material in the original source scene.
在原始原场景中，如何将图像中每个像素与对象名称和/或材料生成一个映射图。

- [Creating a lens shader for Karma（为Karma创建镜头着色器）](https://www.sidefx.com/docs/houdini/solaris/karma_lens_shader.html)

- [Karma filters（Karma过滤器）](https://www.sidefx.com/docs/houdini/solaris/filters.html)


## TUTORIALS（教程）
- [LOPs Introduction Tutorials（LOPs介绍教程）](https://www.sidefx.com/docs/houdini/solaris/tutorials.html)

- [LOPs for Lighting（LOPs的光照）](https://www.sidefx.com/docs/houdini/solaris/tutorial-lighting-1.html)