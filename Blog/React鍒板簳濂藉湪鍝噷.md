### １．首先什么是Ｒｅａｃｔ？

React.js是Facebook公司在2014年前后推出的一款前端的UI库，它并不像Foundation或者bootstrap那些围绕jQuery以及CSS而开发的UI脚手架，你仍然得实打实的为你的模块编写代码，只是开发的模式和以前大有不同。

2010年后，由于社会上对F2E需求的爆发性增长，不少顶级互联网公司对都FE这个领域开始了不同程度的探索。于是，人们开始在前端领域谈MVC、谈MVVM、谈SPA、谈components，而就这些特性而言，Google的Angular(下称ng)已然是众多框架中的翘楚，它允许Dev可以以MVVM的方式很快的实现各种诸如数据双向绑定、自定义标签等等的需求。但所谓有利就有弊，ng对普通Jser的依旧有着很大的要求，而且ng本身是一个高度复杂的框架，而有时候在一些webapp上，我只是想可以快一点、再"快"一点的写view层的模块，并不需要ng这样重量级框架。
而面临这样需求，React.js则应运而生了，也因为这个朴素初衷Fb对它的描述仅仅是一句：
```
A JAVASCRIPT LIBRARY FOR BUILDING USER INTERFACES
```
而它的愿景也很简单：
```
COMPLEX WEB APPS MADE EASY
```
#### HTML5 与 Web Components

从我学习HTML的第一天开始，我就一直坚信着组件化的HTML才是正义。然而过去由于针对浏览器以及web标准本身各大厂商有各自不同的分歧或者利益纠纷导致了或多或少不同程度上的实现差异，因此在web端的开发一直很难像传统的客户端界面那样顺手。好在随着B/S架构的互联网产品越来越多，我们所期待的"组件化"，也一直在以不同的形式不断的迭代着。
React的优势

兼容性：

React是一个view层的Library，人们通常会把他和Polymer相比较，但Goolge的 Polymer因为过于超前，所以在完成Polyfill后最低也只能兼容到IE10，移动端平台倒是可以一试。相比之下React则可以兼容到IE8，就国内的浏览器现状来说，着实是一个不小的优势。

前后端统一，SEO Friendly ：

这两年随着Node.js的崛起，前后端统一这个议题都被说烂了，但这里我想说的不是编程语言上的统一(其实，我觉得这个本身也没什么意义)，而是前后端渲染模板上的统一。

众所周知，Angular.js在开发webapp时会配合大量后端提供的数据接口从而达到动态、异步填充的特性，客户端渲染速度确实会快，体验也会更好，但同时也导致了互联网爬虫无法正确地检索到页面的真实数据而只能爬取到一些模板字段。开发者为了解决这个问题，通常情况下会在server端重写一套渲染逻辑专门供爬虫检索。而使用React的话则可以一定程度上改善这个问题，比如Express上就有一款视图引擎express-react-views可以实现服务端渲染React组件，类似的在.NET平台上还有Reactjs.Net项目，藉此developer可以实现前后端全部组件化的组织。

一次编写，两端运行，同时又能提供良好的SEO。

同时，由于React这样的framework可以同时运行于server side 以及 client side，藉此还引申出了一种名为 “Isomorphic”的App设计风格，但这里暂且不提。

Virtual DOM & Performance ：

所有程序员都爱关注性能，FE也不例外，自从Chrome挑起第二次浏览器大战以来，JavaScript的速度已经越来越快，时至今日，JavaScript的执行速度已经超越了大部分动态语言。但理想很丰满，现实很骨感，在现有的前端体系中，碍于文件对象模型的树形实现，我们不得不面临一个现状，就是：JS很快，但DOM太慢。
