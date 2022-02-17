# Dynamics（动力学）

[Dynamics (sidefx.com)](https://www.sidefx.com/docs/houdini/dyno/index.html)

How to use Houdini’s dynamics networks to create simulations.
==如何使用胡迪尼中的动力学网络创建模拟==

In Houdini you use dynamics networks to create simulations. You create _simulation objects_ and apply one or more _solvers_ to the objects. Houdini has objects and solvers for many different types of simulation, such as cloth, rigid bodies, wires, and fluids. There are also specialized solvers for integrating dynamics with other parts of Houdini, such as script solvers, geometry solvers, particle solvers, and Python solvers.
==在胡迪尼中，你可以使用动力学网络来创建模拟。你可以创建模拟对象，并将一个或多个求解器应用到对象上。胡迪尼有许多不同类型的模拟对象和求解器，如布料、刚体、线和流体。还有一些专门的求解器，用于将动力学与胡迪尼的其他部分结合起来，例如脚本求解器、及和求解器、粒子求解器和Python求解器。==

The most basic dynamics setup is a single simulation object wired to a solver, with a force applied.
==最基本的动力学设置是将单个的模拟对象与一个求解器相连，并为其施加一个力。==

![[Pasted image 20220216185600.png]]

> **DOP Object node（DOP对象节点）**
> A container for data. Specific object nodes import geometry data and set up configuration data for a certain type (RBD object, Cloth object, etc.).
> ==一个数据的容器。为某一类型（RBD对象、布料对象等）导入几何数据并设定配置数据的特殊对象节点。==
> 
> **Merge node（合并节点）**
> The shelf tools automatically create merge nodes between the objects and the solvers. These allow you to use the same solver for multiple objects. DOP merge nodes also set up relationships (usually collision relationships) between the merged objects.
> ==工具架上的图标会自动在对象与求解器之间创建合并节点。这允许你对多个对象使用同一个求解器。DOP合并节点还设置了合并对象之间的关系（通常是碰撞关系）。==
> 
> **Solver node（求解器节点）**
> Attaches data to the object saying this object's position etc. should be calculated using this solver.
> 将数据附加到对象上，表示这个对象的位置等信息，应该使用求解器计算。
> 
> **Grey connectors（灰色连接器）**
> Repersent the object through the network, with each node attaching data to the object.
> 通过网络复制对象，每个节点都会附加数据给对象。
> 
> **Force node（力节点）**
> Attaches data to the object saying that this force is acting on the object.
> 将数据附加到对象上，表示这个力作用在对象上。


Dynamic simulations can also have *constraints*, which constrain one object’s position based on another object’s position. For example, a spring constraint creates the effect of two objects connected by an invisible spring.
==动力学模拟也可以有*约束*，即根据一个对象的位置来约束另一个对象的位置。例如，一个弹簧约束可以创建出两个对象被一根不可视的弹簧连接起来的效果。==

Constraints are a type of *relationship*. Simulation objects can also have *collision* relationships. For example, [rigid body objects](https://www.sidefx.com/docs/houdini/dyno/rbd.html) and fluid simulations can affect each other.
==约束是一种*关系*的类型。模拟对象也可以有*碰撞*关系。例如，刚体对象和流体模拟可以相互影响。==

You can apply *forces* to simulation objects. Simulation objects with different solvers can share the same forces, and you can apply multiple forces to each object.
==你可以为模拟对象施加*力*。相同的力可以施加给有着不同求解器的模拟对象，并且你也可以给每个对象施加多个力。==

Dynamics networks establish a tree of objects with data applied. The viewport shows you the animated geometry created by the simulation. The [details view](https://www.sidefx.com/docs/houdini/ref/windows/index.html "Documents the options in various user interface windows.") shows you all the simulation data applied to each object at the current time in a spreadsheet format.
==动力学网络会用应用数据建立一个对象树。在视口中向你展示模拟生成的几何动画。当前时间内应用于每个对象的所有模拟数据，会在细节视图中以电子表格形式显示。==
![[Pasted image 20220217142323.png]]

You can add drag, wind, impulse (push force), fields, fans, and other forces (see the **Drive simulation** tab).
==你可以添加阻力、风、冲击力（推力）、场、风扇和其他力（详见**驱动模拟**标签）。==

There are many ways to wire a DOP network to get the same result. Nodes that attach data only attach it to the objects that pass through their grey inputs. So you can, for example, limit which objects a certain force applies to by placing the force node at different points in the network,*and/or* by using the force node’s **Group** parameter to set a node name pattern to control which objects it applies to.
==有很多方法可以给DOP网络布线以获得相同的结果。附加数据的节点只附加在通过其灰色输入的物体上。这样你就可以做出例如通过将力节点放在网络中的不同位置，*和/或*通过使用力节点的**组**参数来设定哪些力施加在对象的哪个组上。==

For example, in the following network, the `gravity1` force applies to both `sphere_object1` and `box_object1` because both object’s are eventually wired into it. However, the `fan1` force only applies to `sphere_object1`, because it is the only object that is wired through `fan1`.
==例如，在下面的网络中，`gravity1`力同时作用在`sphere_object1`和`box_object1`上，因为这两个物体最终都连接到它了。而`fan1`力只作用在`sphere_object1`上，因为它只连接到了`fan1`。==
![[Pasted image 20220217143555.png]]

Time-dependent expressions work slightly differently in dynamics. Instead of `$F` (current frame) and `$T` (current time), you should use `$SF` (simulation frame) and `$ST` (simulation time). This is because Houdini’s dynamics engine will sometimes move backwards and forwards in time to resolve collisions. When this happens, `$F` might, say, change to frame 12 twice. `$SF` and `$ST` only ever increase.
==与时间相关的表达式在动力学中的使用方法略有不同。你应该使用`$SF` （模拟帧）和 `$ST`（模拟时间）来代替`$F` （当前帧）和`$T` （当前时间）。这是因为胡迪尼的动力学引擎有时会在时间上向前和向后移动，来解决碰撞问题。当这种时候，可能会出现`$F`变成12两次，而`$SF`和`$ST`则只会增加。==

***

## LEARNING DYNAMICS（学习动力学）

- [Top ten basic things about dynamics（关于动力学的十大基本知识）](https://www.sidefx.com/docs/houdini/dyno/top10_basics.html)
    
- [Top ten intermediate things about dynamics（关于动力学的十大中级知识）](https://www.sidefx.com/docs/houdini/dyno/top10_medium.html)
    
- [Top ten advanced things about dynamics（）关于动力学的十大高级知识](https://www.sidefx.com/docs/houdini/dyno/top10_advanced.html)
    
- [Managing simulation networks（管理模拟网络）](https://www.sidefx.com/docs/houdini/dyno/manage.html)
    
- [Caching simulations（缓存模拟）](https://www.sidefx.com/docs/houdini/dyno/cache.html)
    
- [Visualizing dynamics（可视化动力学）](https://www.sidefx.com/docs/houdini/dyno/visualize.html)
    
- [Fluid sourcing（流体的源头）](https://www.sidefx.com/docs/houdini/dyno/fluid_sourcing.html)
    

## COLLIDING OBJECTS（碰撞对象）

- [Destruction（破坏）](https://www.sidefx.com/docs/houdini/destruction/index.html "How to break different types of materials.")
How to break different types of materials.
==如何破坏不同材料==
    
- [Rigid body dynamics（刚体动力学）](https://www.sidefx.com/docs/houdini/dyno/rbd.html)
    
- [How to auto fracture geometry（如何实现自动断裂的几何体）](https://www.sidefx.com/docs/houdini/dyno/autofracturegeometry.html)
    
- [How to control the effects of voronoi fracture（如何控制泰森多边形法断裂的效果）](https://www.sidefx.com/docs/houdini/dyno/voronoifracture.html)
    
- [Shattering（碎裂）](https://www.sidefx.com/docs/houdini/dyno/shatter.html)
    

## SIMULATION TYPES（模拟类型）

- [Pyro（火焰）](https://www.sidefx.com/docs/houdini/pyro/index.html "How to simulate smoke, fire, and explosions.")
How to simulate smoke, fire, and explosions.
==如何模拟烟雾、火焰和爆炸。==
    
- [Fluids（流体）](https://www.sidefx.com/docs/houdini/fluid/index.html "How to set up fluid and ocean simulations.")
How to set up fluid and ocean simulations.
==如何设置流体和海洋的模拟。==
    
- [Grains（粒状物）](https://www.sidefx.com/docs/houdini/grains/index.html "How to simulate grainy materials (such as sand).")
How to simulate grainy materials (such as sand).
==如何模拟颗粒状的材料（如沙子）。==
    
- [Crowds（人群）](https://www.sidefx.com/docs/houdini/crowds/index.html "How to create and simulate crowds of characters in Houdini.")
How to create and simulate crowds of characters in Houdini.
==如何在胡迪尼中创建和模拟角色构成的人群。==

- [Finite Elements（有限元）](https://www.sidefx.com/docs/houdini/finiteelements/index.html "How to create and simulate deformable objects")
How to create and simulate deformable objects
==如何创建和模拟可变形的物体==

- [Cloth（布料）](https://www.sidefx.com/docs/houdini/vellum/index.html "Vellum uses a Position Based Dynamics approach to cloth, hair, grains, fluids, and softbody objects.")
Vellum uses a Position Based Dynamics approach to cloth, hair, grains, fluids, and softbody objects.
==牛皮纸使用基于位置的动力学方法来处理布料、毛发、颗粒、流体和软体物体。==
    
- [Hair and Fur（头发和毛皮）](https://www.sidefx.com/docs/houdini/fur/index.html "How to create, style, and add dynamics to hair and fur.")
How to create, style, and add dynamics to hair and fur.
==如何创建、设计和添加头发和毛皮的动态。==

- [Particles（粒子）](https://www.sidefx.com/docs/houdini/dopparticles/index.html "How to create particle simulations.")
How to create particle simulations.
==如何创建粒子模拟。==

- [Simulating ropes, wires, and other bendable objects（模拟绳索、线和其他可弯曲的物体）](https://www.sidefx.com/docs/houdini/dyno/wire.html)
    

## NON-DOP SIMULATIONS（非DOP模拟）

- [Oceans（海洋）](https://www.sidefx.com/docs/houdini/fluid/oceans.html)
    
- [Waves and ripples（波浪和涟漪）](https://www.sidefx.com/docs/houdini/dyno/ripples.html)
    

## NEXT STEPS（更进一步）

- [Understanding Houdini dynamics（理解胡迪尼动力学）](https://www.sidefx.com/docs/houdini/dyno/about.html)
    
- [Forces（力）](https://www.sidefx.com/docs/houdini/dyno/forces.html)
    
- [Constraints（约束）](https://www.sidefx.com/docs/houdini/dyno/constraints.html)
    
- [Optimizing a simulation（优化模拟）](https://www.sidefx.com/docs/houdini/dyno/optimize.html)
    
- [Input and output（输入和输出）](https://www.sidefx.com/docs/houdini/dyno/io.html)
    
- [HQueue](https://www.sidefx.com/docs/houdini/hqueue/index.html "HQueue is Houdini’s free distributed render and simulation manager.")
HQueue is Houdini’s free distributed render and simulation manager.
==HQueue是胡迪尼的免费分布式渲染和模拟管理器。==
    
- [Distributing simulations（分布式模拟）](https://www.sidefx.com/docs/houdini/dyno/distribute.html "Distribute shelf tools set up an object’s sim network so it can be solved in parallel on a farm of multiple machines using HQueue.")
Distribute shelf tools set up an object’s sim network so it can be solved in parallel on a farm of multiple machines using HQueue.
==分布式工具架设置了一个对象的模拟网络，因此它可以在一个由多台机器组成的农场上使用HQueue进行并行解算。==
    
- [Mixing keyframe animation and simulation（混合动画关键帧和模拟）](https://www.sidefx.com/docs/houdini/dyno/keyframe.html)