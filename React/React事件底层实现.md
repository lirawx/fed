# React 事件


## 合成事件的实现机制

在React底层，主要对合成事件做了两件事情：事件委派和自动绑定。

1. 事件委派

React中并不是把事件处理函数绑定到当前DOM上，而是把所有的事件绑定到结构的最外层，使用统一的事件监听器。
这个事件监听器上维持了一个映射来保存所有组件内部的事件监听和处理函数。
组件挂载和卸载时，只是在统一事件监听器上插入删除一些对象。

2. 自动绑定

在React组件中，每个方法的上下文都会指向该组件的实例，即自动绑定this为当前的组件。而且React会对这种引用缓存，以达到CPU和内存的最大优化。
注意：在使用es6 class或者纯函数的写法，这种绑定不复存在，我们需要手动实现this绑定。

## 参考
* [React事件系统整理 - 不想当架构的前端不是一个好厨子 - SegmentFault 思否](https://segmentfault.com/a/1190000012961927)