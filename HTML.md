**HTML `<a>` 元素**（或称锚元素）可以创建通向其他网页、文件、同一页面内的位置、电子邮件地址或任何其他 URL 的超链接。

- `href`: 这个属性声明超链接的web地址，当这个链接被点击浏览器会跳转至href声明的web地址。例如：`href="https://www.mozilla.org/"`。
- `title`: 标题`title`属性为超链接声明额外的信息，比如你将链接至的那个页面。例如：`title="The Mozilla homepage"`。当鼠标悬停在超链接上面时，这部分信息将以工具提示的形式显示。
- `target`: 目标`target`属性用于指定链接如何呈现出来。例如，`target="_blank"`将在新标签页中显示链接。如果你希望在当前标签页显示链接，忽略这个属性即可。

```
<p>You can reach Michael at:</p>

<ul>
  <li><a href="https://example.com">Website</a></li>
  <li><a href="mailto:m.bluth@example.com">Email</a></li>
  <li><a href="tel:+123456789">Phone</a></li>
</ul>
```

![image-20210319203100284](C:%5CUsers%5Clenovo%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210319203100284.png)



```
<input type="text" disabled="disabled">
```

一个完整的html页面：

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>我的测试站点</title>
  </head>
  <body>
    <p>这是我的页面</p>
  </body>
</html>
```



1. :声明文档类型. 能自动检测错误和其他有用的东西。使用如下：

   ```
   <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
   "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
   ```

   然而这种写法已经过时了，这些内容已成为历史。只需要知道它是最短有效的文档声明。

2. `<html></html>`: `<html>`元素。包裹了整个完整的页面，是一个根元素。

3. `<head></head>`: `<head>元素`. 这个元素是一个容器，它包含了所有你想包含在HTML页面中但不想在HTML页面中显示的内容。这些内容包括你想在搜索结果中出现的关键字和页面描述，CSS样式，字符集声明等等。以后的章节能学到更多关于<head>元素的内容。

4. `<meta charset="utf-8">`: 这个元素设置文档使用utf-8字符集编码，utf-8字符集包含了人类大部分的文字。基本上他能识别你放上去的所有文本内容。毫无疑问要使用它，并且它能在以后避免很多其他问题。

5. `<title></title>`: 设置页面标题，出现在浏览器标签上，当你标记/收藏页面时它可用来描述页面。

6. `<body></body>`: `<body>`元素。 包含了你访问页面时所有显示在页面上的内容，文本，图片，音频，游戏等等。

多个空格会被视为一个空格

每个字符引用以符号&开始, 以分号(;)结束.

在下面的例子中你可以看到两个段落，它们在谈论web技术:

```html
<p>HTML 中用 <p> 来定义段落元素。</p><!--不出现 -->

<p>HTML 中用 &lt;p&gt; 来定义段落元素</p><!--出现 -->
```

### h1是干啥的？

- 只对每个页面使用一次<h1> — 这是顶级标题，所有其他标题位于层次结构中的下方。
- 确保在层次结构中以正确的顺序使用标题。不要使用<h3>来表示副标题，后面跟<h2>来表示副副标题 - 这是没有意义的，会导致奇怪的结果。
- 在可用的六个标题级别中，您应该只在每页使用不超过三个，除非您认为有必要使用更多。具有许多级别的文档（即，较深的标题层次结构）变得难以操作并且难以导航。在这种情况下，如果可能，建议将内容分散在多个页面上。

```html
<h1>Heading elements</h1>
<h2>Summary</h2>
<p>Some text here...</p>

<h2>Examples</h2>
<h3>Example 1</h3>
<p>Some text here...</p>

<h3>Example 2</h3>
<p>Some text here...</p>

