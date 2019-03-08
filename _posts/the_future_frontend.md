前端之未来
========  

## 引

近期学到一个词：[Digital Twin(数字孪生)](https://en.wikipedia.org/wiki/Digital_twin)，简单来讲就是在计算机世界给现实世界的物体（飞船/城市）、系统（电力/交通）建立数字化镜像，让数字世界和物理世界更好地交互，数字大屏也可以算这种技术一种应用场景。这个概念由 [Dr.Michael Grieves 于](https://www.researchgate.net/publication/307509727_Origins_of_the_Digital_Twin_Concept)[ 2002 年提出](https://www.researchgate.net/publication/307509727_Origins_of_the_Digital_Twin_Concept)，随着 IOT、AI、图形技术、工业 4.0 的飞速发展，[应用前景越来越广阔](https://baijiahao.baidu.com/s?id=1617158077142839496)。[Google 一下](https://www.google.com/search?q=digital+twin) 就会发现：NASA、GE、Microsoft、SAP、IBM 等巨头早已布局和应用这项技术，它还是 [Gartner Top 10 Strategic Technology Trends for 2019](https://www.gartner.com/smarterwithgartner/gartner-top-10-strategic-technology-trends-for-2019/) 中的一项。

![digital_twin_plane.png](https://cdn.nlark.com/yuque/0/2019/png/84145/1550073439172-0b87c0fd-deeb-417d-aab4-a221d0e35089.png#align=left&display=inline&height=242&name=digital_twin_plane.png&originHeight=520&originWidth=1600&size=164017&status=done&width=746)<br />图片来自：[How the visualization has changed by Digital Twin Technology](https://medium.com/@anshita.letsnurture/how-the-visualization-has-changed-by-digital-twin-technology-45693ad406b9)

**前端为应用而生，人机交互技术是我们的生存之本，以应用为桥连接用户和数字世界是我们的使命**。但长期以来前端的生存空间被压缩在 Web 领域，**Digital Twin** 这种新形态无疑将为我们打开一片新天地。Gartner 这份报告中还有两项技术和前端紧密相关：

* **Immersive technologies**：Augmented Reality(AR)、Virtual Reality(VR)、Mixed Reality(MR) 等
* **Smart Spaces**：智慧城市、智能汽车、智能商店等

看到**未来有三项战略性技术居然和前端有关**，着实让人兴奋不已。不过莫急，既然是战略，也就意味着三五年内未必能开花结果。再仔细分析会发现：**当下的前端技术远不足以胜任这些领域**，不由得让人心忧。远方的风景很美，但要成功抵达就需要早做准备。站在 **_201X_** 的末尾、互联网下半场的开始，不妨先结合 Gartner 这份报告一起分析下：**下一个 10 年前端技术的变革在哪里、有哪些值得大力投入的方向？**

## 回顾过去

“以史为鉴，可以知兴替”，如果历史是一组波，它过去的相位所形成的轨迹已足以预见未来。回顾 Web 技术的发展历程，可以清晰地看到三类促使变革发生的关键因子：
* **引擎**：有四大引擎显得尤为重要：
  * **[V8](https://v8.dev/)** ：不仅提升了 JS 的执行效率，助力 ES 规范落地，而且催生了 [Node.js](https://nodejs.org/en/) 
  * **浏览器引擎**：以 [Webkit](https://webkit.org/)、[Blink](https://www.chromium.org/blink)、[Chromium](https://www.chromium.org/) 为典型代表，浏览器的高速发展为 Web 的繁荣奠定了基础
  * **[Node.js](https://nodejs.org/)** ：大大拓展了前端的生存空间，以至于“Any application that can be written in JavaScript, will eventually be written in JavaScript.”
  * **Hybrid 容器**：让被 App 统治的移动互联网时代也给 Web 开发留下了一席之地，小程序是典型代表
* **开发套件**：语法、框架、工具、类库在社区的推动下一直在蓬勃发展，优秀的开源项目灿若星河，前端生态也成为技术圈中最活跃的。虽然以 React 为核心的主流技术栈上手成本还比较高，也做不到让开发人员只关心业务逻辑，但不可否认应用开发正在变简单。有些类型的应用甚至做到了无需 Coding 通过专门的可视化搭建平台就可以完成，比如：门户网站、营销活动、问卷调查等。
* **分工模式**：前后端分离、[BFF(Backend For Frontend)](https://samnewman.io/patterns/architectural/bff/)、全栈、全端、大前端等分工模式的创新不仅提高了前端和其它工种的协作效率，也让前端有机会承担应用研发。由“前端 + 设计”组合形成的“体验技术部”也成为很多业务的标配，部分前端团队甚至发展为应用研发团队并且拥有了自研产品。前端的影响圈已经从应用开发延展到了用户体验甚至产品设计，以人机交互为本的 [体验科技](https://www.yuque.com/yubo/words/tcaywl) 也开始崭露头角。

这些变革因子的背后是**两条主线**：
* **让现有研发工作做得更好**：开发套件是主要推手，一些分工模式（比如：前后端分离）的创新也归属这条线
* **开辟新战场**：引擎是主要推手，一些分工模式（比如：全栈）的创新也归属这条线上

这些变革之所以会发生，是因为有**一个刚需：客户端软件的生产力水平满足不了飞速增长的互联网应用诉求，而前端技术恰好能提升应用研发的生产力水平**。虽然移动互联网的崛起曾一度让前端缺少发力之处，但寄生于超级 App 上的 Hybrid 容器又让前端焕发了生机，小程序更是将之推向了和 PC 时代同样重要的地位。应用虽然琳琅满目，但其形态演化也是有迹可循的，要讲清楚得专门写一篇文档，这里不过多展开，简单介绍几个我认为最重要的：
* **UGC 内容的主流载体在变**：文本 -> 图片 -> 短视频/直播，用户创作内容的成本越来越低了
* **终端的主流交互方式在变**：PC(键盘/鼠标) -> 手机/PAD(触屏/摄像头/语音)，交互越来越自然、简单了
* **信息获取的主流方式在变**：主动获取 -> 被动推送 -> 智能推荐，异步 -> 实时，信息已触手可得

> 这**一个刚需、两条主线、三类因子**也是我们预判未来的重要依据。

## 立足当下

在当下可实践的**新技术中，前端相关的有：AI、Serverless/FaaS、Blockchain、IOT、AR/VR/MR、**智能硬件**、可视化应用开发**。不可否认，它们都是能在一些领域带来颠覆性革命的技术，但是否会给前端带来变革呢？让我们详细分析一下：
* **AI**：核心是云，而且 AI 应用的典型特点是“重引擎轻 UI”，所以前端不在主赛道，只能在应用开发中使用它。目前市面上的 AI 应用，多数是大数据技术的延伸，离 Intelligence 还太远。**作为人类技术的巅峰之作，AI 应该在人类最难解决的问题上发挥价值，比如：语言文字、医疗、科研、教育、环境等**。个人看好机器翻译，打破语言界限将会是人类文明一次划时代的变革。作为前端，我们也应该去关注这些基础领域，并学习和掌握 AI 技术。
* **Serverless/FaaS**： 核心是云，前端能做的是基于这种技术优化 Node.js 在服务端的 Runtime 和运维方式，把服务端复杂的技术细节屏蔽掉，让 Node.js 开辟出来的服务端战场可以延续，让端上所需的数据能以简洁、低成本的方式存储和获取。当然，也可以基于它优化现有的工具体系，让开发越来越简单。
* **Blockchain**：核心还是云，和前端最相关的是 [Decentralized Application(DApp)](https://github.com/DavidJohnstonCEO/DecentralizedApplications)、[IPFS(the InterPlanetary File System)](https://ipfs.io/)。但 DApp 是一种新的应用形态，IPFS 改变的是网络协议。这两者还处于非常早起的阶段，发展形势还不明朗，最好是静观其变，在合适的时候基于它们开发应用。
* **IOT**：核心是端，但关键技术是硬件及嵌入式系统，和前端交集较少，发挥空间很有限。除了在之上开发应用外，能看到的还有两个潜在方向：把 Node.js、浏览器内核移植到 IOT 设备，打造一个可运行前端代码的 Runtime；部分设备需要展示数据，可以基于图形技术打造专属渲染引擎。
* **AR/VR/MR**：核心是硬件及交互方式的变化，前端能参与到类库及应用开发中。但受设备所限，目前还不是应用的主流，需要结合业务特点寻找切入点。
* **智能硬件**：机器人则是这项技术的终极形态。其核心在 AI 、自动化控制及硬件上，给前端带来的更多是应用形态和交互方式的升级。
* **可视化应用开发**：不写/少写代码就完成开发，这是前端的一个夙愿，不可能完全达成，但在特定场景下是可以做到的。MFC、Dreamweaver、Flash、Microsoft 是该领域的先驱，[Wix](https://www.wix.com/)、[Webflow](https://webflow.com/)、[Bubble](https://bubble.is/)、[Node-RED](https://nodered.org/)、[FrameX](https://www.framer.com/)、[PowerApps](https://powerapps.microsoft.com/en-us/) 是当下值得关注的。其本质上仍是通过更好的开发套件提升应用生产效率，其最大竞品是成品 SaaS，毕竟拿来就用比搭建更简单，这就如同当需要一台电脑时多数人会选择买成品而不是买配件组装。

综上来看，**这些新技术的关键路径和核心技术多数都不在前端，但我们能以使用者的身份参与进去，结合业务特点进行实践，让现有研发工作做得更好，让应用的交互体验更好**。不过，还是有两个前端强相关的技术有望带来变革：
* **IOT 上的 App Runtime** ：其背后就是一个引擎，能让前端应用运行在越来越多的新型终端上
* **可视化应用开发**：有望把部分功能和应用的开发成本降到最小

## 一窥未来

应用形态日新月异，新技术风起云涌，未来扑朔迷离...作为前端，我们究竟该往那些方向进行技术储备呢？要找到有指导意义的技术路线图，除了前文这些分析外，还得回到前端的本质中去探寻变革背后那些不变的东西，只有它们才能让我们以不变应万变，把技术转换为生产力。

前端技术发展变化虽然很快，但从程序的视角来看，有两个东西一直未变：
* 终端的形态和交互方式一直在变，其本质未变：
  * **渲染数据**：把数字世界的数据转换成可被人感知的声音或图像，图形技术、音频技术、排版技术是核心
  * **采集数据**：把物理世界的数据、人脑中的知识转换到数字世界，传感器技术、编辑器技术是核心
* 应用的类别和交互方式在变，但应用研发始终可以分解为四大部分：
  * **云**：提供应用运行所需的数据，托管资源及可执行代码
  * **端**：依托某个 App Runtime 提供 UI 给最终用户
  * **专项技术**：业务是技术之本，脱离了业务，前端将是无根之萍，而每个业务都有其专业属性和专项技术
  * **App Development Engine**：也即“开发套件”，在普通工程师完全自主可控的范围内提升生产力

结合以上分析以及我所参与研发的语雀这个业务的特点，整理了下边这幅前端技术大图以抛转引玉：<br />![20190221211405.png](https://cdn.nlark.com/yuque/0/2019/png/84145/1550754874871-896b1612-d27d-4c3d-8691-d741ce8d9f6d.png#align=left&display=inline&height=500&name=20190221211405.png&originHeight=1000&originWidth=1440&size=148796&status=done&width=720)<br />图中的每个区域都是一个不小的技术领域，要完全讲清楚得专门写文章，再加不少领域我只是略知一二，就不过多展开了，只简单介绍几个我认为比较重要的方向。

### App Development Engine
当下的 Web 应用开发真的让人揪心，学习曲线非常陡峭、新概念层出不穷、技术更新换代太快...应用复杂度并不比十年前高多少，但要学习和掌握的东西是之前的很多倍。身处产品研发这个战场的前线，我们的装备一点都不精良，大把精力耗在作战无关的地方。生产力虽然在提升，但完全赶不上业务增长速度，App Developement Engine 这个提升生产力的关键因子在当下显得尤为重要。

这个领域是创新最活跃的地方，从过去的发展历程中能看到一些演进脉络：
* 从 Engine 的角度看，演进的背后有两种理念：
  * **Coding Less**：通过强大的 SDK、框架和工具让工程师更好地 Coding，专注在实现业务上
  * **No Coding**：通过可视化 IDE 达成不写代码，通过拖拽、编写配置文件就能完成应用开发
* 从开发者角度看，对 Engine 有三个期待：
  * **Productivity**：必须能提升生产力，让工程师可以高效地写出健壮、易维护的代码
  * **Simple & Stupid**：[KISS 原则](https://en.wikipedia.org/wiki/KISS_principle) 的核心，让开发变简单不仅能提升效率，还能让更多人成为前端工程师
  * **Business More**：研发资源非常宝贵，让工程师专注在业务上是提升效能的关键

未来的演化也会遵循这些脉络，Coding Less、No Coding 各有其应用场景，需要结合业务特点选择侧重点进行投入。但有一点我觉得是必然的：要开发优质应用，还得靠 Coding，不过写的代码会越来越少。No Coding 过于完美，应用场景有限，再加上有成品 SaaS 作为更好的替代品，我更倾向于用 Coding Less 模式去实现业务主线，把一些机械性、重复性、一次性的开发工作通过 No Coding 模式搞定。不过 No Coding 的一个分支 [Visual Programming](https://en.wikipedia.org/wiki/Visual_programming_language) 非常值得关注，它在编程教育领域应用前景非常好，[Scratch](https://scratch.mit.edu/) 、[Blockly](https://developers.google.com/blockly/) 是典型代表，而编程教育不仅蕴藏着巨大的商机，而且还会给我们带来源源不断的生力军。

### 语雀专项技术

**语雀致力于打通「知识」和「大脑」之间的双向通道**，背后是两大关键技术：
* **编辑器**：知识从大脑到数字世界的关键，语雀当下的文本编辑器、目录编辑器还很初级
* **[知识可视化](https://infovis-wiki.net/wiki/Knowledge_Visualization)**：知识被人脑感知和理解的关键，给知识最佳的呈现形态有助于知识的理解和传播

“数据可视化”和“数字孪生”在当下和语雀的关联并不大，但在未来一定会和语雀紧密相关：
* 数据不仅是科学研究的基础，其背后本身就蕴藏着知识，数据可视化可以让这些知识更好地呈现给人们
* 数字孪生和知识结合蛮有想象空间的，比如：数字博物馆、虚拟天文馆、仿真生态系统

### App Runtime
**为什么 App Rutime 会是变革的生力军呢**？因为历史告诉我们：引擎的革新是开辟新战场的核心驱动力，而 App Rutime 的核心恰好就是引擎及其之上的 SDK。在很长一段时间里，前端技术得益并受限于浏览器引擎，广大前端工程师只能在 App Development Engine 层发力。但时至今日，终端、应用形态的多样性越来越强，移动互联网已经打破浏览器一统天下的局面，不难看出**浏览器技术的进化速度已不能满足越来越多的新型终端和应用形态了**。

可以大胆地预测在这个领域必然会有一场变革，变革有可能由浏览器进化产生，也有可能是一些新的引擎。已经能看到一些苗头了：
* Office 以惊人的速度和 UI 一致性覆盖了所有终端，猜测其背后有一套跨端 UI 方案
* 超级 App 打破了浏览器一统天下格局，小程序已是新的 Runtime
* [Flutter](https://flutter.io/) 在探索的就是一个新的跨端 UI 开发方式
* [Fuchsia](https://en.wikipedia.org/wiki/Google_Fuchsia) 则是 Google 在探索的一个更大的局，从 OS 层面推动变革

更关键的是：**这场变革是前端工程师有机会参与进去的**，因为引擎的核心技术——图形技术已经在数据可视化、H5 Game 的推动下成为不少团队能熟练使用的技术。而应用类型的多样性也会给一些垂直市场的 App Runtime 留下生存空间，这块已经有一些成功案例，比如：游戏领域的 [Cocos 引擎](https://www.cocos.com/) 和 [白鹭引擎](https://www.egret.com/)、桌面软件开发领域的 [Electron](https://electronjs.org/)，未来应该还会有更多。

<a name="88e40f36"></a>
### 领域服务
“**领域服务**”对前端来说可能比较陌生，它的背后是大名鼎鼎的 [领域驱动设计（DDD:Domain-Driven Design）](https://www.jdon.com/ddd.html)，是应用在云端部分的高度抽象，是系统中的稳定部分，这也正是前端总是改版而服务端接口却可以不变的原因。服务端研发有这样一条演化主线：解决编程语言层面的问题 -> 解决开发框架 & 类库问题 -> 专注于解决业务问题，Java -> Spring -> DDD & Sofaware Architecure 就是典型案例。服务端之所以抗变能力这么强，正式由于把主要精力放在了领域模型抽象和系统架构设计上。

为何领域服务在当下对前端也这么重要，因为：
* 领域模型和领域服务是对业务的抽象，也是理解业务的直观体现，好的领域模型能大大降低前端开发成本
* 领域设计的相关思想、理念可以借鉴到前端中，给前端带来解决问题的新思路
* 前端处于研发的十字路口，信息面最广，极有潜力协调产品、设计、服务端等工种共同梳理领域模型和业务链路

关于 DDD，可以从这三种非常容易理解和掌握的经典架构入门：
* [Hexagonal Architecture(Ports and Adapters)](https://fideloper.com/hexagonal-architecture)
* [CQRS - Command Query Responsibility Segregation](https://martinfowler.com/bliki/CQRS.html) 
* [The Clean Architecture](http://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html) 

<a name="5e3aaf2a"></a>
### 全功能型团队
前端是工程师中离用户最近的群体，很多前端心中都有一个产品梦，这个产品可能是一个技术产品也可能是一个用户产品。很长一段时间内，我们疲于生存，只能忙里偷闲折腾个小工具或者参加下 Hackathon。但随着技术的演进，不少团队已经具备了全栈能力，并承担了 App Development Engine 中的一些平台的自主研发，让这个梦近了一些。但要完整实现，光有全栈能力是远远不够的，还需要一个包含技术、产品、设计、运营的全功能团队才能达成，这种团队不仅能提升协作效率、保证交付质量，还有可能催生出商业化产品。很多公司都在往大中台 + 小前台的方向发展，而支撑小前台的恰恰就是全功能型团队。所以在时机成熟时可以组建全功能型团队，逐步承接业务中人机交互部分的研发工作，让“用户体验”能落到实处。

<a name="886ad72f"></a>
## 砥砺前行
![quote-the-best-way-to-predict-the-future-is-to-create-it-peter-drucker-8-18-80.jpg](https://cdn.nlark.com/yuque/0/2019/jpeg/84145/1550673772530-9974e370-e3e4-4a76-94d0-a81dae16e94d.jpeg#align=left&display=inline&height=339&name=quote-the-best-way-to-predict-the-future-is-to-create-it-peter-drucker-8-18-80.jpg&originHeight=400&originWidth=850&size=48353&status=done&width=720)

**前端技术的未来，没有标准大图，这份图蕴含在每个业务中**，更需要脚踏实地把未来亲手打造出来，业界趋势、新技术、新产品形态都是可以借力的因素。如果你已经有一个愿意与之一起奋斗和成长的业务，就可以结合业务定期推演适合它不同发展阶段的技术大图。如果还没有，也不用急，打好技术基础，做好手上的每个项目，结合业务在 Appliaction Development Engine 领域探索和实践，逐步寻找真正想做的业务、想服务的用户。

**软件研发是一项理论和实践并重的技术，实践尤为重要**，因为最终我们是要写出健壮运行的代码给用户用的。不管未来如何，在持续学习和实践中强化对编程、技术、业务的理解才是根本。除了学习和实践与业务最相关的技术外，建议按自己的专长和兴趣把重点放在这些领域：
* **领域驱动设计**：强化领域建模和系统设计能力，力争懂业务、成为领域专家
* **软件架构设计和软件设计哲学**：它们会为系统、框架、类库注入灵魂，让代码有生命力
* **图形技术**：在应用、引擎两层都有广阔的场景，最关键的是图形应用在未来的占比一定会越来越高
* **AI** ：不必深入到底层，但需要掌握其使用，不妨先从 [TensorFlow](https://tensorflow.google.cn/) 开始


<br />**编程是一种修行**，应用修行的产物，也是我们与世界交流的方式。<br />未来在哪里并不重要，重要的是以空杯心态持续学习和实践，**用心写下每行代码**。

> 欢迎来语雀沉淀你的专业知识，让你对编程、技术、产品的理解和思考可以被更多人看见。
> 语雀会努力提供最好的服务，让你安静地创作、愉快地分享。


---
**ref:**
[Digital Twin – The Machines’ Mind](https://medium.com/@tharanignanasegaram/digital-twin-the-mind-of-a-machine-7c540df52026)  
[Origins of the Digital Twin Concept](https://www.researchgate.net/publication/307509727_Origins_of_the_Digital_Twin_Concept) 
[Top 10 Strategic Technology Trends for 2019](https://www.gartner.com/doc/3891569)  
[Gartner发布 2019 年十大战略性技术趋势](https://baijiahao.baidu.com/s?id=1614716982959356641)  
[什么是Digital Twin](https://www.sohu.com/a/271145904_739983)  
[Dapp.com - Learn Everything About Decentralized Apps](https://www.dapp.com/)  
[The General Theory of Decentralized Applications, Dapps](https://github.com/DavidJohnstonCEO/DecentralizedApplications)  
[IPFS is the Distributed Web](https://github.com/ipfs/ipfs)  
[You Do Not Need Blockchain: Eight Popular Use Cases And Why They Do Not Work](https://blog.smartdec.net/you-do-not-need-blockchain-eight-popular-use-cases-and-why-they-do-not-work-f2ecc6cc2129) 
[Cloud Programming Simplified: A Berkeley View on Serverless Computing](https://rise.cs.berkeley.edu/blog/a-berkeley-view-on-serverless-computing/)  
[Knowledge Visualization](https://www.medien.ifi.lmu.de/lehre/ws0809/hs/docs/meyer.pdf)  
[Google Fuchsia release date, news and rumors](https://www.techradar.com/news/google-fuchsia)  
[The Kiss Principle](https://people.apache.org/~fhanik/kiss.html)  
[Basics of the Unix Philosophy](http://www.catb.org/esr/writings/taoup/html/ch01s06.html)  
[Principles Wiki](http://principles-wiki.net/)  
[Demystifying the Hexagon](https://hackernoon.com/demystifying-the-hexagon-5e58cb57bbda)  
[Software Architecture Design](https://github.com/zenany/weekly/blob/master/resources/software_architecture.md)  
[前端开发漫游指南](https://github.com/zenany/zenany.github.io/blob/master/_posts/about_frontend.md)  
[体验科技与好的社会](https://www.yuque.com/yubo/explore/tcaywl)  



