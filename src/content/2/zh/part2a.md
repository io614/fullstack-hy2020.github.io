---
mainImage: ../../../images/part-2.svg
part: 2
letter: a
lang: zh
---

<div class="content">
<!-- Before starting a new part, let's recap some of the topics that proved difficult last year.-->
 在开始新的部分之前，让我们回顾一下去年被证明是较难的一些主题。

### console.log

<!-- ***What's the difference between an experienced JavaScript programmer and a rookie? The experienced one uses console.log 10-100 times more.***-->
 ***一个有经验的JavaScript程序员和一个菜鸟之间有什么区别？有经验的老鸟使用console.log的次数要多10-100倍***。

<!-- Paradoxically, this seems to be true even though a rookie programmer would need <i>console.log</i> (or any debugging method) more than an experienced one.-->
 矛盾的是，一个菜鸟程序员应该比一个有经验的程序员更需要<i>console.log</i>（或任何调试方法），这也是事实。

<!-- When something does not work, don't just guess what's wrong. Instead, log or use some other way of debugging.-->
 当某些东西不工作时，不要只是猜测什么是错的。相反，要记录或使用一些其他的调试方法。

<!-- **NB** As explained in part 1, when you use the command _console.log_ for debugging, don't concatenate things 'the Java way' with a plus. Instead of writing:-->
 **NB** 正如第一章节所说的，当你使用_console.log_命令进行调试时，不要用 "Java式 "的加号来连接。不要写：

```js
console.log('props value is' + props)
```

<!-- separate the things to be printed with a comma:-->
而要用逗号分开要打印的东西：

```js
console.log('props value is', props)
```

<!-- If you concatenate an object with a string and log it to the console (like in our first example), the result will be pretty useless:-->
 如果你把一个对象和一个字符串连接起来并记录到控制台(就像我们的第一个例子)，其结果将无法使用：

```js
props value is [Object object]
```

<!-- On the contrary, when you pass objects as distinct arguments separated by commas to _console.log_, like in our second example above, the content of the object is printed to the developer console as strings that are insightful.-->
 相反，当你把对象作为不同的参数用逗号隔开传递给_console.log_，就像我们上面的第二个例子，对象的内容被打印到开发者控制台，成为可检查的字符串。
