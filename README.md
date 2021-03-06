Markdown Preview Enhanced
===
Still Beta Version!    
[![](https://img.shields.io/github/tag/shd101wyy/markdown-preview-enhanced.svg)](https://github.com/shd101wyy/markdown-preview-enhanced/releases) ![](https://img.shields.io/apm/dm/markdown-preview-enhanced.svg)  [![](https://img.shields.io/github/stars/shd101wyy/markdown-preview-enhanced.svg?style=social&label=Star)](https://github.com/shd101wyy/markdown-preview-enhanced)  

[中文文档](./docs/README_CN.md)    
[Wiki](https://github.com/shd101wyy/markdown-preview-enhanced/wiki) (not done yet)

---

Version `0.10.9` supports [prince](https://www.princexml.com) pdf export.  
More information can be found [at this doc](./docs/prince.md).

---

[language-gfm-enhanced](https://atom.io/packages/language-gfm-enhanced) is recommended to be installed to work with markdown-preview-enhanced.  

Post [here](https://github.com/shd101wyy/markdown-preview-enhanced/issues) if you request new features or you want to report bugs ;)

(TOC below was generated by this package `Markdown Preview Enhanced: Create Toc`)

<!-- toc orderedList:0 -->

* [Markdown Preview Enhanced](#markdown-preview-enhanced)
	* [Features](#features)
	* [How it works](#how-it-works)
	* [Usages](#usages)
	* [Preview Context Menu](#preview-context-menu)
	* [Extra](#extra)
	* [For Developer](#for-developer)
	* [FAQ](#faq)
	* [Credits](#credits)
	* [Thanks](#thanks)

<!-- tocstop -->
---

![intro](https://cloud.githubusercontent.com/assets/1908863/22763072/32f09e80-ee28-11e6-9d42-c3953f5749a1.gif)

## Features
- **2-side scroll sync**  
- **[Import external files](./docs/doc-imports.md)**
- **[Code Chunks (beta)](./docs/code-chunk.md)**
- **[pandoc](./docs/pandoc.md)**
- **[prince](./docs/prince.md)**  
- **[ebook](./docs/ebook.md)**
- **[Presentation Writer](https://rawgit.com/shd101wyy/markdown-preview-enhanced/master/docs/presentation-intro.html)**
- **[Extensible](#for-developer)**
- markdown preview with math typesetting support   
You can choose [MathJax](https://github.com/mathjax/MathJax) or [KaTeX](https://github.com/Khan/KaTeX) to render math expressions  
- export **PDF**, **PNG**, and **JPEG**   
- export beautiful **HTML** (mobile device supported)  
- [compile to Markdown](./docs/markdown.md)
- customize Markdown Preview css  
- [TOC](./docs/toc.md) generation **(beta)**  
- Flowchart / Sequence diagram
- Task List *(Github Flavored)*  
- Image Helper
- [Footnotes](https://github.com/shd101wyy/markdown-preview-enhanced/issues/35)  
- [Front Matter](https://github.com/shd101wyy/markdown-preview-enhanced/issues/100)
- And many more...

## How it works
- [remarkable](https://github.com/jonschlinkert/remarkable) to convert markdown to html.
- [KaTeX](https://github.com/Khan/KaTeX) or [MathJax](https://github.com/mathjax/MathJax) to render math expressions. ([KaTeX Supported functions/symbols](https://github.com/Khan/KaTeX/wiki/Function-Support-in-KaTeX)) (MathJax is incompatible with `preview-inline` package)
  - expression within `$...$` will be rendered normally.  
  - expression within `$$...$$` and code block <code>\`\`\`math</code> will be rendered in displayMode.   
  - if you want to enable math highlighting, try [language-gfm-enhanced](https://atom.io/packages/language-gfm-enhanced) package.  
  - You can choose your math rendering method from [settings panel](#settings-panel).   
		**MathJax** supports more symbols, but it has slower rendering speed compared to **KaTeX**.
  - <img src="https://cloud.githubusercontent.com/assets/1908863/14398210/0e408954-fda8-11e5-9eb4-562d7c0ca431.gif">
- [mermaid](https://github.com/knsv/mermaid) to render flowchart and sequence diagram.  
	- code block with `mermaid` (or `@mermaid`) notation will be rendered by [mermaid](https://github.com/knsv/mermaid)  
	- check [mermaid doc](http://knsv.github.io/mermaid/#flowcharts-basic-syntax) for more information about how to create flowchart and sequence diagram   
	- ![mermaid](https://cloud.githubusercontent.com/assets/1908863/23383956/5c8cb37e-fd0e-11e6-8a22-f3946841bbbd.gif)
- [PlantUML](http://plantuml.com/) to create multiple kinds of graph. (**Java** is required)  
	- You can install [Graphviz](http://www.graphviz.org/) (not required) to generate all diagram types.
	- code block with `puml` or `plantuml` or (`@puml` or `@plantuml`) notation will be rendered by [PlantUML](http://plantuml.com/).  
- [WaveDrom](http://wavedrom.com/) to create digital timing diagram.  
	- code block with `wavedrom` (or `@wavedrom`) notation will be rendered by [wavedrom](https://github.com/drom/wavedrom).
- [Viz.js](https://github.com/mdaines/viz.js) to render [dot language](https://en.wikipedia.org/wiki/DOT_(graph_description_language)) graph.  
	- code block with `viz` (or `@viz`) notation will be rendered by [Viz.js](https://github.com/mdaines/viz.js).
    - add `engine:[engine_name]` at the first line of code block to choose different render engine. For example `engine:dot`. Engine `circo`, `dot`, `neato`, `osage`, or `twopi` are supported. Default engine is `dot`.   
- [reveal.js](https://github.com/hakimel/reveal.js) to render beautiful presentations.
	- [Click here](https://rawgit.com/shd101wyy/markdown-preview-enhanced/master/docs/presentation-intro.html) to see the introduction.

## Usages
To use this package, press <kbd>cmd + shift + p</kbd>   in atom editor first to toggle <strong> Command Palette </strong>. Then choose the commands below:
- <strong>Markdown Preview Enhanced: Toggle</strong>
  - Toggle Markdown file preview with KaTeX support.   
	You can also use the keymap <kbd>ctrl+shift+m</kbd> to toggle preview. (To use keymap, you have to disable the default [markdown preview](https://atom.io/packages/markdown-preview) package, otherwise there would be keymap conflict)
- <strong>Markdown Preview Enhanced: Toggle Zen Mode </strong>  
	- Toggle distraction free writing.  
- <strong>Markdown Preview Enhanced: Customize CSS</strong>
  - Customize preview page css. You can edit styles inside `markdown-preview-enhanced-custom` section in `style.less` file.  
  - If you didn't see `markdown-preview-enhanced-custom` section in `style.less` file, you may need to run `Markdown Preview Enhanced: Customize CSS` command first.
- <strong>Markdown Preview Enhanced: Create Toc </strong>
  - Generate TOC (need preview toggled). [doc is here](./docs/toc.md).    
- <strong>Markdown Preview Enhanced: Toggle Scroll Sync </strong>
  - Enable/Disable scroll sync for preview.
- <strong>Markdown Preview Enhanced: Toggle Live Update </strong>
	 - Enable/Disable live update for preview.
	 - If disabled, preview will only be rendered when the file is saved.  
- <strong>Markdown Preview Enhanced: Toggle Break On Single Newline </strong>
  - Enable/Disable breaking on single newline.
- <strong>Markdown Preview Enhanced: Insert New Slide </strong>  
- <strong>Markdown Preview Enhanced: Insert Table </strong>
- <strong>Markdown Preview Enhanced: Insert Page Break </strong>
- <strong> Markdown Preview Enhanced: Config Mermaid</strong>
  - Edit `mermaid` init configuration.
- <strong> Markdown Preview Enhanced: Config Header Footer</strong>
  - **PDF** export header and footer configuration.
- <strong>Markdown Preview Enhanced: Image Helper</strong>  
	- Image Helper supports image url quick insertion, image paste, and image upload powered by [imgur](http://imgur.com/) and [sm.ms](https://sm.ms/).       
	(if **imgur** is blocked by **the Great Firewall**, then you can choose **sm.ms** instead).    
	- Keymap <kbd>ctrl+shift+i</kbd>    
	-  ![image_helper](https://cloud.githubusercontent.com/assets/1908863/15414603/c40b6556-1e6e-11e6-956c-090b5996ec87.gif)   

## Preview Context Menu
**Right click at preview to see the menu**

![contextmenu](http://i.imgur.com/hOxseAS.gif)

- <strong> Open in Browser </strong>
  - Open HTML in browser
- **Export to Disk**
	- Export **HTML**, **PDF**, **PNG**, **JPEG**, **ePub** etc files.
- **Pandoc Document Export**
	- [doc](./docs/pandoc.md)
- **Save as Markdown**
	- [doc](./docs/markdown.md)

## Extra
* **Code Chunks** [doc](./docs/code-chunk.md)
* **EBook**  
	More information about how to create ebook can be found [here](./docs/ebook.md).
* **Presentation Writer**  
	More information about how to create Presentation can be found [here](https://rawgit.com/shd101wyy/markdown-preview-enhanced/master/docs/presentation-intro.html).
* **Task List**  
	This package supports *Github Flavored* task list.  
	More information about how to create **task list** can be found [here](https://github.com/blog/1375-task-lists-in-gfm-issues-pulls-comments)
* **Smart Navigation**    
	You can quickly open another markdown file by clicking its link in preview.  
* **Preview Auto Open**  
	Open preview pane automatically when you open a markdown file. You can disable this functionality from settings panel.

## For Developer
Manual installation instruction can be found [here](./docs/DEVELOPER.md).   
It is also very easy to write your own extension, more information can be found [here](./docs/extension.md).

## FAQ
1. **I am not able to find this package in atom?**  
Please search for the full name of this package. `markdown-preview-enhanced`  
2. **I exported a html file, and I want to deploy it on my own remote server. But math typesetting (MathJax or KaTeX) doesn't work, what should I do?**  
Please make sure you have `Use CDN hosted resources` checked when exporting.  
3. **I exported a presentation html file, and I want to put it on my Github Page or deploy remotely?**  
Please check the last question.  
4. **How do I get dark style preview?**  
If you want the style of the preview to be consistent with your atom editor, go to settings of this package, then change the `Preview Theme`.  
Or you can run `Markdown Preview Enhanced: Customize Css` command, then modify the `style.less` file.  [#68](https://github.com/shd101wyy/markdown-preview-enhanced/issues/68), [#89](https://github.com/shd101wyy/markdown-preview-enhanced/issues/89).
5. **The preview is super super lagging?**  
This might happen when your markdown file is too big, or you are using too many math or graphs.  
Therefore I would like to recommend you to disable `Live Update` functionality.  
You can run `Markdown Preview Enhanced: Toggle Live Update` to disable it.  
6. **Do you need a job? (Huh... is this question really related to FAQ???)**  
Yes, I am looking for job. `(*/ω＼*)` (Any country (region) should be fine for me. I can also work remotely.)     
I am an international student from China currently studying at University of Illinois at Urbana-Champaign. I am a CS major student and I will get my BS/MCS degree this May (2017).  
I am personally very interested in game development and front-end web development. If you are willing to offer me a job opportunity, please contact me by my school email `ywang189@illinois.edu` or my personal email `shd101wyy@(sina|gmail).com`. (plz don't be mad if you don't get any response from me because I might be busy working on my homework `(✿◡‿◡)).      
Thank you very much :)  

## Credits  
* [remarkable](https://github.com/jonschlinkert/remarkable) - Markdown parser, done right. Commonmark support, extensions, syntax plugins, high speed - all in one. Gulp and metalsmith plugins are also available.  
* [KaTeX](https://github.com/Khan/KaTeX) - Fast math typesetting for the web.  
* [MathJax](https://github.com/mathjax/MathJax) - Beautiful math in all browsers.  
* [mermaid](https://github.com/knsv/mermaid) - Generation of diagram and flowchart from text in a similar manner as markdown.  
* [viz.js](https://github.com/mdaines/viz.js) - A hack to put Graphviz on the web.
* [plantuml](https://github.com/plantuml/plantuml) - Generate UML diagram from textual description.
* [WaveDrom](https://github.com/drom/wavedrom) - Digital timing diagram rendering engine.
* [reveal.js](https://github.com/hakimel/reveal.js) - The HTML Presentation Framework.
* [save-svg-as-png](https://github.com/exupero/saveSvgAsPng) - Save SVGs as PNGs from the browser.
* [pandoc](https://github.com/jgm/pandoc) - Universal markup converter.
* [async](https://github.com/caolan/async) - Async utilities for node and the browser.
* [babyparse](https://github.com/mholt/PapaParse) - Fast and powerful CSV (delimited text) parser that gracefully handles large files and malformed input.
* [cheerio](https://github.com/cheeriojs/cheerio) - Fast, flexible, and lean implementation of core jQuery designed specifically for the server.
* [gray-matter](https://github.com/jonschlinkert/gray-matter) - Smarter yaml front matter parser, used by assemble, metalsmith and many others.
* [html-pdf](https://github.com/marcbachmann/node-html-pdf) - Html to pdf converter in nodejs. It spawns a phantomjs process and passes the pdf as buffer or as filename.
* [node-imgur](https://github.com/kaimallea/node-imgur) - Upload images to imgur.com.
* [request](https://github.com/request/request) - Simplified HTTP request client.
* [node-temp](https://github.com/bruce/node-temp) - Temporary File, Directory, and Stream support for Node.js.
* [uslug](https://github.com/jeremys/uslug) - A permissive slug generator that works with unicode.
* [atom](https://github.com/atom/atom) - The hackable text editor.

## Thanks  
Thanks for using and supporting this package ;)

> University of Illinois/NCSA Open Source License
