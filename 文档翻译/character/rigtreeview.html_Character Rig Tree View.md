# Character Rig Tree View

[Character Rig Tree View (sidefx.com)](https://www.sidefx.com/docs/houdini/character/rigtreeview.html)

---

## Overview（概述）
The rig tree view gives a hierarchical view of character components and is compatible with object-node-based rigs and SOP rigs. Traversals work a bit differently between object rigs and SOP rigs.
==绑定树视图提供了一个角色组件的分层视图，与基于对象节点绑定和SOP绑定兼容。但在二者之间的遍历方式略有不同。==

### Object node rigs（对象节点绑定）
These are rigs composed of object nodes. When displaying object node rigs, each item corresponds to an object node in the rig.
==这些绑定由对象节点组成。当现实对象节点绑定时，每一项对应一个绑定中的对象节点。==

If a subnet containing object nodes is selected, then its child network of object nodes will be traversed based on each node’s inputs and outputs. E.g. let’s say `subnet1` contains 2 children nodes, `geo1` and `geo2`, where the output of `geo1` feeds into `geo2`. If we select `subnet1`, then the rig tree view will display a simple hierarchy where `geo1` is the parent of `geo2`.
==如果选择了一个包含对象节点的子网，那么它的对象节点的子网将根据每个节点的输入输出来进行遍历。例如，假设`subnet1`包含了2个子节点`geo1` 和 `geo2`，其中`geo1` 的输出连接到 `geo2`的输入。如果我们选择 `subnet1`，绑定树视图会显示一个简单的层结构，其中`geo1` 是 `geo2`的父节点。==

### SOP rigs（SOP绑定）
These are rigs produced by the output of SOP nodes in the form of points and prims connecting the points. When displaying SOP rigs, each item in the tree view represents a point.
==这些是由SOP节点以点和连接这些点的基元形式输出的绑定。在显示SOP绑定时，树视图中的每一项都代表一个点。==

When a SOP node is selected, its geometry is read, and the hierarchy is generated from the points and what prims connect the points.
==当选择一个SOP节点时，会读取它的几何，并以点和连接点的基元生成层结构。==

## Custom behavior（自定义行为）
Whenever the rig tree view traverses a node, it checks if node contains a configuration section called “rigtreeconfig” in its type definition. If this is missing, the tree view performs the default for selection and drag and drop.
==每当绑定树视图遍历一个节点时，它都会检查节点在其类型定义中是否包含一个名为“rigtreeconfig”的配置项。如果缺少该项，树视图将会执行默认的选择与拖放。==

The `rigtreeconfig` is a python module that the user can use to implement custom behavior by registering an class instance with named methods. If a method is found on for a custom behavior, the default for that behavior won’t be performed.
==`rigtreeconfig`是一个python模块，用户可以通过注册一个带有命名方法的类实例来实现自定义行为。如果发现了一个自定义行为的方法，该行为的默认值将不会被执行。==

Details are in the following subsections.
==详细信息在下面的小节中。==
``` python
"""Create a class with the right methods."""
"""创建一个具有正确方法的类"""
class RigTreeConfig:
    def __init__(self,widget): 
        self._widget = widget 
        """
        Implement your own RigTree methods. 
        All methods are optional and not implementing a method will result a default behavior. 
        实现你自己的绑定树方法。
        所有的方法都是可选的，不实现某个方法则会调用默认行为。
        
        def select(self,kwargs):
        def get_selection(self,kwargs):
        def default_output(self,kwargs):
        def drag_drop(self,kwargs):
        def rename(self,kwargs):
        def available_actions(self,kwargs):
        def delete(self,kwargs): 
        """
"""
Entry point for the rigtreeconfig module. 
The parent RigTreeView widget is given as an argument of the function.
rigtreeconfig模块的入口点。
父级绑定树视图小部件将作为该函数的一个参数给出。
"""
def rigtreeconfig(widget):
    return RigTreeConfig(widget)
```

### Registration（注册）
Define a `rigtreeconfig` global function.
==定义一个全局函数`rigtreeconfig`。==

The `rigtreeconfig` function is called when a Rig Tree Pane updates its current node. The `widget` argument holds a reference to the parent Rig Tree View python widget. You can keep the `widget` as a data member of your class to access more information from the widget if the `kwargs` arguments don’t supply what you want.
==在当前节点的绑定树窗格更新时，`rigtreeconfig`函数会被调用。`widget` 参数持有一个对父绑定树视图python小组件的引用。如果`kwargs`参数没有提供你想要的东西，你可以把`widget`作为你的类的一个数据成员来访问小组件的更多信息。==

It should return an instance of your custom class, or a instance from one of the builtin classes in `kinefx.ui.rigtreeconfig`.
==它应该返回一个你的自定义类的实例，或者在`kinefx.ui.rigtreeconfig`中的一个内置类的实例。==

``` python
from kinefx.ui.rigtreeconfig import GroupRigTreeConfig
def rigtreeconfig(widget):
    return GroupRigTreeConfig(widget=widget)
```

### Default Output（默认输出）
This method is relevant only for SOP rigs, particularly those with multiple outputs or inputs.
==这个方法仅适用于SOP绑定，特别是有多个输入输出的情况。==

It is called when opening the Rig TreeView to define which geometry to build the tree view from. It is an index, in the drop down menu on the header of the widget.
==它在打开绑定树视图时被调用，以定义从哪个几何建立树视图。它是一个在小组件头部下拉菜单中的索引。==
``` python
def default_output(self,kwargs):
    """
    To return the index, set the named value `default_output` to an integer.
    You can also hide the dropdown menu by setting `show_dropdown` to `False`.
    要返回索引，设置一个名为`default_output`的值为一个整数。
    你也可以通过设置`show_dropdown`为`False`来隐藏下拉菜单。
    """
    kwargs["default_output"] = 1
    kwargs["show_dropdown"] = True
```

### Tree View Selection（树视图的选择）
By default, selection has the following behavior:
- With object node rigs, selecting an item in the rig tree view selects that object node in the network view.
- With SOP rigs, selecting an item in the rig tree view selects that point in the scene viewer.

To customize selection behavior, include a `select` method in your class.
==默认情况下，选择具有以下行为：
- ==对于对象节点绑定，在树视图中选择一项，也会在网络视图中选择该对象节点。==
- ==对于SOP绑定，在树视图中选择一项，会在场景查看器中选择该点。==

==要自定义选择行为，需要在你的类中加入一个`select` 方法。==

``` python
def select(self, kwargs):
    """
    Custom selection behavior.
    自定义选择行为。

    This is called whenever a selection event happens (whether selecting all items in a subtree, deselecting everything, or selecting a single item).
    每当一个选择时间发生时（无论是选择子树中的所有项目，取消选择所有项目，还是选择单个项目），都会调用这个行为。

    - selection is a list of all the selected items.
    - selected is a list of what's just been selected. 
        If it's an object node network, then each list element is a full path to the node. 
        If it's a SOP network, then it's the name associated with the point, if there is one (if there isn't one, a default is used).
    - deselected is a list of what's just been deselected.

    - selection是一个所有被选中的项目的列表。
    - selected是一个刚刚被选中的项目的列表。
        如果它是一个对象节点网络，那么每个列表元素都是指向节点的完整路径。
        如果它是一个SOP网络，那么它是与该点相关的名称，如果有的话（如果没有，就使用默认值。）
    - deselected是一个刚刚被取消选择项目的列表。
    """
    # do something with the selection
    # 对选择做点啥
    print(kwargs['selection'])
```
Note that the handler isn’t expected to actually interfere with the rig tree view UI selection. I.e. the handler isn’t expected to change what’s being selected in the rig tree view UI.
==请注意，处理程序并不希望真的干扰到绑定树视图在UI中的选项。也就是说，处理程序不会改变绑定树视图在UI中的选项。==

### Tree View Drag and drop（树视图的拖放）
Dragging and dropping of single items is supported. The default behavior for each type of rig is the following:
- For object node rigs, dragging and dropping rearranges the connections between the object nodes.
- For SOP rigs, dragging and dropping does nothing by default.

To define custom behavior for drag and drop, define a `drag_drop` method in your class.
==支持拖放单个项目。每种类型的绑定默认行为如下：==
- ==对于对象节点绑定，拖放会重新安排对象节点之间的连接。==
- ==对于SOP绑定，拖拽默认不做任何操作。==

==要自定义拖拽的行为，请在你的类中定义一个`drag_drop`方法。==

``` python
def drag_drop(self,kwargs):
    """
    Called whenever an item is dragged and dropped in the UI.
    当一个项目在UI中被拖放时调用。

    Return True to signal to the UI that the rig should be retraversed (i.e. something's changed). 
	Return False if no retraversal is needed.
    返回True，向UI表明绑定需要被重新遍历（即有什么变动）。
    返回False则表示不需要被遍历。

    - item is the data being dragged and dropped.
    - old_parent_item is the data representing the previous parent item that `item` is being dragged from. 
        Parent in this case refers to the rig tree view sense, not the object node parent sense. 
        This may be None if the item was top level.
    - new_parent_item is the data representing the new parent item that `item` is being dropped under. 
        This may be None if the item is moved to the top level.
    -item是被拖放的东西。
    -old_parent_item是代表`item`被拖放前的父项数据。
        在这种情况下，父项是指绑定树形图，而不是对象节点的父项。
        如果项目在顶层，这可能是None。
    -new_parent_item是代表`item`被拖放后的父项数据。
        如果项目在顶层，这可能是None。
    """
    return False
```

### Actions（动作）
Actions are custom functions that users can access via the context menu that’s opened by right-clicking and choosing the “Node actions” option. By default, no actions are available.

To define custom actions for a rig, define the function `available_actions` in the `rigtreeconfig` section of the node’s type definition:
==动作是用户可以通过右击并选择“Node actions”选项打开的上下文菜单中访问的自定义功能。默认情况下，没有可用的动作。
要为绑定添加自定义动作，需要在节点类型定义的`rigtreeconfig`部分，定义`available_actions`函数。==

``` python
def available_actions(self,kwargs):
    """
    Called whenever a context menu is open via right click.
    - `selection` can be used to dynamically select what node actions should be available based on the current selection.
    每当通过右击打开上下文菜单时，就会被调用。
    -`selection` 可以用来基于当前选择的节点动态选择哪些动作可用。
    """
    
    # We can choose to return a different set of actions based on the selection, or return the same actions.
    # 我们可以选择根据选择返回一组不同的动作，或者返回相同的动作。

    return {
        'action_1': lambda: "do something here",
        'action_2': lambda: "do something else here",
    }
```

### Renaming（重命名）
For OBJ rigs, renaming by default changes the name of the associated object node.

For SOP rigs, there is no default renaming behavior, so a custom renaming function must be defined.

To define custom renaming behavior, define a `rename` function to the `rigtreeconfig`:
==对于OBJ绑定，重命名默认会改变相关对象节点的名称。
对于SOP绑定，没有默认的重命名行为，所以必须定义一个自定义重命名函数。
要创建自定义重命名行为，请在`rigtreeconfig`中定义一个`rename`函数：==

``` python
# Inside rigtreeconfig
#在rigtreeconfig内部

def rename(self,kwargs):
    """
    Return True to signal that the rig tree view should do a re-traversal.
    返回True，表示绑定树视图应该被重新遍历。

    Return False if the change doesn't warrant a re-traversal. 
    For example: if the rename didn't produce a change due to failure.
    返回False，表示不需要被重新遍历。
    例如：重命名失败而导致没有发生变化。

    Params:
    - item: represents the item being renamed. This could either be a node path (in the case of object rigs) or a number (in the case of SOP rigs).
    - old_name: the previously displayed name.
    - new_name: the new name that the user has requested.
    参数：
    -item：代表被重命名的项目。这可以是一个节点路径（在对象绑定的情况下）或一个数字（在SOP绑定的情况下）。
    -old_name：以前显示的名称。
    -new_name：用户要求的新名称。

    Note that rename events will be fired even if the old name and new name are identical.
    注意，即使旧名称和新名称相同，也会触发重命名事件。
    """
    # Some renaming operation here...
    #一些改名的操作放在这里...
    return True
```

### Delete（删除）
There is no default delete behavior, so a custom deletion function must be defined.

To define custom deletion behavior, define a `delete` function to the `rigtreeconfig`:
==没有默认的删除行为，所以必须自定义一个删除函数。
要创建自定义删除行为，请在`rigtreeconfig`中定义一个`delete`函数：==

``` python
# Inside rigtreeconfig
#在rigtreeconfig内部

def delete(self,kwargs):
    """
    Return True to signal that the rig tree view should do a re-traversal.
    返回True，表示绑定树形图应该进行重新遍历。

    Return False if the change doesn't warrant a re-traversal. 
    For example: if the delete didn't produce a change due to failure.
    返回False，表示不需要被重新遍历。
    例如：因为删除失败而导致没有产生变化。

    Params:
    - selection is a list of all the selected items.
    参数：
    -selection是所有选定项目的列表。
    """
    # Some delete operation here... such as removing a point or deleting an object node.
    #在这里做一些删除的操作... 例如删除一个点或删除一个对象节点。
    return True
```

## API
Items are uniquely identified by an “item id”. In the SOP rig case, these are the point indices (i.e. integers). In the OBJ rig case, these are the full paths of the object nodes (e.g. “/obj/myrig/shoulder1”).
==项目是由一个唯一的“项目ID”来识别的。在SOP绑定的情况下，这些是点的索引（即整数）。在OBJ绑定的情况下，这些是对象节点的完整路径（例如 “/obj/myrig/shoulder1”）。==

- `selectItem(self, item_id, select_if_true, enable_handler=True)` → `bool`
Select or deselect the item corresponding to `item_id` in the rig tree widget. If a matching item was found, returns True. Otherwise, returns False. If `enable_handler` is set to `False`, then the default or user-defined selection handler (i.e. `select` in `rigtreeconfig`) will not trigger.
==选择或取消选择绑定树视图中`item_id`所对应的项目。如果找到一个匹配的项目则返回True，否则返回False。
如果`enable_handler`设置为`False`，那么默认的或用户自定义的选择处理程序(即`rigtreeconfig`中的`select`)将不会被触发。==

- `selectedItems(self)` → `list`
Returns a list of the selected items' ids.
==返回所选项目的ID的列表。==

- `clearSelection(self, enable_handler=True)`
Clears the rig tree view’s current selection. The `enable_handler` functions similarly to `selectItem`.
==清空绑定树视图的当前选择。`enable_handler`的功能与`selectItem`类似。==


- `getCurrentNodePath()` → `str` or `None`
Get the full path of the node representing the current rig. If no node is currently being traversed, returns `None`.
==获取当前绑定节点代表的完整路径。如果当前没有节点正在被遍历，则返回 `None`。==

- `setNode(node)`
Traverses the rig represented by `node`. If `node` is the current node displayed by the tree widget, a re-traversal will not occur.
==遍历`node`所代表的绑定。如果`node`是树视图小组件当前显示的，将不会发生重新遍历。==

- `resetCurrentNode()`
Re-traverses the current node.
==重新遍历当前节点。==