<!-- If necessary, read more about [debugging React-applications](/en/part1/a_more_complex_state_debugging_react_apps#debugging-react-applications).-->
 如果有必要，请阅读更多关于[调试React-应用](/en/part1/a_more_complex_state_debugging_react_apps#debugging-react-applications)的内容。

### Protip: Visual Studio Code snippets

<!-- With Visual Studio Code it's easy to create 'snippets', i.e., shortcuts for quickly generating commonly re-used portions of code, much like how 'sout' works in Netbeans.-->
 通过Visual Studio Code，可以很容易地创建"'片段'，即快速生成常用的重复使用的代码部分，很像Netbeans中的 "sout "工作方式。

<!-- Instructions for creating snippets can be found [here](https://code.visualstudio.com/docs/editor/userdefinedsnippets#_creating-your-own-snippets).-->
 创建片段的说明可以查看[这里](https://code.visualstudio.com/docs/editor/userdefinedsnippets#_creating-your-own-snippets)。

<!-- Useful, ready-made snippets can also be found as VS Code plugins, in the [marketplace](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets).-->
有用的、现成的片段也可以在[市场](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)中作为VS Code插件找到。

<!-- The most important snippet is the one for the <em>console.log()</em> command, for example, <em>clog</em>. This can be created like so:-->
 最重要的片段是用于<em>console.log()</em>命令的片段，例如，<em>clog</em>。这可以这样创建。

```js
{
  "console.log": {
    "prefix": "clog",
    "body": [
      "console.log('$1')",
    ],
    "description": "Log output to console"
  }
}
```

<!-- Debugging your code using _console.log()_ is so common that Visual Studio Code has that snippet built in. To use it, type _log_ and hit tab to autocomplete. More fully featured _console.log()_ snippet extensions can be found in the [marketplace](https://marketplace.visualstudio.com/search?term=console.log&target=VSCode&category=All%20categories&sortBy=Relevance).-->
 使用_console.log()_来调试你的代码非常普遍，因此Visual Studio Code内置了这个片段。要使用它，请输入_log_并点击tab来自动完成。更多功能的_console.log()_片段扩展可以在[市场](https://marketplace.visualstudio.com/search?term=console.log&target=VSCode&category=All%20categories&sortBy=Relevance)中找到。

### JavaScript Arrays

<!-- From here on out, we will be using the functional programming methods of the JavaScript [array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array), such as  _find_, _filter_, and _map_ - all of the time. They operate on the same general principles as streams do in Java 8, which have been used during the last few years in both the 'Ohjelmoinnin perusteet' and 'Ohjelmoinnin jatkokurssi' courses at the university's department of Computer Science, and also in the programming MOOC.-->
 从这里开始，我们将使用JavaScript[数组](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)的函数式编程方法，例如_find_、_filter_和_map_--我们将一直这么使用。它们的操作原理与Java 8中的流相同，在过去几年中，在大学计算机系的"Ohjelmoinnin perusteet"和"Ohjelmoinnin jatkokurssi" 课程以及编程MOOC中都有使用。

<!-- If functional programming with arrays feels foreign to you, it is worth watching at least the first three parts of the YouTube video series [Functional Programming in JavaScript](https://www.youtube.com/playlist?list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84):-->
 如果你对用数组进行函数式编程感到陌生，那么至少可以看看YouTube视频系列[JavaScript中的函数式编程](https://www.youtube.com/playlist?list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84)的前三部分。

<!-- - [Higher-order functions](https://www.youtube.com/watch?v=BMUiFMZr7vk&list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84)-->

 - [高阶函数](https://www.youtube.com/watch?v=BMUiFMZr7vk&list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84)
<!-- - [Map](https://www.youtube.com/watch?v=bCqtb-Z5YGQ&list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84&index=2)-->
 - [map](https://www.youtube.com/watch?v=bCqtb-Z5YGQ&list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84&index=2)
<!-- - [Reduce basics](https://www.youtube.com/watch?v=Wl98eZpkp-c&t=31s)-->
 - [Reduce基础知识](https://www.youtube.com/watch?v=Wl98eZpkp-c&t=31s)

### Event Handlers Revisited

<!-- Based on last year's course, event handling has proved to be difficult.-->
 基于去年的课程，事件处理有些难度。

<!-- It's worth reading the revision chapter at the end of the previous part [event handlers revisited](/en/part1/a_more_complex_state_debugging_react_apps#event-handling-revisited), if it feels like your own knowledge on the topic needs some brushing up.-->
 如果你觉得自己在这个主题上的知识需要精进一下的话，那么值得读一读上一章节[复习事件处理程序](/en/part1/a_more_complex_state_debugging_react_apps#event-handling-revisited)最后的修订章节。

<!-- Passing event handlers to the child components of the <i>App</i> component has raised some questions. A small revision on the topic can be found [here](/en/part1/a_more_complex_state_debugging_react_apps#passing-event-handlers-to-child-components).-->
 将事件处理程序传递给<i>App</i>组件的子组件，引起了一些问题。关于这个话题的小复习可以在[这里](/en/part1/a_more_complex_state_debugging_react_apps#passing-event-handlers-to-child-components)找到。

### Rendering Collections

<!-- We will now do the 'frontend', or the browser-side application logic, in React for an application that's similar to the example application from [part 0](/en/part0)-->
 我们现在将在React中为一个类似于[第0章节](/en/part0)中的示例程序做'前端'，或浏览器端应用逻辑。

<!-- Let's start with the following (the file <i>App.js</i>):-->
 让我们从下面开始（文件<i>App.js</i>）。

```js
const App = (props) => {
  const { notes } = props

  return (
    <div>
      <h1>Notes</h1>
      <ul>
        <li>{notes[0].content}</li>
        <li>{notes[1].content}</li>
        <li>{notes[2].content}</li>
      </ul>
    </div>
  )
}

export default App
```

<!-- The file <i>index.js</i> looks like:-->
 文件<i>index.js</i>如下所示：

```js
import React from 'react'
import ReactDOM from 'react-dom/client'

import App from './App'

const notes = [
  {
    id: 1,
    content: 'HTML is easy',
    date: '2019-05-30T17:30:31.098Z',
    important: true
  },
  {
    id: 2,
    content: 'Browser can execute only JavaScript',
    date: '2019-05-30T18:39:34.091Z',
    important: false
  },
  {
    id: 3,
    content: 'GET and POST are the most important methods of HTTP protocol',
    date: '2019-05-30T19:20:14.298Z',
    important: true
  }
]

ReactDOM.createRoot(document.getElementById('root')).render(
  <App notes={notes} />
)
```

<!-- Every note contains its textual content and a timestamp, as well as a _boolean_ value for marking whether the note has been categorized as important or not, and also a unique <i>id</i>.-->
 每个笔记都包含它的文本内容和一个时间戳，以及一个用于标记该笔记是否被归类为重要的 _布尔值_，还有一个唯一的<i>id</i>。

<!-- The example above works due to the fact that there are exactly three notes in the array.-->
 上面的例子之所以有效，是因为数组中正好有三个笔记。

<!-- A single note is rendered by accessing the objects in the array by referring to a hard-coded index number:-->
 通过引用一个硬编码的索引号来访问数组中的对象，从而渲染一个单一的笔记。

```js
<li>{notes[1].content}</li>
```

<!-- This is, of course, not practical. We can improve on this by generating React elements from the array objects using the [map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) function.-->
 这当然不实用。我们可以通过使用[map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)函数从数组对象中生成React元素来改进这一点。

```js
notes.map(note => <li>{note.content}</li>)
```

<!-- The result is an array of <i>li</i> elements.-->
 其结果是一个<i>li</i>元素的数组。

```js
[
  <li>HTML is easy</li>,
  <li>Browser can execute only JavaScript</li>,
  <li>GET and POST are the most important methods of HTTP protocol</li>,
]
```


<!-- Which can then be placed inside <i>ul</i> tags:-->
 然后可以放在<i>ul</i>标签内。

```js
const App = (props) => {
  const { notes } = props

  return (
    <div>
      <h1>Notes</h1>
// highlight-start
      <ul>
        {notes.map(note => <li>{note.content}</li>)}
      </ul>
// highlight-end
    </div>
  )
}
```

<!-- Because the code generating the <i>li</i> tags is JavaScript, it must be wrapped in curly braces in a JSX template just like all other JavaScript code.-->
 因为生成<i>li</i>标签的代码是JavaScript，它必须像其他JavaScript代码一样被包裹在JSX模板的大括号内。

<!-- Parannetaan koodin luetteloa vielä jakamalla nuolifunktion määrittely useammalle riville: -->
<!-- We will also make the code more readable by separating the arrow function's declaration across multiple lines:-->
我们还通过把箭头函数的声明分成多行来使代码更容易阅读。

```js
const App = (props) => {
  const { notes } = props

  return (
    <div>
      <h1>Notes</h1>
      <ul>
        {notes.map(note =>
        // highlight-start
          <li>
            {note.content}
          </li>
        // highlight-end
        )}
      </ul>
    </div>
  )
}
```

### Key-attribute

<!-- Even though the application seems to be working, there is a nasty warning in the console:-->
 尽管应用似乎在工作，但控制台有一个讨厌的警告。

![](../../images/2/1a.png)

<!-- As the linked [React page](https://reactjs.org/docs/lists-and-keys.html#keys) in the error message suggests; the list items, i.e. the elements generated by the _map_ method, must each have a unique key value:  an attribute called <i>key</i>.-->
 正如错误信息中链接的[React页面](https://reactjs.org/docs/lists-and-keys.html#keys)所提示的；列表项，即由_map_方法生成的元素，必须有一个唯一的键值：一个叫做<i>key</i>的属性。

<!-- Let's add the keys:-->
 我们来添加键值。

```js
const App = (props) => {
  const { notes } = props

  return (
    <div>
      <h1>Notes</h1>
      <ul>
        {notes.map(note =>
          <li key={note.id}> // highlight-line
            {note.content}
          </li>
        )}
      </ul>
    </div>
  )
}
```

<!-- And the error message disappears.-->
 错误信息就消失了。

<!-- React uses the key attributes of objects in an array to determine how to update the view generated by a component when the component is re-rendered. More about this in the [React documentation](https://reactjs.org/docs/reconciliation.html#recursing-on-children).-->
 React使用数组中对象的键属性来决定如何在组件重新渲染时更新该组件生成的视图。关于这一点，更多的可以查看[React文档](https://reactjs.org/docs/reconciliation.html#recursing-on-children)。

### Map

<!-- Understanding how the array method, [map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) works is crucial for the rest of the course.-->
 了解数组方法，[map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)是如何工作的，对课程剩下的章节至关重要。

<!-- The application contains an array called _notes_:-->
 应用包含一个名为_notes_的数组。

```js
const notes = [
  {
    id: 1,
    content: 'HTML is easy',
    date: '2019-05-30T17:30:31.098Z',
    important: true
  },
  {
    id: 2,
    content: 'Browser can execute only JavaScript',
    date: '2019-05-30T18:39:34.091Z',
    important: false
  },
  {
    id: 3,
    content: 'GET and POST are the most important methods of HTTP protocol',
    date: '2019-05-30T19:20:14.298Z',
    important: true
  }
]
```

<!-- Let's pause for a moment and examine how _map_ works.-->
 让我们停顿一下，研究一下_map_是如何工作的。


<!-- If the following code is added to, let's say, the end of the file:-->
 如果下面的代码被添加到，比方说，文件的末端。

```js
const result = notes.map(note => note.id)
console.log(result)
```

<i>[1, 2, 3]</i>  will be printed to the console.

<i>[1, 2, 3]</i> 会打印出来

<!--  _map_ always creates a new array, the elements of which have been created from the elements of the original array by <i>mapping</i>: using the function given as a parameter to the _map_ method.-->
 _map_总是创建一个新的数组，其中的元素是通过<i>mapping</i>从原始数组的元素中创建的：原始值作为_map_方法函数的参数。

<!-- The function is-->
而这个函数就是

```js
note => note.id
```

<!-- Which is an arrow function written in compact form. The full form would be:-->
 这是一个简洁形式写的箭头函数。完整的形式应该是：

```js
(note) => {
  return note.id
}
```

<!-- The function gets a note object as a parameter, and <i>returns</i> the value of its <i>id</i> field.-->
 该函数得到一个笔记对象作为参数，并<i>返回</i>其<i>id</i>字段的值。

<!-- Changing the command to:-->
 把命令改成:

```js
const result = notes.map(note => note.content)
```

<!-- results in an array containing the contents of the notes.-->
结果是一个包含笔记内容的数组。

<!-- This is already pretty close to the React code we used:-->
 这已经非常接近我们使用的React代码了。

```js
notes.map(note =>
  <li key={note.id}>{note.content}</li>
)
```

<!-- which generates an <i>li</i> tag containing the contents of the note from each note object.-->
它生成一个<i>li</i>标签，包含每个笔记对象的笔记内容。

<!-- Because the function parameter passed to the _map_ method --->
 Because the function parameter passed to the _map_ method -

因为函数参数是传递给 _map_ 方法：

```js
note => <li key={note.id}>{note.content}</li>
```

<!-- &nbsp;- is used to create view elements, the value of the variable must be rendered inside curly braces. Try to see what happens if the braces are removed.-->
 &nbsp;- 是用来创建视图元素的，变量的值必须被渲染在大括号内。试着看看如果去掉大括号会发生什么。

<!-- The use of curly braces will cause some pain in the beginning, but you will get used to them soon enough. The visual feedback from React is immediate.-->
 大括号的使用在一开始会造成一些痛苦，但你很快就会习惯。React的视觉反馈是即时的。

### Anti-pattern: Array Indexes as Keys

<!-- We could have made the error message on our console disappear by using the array indexes as keys. The indexes can be retrieved by passing a second parameter to the callback function of the _map_ method:-->
 我们可以通过使用数组索引作为键来使控制台中的错误信息消失。通过向_map_方法的回调函数传递第二个参数，可以拿到索引。

```js
notes.map((note, i) => ...)
```

<!-- When called like this, _i_ is assigned the value of the index of the position in the array where the note resides.-->
 当这样调用时，_i_被分配为笔记所在的数组中的索引值。

<!-- As such, one way to define the row generation without getting errors is:-->
因此，定义行的生成也是不出错的一种方法：

```js
<ul>
  {notes.map((note, i) =>
    <li key={i}>
      {note.content}
    </li>
  )}
</ul>
```

<!-- This is; however, **not recommended** and can create undesired problems even if it seems to be working just fine.-->
 然而，这是不推荐的，即使它看起来工作得很好，也会产生想不到的问题。

<!-- Read more about this in [this article](https://robinpokorny.medium.com/index-as-a-key-is-an-anti-pattern-e0349aece318).-->
 在[这篇文章](https://robinpokorny.medium.com/index-as-a-key-is-an-anti-pattern-e0349aece318)中可以阅读更多关于这个问题的内容。

### Refactoring Modules

<!-- Let's tidy the code up a bit. We are only interested in the field _notes_ of the props, so let's retrieve that directly using [destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment):-->
 让我们把代码整理一下。我们只对prop的字段_notes_感兴趣，所以让我们直接使用[解构](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)来检索它。

```js
const App = ({ notes }) => { //highlight-line
  return (
    <div>
      <h1>Notes</h1>
      <ul>
        {notes.map(note =>
          <li key={note.id}>
            {note.content}
          </li>
        )}
      </ul>
    </div>
  )
}
```

<!-- If you have forgotten what destructuring means and how it works, please review the [section on destructuring](/en/part1/component_state_event_handlers#destructuring).-->
 如果你忘记了解构是什么意思以及它是如何工作的，请复习一下一下[解构部分](/en/part1/component_state_event_handlers#destructuring) 。

<!-- We'll separate displaying a single note into its own component <i>Note</i>:-->
 我们将把显示一个笔记分离成独立的组件<i>Note</i>。

```js
// highlight-start
const Note = ({ note }) => {
  return (
    <li>{note.content}</li>
  )
}
// highlight-end

const App = ({ notes }) => {
  return (
    <div>
      <h1>Notes</h1>
      <ul>
        // highlight-start
        {notes.map(note =>
          <Note key={note.id} note={note} />
        )}
         // highlight-end
      </ul>
    </div>
  )
}
```

<!-- Note that the <i>key</i> attribute must now be defined for the <i>Note</i> components, and not for the <i>li</i> tags like before.-->
 注意，现在必须为<i>Note</i>组件定义<i>key</i>属性，而不是像以前那样为<i>li</i>标签定义。

<!-- A whole React application can be written in a single file. Although that is, of course, not very practical. Common practice is to declare each component in their own file as an <i>ES6-module</i>.-->
 整个React应用可以写在一个文件中。虽然这当然不是很实用。通常的做法是将每个组件作为<i>ES6-module</i>在自己的文件中声明。

<!-- We have been using modules the whole time. The first few lines of the file <i>index.js</i>:-->
 我们一直都在使用模块。文件<i>index.js</i>的前几行。

```js
import React from 'react'
import ReactDOM from 'react-dom/client'

import App from './App'
```

<!-- [import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import) three modules, enabling them to be used in that file. The  module <i>React</i>  is placed into the variable _React_, the module <i>react-dom</i> into the variable _ReactDOM_, and the module that defines the main component of the app is placed into the variable _App_-->
 [import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)了三个模块，使它们可以在该文件中使用。模块<i>React</i>被放入变量_React_，模块<i>react-dom</i>被放入变量_ReactDOM_，而定义应用主要组件的模块被放入变量_App_。

<!-- Let's move our <i>Note</i> component into its own module.-->
 让我们把我们的<i>Note</i>组件移到自己的模块中。

<!-- In smaller applications, components are usually placed in a directory called <i>components</i>, which is in turn placed within the <i>src</i> directory. The convention is to name the file after the component.-->
 在较小的应用中，组件通常被放在一个叫做<i>components</i>的目录中，而这个目录又被放在<i>src</i>目录中。惯例是用组件的名字来命名文件。

<!-- Now, we'll create a directory called <i>components</i> for our application and place a file named <i>Note.js</i> inside.-->
 现在，我们将为我们的应用创建一个名为<i>components</i>的目录，并在其中放置一个名为<i>Note.js</i>的文件。
<!-- The contents of the Note.js file are as follows:-->
 Note.js文件的内容如下。

```js
import React from 'react'

const Note = ({ note }) => {
  return (
    <li>{note.content}</li>
  )
}

export default Note
```

<!-- The last line of the module [exports](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export) the declared module, the variable <i>Note</i>.-->
 模块的最后一行 [exports](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export) 声明的模块，即变量<i>Note</i>。

<!-- Now the file that is using the component - <i>App.js</i> - can [import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import) the module:-->
 现在使用该组件的文件--<i>App.js</i>--可以[导入](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import) 该模块。

```js
import Note from './components/Note' // highlight-line

const App = ({ notes }) => {
  // ...
}
```

<!-- The component exported by the module is now available for use in the variable <i>Note</i>, just as it was earlier.-->
 模块导出的组件现在可以在变量<i>Note</i>中使用，就像之前那样。

<!-- Note that when importing our own components, their location must be given <i>in relation to the importing file</i>:-->
注意，当导入我们自己的组件时，必须给出它们的位置，<i>与导入的文件位置有关</i>。

```js
'./components/Note'
```

<!-- The period - <i>.</i> - in the beginning refers to the current directory, so the module's location is a file called <i>Note.js</i> in the <i>components</i> sub-directory of the current directory. The filename extension _.js_ can be omitted.-->
 开头的句号--<i>.</i>--指的是当前目录，所以模块的位置是当前目录下<i>components</i>子目录中一个叫<i>Note.js</i>的文件。文件名的扩展名_.js_可以省略。

<!-- Modules have plenty of other uses other than enabling component declarations to be separated into their own files. We will get back to them later in this course.-->
 除了使组件声明分离到自己的文件中，模块还有很多其他的用途。我们将在本课程的后面再学习它们。

<!-- The current code of the application can be found on [GitHub](https://github.com/fullstack-hy2020/part2-notes/tree/part2-1).-->
 该应用的当前代码可以在[GitHub](https://github.com/fullstack-hy2020/part2-notes/tree/part2-1)上找到。

<!-- Note that the <i>main</i> branch of the repository contains the code for a later version of the application. The current code is in the branch [part2-1](https://github.com/fullstack-hy2020/part2-notes/tree/part2-1):-->
 请注意，仓库的<i>main</i>分支包含了该应用的后期版本的代码。目前的代码在分支[part2-1](https://github.com/fullstack-hy2020/part2-notes/tree/part2-1)中。

![](../../images/2/2e.png)

<!-- If you clone the project, run the command _npm install_ before starting the application with _npm start_.-->
 如果你克隆了这个项目，在用_npm start_启动应用之前，运行_npm install_命令。

### When the Application Breaks

<!-- Early in your programming career (and even after 30 years of coding like yours truly), what often happens is that the application just completely breaks down. This is even more the case with dynamically typed languages, such as JavaScript, where the compiler does not check the data type. For instance, function variables or return values.-->
 在你的编程生涯的早期（甚至编码30年后），经常发生的情况是，应用就是完全崩溃了。对于动态类型的语言，如JavaScript，这种情况就更多了，因为编译器不会检查数据类型。例如，函数变量或返回值。

<!-- A "React explosion" can, for example, look like this:-->
 例如，一个 "React崩了 "可能是这样的。

![](../../images/2/3b.png)

<!-- In these situations your best way out is the <em>console.log</em> method.-->
 在这些情况下，你最好的办法是使用<em>console.log</em>方法。

<!-- The piece of code causing the explosion is this:-->
 引起崩溃的那段代码是这样的。

```js
const Course = ({ course }) => (
  <div>
    <Header course={course} />
  </div>
)

const App = () => {
  const course = {
    // ...
  }

  return (
    <div>
      <Course course={course} />
    </div>
  )
}
```

<!-- We'll hone in on the reason for the breakdown by adding <em>console.log</em> commands to the code. Because the first thing to be rendered is the <i>App</i> component, it's worth putting the first <em>console.log</em> there:-->
 我们将通过在代码中加入<em>console.log</em>命令来探寻故障的原因。因为首先要渲染的是<i>App</i>组件，所以应当把第一个<em>console.log</em>放在那里。

```js
const App = () => {
  const course = {
    // ...
  }

  console.log('App works...') // highlight-line

  return (
    // ..
  )
}
```

<!-- To see the printing in the console, we must scroll up over the long red wall of errors.-->
 要看到控制台中的打印内容，我们必须在长长的红色错误墙上滚动鼠标。

![](../../images/2/4b.png)

<!-- When one thing is found to be working, it's time to log deeper. If the component has been declared as a single statement, or a function without a return, it makes printing to the console harder.-->
 当发现日志是有效的，就该深入打日志了。如果组件被声明为一个单一的语句，或一个没有返回的函数，就会使打印到控制台的难度增加。

```js
const Course = ({ course }) => (
  <div>
    <Header course={course} />
  </div>
)
```

<!-- The component should be changed to its longer form in order for us to add the printing:-->
 该组件可以改为较长的形式，以便我们增加打印功能。

```js
const Course = ({ course }) => {
  console.log(course) // highlight-line
  return (
    <div>
      <Header course={course} />
    </div>
  )
}
```

<!-- Quite often the root of the problem is that the props are expected to be of a different type, or called with a different name than they actually are, and destructuring fails as a result. The problem often begins to solve itself when destructuring is removed and we see what the <em>props</em> actually contains.-->
 问题的根源往往是prop被期望为不同的类型，或者用不同的名字调用，其结果就是解构失败。当去掉重构，我们看到<em>props</em>实际包含的内容时，问题往往会开始自行解决。

```js
const Course = (props) => { // highlight-line
  console.log(props)  // highlight-line
  const { course } = props
  return (
    <div>
      <Header course={course} />
    </div>
  )
}
```

<!-- If the problem has still not been resolved, there really isn't much to do apart from continuing to bug-hunt by sprinkling more _console.log_ statements around your code.-->
 如果问题仍然没有得到解决，除了继续通过在你的代码周围撒上更多的_console.log_语句来寻找错误之外，真的没有什么可做的。

<!-- I added this chapter to the material after the model answer for the next question exploded completely (due to props being of the wrong type), and I had to debug it using <em>console.log</em>.-->
 在下一个问题的模型答案完全崩掉之前（由于prop的类型不对），我不得不用<em>console.log</em>来调试它之后，我把这一章加入了教材。

</div>

<div class="tasks">

<h3>Exercises 2.1.-2.5.</h3>

<!-- The exercises are submitted via GitHub, and by marking the exercises as done in the [submission system](https://studies.cs.helsinki.fi/stats/courses/fullstackopen).-->
 练习通过GitHub提交，并在[提交系统](https://studies.cs.helsinki.fi/stats/courses/fullstackopen)中标记练习已完成。

<!-- You can submit all of the exercises into the same repository, or use multiple different repositories. If you submit exercises from different parts into the same repository, name your directories well.-->
 你可以将所有的练习提交到同一个仓库，或者使用多个不同的仓库。如果你将不同部分的练习提交到同一个仓库中，请将你的目录命名好。

<!-- The exercises are submitted **One part at a time**. When you have submitted the exercises for a part, you can no longer submit any missed exercises for that part.-->
 练习是一次提交一个章节的。当你提交了一个章节的练习，你就不能再提交该章节的任何遗漏的练习。

<!-- Note that this part has more exercises than the ones before, so <i>do not submit</i> before you have done all exercises from this part you want to submit.-->
 注意，这章节的练习比之前的要多，所以在你做完这章节的所有练习之前，<i>不要提交</i>你想提交的练习。

<!-- **WARNING** create-react-app makes the project automatically into a git-repository, if the project is not created inside of an already existing repository. You probably **do not** want the project to become a repository, so run the command  _rm -rf .git_ from its root.-->
 **警告** create-react-app会使项目自动变成一个git-repository，如果项目不是在一个已经存在的repository中创建的。你可能不希望该项目成为一个仓库，所以从它的根部运行_rm -rf .git_命令。

<h4>2.1: Course information step6</h4>

<!-- Let's finish the code for rendering course contents from exercises 1.1 - 1.5. You can start with the code from the model answers. The model answers for part 1 can be found by going to the [submission system](https://studies.cs.helsinki.fi/stats/courses/fullstackopen), click on <i>my submissions</i> at the top, and in the row corresponding to part 1 under the <i>solutions</i> column click on <i>show</i>. To see the solution to the <i>course info</i> exercise, click on _index.js_ under <i>kurssitiedot</i> ("kurssitiedot" means "course info").-->
 让我们完成练习1.1-1.5中渲染课程内容的代码。你可以从模型答案的代码开始。第1章节的模型答案可以在[提交系统](https://studies.cs.helsinki.fi/stats/courses/fullstackopen)中找到，点击顶部的<i>我的提交</i>，在<i>解决方案</i>栏下对应第1章节的行中点击<i>显示</i>。要看<i>课程信息</i>练习的解决方案，请点击<i>kurssitiedot</i>下的_index.js_（"kurssitiedot "意为 "课程信息"）。


<!-- **Note that if you copy a project from one place to another, you might have to delete the <i>node\_modules</i> directory and install the dependencies again with the command _npm install_ before you can start the application.**-->
 注意，如果你把一个项目从一个地方复制到另一个地方，你可能要删除<i>node\_modules</i>目录，并在启动应用之前用_npm install_命令重新安装依赖项。
<!-- Generally, it's not recommended that you copy a project's whole contents and/or add the <i>node\_modules</i> directory to the version control system.-->
 一般来说，不建议你复制一个项目的全部内容 和/或 将<i>node\_modules</i>目录添加到版本控制系统中。

<!-- Let's change the <i>App</i> component like so:-->
 让我们像这样改变<i>App</i>组件。

```js
const App = () => {
  const course = {
    id: 1,
    name: 'Half Stack application development',
    parts: [
      {
        name: 'Fundamentals of React',
        exercises: 10,
        id: 1
      },
      {
        name: 'Using props to pass data',
        exercises: 7,
        id: 2
      },
      {
        name: 'State of a component',
        exercises: 14,
        id: 3
      }
    ]
  }

  return <Course course={course} />
}
```

<!-- Define a component responsible for formatting a single course called <i>Course</i>.-->
 定义一个负责格式化单一课程的组件，称为<i>Course</i>。

<!-- The component structure of the application can be, for example, the following:-->
例如，应用的组件结构可以是这样的。

<pre>
App
  Course
    Header
    Content
      Part
      Part
      ...
</pre>

<!-- Hence, the <i>Course</i> component contains the components defined in the previous part, which are responsible for rendering the course name and its parts.-->
 因此，<i>Course</i>组件包含前一部分定义的组件，负责渲染课程名称及其部分。

<!-- The rendered page can, for example, look as follows:-->
 例如，渲染的页面可以如下。

![](../../images/teht/8e.png)

<!-- You don't need the sum of the exercises yet.-->
 你还不需要练习的总和。

<!-- The application must work <i>regardless of the number of parts a course has</i>, so make sure the application works if you add or remove parts of a course.-->
<i> 无论课程有多少部分，应用都必须工作<i>，所以要确保在你增加或删除课程的部分时，应用能够工作。

<!-- Ensure that the console shows no errors!-->
确保控制台没有显示错误!

<h4>2.2: Course information step7</h4>

<!-- Show also the sum of the exercises of the course.-->
同时显示课程练习的总和。

![](../../images/teht/9e.png)

<h4>2.3*: Course information step8</h4>

<!-- If you haven't done so already, calculate the sum of exercises with the array method [reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce).-->
 如果你还没有这样做，用数组方法[reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)来计算练习的总和。

<!-- **Pro tip:** when your code looks as follows:-->
 **专业提示：**当你的代码看起来如下。

```js
const total =
  parts.reduce((s, p) => someMagicHere)
```

<!-- and does not work, it's worth to use <i>console.log</i>, which requires the arrow function to be written in its longer form:-->
 不工作时，值得使用<i>console.log</i>，它要求箭头函数以较长的形式写出来。

```js
const total = parts.reduce((s, p) => {
  console.log('what is happening', s, p)
  return someMagicHere
})
```

<!-- **Pro tip 2:** There is a [plugin for VS Code](https://marketplace.visualstudio.com/items?itemName=cmstead.jsrefactor) that automatically changes short form arrow functions into their longer form, and vice versa.-->
 **专业提示2：**有一个[VS Code的插件](https://marketplace.visualstudio.com/items?itemName=cmstead.jsrefactor)可以自动将短形式的箭头函数改为长形式，反之亦然。

![](../../images/2/5b.png)

<h4>2.4: Course information step9</h4>


<!-- Let's extend our application to allow for an <i>arbitrary number</i> of courses:-->
 让我们扩展我们的应用以允许一个<i>任意数量的</i>课程。

```js
const App = () => {
  const courses = [
    {
      name: 'Half Stack application development',
      id: 1,
      parts: [
        {
          name: 'Fundamentals of React',
          exercises: 10,
          id: 1
        },
        {
          name: 'Using props to pass data',
          exercises: 7,
          id: 2
        },
        {
          name: 'State of a component',
          exercises: 14,
          id: 3
        },
        {
          name: 'Redux',
          exercises: 11,
          id: 4
        }
      ]
    },
    {
      name: 'Node.js',
      id: 2,
      parts: [
        {
          name: 'Routing',
          exercises: 3,
          id: 1
        },
        {
          name: 'Middlewares',
          exercises: 7,
          id: 2
        }
      ]
    }
  ]

  return (
    <div>
      // ...
    </div>
  )
}
```

<!-- The application can, for example, look like this:-->
 例如，这个应用可以是这样的。

![](../../images/teht/10e.png)

<h4>2.5: separate module</h4>

<!-- Declare the <i>Course</i> component as a separate module, which is imported by the <i>App</i> component. You can include all subcomponents of the course into the same module.-->
 将<i>课程</i>组件声明为一个单独的模块，它被<i>应用</i>组件导入。你可以将课程的所有子组件纳入同一个模块。

</div>
