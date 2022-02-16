# Object-level characters（对象层级角色）

[Object-level characters (sidefx.com)](https://www.sidefx.com/docs/houdini/character/object_level/index.html)

Object-level rigging and animation with bone-based rigs.
==对象层级基于骨骼绑定的绑定与动画。==

***

Character setup and animation involves three stages: rigging, animation, and finaling.
==角色的设置和动画包括了三个阶段：绑定、动画和收尾。==

In Houdini, you usually separate the responsibilities of technical setup of a character and the creative animation process with [digital assets](https://www.sidefx.com/docs/houdini/assets/index.html "Digital assets let you create reusable nodes and tools from existing networks.").
==在胡迪尼中，通常会让你将角色的技术设置和数字资产的创意动画两者的责任分开。==

The technical director can encapsulate characters as digital assets so to the animators the character becomes just like any other Houdini tool, with its own interface.
==技术总监可以将角色封装为数字资产，因此对于动画师来说，角色就像其他的胡迪尼工具一样，有着自己的接口。==

This lets the TD promote handles and parameter controls to the asset’s interface for use by animators, and the animator can use this high-level interface while the TD or rigger continues to refine the rigging, capturing, and facial setup.
==这可以让技术总监将控制资产的参数放到接口上，以供动画师使用，而动画师可以在技术总监或绑定师在继续完善绑定、捕捉和面部设置时，继续使用这个高级别的接口。==

As new versions of the character are completed, you can seamlessly update the asset to make the latest controls available to the animators. You can also use this technique to animate with lo-fi characters and swap in hi-fi characters at render time.
==当角色的新版本完成后，你可以无缝地更新资产，使动画师可以获得最新的控制。你也可以使用这种技术，用低保真角色做动画，并在渲染的时候更换为高保真角色。==

## RIGGING（绑定）
- [Building rigs（创建绑定）](https://www.sidefx.com/docs/houdini/character/object_level/buildingrigs.html)


- [Capture Skin（捕获皮肤）](https://www.sidefx.com/docs/houdini/character/object_level/captureskin.html)


- [Facial Rigging（脸部绑定）](https://www.sidefx.com/docs/houdini/character/object_level/facialrigging.html)


- [Lattice deformer（晶格变形器）](https://www.sidefx.com/docs/houdini/character/object_level/latticedeformer.html)


- [Make a character into a digital asset（将角色转换为数字资产）](https://www.sidefx.com/docs/houdini/character/object_level/digitalassets.html)


- [Capture pipeline strategies（捕获管线策略）](https://www.sidefx.com/docs/houdini/character/object_level/pipeline.html)


- [Constraints（限制条件）](https://www.sidefx.com/docs/houdini/character/object_level/constraints.html)



## PANES（窗格）

- [Rig Tree View（绑定树视图）](https://www.sidefx.com/docs/houdini/character/rigtreeview.html)
【[[rigtreeview.html_Character Rig Tree View]]】
    
- [Auto Rigs（自动绑定）](https://www.sidefx.com/docs/houdini/character/autorigs.html)
    
- [Character Picker（角色选择器）](https://www.sidefx.com/docs/houdini/character/charpicker.html)
    
- [Pose Library（动作库）](https://www.sidefx.com/docs/houdini/character/poselibrary.html)
    
- [Pose-Space Deformation（动作空间变换）](https://www.sidefx.com/docs/houdini/character/posespacedeform.html)
    

## ANIMATION（动画）

- [Animation Overview（动画预览）](https://www.sidefx.com/docs/houdini/character/object_level/animationoverview.html)
    
- [Getting Started（开始工作）](https://www.sidefx.com/docs/houdini/character/object_level/starthere.html)
    
- [Proximity, Pills, and Painting（靠近、药丸和绘制）](https://www.sidefx.com/docs/houdini/character/object_level/proximityvspills.html)
    
- [Playbar（播放条）](https://www.sidefx.com/docs/houdini/character/object_level/playbar.html)
    
- [Blending（混合器）](https://www.sidefx.com/docs/houdini/character/object_level/blending.html)
    
- [Pose tool（动作工具）](https://www.sidefx.com/docs/houdini/character/object_level/pose_tool.html "The Pose tool is used to pose characters by manipulating objects.")
The Pose tool is used to pose characters by manipulating objects.
==动作工具用于操纵物体来摆出任务的动作。==
    
- [Posing a character（为角色添加动作）](https://www.sidefx.com/docs/houdini/character/object_level/pose.html)
    
- [Channel List（通道列表）](https://www.sidefx.com/docs/houdini/character/object_level/scoping.html)
    
- [Keyframing（关键帧）](https://www.sidefx.com/docs/houdini/character/object_level/keyframing.html)
    
- [Graph Editor（图像编辑器）](https://www.sidefx.com/docs/houdini/character/object_level/grapheditor.html)
    
- [Motion Path handles（运动路径控制器）](https://www.sidefx.com/docs/houdini/basics/motionpath.html "Showing a Motion Path handle for an object lets you visualize and modify the object’s path through space over the course of the animation.")
Showing a Motion Path handle for an object lets you visualize and modify the object’s path through space over the course of the animation.
==显示一个物体的运动路径控制器，可以让你直观地看到并修改物体的该物体在动画过程中的空间路径。==
    
- [Cycling Animation（循环动画）](https://www.sidefx.com/docs/houdini/character/object_level/cycling.html)
    
- [Animation Layer Mixer（动画层级混合器）](https://www.sidefx.com/docs/houdini/character/object_level/animlayer.html)
    
- [Channel Groups（通道组）](https://www.sidefx.com/docs/houdini/character/object_level/channelgroups.html)
    
- [Motion capture（运动捕捉）](https://www.sidefx.com/docs/houdini/character/object_level/motioncapture.html)
    
- [Using Onion Skinning（使用洋葱剥皮法）](https://www.sidefx.com/docs/houdini/character/object_level/onionskinning.html)