<h2>See also</h2>
<p>Some text here...</p>
```

![image-20210319205635618](C:%5CUsers%5Clenovo%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210319205635618.png)

许多`<meta>` 元素包含了`name` 和 `content` 特性：

- `name` 指定了meta 元素的类型； 说明该元素包含了什么类型的信息。
- `content` 指定了实际的元数据内容。

这两个meta 元素对于定义你的页面的作者和提供页面的简要描述是很有用的 。让我们看一个例子：

```
<meta name="author" content="Chris Mills">
<meta name="description" content="The MDN Learning Area aims to provide
complete beginners to the Web with all they need to know to get
started with developing web sites and applications.">
```

指定作者在某些情况下是很有用的：如果你需要联系页面的作者，问一些关于页面内容的问题。 一些内容管理系统能够自动获取页面作者的信息，然后用于某些用途。

#### 在HTML中应用CSS和JavaScript

使用 <link>元素以及 <script> 元素引入外部css和js文件。

 <link> 元素经常位于文档的头部。这个link元素有2个属性，rel="stylesheet"表明这是文档的样式表，而 href包含了样式表文件的路径：

```
<link rel="stylesheet" href="my-css-file.css">
```

<script> 部分没必要非要放在文档头部；实际上，把它放在文档的尾部（在 </body>标签之前）是一个更好的选择，这样可以确保在加载脚本之前浏览器已经解析了HTML内容（如果脚本加载某个不存在的元素，浏览器会报错）。

<script src="my-js-file.js"></script>
注意： <script>元素看起来像一个空元素，但它并不是，因此需要一个结束标记。您还可以选择将脚本放入<script>元素中，而不是指向外部脚本文件。

#### 为文档设置主语言：

```
<html lang="zh-CN">
```

#### span元素的作用

HTML <span> 元素是短语内容的通用行内容器，并没有任何特殊语义。可以使用它来编组元素以达到某种样式意图（通过使用类或者Id属性），或者这些元素有着共同的属性，比如lang。应该在没有其他合适的语义元素时才使用它。<span> 与 <div> 元素很相似，但 <div> 是一个 块元素 而 <span> 则是 行内元素 .

#### 无序列表

```
<ul>
  <li>豆浆</li>
  <li>油条</li>
  <li>豆汁</li>
  <li>焦圈</li>
</ul>
```

![image-20210319212850145](C:%5CUsers%5Clenovo%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210319212850145.png)

#### 有序列表

![image-20210319212837957](C:%5CUsers%5Clenovo%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210319212837957.png)

```
<ol>
  <li>沿着条路走到头</li>
  <li>右转</li>
  <li>直行穿过第一个十字路口</li>
  <li>在第三个十字路口处左转</li>
  <li>继续走 300 米，学校就在你的右手边</li>
</ol>
```

#### 嵌套列表

```
<ol>
  <li>先用蛋白一个、盐半茶匙及淀粉两大匙搅拌均匀，调成“腌料”，鸡胸肉切成约一厘米见方的碎丁并用“腌料”搅拌均匀，腌渍半小时。</li>
  <li>用酱油一大匙、淀粉水一大匙、糖半茶匙、盐四分之一茶匙、白醋一茶匙、蒜末半茶匙调拌均匀，调成“综合调味料”。</li>
  <li>鸡丁腌好以后，色拉油下锅烧热，先将鸡丁倒入锅内，用大火快炸半分钟，炸到变色之后，捞出来沥干油汁备用。</li>
  <li>在锅里留下约两大匙油，烧热后将切好的干辣椒下锅，用小火炒香后，再放入花椒粒和葱段一起爆香。随后鸡丁重新下锅，用大火快炒片刻后，再倒入“综合调味料”继续快炒。
    <ul>
      <li>如果你采用正宗川菜做法，最后只需加入花生米，炒拌几下就可以起锅了。</li>
      <li>如果你在北方，可加入黄瓜丁、胡萝卜丁和花生米，翻炒后起锅。</li>
    </ul>
  </li>
</ol>
```

#### 重点突出

```
<p>I am <em>glad</em> you weren't <em>late</em>.</p>
```

```
<p>This liquid is <strong>highly toxic</strong>.</p>

<p>I am counting on you. <strong>Do not</strong> be late!</p>
```

#### 斜体字、粗体字、下划线：

- i被用来传达传统上用斜体表达的意义：外国文字，分类名称，技术术语，一种思想……
- b 被用来传达传统上用粗体表达的意义：关键字，产品名称，引导句……
- u 被用来传达传统上用下划线表达的意义：专有名词，拼写错误……



```
<!-- 学名 -->
<p>
  红喉北蜂鸟（学名：<i>Archilocus colubris</i>）
  是北美东部最常见的蜂鸟品种。
</p>

<!-- 舶来词 -->
<p>
  菜单上有好多舶来词汇，比如 <i lang="uk-latn">vatrushka</i>（东欧乳酪面包）,
  <i lang="id">nasi goreng</i>（印尼炒饭）以及<i lang="fr">soupe à l'oignon</i>（法式洋葱汤）。
</p>

<!-- 已知的错误书写 -->
<p>
  总有一天我会改掉写<u style="text-decoration-line: underline; text-decoration-style: wavy;">措字</u>的毛病。
</p>

