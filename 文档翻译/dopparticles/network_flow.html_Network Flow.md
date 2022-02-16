# Network Flow

[Network Flow (sidefx.com)](https://www.sidefx.com/docs/houdini/dopparticles/network_flow.html)

## 目的与方法
### Create a particle system（创建粒子系统）
You can either use the [tab menu](https://www.sidefx.com/docs/houdini/basics/tabmenu.html) in a [geometry object](https://www.sidefx.com/docs/houdini/nodes/obj/geo.html "Container for the geometry operators (SOPs) that define a modeled
    object."), or by use the tools on the **Particles** shelf. See [Emitting](https://www.sidefx.com/docs/houdini/dopparticles/emitting.html) for more information.
[[emitting.html_Emitting]]
==你可以在几何对象层级下使用tab菜单，或使用工具架上的**Particles**图标。更多信息请参见“发射粒子”。==


### View the simulation（查看模拟）
Make sure the [display flag](https://www.sidefx.com/docs/houdini/nodes/dop/index.html "Dynamics nodes set up the conditions and rules for dynamics simulations.") is turn on the [POP Solver](https://www.sidefx.com/docs/houdini/nodes/dop/popsolver.html "A POP solver updates particles according to their velocities and forces.") or a node after it in the network.
==确定在网络中POP解算器或其之后的节点上的显示标志开启了。==

### Disable POP nodes you don’t want to affect your simulation（在你不想启用模拟的情况下关闭POP节点）
You can’t just move the [display flag](https://www.sidefx.com/docs/houdini/nodes/dop/index.html "Dynamics nodes set up the conditions and rules for dynamics simulations.") like in old POPs. You must either remove it from the chain, or turn on the [bypass flag](https://www.sidefx.com/docs/houdini/nodes/dop/index.html "Dynamics nodes set up the conditions and rules for dynamics simulations."). The [display flag](https://www.sidefx.com/docs/houdini/nodes/dop/index.html "Dynamics nodes set up the conditions and rules for dynamics simulations.") must always be on the [POP Solver](https://www.sidefx.com/docs/houdini/nodes/dop/popsolver.html "A POP solver updates particles according to their velocities and forces.") or a node after it in the network.
==你不能像在老的POPs上一样关闭显示标志。你必须把它从链上断开或打开忽略标志。显示标志必须总是在网络中POP解算器或其之后的节点上。==

### Allow other DOPs to affect POPs（允许其他DOPs影响POPs）
Verify the **External Forces** parameter on the [POP Solver](https://www.sidefx.com/docs/houdini/nodes/dop/popsolver.html "A POP solver updates particles according to their velocities and forces.") is turned on. It should be on by default.
==确认POP解算器上的**External Forces**参数是开启的。该参数默认情况下是开启。==

### Merge two or more streams（合并两个及以上的流）
Use a [Merge node](https://www.sidefx.com/docs/houdini/nodes/dop/merge.html " Merges multiple streams of objects or data into a single stream.") before the [POP Solver](https://www.sidefx.com/docs/houdini/nodes/dop/popsolver.html "A POP solver updates particles according to their velocities and forces.").
==在POP解算器后使用合并节点。==

### Switch a node on or off as part of the simulation（将一个可开关的节点作为模拟的一部分）
Turn on the yellow [Bypass flag](https://www.sidefx.com/docs/houdini/nodes/dop/index.html "Dynamics nodes set up the conditions and rules for dynamics simulations.") for the node you want to exclude from the simulation.
==将你想从模拟中去除的节点的忽略标志设置为开启。==

## See also（扩展阅读）
- [How to set up a particle system（如何设置粒子系统）](https://www.sidefx.com/docs/houdini/dopparticles/emitting.html)
- [Major differences from the old particle system（与旧粒子系统的主要区别）](https://www.sidefx.com/docs/houdini/dopparticles/differences.html)