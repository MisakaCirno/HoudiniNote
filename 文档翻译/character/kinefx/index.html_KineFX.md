# KineFX

[KineFX (sidefx.com)](https://www.sidefx.com/docs/houdini/character/kinefx/index.html)

Procedural rigging and animation with SOP-based characters and rigs.
==基于SOP的绑定实现的几何级别程序化绑定和添加动画。==

***

## What is KineFX?（什么是KineFX？）

KineFX is a rigging and animation framework and toolset that allows you to create and edit characters all at the _geometry-level_. You can use special KineFX SOPs and regular stock Houdini SOPs together to edit imported characters and animation or create your own KineFX characters from scratch.
==KineFX是一个绑定、动画框架和工具集，它允许你在几何层面上创建和编辑角色。你可以使用特殊的FineFX SOPs 和普通的Houdini SOPs一起来编辑导入的角色和动画，或者从头开始创建你自己的KineFX角色。==

For definitions of KineFX terminology, see the [Glossary](https://www.sidefx.com/docs/houdini/character/kinefx/glossary.html).
==有关FineFX的术语，请参见术语表。==


## What is procedural rigging?（什么是程序化绑定？）

The KineFX framework is built on the principles of _procedural rigging_. Procedural rigging allows you to iterate on your rigs quickly, experiment non-destructively, and explore set-ups without having to fear that you will break anything like you would with a static graph system. For example, with KineFX you can reconfigure a rig while animating, delete entire parts of an animated hierarchy and not lose its capture (skin) or animation, or unparent all your points and retain their positions (world space transforms).
==KineFX框架是建立在程序化绑定的框架之上的。_程序化绑定_ 允许你快速迭代你的绑定，进行非破坏性的实验并探索设置，而不必担心你会像静态图形系统那样破坏任何东西。例如，在KineFX中，你可以在制作动画时重新绑定，删除动画层次的整个部分而不会丢失其捕获（皮肤）或动画，或者解除所有点的父子关系而保留它们的位置（世界空间变换）。==

With KineFX, joint data is simpler, the transform model is simpler, your input stream is always there and you will never lose your original data, everything by default lives in world space (but it is easy to switch between world and local), and the framework is attribute-driven by nature.
==使用KineFX，联合数据更简单，变换模型更简单，你的输入流总是在那里，你永远不会丢失原始数据，所有东西默认存在于世界空间中（但很容易在世界和本地之间切换），而框架本质是上通过属性驱动的。==


## What is animation retargeting?（什么是动画重定向？）

Retargeting is the process by which you take the animation from one character and transfer it to a different character.
==重定向是指将一个角色的动画转移到另一个角色的过程。==

Since KineFX is a robust and flexible system, it can handle many possible differences in morphology and hierarchical structure between the source and target characters.
==由于KineFX是一个强大而灵活的系统，它可以处理原角色和目标角色之间在形态和层次结构上许多可能的差异。==

## PROCEDURAL RIGGING（程序化绑定）

- [Working with skeletons（制作骨骼）](https://www.sidefx.com/docs/houdini/character/kinefx/skeletons.html)
    
- [Setting up control shapes（设置控制形状）](https://www.sidefx.com/docs/houdini/character/kinefx/controlshapes.html)
    
- [Constraints（限制条件）](https://www.sidefx.com/docs/houdini/character/kinefx/constraints.html)
    
- [Blend shapes（混合形状）](https://www.sidefx.com/docs/houdini/character/kinefx/blendshapes.html)
    
- [KineFX glossary（KineFX 术语表）](https://www.sidefx.com/docs/houdini/character/kinefx/glossary.html)
    

## COMPATIBILITY（适应性）

- [Transitioning from KineFX v18.5 to v19（将KineFX从v18.5转移到v19）](https://www.sidefx.com/docs/houdini/character/kinefx/compatibility.html)
    

## ANIMATION RETARGETING（动画重定向）

- [Importing animation and character data（导入动画和角色数据）](https://www.sidefx.com/docs/houdini/character/kinefx/importcharacters.html)
    
- [Transferring animation（转移动画）](https://www.sidefx.com/docs/houdini/character/kinefx/retargeting.html)
    
- [Refining the retarget result（完善重定向结果）](https://www.sidefx.com/docs/houdini/character/kinefx/retargetcleanup.html)
    
- [Posing characters and layering animation（摆放角色和分层动画）](https://www.sidefx.com/docs/houdini/character/kinefx/posing.html)
    
- [Working with motion capture（制作动作捕捉）](https://www.sidefx.com/docs/houdini/character/kinefx/motioncapture.html)
    
- [Adding secondary motion effects to characters（为角色添加二次运动效果）](https://www.sidefx.com/docs/houdini/character/kinefx/secondarymotion.html)
    
- [Setting up ragdoll simulations for characters（为角色设置布娃娃模拟）](https://www.sidefx.com/docs/houdini/character/kinefx/ragdoll.html)
    
- [Exporting animation and character data（导出动画和角色数据）](https://www.sidefx.com/docs/houdini/character/kinefx/exportcharacters.html)
    

## PANES（窗格）

- [Character Rig Tree View（角色绑定树状图）](https://www.sidefx.com/docs/houdini/character/rigtreeview.html)
【[[rigtreeview.html_Character Rig Tree View]]】
    
- [Geometry Spreadsheet pane（几何电子数据表窗格）](https://www.sidefx.com/docs/houdini/ref/panes/geosheet.html)
    
- [Animation Editor（动画编辑器）](https://www.sidefx.com/docs/houdini/ref/panes/animeditor.html)