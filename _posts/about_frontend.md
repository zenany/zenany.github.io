前端开发漫游指南
========

> 取名借鉴自：[银河系漫游指南](https://book.douban.com/subject/1394364/) [开源世界旅行手册](http://i.linuxtoy.org/docs/guide/)

在业界，“前端研发”基本上等价于“Web 前端研发”，Wikipedia 词条 [Front-end web development](https://en.wikipedia.org/wiki/Front-end_web_development) 中给出的官方定义为：

> Front-end web development, also known as client-side development is the practice of producing HTML, CSS and JavaScript for a website or web application so that a user can see and interact with them directly. The challenge associated with front end development is that the tools and techniques used to create the front end of a website change constantly and so the developer needs to constantly be aware of how the field is developing.

总体来说，“前端开发”就是使用 HTML、CSS、JS 技术给一个网站或 Web 应用开发图形用户界面（Graphical User Interface）。所以，前端应用本质上一个 GUI 程序，而 GUI 程序有三种典型形态：  

- [Web](https://en.wikipedia.org/wiki/Web_application) : 以浏览器为运行环境，基于浏览器内核支持的编程语言、API 来实现，被浏览器解释执行
- [Native](https://www.google.com/#newwindow=1&q=native+application) : 以操作系统为运行环境，基于操作系统原生支持的编程语言、API 接口实现，以二进制包的形式运行
- [Hybird](https://www.google.com/#newwindow=1&q=hybrid+application) : 基于 Native 应用提供的一个支持 HTML、CSS、JS 的容器开发的应用，相当与用开发 Web 的方式开发 Native 应用

这三种形态的背后是实现 GUI 程序的两大技术流派：[Web]()、Native。它们的本质差异在于：运行环境不同。浏览器给前端带来了很多优势，比如：实时更新、跨平台、跨终端、开发成本低等；但也带来了很多不便，比如：无法最大程度利用设备的特性和能力、无法使用最新的语言特性、性能和体验没有 Native 应用好、浏览器兼容性问题等。Web 和 Native 之争已经从 PC 时代持续到延续到移动时代，它们各自其应用场景和生存空间，相互促进共同进行。Native 技术研发大型复杂应用的经验和所能提供的精品体验对 Web 技术非常有借鉴意义。Web 的特性也能帮助 Native 实现功能动态更新并提高开发效率。

跨平台开发是 GUI 程序开发的一大问题，在移动端开发衍生出了应用的 N 种做法，见 [聊聊移动端跨平台开发的各种技术](http://fex.baidu.com/blog/2015/05/cross-mobile/) 。这么多种做法背后有两种理念：

- [write once, run anywhere](https://en.wikipedia.org/wiki/Write_once,_run_anywhere) ：这是编程界长期以来的一个理念，跨平台的理想方案，Java、Web 是最成功的实践。
- [learn once, write anywhere](https://code.facebook.com/posts/1014532261909640/react-native-bringing-modern-web-techniques-to-mobile/)：是 [React](https://facebook.github.io/react/) 提出的一个理念，开发者掌握一种 UI 开发的模式，用这种模式去开发 Web、Native 应用的界面。这种理念承认平台的差异性，使用平台自带的 UI 组件保证体验。

关于前端研发，还有两个广为流传的观点：  

- 前端不就是 `切图 + 写 JS 脚本 + 调 CSS 样式` 嘛，没啥技术含量，搞个两三年就到头了  
- 前端总是变来变去，基础库从 [jQuery](https://jquery.com/) -> [Angular](https://angularjs.org/) -> [React](https://facebook.github.io/react/)，工具从 [Grunt](http://gruntjs.com/) -> [Gulp](http://gulpjs.com/) -> [Webpack](https://webpack.github.io/)，应用架构从 [Flux](https://facebook.github.io/flux/) -> [Redux](http://redux.js.org/) -> [MobX](https://mobxjs.github.io/mobx/)...技术更新换代太快，缺少积累和传承，以至于都有人提出了前端摩尔定律：每 18 个月难度增加一倍

且不论这两个观点的对错，前端呈现给外界的第一印象或许就是这样的，这也正是前端的生存环境。然“穷则变、变则通、通则久”，变化的背后其实是生机。深入探索和实践前端这个技术领域，不难发现：

- 前端是有完整的知识体系的，其技术栈也很深，足够研究 10 多年  
- 前端的技术演进是有脉络可寻的，掌握这个脉络，对 `技术选型、技术创新、探索前端技术的边界和可能` 将会非常有帮助  
- 前端是一个产品/服务的最前沿，连接用户与服务，关乎产品的体验和品质  

让我们从前端业务模型、Web 应用典型系统架构、前端知识谱系这三个维度来重新认识下前端。

---

## 前端业务模型

业务模型是前端跟现实世界的对接点，决定了这个技术领域所需要解决的问题，也是前端核心价值之所在。无论技术、产品形态、开发模式怎么变化，这个业务模型是不会变的。对于码农来说， [input -> process -> output](https://en.wikipedia.org/wiki/IPO_model) 是最熟悉不过的模型了，这个经典模型是对计算机系统的高度抽象，借助这个模型对前端对前端进行分析，可以得到这样的业务模型：



在这个模型中：

- `INPUT` 包含产品需求 + 数据服务，产品需求通常以：[PRD](https://en.wikipedia.org/wiki/Product_requirements_document) + [UI](https://en.wikipedia.org/wiki/User_interface_design) 的形式提供，UI 通常包含：视觉设计、交互设计。数据服务的提供形式随着技术的进化在不断改变，大致路径为：`模板变量 -> HTTP 接口 -> Service 接口` ；
- `PROCESS` 利用前端技术对 INPUT 进行加工，把它们转换成可运行在各个终端上的应用。这个过程中这用到的核心技术是浏览器技术，但理论上来说浏览器技术只是一种选择，在必要的时候是可以采用原生 Native 技术的，这也就衍生出前端的一个跨界方向 `全端开发（全栈的一种）`；
- `OUTPUT` 为运行在浏览器或终端设备上的 Web 应用，是用户与产品的直接接触点； 

所以，前端 `为应用而生`，战斗在最前沿，将技术和艺术很好的结合在一起，搭起了用户、终端设备、服务之间的桥梁，让互联网服务可以被用户感知和使用。

---

## Web 应用典型系统架构

前端是 Web 应用的组成部分，一个典型的 Web 应用系统包含：  

- 静态资源 Server ： 提供前端程序运行时所需的 [静态内容(Static Content)](https://www.maxcdn.com/one/visual-glossary/static-content/)，JS、CSS、图片、视音频文件是最典型的代表。Nginx  是使用最广泛的静态资源 Server，和它配套的还有 [CDN](https://en.wikipedia.org/wiki/Content_delivery_network) 服务。
- Application Server ： 提供前端程序运行所需的 [动态内容](https://www.google.com/#hl=en&q=dynamic+content)，在收到用户发起的请求后，需要运行 Server 端程序进行一系列处理才能得到最终结果。需动态生成的 HTML 文档、JSON 数据是典型代表。Tomcat 就是一个典型的 Application Server。
- 浏览器： 负责加载并运行前端程序，Chrome 及基于 Chrome 内核打造的各种浏览器和容器是典型代表。

它们的协作方式如下图所示：

其中 Application Server 和 静态资源 Server，是通过 HTML 文档中的 `<scrpt> <link> <img> <autio> <video>` 等 资源标签关联起来的。Application 是前端和 Server 端程序的交汇点，也是催生跨界创新的地方。在很长一段时间内，前端和 Server 端的交互就是一份约定好的模板变量，这份变量往往还是 Server 端工程师按照他们的理解定义好的，这就造成了数据的使用方和定义方隔离的情况，在一定程度上束缚了前端并影响到应用研发效率。最近几年，Node.js、bff 就是顺着这个方向持续的产物。

这个结构在技术的进化中并没有发生本质变化，但在现实世界，Web 应用有很多种类型，导致这个模型有很多变种，比如：  

- 静态站点（Static Site），只需要一个静态资源 Server 即可，并不需要 Application Server，GitHub Pages 使用的 [Jelly](https://jekyllrb.com/) 就是目前最流行的静态站点生成器，[StaticGen](https://www.staticgen.com/) 汇集了目前可用的开源站点生成器。静态站点让 Web 回归内容，在访问速度、内容传播等方面有很大的优势，应用前景非常广，这篇文章 ：[Why Static Website Generators Are The Next Big Thing](https://www.smashingmagazine.com/2015/11/modern-static-website-generators-next-big-thing/) 给出了详细的分析。
- 小型站点，通常会将静态资源 Server 和 Application Server 由同一个 Web Server 来承载，常见的论坛、个人 blog、门户网站通常会用这种方式实现  
- 浏览器（含基于浏览器内核的变种）长期以来是前端的主流运行环境，但随着移动互联网的兴起，出现了一些新型的运行环境，比如：Weex、React Native 等，这些运行环境做到极致也将是一个“浏览器”，只不过实现方式、支持的编程语言和接口与传统的浏览器有差异。
- [noBackend](http://nobackend.org/solutions.html) 和 [Serverless](http://martinfowler.com/articles/serverless.html) 模式，使得 Application Server 逐步由为一些云服务来提供了，开发人员只需要专注于使用这些服务实现业务路基即可

技术的进步使得这三大组成部分对开发人员越来越友好，使得前端研发可以专注且高效地创造应用。

---

## 前端知识谱系

前端其实是有完整的知识谱系的，只不过由于新技术层出不穷，导致我们有时候会看不清变化中的不变，被变化牵着走。要走出这个困境，还是得回归本源，用计算机技术的视角从前端研发的本质上寻求突破。前端研发的本质仍然是编写程序，前端码农辛勤劳动的结晶本质上是一个 [Computer Program](https://en.wikipedia.org/wiki/Computer_program)，作为一个程序，通常要包含如下要素：

- 运行环境：运行在什么环境上
- 编程语言：用什么语言编写
- 开发框架：有什么开发框架可以方便开发者快速开发程序
- 工程设施：帮助开发者解决构建、环境、调试、发布等问题
- 分发渠道：代码如何分发到运行环境

结合前端的业务模型，从这个角度去看前端，会发现一条比较清晰的知识谱系概览图：

总体来说，前端研发设计的知识包含如下大类：

- 运行环境
- 编程语言
- 数据通道
- 应用开发
- 工程化
- 性能
- 安全
- 体验

### 运行环境（Runtime）

前端 Runtime 对终端设备的操作系统进行封装，提供了基于 HTML、CSS、JS 语言的编程接口，赋予前端程序控制终端设备的能力，包含两类：

- 浏览器内核：前端最核心的 Runtime，基于 Web 标准提供了一个跨平台的 Runtime，除了浏览器外，[Electron](http://electron.atom.io/)、[Node Webkit](http://nwjs.io/) 等 基于浏览器内核提供开发平台也属于这类
- Native 容器：基于 Native 或 Webview 打造的运行容器，在跨平台开发 Native 应用中非常普遍，以另一种形式对终端设备进行封装，提供一个可以用前端编程语言编写应用的运行环境，[Cordova](https://cordova.apache.org/)、[Weex](http://alibaba.github.io/weex/)、[React Native]() 算是典型代表。微信、支付宝、手机百度等超级 App 都有一个这样的内置容器。

作为主流 Runtime ，浏览器内核包含三大组成部分：

- [Browser Engine](https://en.wikipedia.org/wiki/Web_browser_engine)：负责渲染页面，有  [Webkit](https://webkit.org/)、[Googke Blink](http://www.chromium.org/blink)、[Firefox Gecko](https://developer.mozilla.org/en-US/docs/Mozilla/Gecko)、[Microsoft EdgeHTML](https://blogs.windows.com/msedgedev/tag/edgehtml/) ，Webkit 和 Blink 使用最广
- [JavaScript Engine](https://en.wikipedia.org/wiki/List_of_ECMAScript_engines)：负责执行 JavaScript，基本上已经是 [V8](https://developers.google.com/v8/) 的天下了，微软也开源了自家的引擎 [ChakraCore](https://github.com/Microsoft/ChakraCore)
- 浏览器：也就是大家日常使用的 Firefox、Chrome、IE，负责调度硬件资源、与 Web Server 通信、处理用户操作等，包含：图形、网络、进程、界面、安全等模块，见 [Chromium Design Documents](http://www.chromium.org/developers/design-documents)

在 Runtime 上，前端 和 Server 端有一个本质差异：前端的 Runtime 不是前端工程师所能指定和控制的，而 Server 端的 Runtime 是 Server 端工程师完全可掌控的，这个差异带来的影响是：  

- 前端很难通过优化 Runtime 去解决问题  
- 新技术从出现到可以大范围使用，周期非常长，ES6、HTML5 就是典型代表
- 前端需要花大量精力去兼容多种 Runtime  
- 前端研究 Rutime 所能产生的直接价值远小于 Server 端

作为前端最底层的技术，研究它所能产生的直接收益却不大，这的确有点尴尬。但是，浏览器是世界上最复杂的 GUI 程序之一，通过研究其实现可以学到很多 GUI 程序开发的知识和技术，对我们掌控复杂应用的实现、研究跨平台开发非常有帮助。

### 编程语言

前端要掌握的基础编程语言是：HTML、CSS、JS，这三种语言背后都有规范支持，随着浏览器技术的进化也在持续进化，功能和易用性越来越好了。除此之外，前端开发还会涉及两类语言：

- 对 HTML、CSS、JS 进行语法增强的衍生语言，以提升其易用性，TypeScript、JSX、SASS、LESS 就是典型代表
- 模板语言：负责根据数据动态构造 HTML，Nunjucks、Mustache、Jade、Velocity 都属于这类语言，模板语言提供了一种通过编程语言输出大规模结构化文本的思想，可以活用在很多地方

### 数据通道

数据通道将 Client 和 Server 连接起来，涉及如下组成部分：

- 网络设施：wifi、局域网、3g、4g、2g 等都属于这个范畴，
- 协议：让前端程序和 Server 端程序能以双方能识别和处理的语言进行协助，HTTP 是使用最广的协议，初次之外还有 [WebScoket](https://en.wikipedia.org/wiki/WebSocket)、移动端普遍采用的 RPC 、[QUIC](https://www.chromium.org/quic) 等协议

与这个通道对接的是前文提到的：静态资源 Server、Application Server，浏览器通过这个通道和它们进行通信。

### 应用开发

应用专注在如何开发各种类别的应用，探索和实践 Web 应用的 N 做法，是前端最核心的一个技术领域，总体来说包含如下内容：

- 基础库：提供网络操作、DOM 操作、日期、事件、Canvas 等功能，jQuery 、React、Underscore 就是典型代表
- UI 组件库：提供可被复用的原子级别的界面元素，AntD、Bootstrop、jQuery UI 为典型代表
- 业务组件库：提供一些包含业务属性的组件，比如：登录框、富文本编辑器等
- 业务框架：规范应用代码的拆分、组织、实现方式，Angular 为典型代表

以上是开发应用都会需要的东西，但是一些专业应用，光有这些是不够的，还需要掌握对应的专项技术和业务知识才能胜任。前端领域最典型的几个专项技术是：  

- 图形：根据数据绘制各种图形，地图、数据报表、大屏是其典型场景
- 编辑器：终端设备有两大核心功能，展示信息 + 创造内容，其中创造内容就是有编辑器来支持的，编辑器因所编辑内容的不同会有各种形态，对应着多种不同的实现方式，比如：源码编辑器 [Ace](https://ace.c9.io/)、[Monaco Editor](https://github.com/Microsoft/monaco-editor)，富文本编辑器 [TinyMCE](https://www.tinymce.com/)、[Draft.js](https://facebook.github.io/draft-js/)，Markdown 编辑器 [StackEdit](https://stackedit.io/)
- [实时应用](https://en.wikipedia.org/wiki/Real-time_web)：消息、聊天、Game、协同办公等类别的应用，这也是 Web 程序一直未能完美支持的地方，该领域目前做的最好的是 Google Docs 

### 工程化

工程化是一个综合性话题，其本质是实现一个研发团队可以规模化、高质量的开发前端应用。规模化有两层含义：研发模式可以支持多人并行开发，人员数量翻倍产能即可翻倍；技术架构和基础设施能有效地支撑不同类别产品的快速研发。高质量有三个基本要求：易维护、高性能、体验好。前端是一个系统中变化最频繁、新业务出现速度最快的部分，工程化显得尤为重要。

广义的前端工程化就是软件工程在前端领域的应用，几乎包含了研发的方方面面。总体来说，分为两大技术方向：  

- 加速 coding 本身的过程，让开发应用像搭积木一样简单，也即 `应用开发` 章节所关注的内容，其呈现形态就是各种框架、类库、解决方案
- 管理代码及研发生命周期，让代码安全高效地发布，让 coding 外的事情也可以高效进行，其呈现形态程是一些工具类产品和服务

狭义的工程化重点关注第二个方向，保证工程师可以专注于 coding 本身，包括如下技术领域：

- 源代码管理：如何管理源代码
- 代码规范：制定团队统一的代码规范，提供规范检查工具
- 构建：将源代码转变成目标代码
- 调试：如何在各个环境下测试程序
- 发布：如何保证程序高效、安全的发布出去给用户使用
- 质量：如何有效的保证代码质量
- 数据监控：如何监控前端程序运行过程中产生的一些有价值数据

### 性能

性能是任何程序都需要考虑的问题，也是体现码农综合技术能力之处。前端性能优化不仅可以提升用户体验，还可降低服务器带宽成本。性能优化通常包含如下四大部分内容：

- 性能指标体系：确定好该优化什么
- 监控：持续监测核心指标，为优化提供理论依据
- 评测：通过一套完整的工具或者监控体系，评估应用的运行性能是否符合预期
- 优化：制定并实施优化方案，解决产品遇到的性能问题

其中，`优化` 是关注最多的地方。但实际上，若不需要结合业务特点确定好优化目标和时机，很容易陷入过度优化或过早优化的误区。

### 安全

安全无小事，对于金融、电商类业务，安全更是必须保证的。前端涉及的安全问题通常包括：

- [XSS](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) : Web 应用安全问题之源，利用 Web 应用程序对用户数据的处理缺陷来攻击 Web 应用，这里有一份详细的防护指南 [给开发者的Web应用程序XSS防护快速指南](http://blog.knownsec.com/2014/07/%E7%BB%99%E5%BC%80%E5%8F%91%E8%80%85%E7%9A%84%E7%BB%88%E6%9E%81xss%E9%98%B2%E6%8A%A4%E5%A4%87%E5%BF%98%E5%BD%95-v1-0/)  
- [CSRF](https://www.owasp.org/index.php/CSRF) : 利用 Server 端接口设计的一些漏洞，在其它站点嵌入敏感操作对应的 URL ，使得有权限的用户在不知情的情况下就触发了操作
- [Clickjacking](https://www.owasp.org/index.php/Clickjacking) : 通过伪造界面，诱导用户进行一些敏感操作
- 用户隐私信息泄露：数据通常会以全集的的形式提供给前端，这些数据一不小心（比如 json 序列化）就会被输出到页面，所以在使用数据时，务必要提醒自己：遵循最小化原则、隐私信息只在必要时输出
- 防篡改：HTTP 协议本身的特性使得数据在从 Server 到浏览器端传递的过程中，可以被第三方劫持和篡改

### 体验

体验虽然不直接和编码相关，但决定了前端程序的品质，是一个前端程序从能用 -> 好用 的重要过程。在一个公司内，风格统一的视觉和交互设计，还能大大提升研发效率。体验也是是前端可直接影响产品业务之处，也是区别于其它技术工种的独特价值之所在。体验也是前端领域可催生跨界创新之处，Ant Design、Bootstrap 就是典型代表。体验是一个非常大的专业领域，和前端工作息息相关的有：

- 交互 & 视觉设计的理念和原则
- 业界同类产品的界面设计
- 常见视觉、交互、动效效果的实现
 
---- 

### 结语

以上是用程序员的视角对前端开发进行的的一些思考，知识谱系目前只是索引，其枝叶会在后续逐步完善。`前端研发的本质是什么？前端的未来是什么样子的？` 这是值得每个前端工程认真思考的两个问题，也是我们能顺应甚至引领变化的关键之所在。

---

## 延伸阅读

下边这些资料能帮助我们更好地认识和学习前端及 GUI 开发：  

- [Front-End Developer Handbook](http://www.frontendhandbook.com/)  
- [Frontend Development Bookmarks](https://frontend.directory/)  
- [Front End Engineer's Manifesto](http://f2em.com/)  
- [What makes a good front end engineer](https://www.nczonline.net/blog/2007/08/15/what-makes-a-good-front-end-engineer/)  
- [Native, HTML5, or Hybrid: Understanding Your Mobile Application Development Options](https://developer.salesforce.com/page/Native,_HTML5,_or_Hybrid:_Understanding_Your_Mobile_Application_Development_Options)  
- [Learn Once, Write Anywhere](http://agateau.com/2015/learn-once-write-anywhere/), [PPT](https://speakerdeck.com/cassiozen/react-learn-once-write-everywhere-1)  
- [React Native and the New Dream of Learn Once, Write Anywhere](http://thenewstack.io/react-native-learn-write-anywhere/)  
- [The Art of Unix Programming - User-Interface Design Patterns in the Unix Environment](http://www.catb.org/esr/writings/taoup/html/interfacechapter.html)  
- [Why Static Website Generators Are The Next Big Thing](https://www.smashingmagazine.com/2015/11/modern-static-website-generators-next-big-thing/)

-- THE END --
