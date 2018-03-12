**如何评价AngularJS和BackboneJS**

- backbone具有依赖性，依赖underscore.js。Backbone + Underscore + jQuery(or Zepto)就比一个AngularJS 多出了2 次HTTP请求.

- Backbone的Model没有与UI视图数据绑定，而是需要在View中自行操作DOM来更新或读取UI数据。AngularJS与此相反，Model直接与UI视图绑定，Model与UI视图的关系，通过directive封装，AngularJS内置的通用directive，就能实现大部分操作了，也就是说，基本不必关心Model与UI视图的关系，直接操作Model就行了，UI视图自动更新
- AngularJS的directive，你输入特定数据，他就能输出相应UI视图。是一个比较完善的前端MVW框架，包含模板，数据双向绑定，路由，模块化，服务，依赖注入等所有功能，模板功能强大丰富，并且是声明式的，自带了丰富的 Angular 指令

**谈谈你对重构的理解**

- 网站重构：在不改变外部行为的前提下，简化结构、添加可读性，而在网站前端保持一致的行为。也就是说是在不改变UI的情况下，对网站进行优化， 在扩展的同时保持一致的UI

- 对于传统的网站来说重构通常是：

  - 表格(table)布局改为DIV+CSS

  - 使网站前端兼容于现代浏览器(针对于不合规范的CSS、如对IE6有效的)

  - 对于移动平台的优化

  - 针对于SEO进行优化

  - 深层次的网站重构应该考虑的方面
  
**说说你对前端架构师的理解**

- 负责前端团队的管理及与其他团队的协调工作，提升团队成员能力和整体效率；带领团队完成研发工具及平台前端部分的设计、研发和维护； 带领团队进行前端领域前沿技术研究及新技术调研，保证团队的技术领先负责前端开发规范制定、功能模块化设计、公共组件搭建等工作，并组织培训

**什么样的前端代码是好的**

- 高复用低耦合，这样文件小，好维护，而且好扩展。

**谈谈你对webpack的看法**

> WebPack 是一个模块打包工具，你可以使用WebPack管理你的模块依赖，并编绎输出模块们所需的静态文件。它能够很好地管理、打包Web开发中所用到的HTML、Javascript、CSS以及各种静态文件（图片、字体等），让开发过程更加高效。对于不同类型的资源，webpack有对应的模块加载器。webpack模块打包器会分析模块间的依赖关系，最后 生成了优化且合并后的静态资源

**页面重构怎么操作？**

* 网站重构：不改变UI的情况下，对网站进行优化，在扩展的同时保持一致的UI。

* 页面重构可以考虑的方面：
    - 升级第三方依赖
    - 使用HTML5、CSS3、ES6 新特性
    - 加入响应式布局
    - 统一代码风格规范
    - 减少代码间的耦合
    - 压缩/合并静态资源
    - 程序的性能优化
    - 采用CDN来加速资源加载
    - 对于JS DOM的优化
    - HTTP服务器的文件缓存
    
**列举IE与其他浏览器不一样的特性？**

* IE 的渲染引擎是 Trident 与 W3C 标准差异较大：例如盒子模型的怪异模式
* JS 方面有很多独立的方法，例如事件处理不同：绑定/删除事件，阻止冒泡，阻止默认事件等
* CSS 方面也有自己独有的处理方式，例如设置透明，低版本IE中使用滤镜的方式

**是否了解公钥加密和私钥加密？**


* 私钥用于对数据进行签名，公钥用于对签名进行验证
* 网站在浏览器端用公钥加密敏感数据，然后在服务器端再用私钥解密

**WEB应用从服务器主动推送Data到客户端有那些方式？**
* AJAX 轮询
* html5 服务器推送事件
`(new EventSource(SERVER_URL)).addEventListener("message", func);`
* html5 Websocket
 - `(new WebSocket(SERVER_URL)).addEventListener("message", func);`
 
**你怎么看待 Web App/hybrid App/Native App？（移动端前端 和 Web 前端区别？）**

* Web App(HTML5)：采用HTML5生存在浏览器中的应用，不需要下载安装
  - 优点：开发成本低，迭代更新容易，不需用户升级，跨多个平台和终端
  - 缺点：消息推送不够及时，支持图形和动画效果较差，功能使用限制（相机、GPS等）
  
 * Hybrid App(混合开发)：UI WebView，需要下载安装
   - 优点：接近 Native App 的体验，部分支持离线功能
   - 缺点：性能速度较慢，未知的部署时间，受限于技术尚不成熟
  
* Native App(原生开发)：依托于操作系统，有很强的交互，需要用户下载安装使用

  - 优点：用户体验完美，支持离线工作，可访问本地资源（通讯录，相册）
  - 缺点：开发成本高（多系统），开发成本高（版本更新），需要应用商店的审核
  
**Web 前端开发的注意事项？**

* 特别设置 meta 标签 viewport
* 百分比布局宽度，结合 box-sizing: border-box;
* 使用 rem 作为计算单位。rem 只参照跟节点 html 的字体大小计算
* 使用 css3 新特性。弹性盒模型、多列布局、媒体查询等
* 多机型、多尺寸、多系统覆盖测试

**在设计 Web APP 时，应当遵循以下几点**

* 简化不重要的动画/动效/图形文字样式
* 少用手势，避免与浏览器手势冲突
* 减少页面内容，页面跳转次数，尽量在当前页面显示
* 增强 Loading 趣味性，增强页面主次关系

**平时如何管理你的项目？**

* 规定全局样式、公共脚本
* 严格要求代码注释(html/js/css)
* 严格要求静态资源存放路径
* Git 提交必须填写说明

**如何设计突发大规模并发架构？**

* 及时响应(NoSQL缓存)
* 数据安全(数据备份)
* 负载均衡

**说说最近最流行的一些东西吧？**

- ES6、Node、React、Webpack
