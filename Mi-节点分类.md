# 节点分类

## OBJ - Object nodes（对象节点）

[网页链接](https://www.sidefx.com/docs/houdini/nodes/obj/index.html "Object nodes represent objects in the scene, such as character parts, geometry objects, lights, cameras, and so on.")

> Object nodes represent objects in the scene, such as character parts, geometry objects, lights, cameras, and so on.

对象节点代表场景中的对象，如角色部件、几何对象、灯光、摄像机等。

***

## SOP - Geometry nodes（几何节点）

[网页链接](https://www.sidefx.com/docs/houdini/nodes/sop/index.html "Geometry nodes live inside Geo objects and generate geometry.")

> Geometry nodes live inside Geo objects and generate geometry.

几何节点是存在于Geo对象内部，用于生成几何的节点。

***

## DOP - Dynamics nodes（动力学节点）

[网页链接](https://www.sidefx.com/docs/houdini/nodes/dop/index.html "Dynamics nodes set up the conditions and rules for dynamics simulations.")

> Dynamics nodes set up the conditions and rules for dynamics simulations.

动力学节点为动力学模拟设定条件和规则。

### Dynamics node (DOP) networks

> DOP networks contain [dynamics nodes](https://www.sidefx.com/docs/houdini/nodes/dop/index.html "Dynamics nodes set up the conditions and rules for dynamics simulations.") (DOPs) that create or load objects and forces, establish the connections between them, and configure solvers for simulating their interactions.
> 
> If you use dynamics shelf tools, they will create a DOP network for you if necessary. You can also create your own DOP network at any network level of the scene.
> 
> You can have multiple DOP networks containing separate simulations. The [dynamics menu](https://www.sidefx.com/docs/houdini/dyno/index.html "How to use Houdini’s dynamics networks to create simulations.") lets you choose which network the shelf tools use.

DOP网络中包含着动力学节点（DOPs），这些节点可以创建或加载对象及力，建立他们之间的连接，并配置求解器来模拟它们之间的相互作用。

如果你使用动力学工具架，它们会在必要时为你创建一个DOP网络。你也可以在任意层级的场景中创建自己的DOP网络。

你可以有多个包含独立模拟的DOP网络。动力学菜单允许您选择使用哪个网络工具架。

***

## VOP - Shader nodes（着色器节点）

[网页链接](https://www.sidefx.com/docs/houdini/nodes/vop/index.html "VOP nodes let you define a program (such as a shader) by connecting nodes together. Houdini then compiles the node network into executable VEX code.")

> VOP nodes let you define a program (such as a shader) by connecting nodes together. Houdini then compiles the node network into executable VEX code.

VOP节点让你通过将节点连接在一起来定义一个程序（如着色器）。然后，胡迪尼将节点网络编译成可执行的VEX代码。


> See [working with VOP nodes](https://www.sidefx.com/docs/houdini/shade/vops.html "Tips for working with shaders in the VOP network.") for information on VOP node features in the network editor.

有关网络编辑器中的VOP节点特性的信息，请参见使用VOP节点。

### VEX networks

[网页链接](http://127.0.0.1:48626/nodes/vex/index.html "Containers for VOP networks.")

> These nodes are containers for VOP networks.

这些节点是VOP网络的容器。

***

## LOP - USD nodes（USD节点）

[网页链接](https://www.sidefx.com/docs/houdini/nodes/lop/index.html "LOP nodes generate USD describing characters, props, lighting, and rendering.")

> LOP nodes generate USD describing characters, props, lighting, and rendering.

LOP节点生成描述角色、道具、照明和渲染的USD。

***

## ROP - Render nodes（渲染节点）

[网页链接](https://www.sidefx.com/docs/houdini/nodes/out/index.html "Render nodes either render the scene or set up render dependency networks.")

> Render nodes either render the scene or set up render dependency networks.

渲染节点可以渲染场景或设置渲染依赖网络。

### Render node (ROP) network

> Render networks contain render nodes (ROPs), which represent rendering jobs. Different nodes launch different renderers (for example, mantra or RenderMan). The node parameters specify options such as the frame range to render and the output filename.
> 
> Houdini creates a default render network at `/out`. Items in the top-level **Render** menu let you create and edit render nodes in this network. You can also create your own ROP networks at any level of the scene. For example, you might embed a render node in an asset as part of an ability to generate its own textures.
> 
> The ROP level does not require you to connect nodes: each node represents a renderer and configuration you can use to render the scene. However, you can connect ROP nodes together to create [dependency graphs](http://127.0.0.1:48626/render/batch.html), allowing you to define dependency relationships between render passes.

渲染网络中包含着渲染节点（ROPs），它们代表渲染工作。不同的节点启动不同的渲染器（例如mantra或RenderMan）。节点的参数指定了一些选项，例如要渲染的帧范围和输出的文件名。

胡迪尼在`/out`中创建了一个默认的渲染网络。顶层的Render菜单中的项目允许你创建和编辑这个网络中的渲染节点。你也可以在场景的任意层级中创建自己的ROP网络。例如，你可以在一个资产中嵌入一个渲染节点，作为其生成自身纹理能力的一部分。

ROP层不需要你连接节点：每个节点代表一个你可以用来渲染场景的渲染器和配置。不过你也可以将ROP节点连接起来创建依赖图，这将允许你定义渲染通道之间的依赖关系。

***

## CHOP - Channel nodes（通道节点）

[网页链接](https://www.sidefx.com/docs/houdini/nodes/chop/index.html "Channel nodes create, filter, and manipulate channel data.")

> Channel nodes create, filter, and manipulate channel data.

通道节点创建、过滤和操作通道数据。

***

### Channel node (CHOP) networks

> A CHOP network contains [channel nodes](http://127.0.0.1:48626/nodes/chop/index.html "Channel nodes create, filter, and manipulate channel data.") (CHOPs) for manipulating time-based channel data such as animation curves or audio.
> 
> Houdini creates a default CHOP network at `/ch`. You can also create your own CHOP networks at any level of the scene (for example, inside a character to control kinematics).
> 
> [Wiring](http://127.0.0.1:48626/network/wire.html "How to connect nodes to each other to make them work together.") CHOPs together controls the flow of channel data, from nodes that load or fetch the channel data through nodes that modify the channels.
> 
> You can view the data generated by a CHOP network in the Motion FX View tab.

一个CHOP网络中包含着通道节点（CHOPs），用于操作基于时间的通道数据，例如动画曲线或音频。

胡迪尼在`/ch`中创建了默认的CHOP网络。你也可以在场景的任意层级中创建你自己的CHOP网络（例如在一个角色内部用于控制运动学）。

将CHOPs连接起来，可以在节点的加载或获取通道数据节点到修改通道的节点之间控制通道数据的流动。

你可以在Motion FX View标签中查看CHOP网络生成的数据。

***

## COP2 - Compositing nodes（合成节点）

[网页链接](https://www.sidefx.com/docs/houdini/nodes/cop2/index.html "Composite nodes create, filter, and manipulate image data.")

> Composite nodes create, filter, and manipulate image data.

复合节点创建、过滤和处理图像数据。

### Compositing node (COP) networks

> A COP network contains [compositing nodes](http://127.0.0.1:48626/nodes/cop2/index.html "Composite nodes create, filter, and manipulate image data.") (COPs) for manipulating 2D pixel data. This is useful for compositing images such as render passes, but you can also use COPs to manipulate other pixel-based data, such as depth maps.
> 
> Houdini creates a default compositing network at `/img`. You can also create your own COP networks at any level of the scene (for example, next to a render node that uses the COP network to process its output).
> 
> [Wiring](http://127.0.0.1:48626/network/wire.html "How to connect nodes to each other to make them work together.") COPs together controls the flow of image data, from nodes that load or generate image data through nodes that modify the i.

一个COP网络中包含着合成节点（COPs），用于操作二维像素数据。这对合成图像很有用，例如渲染通道，但你也可以用COP来操作其他基于像素的数据，例如深度图。

胡迪尼在`/img`中创建了默认的合成网络。你也可以在场景的任意层级中创建你自己的COP网络（例如，在渲染节点旁使用COP网络去处理它的输出）。

将COPs连接起来，可以在加载或生成图像数据的节点至修改i的节点之间控制图像数据的流动。

***

## TOP - Task nodes（任务节点）

[网页链接](https://www.sidefx.com/docs/houdini/nodes/top/index.html "TOP nodes define a workflow where data is fed into the network, turned into work items and manipulated by different nodes. Many nodes represent external processes that can be run on the local machine or a server farm.")

> TOP nodes define a workflow where data is fed into the network, turned into work items and manipulated by different nodes. Many nodes represent external processes that can be run on the local machine or a server farm.

TOP节点定义了一个工作流程，数据被送入网络，变成工作项目并被不同的节点操作。许多节点代表外部进程，可以在本地机器或服务器群上运行。

### Task node (TOP) networks

> TOP networks contain task nodes that represent a series of tasks or _work items_ to be performed. There are four main types of TOP node: _processors_ that generate work items, _schedulers_ that run the work item’s jobs, _partitioners_ that join together incoming work items, and _mappers_ that establish dependencies between otherwise unrelated work items.
> 
> With a TOP node network, you can create a scalable recipe for generating work items, running them locally or on a farm, establishing the network of dependencies between all the work items, and figuring out how to do it all as efficiently as possible. This recipe is called a _PDG_ (Procedural Dependency Graph). For more information about TOPs and PDG, see [Intro to TOPs](http://127.0.0.1:48626/tops/intro.html "Explains the basic concepts behind TOP networks and what you can do with them.").
> 
> Houdini creates a default task network (`/topnet1`) at `/tasks`, and a default scheduler (`localscheduler`) at `/tasks/topnet1`. Much like ROPs, you can create a standalone TOP network at any level of the scene. For example, you can create a TOP network in the `/stage` context to generate variations of LOP prims for a Solaris project.
> 
> The TOP level requires that you connect your nodes, all except for schedulers.

TOP网络包含着代表一系列要执行的任务或工作项目的任务节点。TOP节点主要有四种类型：生成工作项的处理器、运行工作项目任务的调度器、将传入的工作项目连接在一起的分区器，以及在其他不相关的工作项之间建立依赖关系的映射器。

通过TOP节点网络，你可以创建一个可扩展的流程，用于生成工作项目，并在本地或外包机器上运行它们，建立所有工作项目之间的依赖关系网络，并找出如何尽可能高效地完成这一切，这个流程被称为PDG（程序化依赖图）。关于TOPs和PDG的更多信息，请参阅TOPs介绍。

胡迪尼在`/tasks`中创建了一个默认的任务网络（`/topnet1`），并在`/tasks/topnet1`中创建了一个默认的调度器（`localscheduler`）。与ROPs非常相似，你也可以在场景的任意层级中创建一个独立的TOP网络。例如，你可以在`/stage`上下文中创建一个TOP网络，为一个Solaris项目生成LOP基元的变化。

TOP层要求你除了调度器之外，连接所有的节点。