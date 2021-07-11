---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
aspectRatio: 16/9
info: |
  ## Memocast Presentation Slides

  Learn more at [GitHub](https://github.com/TankNee/Memocast)
title: Memocast
---

# Memocast

一个所见即所得的为知笔记客户端，基于 Electron 打造。

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    即刻一览! <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/TankNee/Memocast" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
layout: cover
class: text-center
---
# 获取演示并体验

可以通过以下链接获取到当前幻灯片

幻灯片链接: [https://www.tanknee.cn/Memocast-Slide](https://www.tanknee.cn/Memocast-Slide)

---
layout: image-right
image: https://source.unsplash.com/collection/94714566/1920x1080
---

# 团队成员

<div>
  <div style="display:flex;align-items:center;">
    <img src="https://img.tanknee.cn/blogpicbed/2020/06/2020060186bc451656937.png" style="width:100px;height:100px;border-radius:50%;margin:10px;">
    <p>
      <p>
        <span>倪桐珂</span>
      </p>
      <p>
        <span>Memocast 小组组长，负责框架搭建，技术选型，产品主体开发。</span>
      </p>
    </p>
  </div>
  <div style="display:flex;align-items:center;">
    <img src="https://img.tanknee.cn/blogpicbed/2021/07/11/20210711c47d246ed8d05.png" style="width:100px;height:100px;border-radius:50%;margin:10px;">
    <p>
      <p>
        <span>王格格</span>
      </p>
      <p>
        <span>负责项目部分功能实现，承担产品测试等职责。</span>
      </p>
    </p>
  </div>
  <div style="display:flex;align-items:center;">
    <img src="https://img.tanknee.cn/blogpicbed/2021/07/09/20210709d6d69c230d466.png" style="width:100px;height:100px;border-radius:50%;margin:10px;">
    <p>
      <p>
        <span>王怡贤</span>
      </p>
      <p>
        <span>负责产品测试，承担产品文档编写，产品国际化部分实现等职责</span>
      </p>
    </p>
  </div>
  <!-- <img src="https://img.tanknee.cn/blogpicbed/2021/07/09/20210709d6d69c230d466.png" style="width:100px;height:100px;border-radius:50%;margin:20px;">
  <img src="https://img.tanknee.cn/blogpicbed/2021/07/09/20210709d6d69c230d466.png" style="width:100px;height:100px;border-radius:50%;margin:20px;"> -->
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4E25D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
}
</style>

---
preload: false
---

# 起源

时间来到2021年，许多的笔记应用都支持了Markdown，但大多支持的并不够完整，或是缺少快捷的输入设置，或是不支持完整的Markdown语法，抑或是其他不尽人意的地方，因此我也借这个机会想要创造一款流畅优雅的笔记软件满足这一部分人的细分需求。

于是我们决定开始着手创建。

我们将它称之为 Memocast ，意为 Cast Your Memo ，将你的思想碎片汇集成笔记，其体验一如思考般简单，同时，我们还为此绘制了图标，以 M 为主体，黑色为底调，其含义一为我们产品名称的开头字符，二为我们所处理的文件格式主要是 Markdown 格式，同时也希望我们的产品能像图标一般简洁明了。

<div>
  <!-- <img src="https://img.tanknee.cn/blogpicbed/2021/07/08/20210708fc3b67e797e90.png" style="width:250px;height:250px;margin:20px;"> -->
  <div class="w-60 relative mt-6">
  <div class="relative w-40 h-40">
    <img
      v-motion
      :initial="{ x: 800, y: -100, scale: 1.2 }"
      :enter="final"
      class="absolute top-0 left-0 right-0 bottom-0"
      src="https://img.tanknee.cn/blogpicbed/2021/07/11/2021071137c6d82e085c4.png"
    />
  </div>

  <div 
    class="text-5xl absolute top-14 left-60 -z-1"
    v-motion
    :initial="{ x: -150, opacity: 0}"
    :enter="{ x: 0, opacity: 1, transition: { delay: 2000, duration: 1000 } }">
    Memocast
  </div>
</div>
</div>


<script setup lang="ts">
const final = {
  x: 0,
  y: 0,
  rotate: 0,
  scale: 1,
  transition: {
    type: 'spring',
    damping: 10,
    stiffness: 20,
    mass: 2
  }
}
</script>

---

# 技术栈

<div style="display:flex;">
  <div style="display:flex;align-items:center;flex-direction:column;">
    <img src="https://img.tanknee.cn/blogpicbed/2021/07/09/2021070993e5adfdbc3f3.png" style="width:100px;height:100px;border-radius:50%;margin:20px;">
    <p>
      <span>Electron</span>
    </p>
  </div>
  <div style="display:flex;align-items:center;flex-direction:column;">
    <img src="https://img.tanknee.cn/blogpicbed/2021/07/09/202107096c8071b08c1fa.png" style="width:100px;height:100px;border-radius:50%;margin:20px;">
    <p>
      <span>Quasar</span>
    </p>
  </div>
  <div style="display:flex;align-items:center;flex-direction:column;">
    <img src="https://img.tanknee.cn/blogpicbed/2021/07/09/20210709cd74c125eb56c.png" style="width:100px;height:100px;margin:20px;">
    <p>
      <span>Vue</span>
    </p>
  </div>
  <!-- <img src="https://img.tanknee.cn/blogpicbed/2021/07/09/20210709d6d69c230d466.png" style="width:100px;height:100px;border-radius:50%;margin:20px;">
  <img src="https://img.tanknee.cn/blogpicbed/2021/07/09/20210709d6d69c230d466.png" style="width:100px;height:100px;border-radius:50%;margin:20px;"> -->
</div>

- 使用Electron构建桌面平台，支持 Windows、macOS、Linux，并使用 Electron-Builder 构建分发包，在 GitHub 提供升级服务器。同时借助Electron提供的能力为用户提供接近原生应用的体验（例如列表、文档树的上下文菜单）

- 使用Quasar UI Framework构建用户界面，实现统一的Material Design风格

- 使用Vue、Vuex、Vue Router生态构建页面框架，使用Vue-i18n实现用户界面、用户提示的多语言

---
layout: cover
class: text-center
---
# 设计思路

Design
---

# 设计思路

## 调研市面上的优秀笔记软件

Typora

![](https://img.tanknee.cn/blogpicbed/2021/07/09/202107099685b3390fe6f.png)

---

# 设计思路

## Mark Text

![](https://img.tanknee.cn/blogpicbed/2021/07/09/2021070953550854445f0.png)

---

# 设计思路

## 为知笔记

![](https://img.tanknee.cn/blogpicbed/2021/07/09/202107097684ed18db9f2.png)

---

# 设计思路

## 原型图

![](https://img.tanknee.cn/blogpicbed/2021/07/09/2021070939dc151e2e57a.png)

---
layout: cover
class: text-center
---
# 确定需求与项目目标

Requirement and Destination

---

# 确定需求与项目目标

| 需求名称         | 描述            |
| ------------ | ----------------------- |
| 用户注册         | 用户第一次使用时需要注册            |
| 用户登陆         | 用户需要登陆以使用软件             |
| 新建笔记         | 用户可以新建一个笔记              |
| 笔记修改         | 用户可以对笔记内容进行编辑           |
| 笔记排序         | 用户可以选择不同的方式对笔记进行排序      |
| Markdown实时渲染 | Markdown文档可以进行实时渲染      |
| 切换源代码模式      | 用户可以在实时渲染和源代码模式之间切换     |
| 快速插入         | 通过快捷方式插入图片等             |
| 笔记管理         | 用户对笔记进行管理               |
| 文件夹管理        | 用户可以建立文件夹并管理            |

---

# 确定需求与项目目标

| 需求名称         | 描述            |
| ------------ | ----------------------- |
| 标签管理         | 用户可以建立标签并管理             |
| 内容搜索         | 对所有笔记内容进行搜索             |
| 编辑器主题修改      | 编辑器的主题可以修改              |
| 多语言支持        | 软件语言可以在中文和英文之间切换        |
| 笔记锁定         | 笔记可以进行锁定，无法编辑           |
| 界面切换         | 软件界面可以在不同排布方式下切换        |
| 网络笔记导入       | 可以对微信、微博等网络笔记进行快捷导入     |
| 本地笔记导入       | 用户可以将本地的Markdown笔记导入编辑器 |
| 笔记导出         | 用户可以导出笔记到本地             |

---

# 确定需求与项目目标

| 需求名称         | 描述            |
| ------------ | ----------------------- |
| 快捷键          | 用户可以使用快捷键访问功能           |
| 软件更新         | 软件可以检查版本更新              |

## 项目目标

我们希冀创造一个流畅，便捷，得心应手的编辑器软件，我们将会把 Markdown 作为第一公民，用更多的精力去保障 Markdown 的写作、阅读体验，同时在保证体验的目标以外还要竭尽可能去提升写作效率，并完成从发布到更新的全链条产品，而不是单纯的一个软件，我们希望用 GitHub 的平台来串联所有的用户，让软件不是无本之木、无源之水。

---
layout: cover
class: text-center
---
# 项目结构

Project Structure

---

# 项目结构

<div align="center">
  <img src="https://img.tanknee.cn/blogpicbed/2021/07/10/2021071096eff5151fa5b.svg" alt="structure"/>
</div>



---

# 项目结构

> 为什么要这么做，因为笔记应用一个重要的特征就是流畅，如果动画，渲染等部分出现了少许停顿，就可能在用户心里留下卡顿的印象，如果出现某些错误没有提示，而是直接卡死那么更会导致用户心理预期直线下降。分层，是为了更好的划清职责，也是为了让每一层都做好自己的事情。

##  Render And Interact

这一层是与用户直接接触的，是最影响体验的，我将这一层再细分为几个部分：

1. **UI 与动画**。如果说功能是让用户留下来的关键，那么第一眼的视觉观感就是用户会不会来尝试的关键，我们使用了开源社区知名的 Quasar UI Framework 来绘制我们的用户界面，应用经典的 Material Design 风格，并且大量使用了水波纹动画，让整体质感更加灵动圆润。

2. **性能**。除了必要的样式资源，js资源以及部分网络图片资源以外，整个渲染进程不会发送额外的网络请求，专注于体验。

3. **快捷输入与快捷键**。我们的编辑器将对 Markdown 进行针对性优化，由于 Markdown 中有许多的样式代码，虽然不是特别复杂，但是如果缺少了快捷输入那么也会影响用户体验，同时针对复杂的表格操作，无处安放的笔记图片资源，我们也都提供了一套完整的解决方案。

---

# 项目结构

## Data Processing

这一层接受来自主进程的笔记数据，同时将来自渲染层的请求包装成合法的请求传递给主进程。

同时这一层还管理着整个应用界面的状态，将原始数据包装成 Getters 提供给渲染层，将与主进程交互的能力包装成 Actions ，为渲染层和主进程两者提供沟通的桥梁

## File System and Native Platform

这一层主要是处理存储在本地的用户信息，包括账号，编辑器设置，图片缓存，笔记缓存等等，一切的手段都是为了提高交互体验，减少等待时间，同时也在这一层注册一些跟操作系统相关的菜单，快捷键等。

我们还在这一层自定了私有协议，部分上传到笔记服务器的图片数据将会通过私有协议保存到本地，第二次访问时，如果本地的缓存仍然存在，那么就直接传输本地数据，而不需要再次进行请求。

---
layout: cover
class: text-center
---
# 功能展示

---
layout: cover
class: text-center
---
# 细节优化与提升

---

# 细节优化与提升

> 以打字机模式为例
## 打字机模式

在 Word 等大多数编辑软件中，如果你输入了很多内容，超过一屏之后，光标通常会位于屏幕最下方，这时除非你滚动一下文档，否则光标会一直处于屏幕最下的位置，你的视线也只能一直盯在这个位置，这对需要长时间输入的用户来说并不友好。所谓打字机模式，其实就是像传统的打字机一样，在用户输入时将光标在屏幕上的 y 坐标固定（比如固定在屏幕中间），这样便能保持用户视线高度固定。在技术上来说，就是固定文档的滚动位置。

在 Memocast 中，也同样会有这样的问题，因此我们选择监听用户的光标位置，当其与视窗底部的距离小于一个固定值时，自动向下滚动一段距离

```javascript{all|2|4|6|7|all}
// 如果当前光标已经非常靠近视窗底部，那么就进行打字机模式的滚动
if (container.clientHeight - y < 100) {
  // 计算当前可编辑区域的高度
  const editableHeight = container.clientHeight - 100
  // 对于不同的操作系统进行不同的处理
  if (this.$q.platform.is.mac) {
    helper.animatedScrollTo(container, container.scrollTop + (y - editableHeight), 100)
  } else {
    container.scrollTop = container.scrollTop + (y - editableHeight)
  }
}
```
---

# 细节优化与提升

<div align="center">
  <img border="rounded" src="http://cdn.jsdelivr.net/gh/TankNee/Memocast-Slide/resource/typewriter.gif"/>
</div>

除此以外还有源代码模式，多栏模式，单栏模式等，不再赘述。

---
layout: cover
class: text-center
---
# 性能优化
---
---
# 性能优化

> 性能也是笔记应用的重中之重

在项目的开发伊始，我们只是顺着网页应用开发的思维惯性，将网络请求，图片，样式资源等都放在渲染进程中，与后端服务的交互也全部都放在渲染进程中，这样做的好处是显而易见的，那就是开发十分便捷，所有请求都可以直接通过 Chrome Devtool 直观的看到，方便调试，不过也有不利的影响，那就是渲染进程的资源终归是有限的，当有一大部分去执行网络请求时，就会导致渲染、用户交互部分的性能变得捉襟见肘，也就容易出现卡顿等问题。

我们的解决方案是迁移网络请求部分，把所有跟为知服务后端交互等接口都封装起来，通过 IPC 调用 Electron 主进程提供等一个接口，通过主进程调用网络请求，降低渲染进程等压力。

---

# 性能优化

<div grid="~ cols-2 gap-2" m="-t-2">

## 迁移之前

## 迁移之后

<img border="rounded" src="http://cdn.jsdelivr.net/gh/TankNee/Memocast-Slide/resource/performance/before.png"/>

<img border="rounded" src="http://cdn.jsdelivr.net/gh/TankNee/Memocast-Slide/resource/performance/after.png"/>

</div>
<br/>
可见在调整了网络请求等策略之后，还是有一定的性能提升的。
