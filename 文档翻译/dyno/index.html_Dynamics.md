# Dynamics

[Dynamics (sidefx.com)](https://www.sidefx.com/docs/houdini/dyno/index.html)

How to use Houdini’s dynamics networks to create simulations.
==如何使用胡迪尼中的动力学网络创建模拟==

In Houdini you use dynamics networks to create simulations. You create _simulation objects_ and apply one or more _solvers_ to the objects. Houdini has objects and solvers for many different types of simulation, such as cloth, rigid bodies, wires, and fluids. There are also specialized solvers for integrating dynamics with other parts of Houdini, such as script solvers, geometry solvers, particle solvers, and Python solvers.
==在胡迪尼中，你可以使用动力学网络来创建模拟。你可以创建模拟对象，并将一个或多个求解器应用到对象上。胡迪尼有许多不同类型的模拟对象和求解器，如布料、刚体、线和流体。还有一些专门的求解器，用于将动力学与胡迪尼的其他部分结合起来，例如脚本求解器、及和求解器、粒子求解器和Python求解器。==

The most basic dynamics setup is a single simulation object wired to a solver, with a force applied.
==最基本的动力学设置是将单个的模拟对象与一个求解器相连，并为其施加一个力。==

![[Pasted image 20220216185600.png]]

**DOP Object node**
A container for data. Specific object nodes import geometry data and set up configuration data for a certain type (RBD object, Cloth object, etc.).


**Merge node**
The shelf tools automatically create merge nodes between the objects and the solvers. These allow you to use the same solver for multiple objects. DOP merge nodes also set up relationships (usually collision relationships) between the merged objects.

**Solver node**
Attaches data to the object saying this object's position etc. should be calculated using this solver.

**Grey connectors**
Repersent the object through the network, with each node attaching data to the object.

**Force node**
Attaches data to the object saying that this force is acting on the object.