<!-- 在一组指令中突出显示关键字 -->
<ol>
  <li>
    <b>切</b>下两片面包，
  </li>
  <li>
    在两片面包中间<b>夹入</b>一片西红柿和一片生菜叶。
  </li>
</ol>
```

### 创建超链接

herf title

```
<p>我创建了一个指向
<a href="https://www.mozilla.org/zh-CN/" title="了解 Mozilla 使命以及如何参与贡献的最佳站点。">Mozilla 主页</a>
的超链接。
</p>
```

图像的超链接：

```
<a href="https://www.mozilla.org/zh-CN/">
  <img src="mozilla-image.png" alt="链接至 Mozilla 主页的 Mozilla 标志">
</a>
```

#### 文档片段：

超链接除了可以链接到文档外，也可以链接到HTML文档的特定部分（被称为**文档片段**）。要做到这一点，你必须首先给要链接到的元素分配一个[`id`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes#attr-id)属性。例如，如果你想链接到一个特定的标题，可以这样做：

```
<h2 id="Mailing_address">邮寄地址</h2>
```

然后链接到那个特定的`id`，您可以在URL的结尾使用一个井号指向它，例如：

```
<p>要提供意见和建议，请将信件邮寄至 <a href="contacts.html#Mailing_address">我们的地址</a>。</p>
```

你甚至可以在同一份文档下，通过链接文档片段，来链接到同一份文档的另一部分：

```
<p>本页面底部可以找到 <a href="#Mailing_address">公司邮寄地址</a>。</p>
```

**绝对URL**：http://www.example.com/projects/index.html

**相对URL**：

如果我们想从示例文件链接`http://www.example.com/projects/index.html`转到相同目录下的一个PDF文件，URL就是文件名URL——例如`project-brief.pdf`——没有其他的信息要求。如果PDF文件能够在`projects`的子目录`pdfs`中访问到，相对路径就是`pdfs/project-brief.pdf`（对应的绝对URL是`http://www.example.com/projects/pdfs/project-brief.pdf`）

#### 下载链接使用download属性

其最基本和最常用的使用形式为一个`mailto`:link （链接），链接简单说明收件人的电子邮件地址。

```
<a href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=zh-CN"
   download="firefox-latest-64bit-installer.exe">
  下载最新的 Firefox 中文版 - Windows（64位）
</a>
```

除了电子邮件地址，还可以提供其他信息。任何标准的邮件头字段可以被添加到你提供的邮件URL。 其中最常用的是主题(subject)、抄送(cc)和主体(body) (这不是一个真正的头字段，但允许您为新邮件指定一个短内容消息)。 每个字段及其值被指定为查询项。

下面是一个包含cc、bcc、主题和主体的示例：

```
<a href="mailto:nowhere@mozilla.org?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&subject=The%20subject%20of%20the%20email&body=The%20body%20of%20the%20email">
  Send mail with cc, bcc, subject and body
</a>
```

# 发送表单数据

### 在客户端:定义如何发送数据

####  action 属性

这个属性定义了发送数据要去的位置。它的值必须是一个有效的URL。如果没有提供此属性，则数据将被发送到包含这个表单的页面的URL

```
<form action="http://foo.com">
<form action="/somewhere_else">
```

####  [`method`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form#attr-method)属性

##### GET 方法

```
<form action="http://foo.com" method="get">
  <div>
    <label for="say">What greeting do you want to say?</label>
    <input name="say" id="say" value="Hi">
  </div>
  <div>
    <label for="to">Who do you want to say it to?</label>
    <input name="to" id="to" value="Mom">
  </div>
  <div>
    <button>Send my greetings</button>
  </div>
</form>
```

数据作为一系列的名称/值对被附加到URL。在URL web地址结束之后，我们得到一个问号(`?`)，后面跟着由一个与符号(`&`)互相分隔开的名称/值对。在本例中，我们将两个数据传递给服务器。

- `say`, 它有一个 `Hi`的值。
- `to`, 它有一个 `Mom`的值。

HTTP请求如下：

```
GET /?say=Hi&to=Mom HTTP/2.0
Host: foo.com
```

##### POST 方法

使用[`method`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form#attr-method)属性设置为`post`。

```
<form action="http://foo.com" method="post">
  <div>
    <label for="say">What greeting do you want to say?</label>
    <input name="say" id="say" value="Hi">
  </div>
  <div>
    <label for="to">Who do you want to say it to?</label>
    <input name="to" id="to" value="Mom">
  </div>
  <div>
    <button>Send my greetings</button>
  </div>
</form>
```

