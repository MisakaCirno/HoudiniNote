# Hair and fur（头发和毛皮）

[Hair and fur (sidefx.com)](https://www.sidefx.com/docs/houdini/fur/index.html)

How to create, style, and add dynamics to hair and fur.
如何为头发和毛皮创造、样式化并添加动态。

The tools the **Hair Utils** shelf let you quickly set up hair and fur objects, jump between objects, as well as animate and simulate. The tools on the **Guide Process** tab are used to style the fur, as they let you influence the placement and orientation of guide hairs by painting skin attributes.
==利用工具架上的**Hair Utils**工具，可以让你快速设置头发或毛皮对象，在对象之间跳转，并创建动画和模拟。在**Guide Process**分页里的工具可以为毛皮设置样式，它们可以通过绘制皮肤属性来影响毛皮的朝向与位置。==

To create fur, start with a piece of geometry and use the [Add Fur](https://www.sidefx.com/docs/houdini/shelf/groom_addfur.html "Adds fur to a surface.") tool on the **Hair Utils** shelf. By default, two nodes are created: [Guide Groom](https://www.sidefx.com/docs/houdini/nodes/obj/guidegroom.html "Generates guide curves from a skin geometry and does further
processing on these using an editable SOP network contained within the node.") and [Hair Generate](https://www.sidefx.com/docs/houdini/nodes/obj/hairgen.html "Generates hair from a skin geometry and guide curves.").
==要创建毛皮，需要从一块几何体开始，使用工具架上的**Hair Utils**中的Add Fur。默认情况下会创建Guide Groom和Hair Generate两个节点。==

![[Pasted image 20220217164614.png]]

The Guide Groom and Hair Generate networks have the exact same set up with the exact same workflow, except the hair generation network has less outputs. This makes it very simple to use, since everything is done in SOPs with curves. The [Guide Process](https://www.sidefx.com/docs/houdini/nodes/sop/guideprocess.html "Modifies guide or hair using one or more operations.") node lets you layer many different operations, and very easily control where the operation takes place along the curve using ramps or by painting attributes on the skin. This allows you to easily create natural looking hair and fur very quickly.
==Guide Groom和Hair Generate网络的设置完全相同，工作流程也完全相同，只是Hair Generate网络的输出较少。这使得它的使用非常简单，因为一切都在带有曲线的SOPs里完成。导向处理节点可以让你把许多不同的操作分层，并且非常容易通过斜坡或在皮肤上绘制属性来控制沿着曲线的效果。这能使你很容易快速地创建自然的头发和毛皮。==


One improvement is that there is no longer a separation between manipulating guide curve geometry or painting skin attributes. Everything flows through a single graph. All of the components that make up the groom are displayed in a single network. Each of the nodes also have at least 3 inputs and 3 outputs, which allows the 3 types of data to flow through the nodes. This results in a very clean and easy to read network, and eliminates the need to reference other nodes. Another advantage is that the operators can be placed in any order, which gives you complete control and flexibility.
==一个改进是在操作引导曲线几何形状和绘制皮肤属性之间不再有分隔。所有流程都在一个图形中。构成梳理毛发的组件也都在一个网络中。每个节点也至少有3个输入和3个输出，这使得三种类型的数据可以流经节点。这使得网络非常干净，可读性也非常高，并消除了其他节点的需求。另一个优点是，操作者可以按任何顺序放置，这提升了灵活性的同时也使你能完全掌控。==

![[Pasted image 20220217171258.png]]

> Note
> Mantra uses the SOP network you create to do the grooming and does the cooking of the node network (SOP network) at render time. It does this without taking a license, which allows for rendering with Engine for hair, fur, and anything else that’s comprised of curves and points (grass).

==Mantra使用你创建的SOP网络来梳理，并在渲染的时候对节点网络（SOP网络）进行烘焙。它这样做是不需要授权的，这样就可以用引擎来渲染头发、毛皮和一切由曲线和点组成的东西（例如草地）。 ==

> Note
> Grooming should always be done on the static mesh, not the animated mesh.

==梳理应该在静态网格上完成，而不是在动画网格上。==

---

## WORKING WITH FUR（使用毛皮）
- [Fur workflow（毛皮的工作流程）](https://www.sidefx.com/docs/houdini/fur/workflow.html)
    
- [Creating and styling guide hair with Guide Groom（用Guide Groom创建毛发并添加样式）](https://www.sidefx.com/docs/houdini/fur/groom.html)
    
- [Painting masks to control attributes（绘制遮罩用以控制属性）](https://www.sidefx.com/docs/houdini/fur/masking.html)
    
- [Generating hair cards for games（为游戏生成毛发卡片）](https://www.sidefx.com/docs/houdini/fur/haircards.html)
    

## SHELF TOOLS FOR CREATING FUR（创建毛发的工具架）
- [Add Fur（添加毛皮）](https://www.sidefx.com/docs/houdini/shelf/groom_addfur.html "Adds fur to a surface.")
Adds fur to a surface.
==在曲面上添加毛皮。==

- [Create Guides（创建导向）](https://www.sidefx.com/docs/houdini/shelf/groom_guidegroom.html "Creates a guide curves from a skin geometry or manipulates the guides of another groom object.")
Creates a guide curves from a skin geometry or manipulates the guides of another groom object.
==从皮肤的几何上创建引导线或操作另一个梳理对象的导向。==

- [Groom（梳理）](https://www.sidefx.com/docs/houdini/shelf/groom_groom.html "Creates a Guide Groom SOP ready to draw & brush curves. ")
Creates a Guide Groom SOP ready to draw & brush curves.
==创建导向梳理SOP，为绘制或刷曲线做准备。==

## SHELF TOOLS FOR STYLING WITH GUIDE PROCESSES（用于导向程序进行样式化的工具架）
- [Initialize Guides（初始化导向）](https://www.sidefx.com/docs/houdini/shelf/sop_groom_guideinit.html "Gives the guides an initial direction.")
Gives the guides an initial direction.
==给导向一个初始的方向。==
    
- [Curve Advect（曲线平移）](https://www.sidefx.com/docs/houdini/shelf/sop_groom_curveadvect.html "Advects curves using a vector field generated from curves drawn on the skin surface.")
Advects curves using a vector field generated from curves drawn on the skin surface.
==使用从皮肤曲面上绘制的曲线产生的矢量场来对曲线进行平移。==
    
- [Groom（梳理）](https://www.sidefx.com/docs/houdini/shelf/groom_groom.html "Creates a Guide Groom SOP ready to draw & brush curves. ")
Creates a Guide Groom SOP ready to draw & brush curves.
==创建导向梳理SOP，为绘制或刷曲线做准备。==
    
- [Reguide（调整导向）](https://www.sidefx.com/docs/houdini/shelf/reguide.html "Interpolates guides between planted guides.")
Interpolates guides between planted guides.
==在已有的导向之间插补导向。==
    
- [Set Guide Direction（设置导向朝向）](https://www.sidefx.com/docs/houdini/shelf/sop_groom_guideprocess_setdir.html "Points guides in the direction of a vector.")
Points guides in the direction of a vector.
==将导向的方向指向一个向量。==
    
- [Set Guide Length（设置导向长度）](https://www.sidefx.com/docs/houdini/shelf/sop_groom_guideprocess_length.html "Lengthens or shortens guide hairs.")
Lengthens or shortens guide hairs.
==延长或索道导向的长度。==
    
- [Lift Guides（提升导向）](https://www.sidefx.com/docs/houdini/shelf/sop_groom_guideprocess_lift.html "Lifts curves off the skin or flattens them against it.")
Lifts curves off the skin or flattens them against it.
==将曲线从皮肤上抬起来或压平到皮肤上。==
    
- [Straighten Guides（拉直导向）](https://www.sidefx.com/docs/houdini/shelf/sop_groom_guideprocess_straighten.html "Straightens the hair by bending each segment back so that it’s in the same direction as the previous segment.")
Straightens the hair by bending each segment back so that it’s in the same direction as the previous segment.
==通过将每段毛发向后弯曲，使其与前段毛发一致来拉直。==
    
- [Smooth Guides（平滑导向）](https://www.sidefx.com/docs/houdini/shelf/sop_groom_guideprocess_smooth.html "Blends the shapes of the neighboring guides to create a smoother look. ")
Blends the shapes of the neighboring guides to create a smoother look.
==混合相邻导向的形状，创造一个更平滑的效果。==
    
- [Frizz Guides（卷曲导向）](https://www.sidefx.com/docs/houdini/shelf/sop_groom_guideprocess_frizz.html "Offsets the curve points along the guide hairs to create a frizzy look.")
Offsets the curve points along the guide hairs to create a frizzy look.
==偏移沿着导向头发的曲线点，以创造一个毛躁的外观。==
    
- [Bend Guides（弯曲导向）](https://www.sidefx.com/docs/houdini/shelf/sop_groom_guideprocess_bend.html "Bends curves in a certain direction and by a certain angle. ")
Bends curves in a certain direction and by a certain angle.
==将曲线像某个方向或某个角度弯曲。==
    
- [Clump Guides（丛状导向）](https://www.sidefx.com/docs/houdini/shelf/sop_groom_hairclump.html "Creates bunches of guide hairs. ")
Creates bunches of guide hairs.
==创建成束的导向头发。==
    
- [Part Guides（分割导向）](https://www.sidefx.com/docs/houdini/shelf/drawpartingline.html "Lets you draw a parting line on the skin geometry.")
Lets you draw a parting line on the skin geometry.
==允许你在皮肤几何上绘制一条分割线。==
    
- [Add White Hairs（添加白色毛发）](https://www.sidefx.com/docs/houdini/shelf/sop_groom_whitehair.html "Adds the required attribute to mark hairs as white hairs in the standard hair shader.")
Adds the required attribute to mark hairs as white hairs in the standard hair shader.
==添加所需的属性，在标准毛发着色器中，把标记的毛发转换为白色。==

## SHELF TOOLS FOR ANIMATING AND SIMULATING FUR（用于制作皮毛动画和模拟的工具架）
- [Deform Guides（变形导向）](https://www.sidefx.com/docs/houdini/shelf/groom_animateguides.html "Creates a Guide Deform object in the network.")
Creates a Guide Deform object in the network.
==在网络中创建一个导向变形对象。==
    
- [Simulate Guides（模拟导向）](https://www.sidefx.com/docs/houdini/shelf/groom_simguides.html "Adds physics simulation to a set of guides.")
Adds physics simulation to a set of guides.
==为导向添加物理学模拟。==
    

## HOW TO（如何）
- [How to create hair styled like dreadlocks（如何创建类似辫子的头发样式）](https://www.sidefx.com/docs/houdini/fur/hairstyle_rasta.html)

- [How to create fur on a teddy bear（如何给泰迪熊添加毛发）](https://www.sidefx.com/docs/houdini/fur/teddybear.html)