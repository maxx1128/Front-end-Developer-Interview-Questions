# Front-end Job Interview Questions

<!--
https://quizlet.com/28293152/front-end-interview-questions-css-flash-cards/

http://lucybain.com/blog/tags/interview-questions/
-->

This file contains a number of front-end interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

**Note:** Keep in mind that many of these questions are open-ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would.

## Table of Contents

  1. [General Questions](#general-questions)
  1. [HTML Questions](#html-questions)
  1. [CSS Questions](#css-questions)
  1. [JS Questions](#js-questions)
  1. [Testing Questions](#testing-questions)
  1. [Performance Questions](#performance-questions)
  1. [Network Questions](#network-questions)
  1. [Coding Questions](#coding-questions)
  1. [Fun Questions](#fun-questions)
  1. [Relative Questions](#relative-questions)

## Getting Involved

  1. [Contributors](#contributors)
  1. [How to Contribute](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/CONTRIBUTING.md)
  1. [License](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/LICENSE.md)

#### General Questions:

* What UI, Security, Performance, SEO, Maintainability or Technology considerations do you make while building a web application or site?

* Which version control systems are you familiar with?
  * Git is the major one, often used with Github or Bitbucket. SourceTree is my tool of choice to manage version control projects, will include others later.

* If you have 5 different stylesheets, how would you best integrate them into the site?
  * If limited only to CSS, this would likely be done by crudely cutting and pasting. However, I'd most likely use Sass partials to merge them all together. This allows several Sass files to be quickly merged together into a single file when its converted to CSS, letting the site read the styles much faster.

* Can you describe the difference between progressive enhancement and graceful degradation?
  * **Progressive enhancement** is building a site with a widely accessible baseline of content and functionality, and only adding onto this while keeping it widely accessible across browsers and platforms. **Graceful degradation** takes the opposite approach, building a site optimized for high performance and and then including support for lower-functioning browsers and platforms.
  * [**In short:**](http://alistapart.com/article/understandingprogressiveenhancement) Progressive enhancement is developing from the bottom up, [Graceful Degradation](http://www.w3.org/wiki/Graceful_degradation_versus_progressive_enhancement) is developing from the top down. With the explosion of "mobile-first" design, the former has become more popular for many.

* How would you optimize a website's assets/resources?
  1. Limit the number of separate files and HTTP requests to them as much as possible
  2. Use a CDN that's built for high performance, if needed
  3. Put the CSS at the top and the Javascript at the bottom, and make them completely external
  4. Minify both CSS and Javascript
  5. Compress images to reduce file-load time, or use image sprites
  6. Avoid redirects and iFrames
  7. Use gzipped content
  8. [Many other things](http://www.sitepoint.com/web-site-optimization-steps/)

* How many resources will a browser download from a given domain at a time?
  * IE7 allowed only two concurrent connections per host. But most browsers today allow more than that. IE8 allows 6 concurrent connections, Chrome allows 6, and Firefox allows 8.
  * So if your web page only has 6 images, for example, then it'd really be pointless to spread your images across multiple subdomains. [Answer found here](http://stackoverflow.com/questions/9583172/how-many-resources-will-a-browser-download-from-a-given-domain-at-a-time)

* Name 3 ways to decrease page load (perceived or actual load time).
  1. Avoid any site redirects and unneeded HTTP requests. Keep all resources local, if possible.
  2. Minify CSS and JS files and concatenate them into singular files
  3. Delay or limit the loading of heavy elements, such as images, with tools such as [lazyload.js](http://www.appelsiini.net/projects/lazyload)

* Describe how you would create a simple slideshow page.
  * If done with a plugin, [bxSlider](http://bxslider.com/) is a free jQuery plugin that's responsive, customizable, mobile-friendly, and works with virtually all of today's browsers.
  * If not, I'd use a [custom Dot Nav component](https://codepen.io/max1128/pen/vGjPeM) I made as part of a previous pattern library.

* Explain the importance of standards and standards bodies.
  * **A broader explanation of web standards and why they matter [can be found here](http://www.sitepoint.com/importance-web-standards/), but the main points of the article are:**
  1. Makes websites more stable and easy to maintain
  2. The familiar patterns and structures of standards makes development faster and debugging easier
  3. Increases backward compatability
  4. Improves site ranking in search engines
  5. Makes it easier for other developers to read, understand, and customize others' code.

* What is Flash of Unstyled Content? How do you avoid FOUC?
  * The [FOUC](http://www.techrepublic.com/blog/web-designer/how-to-prevent-flash-of-unstyled-content-on-your-websites/) is when a page first loads and you see all the elements and markup before the CSS loads. This can alienate site visitors since they see a raw, jumbled version of your website and not the one you've made for them. The biggest way to avoid the FOUC is putting the <link> to your stylesheet in the document's <head> tag. The older, less common way of avoiding it is using javascript to hide page elements until the styles can be loaded. A growing trick is to inline the most important above-the-fold styles so they load immediately, but this means they can't be saved in the cache to save time in subsequent visits.
  
* Explain what ARIA and screenreaders are, and how to make a website accessible.
  * **ARIA (Accessible Rich Internet Applications)** is a set of HTML attributes to make web content more accessible to those with disabilities, such as people using screenreaders for webpages. It allows easier access to navigation, widgets, content, and other important landmarks. **Screenreaders** allow users with visual impairments to use computers, such as by taking a webpage's code and translating information into speech (TTS). It can also give information in Braille. This technology is now more common with computers today and therefore is a higher priority for developers who want their sites to be accessible. One of the best ways to use ARIA for better accessibility is simply assigning ARIA and role attributes to elements, which give more information about them to assistive technology so they're easier to use and manage. They can even be used in CSS targeting for more accurate styling, as their values can't be repeated and provide better CSS "hooks." A more comprehensive accessibility checklist can be found [on the A11y Project.](http://a11yproject.com/checklist.html)

* Explain some of the pros and cons for CSS animations versus JavaScript animations.
  * [CSS animations](https://css-tricks.com/myth-busting-css-animations-vs-javascript/) are excellent for simple animations such as transitions, can be easily integrated into many current workflows, and are fast on most browsers. However, JavaScript animations are also fast, if not faster, when not using jQuery, give more control and flexibility for playback and effects, and have more old browser support. A [quick overview](https://developers.google.com/web/fundamentals/design-and-ui/animations/css-vs-javascript?hl=en) is that CSS animations are better for simple, straightforward animations; JavaScript animations are better for more advanced and controlled animations.
* What does CORS stand for and what issue does it address?
  * CORS stands for "Cross Origin Resource Sharing." It addresses the issue of blocking cross-origin communication requests by giving a specification for allowing it from certain sources. [More info here.](http://www.html5rocks.com/en/tutorials/cors/)

#### HTML Questions:

* What does a `doctype` do?
  * It's a small instruction for a browser about what type of HTML is being used. Has become simplified to ` <!DOCTYPE html> ` for HTML5.
* What's the difference between standards mode and quirks mode?
  * All three are browser modes for [interpreting pages based on web standards.](https://developer.mozilla.org/en-US/docs/Quirks_Mode_and_Standards_Mode) "Quirks Mode" is for sites built before the adaption of web standards like IE 5, and "Full Standards" mode is for sites built with all web standards presumably in mind. There's also "Almost Full Standards," which is like Full Standards but includes a small number of quirks.
* What's the difference between HTML and XHTML?
  * XHTML is almost identical to HTML, but has much [stricter standards](https://www.sitepoint.com/web-foundations/differences-html-xhtml/) with elements like closing tags, case-sensitive attributes, and nesting. This is to help prevent poorly-written HTML from appearing in web pages.
* Are there any problems with serving pages as `application/xhtml+xml`?
  * While this ensures browsers will read your XHTML files as such, and not as HTML files, there are [several risks](http://www.xml.com/pub/a/2003/03/19/dive-into-xml.html). The most noticeable ones are:
  1. If your files don't match the XHTML syntax right, the page won't display.
  2. #NotAllBrowsers can handle this MIME type, so the page also needs to be readable as `text/html`.
  3. CSS and JS for XHTML/XML pages are case-sensitive, which should be taken into account for included assets.
* How do you serve a page with content in multiple languages?
  * Use the `lang` attribute to set the language for a page or component. For example, a webpage initially in English should include the `lang="en"` attribute in the `<html>` tag. If an article in that page is written in Italian, the opening tag would include the same attribute: `<article lang="it">`.
* What kind of things must you be wary of when design or developing for multilingual sites?
  * Making sure content in different languages matches the `lang` attribute
  * Seeing if popular search terms are the same or different in other languages
  * Different languages being hosted in subsections or subdomains
  * Pages loaded on the same or a proxy server
  * Automating translations, doing them by hand, or open-sourcing them
* What are `data-` attributes good for?
  * `data-` attributes are good for [storing custom data values](http://www.w3schools.com/tags/att_global_data.asp) for pages or components. These can be easily used by the site's Javascript for more engaging and specific interactions, based on the attributes' values. They're also better used with Javascript than class names, since it's a better separation of concerns between display and functionality.
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
  * __Canvas__ for dynamic, graphical elements, such as basic animations or signature fields.
  * __Video__ for a standard video player with playback controls. It can also be controlled through JavaScript.
  * __Semantic containers__ such as `section` and `article` which give the browser more useful information about the content in each. Helps maintain higher standards for accessibility and page architecture.
* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
  * The basic differences between the three are as follows:
  * __Cookies__ are simple string variables stored in a browser across different sessions. They're also more easily tampered with by the users or intercepted by other parties.
  * __sessionStorage__ can store more complex JavaScript, but only lasts for a single session (erases when the browser is closed). Not supported by all browsers.
  * __localStorage__ can store more complex JavaScript that can be stored in a browser across sessions. Not supported by all browsers.
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
  * __script__ loads a script but stops the HTML parsing, and possibly delaying the webpage. These tags are often placed in the footer, after everything else, to avoid this problem.
  * __script async__ loads the script while the HTML continues to load, and executes the script whenever it's ready. Good for scripts that don't affect the HTML itself, such as analytics.
  * __script defer__ delays the script load until the HTML is finished parsing. Good since it means the DOM is ready. Bad since it doesn't have full browser support.
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
  * Putting the CSS `<link>`s in the header allows the HTML content to appear as it becomes available, which gives the user active feedback about how fast the webpage is loading. Putting it lower on the page often blocks this feature, and users see a blank page while it loads.
  * Putting the JS `<script>`s at the bottom stops the JS from blocking the load, since JS loads after the page has. This is good since browsers almost always have a limit of how many JS files can load in parallel, which can greatly delay the page load. An alternative to this would be using deferred scripts, but these don't have enough browser support.
* What is progressive rendering?
  * Progressive rendering means the browser renders all the content as it becomes available, as soon as it can.

#### CSS Questions:

1. What is the difference between classes and ID's in CSS?
  * Class values can be used multiple times on an HTML page, and IDs can only be used one per page. However IDs have a much higher specificity, so CSS applied with an ID will more easily override other styles. But in the interest of keeping CSS specificity more equal (so there's fewer unexpected overrides), and in case styles need to be used more than once, styling with IDs is strongly discouraged.
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
  * The basic difference is that "resetting" removes all default browser CSS, while "normalizing" it makes it consistent across browsers. Normalize does this by preserving several defaults, corrects common bugs, and can be fine-tuned for normalizing specific elements. However, normalize CSS can include more code that must be overridden later. I would personally choose Normalize.css over a CSS Reset, since it solves common cross-browser issues and makes cross-browser development easier, which outweighs the fact it may be more code to deal with than a CSS Reset.
* Describe Floats and how they work.
  * CSS floats push an element to the left or right while keeping them in the flow of the page's elements. This makes them go as far in one direction as possible and elements flow around them, like text flowing around an image. They're frequently used in positioning elements around text, like the above example, or creating entire page layouts with columns in rows. Floats are best paired with "clears," which will move elements (or the floated element's container) below the floated element.
* Describe z-index and how stacking context is formed.
  * z-index is set whenever elements overlap, which is common with elements within other elements or absolute positioning. A specific z-index value can be set, but only for elements that have been assigned a "position" property-value pair.
* Describe BFC(Block Formatting Context) and how it works.
  * A BFC is what controls the layout of an element's child elements. Whenever [one of many properties](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context) are applied to a container, it establishes a new BFC for its child elements based on that property. For example, using `overflow: hidden` or `display: inline block` on a container creates a new BFC for all the children in that element. It's important for understanding how elements are being organized, and how this changes in different site containers.
* What are the various clearing techniques and which is appropriate for what context?
  * There are two common ways to clear an element, and all involve using the `clear` CSS property. The first is creating a separate class with `clear`, and adding this class to the container of the floated elements. The second is creating a mixin with the `clear` properties attached and using it on the container element. It's usually better to use the second, since it needs fewer classes and keeps the HTML markup cleaner.
* Explain CSS sprites, and how you would implement them on a page or site.
  * CSS sprites are when many images are grouped together into a single image, and then different sections of that image are shown throughout the page. So an image sprite with three images will be loaded once, used three times on a page, but time it's used only one different part of that image is visible. This way multiple images are shown while only loading one. A way I've made it before was through a npm module through gulp, (gulp-sprite)[https://www.npmjs.com/package/gulp-sprite], which generates the image sprite and needed CSS automatically.
* What are your favorite image replacement techniques and which do you use when?
  * The three [techniques](https://css-tricks.com/css-image-replacement/) I've used most in the past are:
    1. Showing the image and text together, but hiding the text itself.
    2. Putting the text and image in a large box, and only making the part with the image visible.
    3. Same as the above, but moving the text off-screen with a large text-indent instead.
  * In almost all situations now I use the third technique, since it's easier to execute and use in complex layouts. Especially if accessibility is a high priority, since the first technique is good but hides the text for screen readers.
* How would you approach fixing browser-specific styling issues?
  1. I'd check caniuse.com to see if it's already a documented browser issue, since it would quickly explain the issue and a possible solution or workaround.
  2. If that still didn't work, I'd use the browser inspector to directly find and solve the problem through some trial-and-error.
  3. If none of that work, I'd take a graceful degradation approach and make sure the styles for that browser were still presentable and functional.
* How do you serve your pages for feature-constrained browsers?
  * I usually aim for a _grace degradation_ approach, so browsers without certain features will fall back to one with wider support. I normally do this with the Modernizr tool for targeted feature testing. However I've read about @supports which allows for feature testing without any JS or CSS add-ons, and will likely experiment with that the next time I write CSS that needs to degrade gracefully.
* What are the different ways to visually hide content (and make it available only for screen readers)?
  * Some [popular techniques](http://webaim.org/techniques/css/invisiblecontent/) to hide content for users not using screen readers are:
    1. Using a very large text indent to force it off the visible screen
    2. Using absolute positioning to force it off the visible screen 
    3. Using a CSS Clip
  * Techniques that hide it from all users, screen readers included, that __shouldn't__ be used are:
    1. Using `display: none`
    2. Setting the `width` and `height` to zero 
* Have you used or implemented media queries or mobile specific layouts/CSS?
  * Yes, I've regularly used media queries for mobile layouts. Preferred strategy is to write CSS with mobile styles as the base, and then use media queries for larger widths so they adjust for tablet and desktop screens. The breakpoints and media queries themselves are best used as mixins to save time and easily adjust breakpoint widths as needed. I've used several grid frameworks in the past, including Susy and Bourbon, for both responsive layouts and media queries in general.
* Are you familiar with styling SVG?
  * __Revisit this later!__
* How do you optimize your webpages for print?
  * __Revisit this later!__
* What are some of the "gotchas" for writing efficient CSS?
  * Most relate to writing better CSS selectors:
    * Use class names for styling instead of base elements or IDs, since they have more equal specificity and allow for better modular use
    * Don't use *, the universal selector
    * Use a naming convention, such as BEM, for consistency and structure that helps avoid specificity issues
    * Avoid nested selectors, since they can cause specificity creep that makes it incredibly difficult to override styles (often in unexpected places)
* What are the advantages/disadvantages of using CSS preprocessors?
  * For me the advantages of preprocessors (in this case Sass) are better organization by breaking a CSS into partial, using variables for reused values, using mixins and functions for easier and faster styling of otherwise complex components, and the increased modularity of Sass files.
  * The disadvantages are setting up a workflow for the preprocessor (such as Gulp), and having to use a new syntax. However, for me the benefits far outweigh the costs.
  * _Describe what you like and dislike about the CSS preprocessors you have used._
    * I like how it makes it easier to reduce redundant, such as using Sass maps and loops to generate styles that are otherwise the same but with only a few different variables. It also makes managing and changing reused values, such as a site color palette, much easier. I also greatly enjoy using different file architectures, since they help makes styles much more organized, less likely to conflict, and easier to reference and combine in the HTML. My only major dislike has been debugging issues without seeing the exact cause, like having to look through a partial for a syntax error without knowing the precise location. However this has always been worth the better organization and control.
* How would you implement a web design comp that uses non-standard fonts?
  * I would import the font files with CSS. Once I had the font files in the needed formats (eot, woff, ttf, svg), or if I could use a web font service such as Google Fonts, I'd import them with `@font-face`. I have experience with both, but if there's extra space in the site's performance budget and offline performance isn't a high priority, I prefer using a web font since it's more convenient and requires fewer assets.
* Explain how a browser determines what elements match a CSS selector.
  * The browser matches the CSS selector by going right to left. So the selector `.class-1 .class-2 .class-3` will start by looking for `.class-3` in the DOM, then seeing if there's a `.class-2` higher up in the DOM branch. This makes the work along the DOM proportional to the most specific selector. Going from left to right will require more traversing with less chance of finding a selector, and means more calculations with less results.
* Describe pseudo-elements and discuss what they are used for.
  * Pseudo-elements are extra identifiers after CSS selectors, with two colons after (`.selector::pseudo-element`). They can be used to style:
    * Specified parts of an element, such as the first line
    * Different element states, such as `::hover`
    * A specific selection of a collection of adjacent elements, like all the odd elements in a group, the first three items, or even more complexly selected ones
    * `::before` and `::after` elements, which can create elements around the selected one via CSS. These can be empty, text, images, or others.
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
  * The CSS box model is how the browser sees different spacing arrangements of a container. It has four parts:
    * The content in the box
    * The padding, which is the spacing inside the content but still inside the container
    * The border that's the boundary of the container
    * The margin, which is the spacing outside the container
  * This can be altered by changing the `box-sizing` property of an element. 
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
  * Normally, adding padding increases the previously calculated width and height of a container. Adding `box-sizing: border-box` means the padding doesn't change the height and width, instead shrinking the content area. It's good if you don't want to disturb the dimensions, like if it's part of a layout, and can help separate the border from the content.
* List as many values for the display property that you can remember.
  * Block, inline-block, block, none, flex, inline-flex, list-item, table table-cell, table-row, table-column, initial, inherit, run-in.
* What's the difference between inline and inline-block?
  * Both can flow within text or around other elements, but inline-blocks can have their width and height set to specific values.
* What's the difference between a relative, fixed, absolute and statically positioned element?
  * Static: Is the default, where elements render based on their order in the HTML. 
  * Relative: Positioned relative to the normal position it would have for `static`.
  * Fixed: Positioned relative to the browser window
  * Absolute: Positioned relative to the parent container (if they have relative positioning).
* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?
  * The two main factors in deciding priority is `weight` and `order`.
    * __Weight__ is the level of importance in a selector. Styles in selectors with a greater weight will override styles in selectors with less weight. For example, classes have less weight than IDs. So when adjusting an element's width with a class and ID, the width in the ID selector will override it. The general order of selectors, from lightest to heaviest, is element tags, classes, IDs, inline styles, and styles with `!important`.
    * __Order__ kicks in when there's multiple styles with the same weight. In this case, the styles written later in the file will be used. So with two selectors that each use a class to change the width, the styles with the class selector written twice will be used. This is where the "Cascading" part of CSS comes into play the most.
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
  * I've worked with Foundation 5 a lot in my current job, using it as a basis for building a pattern library. I've also used Bootstrap, Materialize and HTML5Up for side or personal projects. My biggest issue I've had with them is their naming conventions, since they were developed before conventions like BEM become popular and therefore have been slow to adopt them. It's made components harder to customize and reference due to specificity issues and names too hard to fully understand. I would implement namespacing and BEM to better organize and modularize the code.
* Have you played around with the new CSS Flexbox or Grid specs?
  * I've frequently used Flexbox in my personal and professional work, as it solves a number of modular layout issues I'd previously had issues with. I've also made a Sass grid system based off Flexbox, so I consider myself fairly competent with it. I've researched and experimented with CSS Grid, although the lack of clarity about when it'll receive full browser support has hampered my enthusiasm a little. But I'm still reading Rachel Andrew's continuing work about the basics and practical uses of the grid system so I'll be prepared right when it's ready for production work.
* How is responsive design different from adaptive design?
  * Responsive design is more fluid, with elements actively changing for all possible screen widths (with a possible maximum width). Adaptive design is set to change at specific breakpoints, often in line with popular device dimensions. A good way to quickly see the difference is to resize the screen and see how elements react: responsive designs will move and change constantly as the screen resizes; adaptive designs will stay the same most of the time, with all the content centering in the screen's extra space, and then changing at specific widths.
* Have you ever worked with retina graphics? If so, when and what techniques did you use?
  * I've never used retina graphics, or queries to display high quality graphics for higher resolution devices, since the requirements for it haven't yet come up in my projects. However I'm familiar with the need for them to improve a user's visual experience when they're using higher-quality devices.
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?
  * Normally I stick to absolute positioning, but would go to `translate()` if any animations were needed, performance were an especially high priority, or didn't want to completely remove the transformed object from the flow of the DOM (and not change the space it originally took up). I'd specifically want to use absolute positioning if I needed to change the elements size according to the parent element, like by using `left: 0; right: 0;` to take up its full width.

#### JS Questions:

1. Explain event delegation
  * [Event delegation](https://www.sitepoint.com/javascript-event-delegation-is-easier-than-you-think/) is a way to trigger events for different child elements of a parent element, but without creating event handlers for each one. In essence it's setting up different events for the child elements, but the only event handler is technically from the parent element. For instance, if multiple inputs in a form trigger different events, event delegation lets us set up just one event handler from the form container.
  * The benefits are fewer event handlers, which boosts performance, and it works with dynamically generated elements (such as ones via AJAX). The downsides are not all elements are supported, and some events risk event bottlenecks (too many being triggered), but these can usually be avoided with proper foresight.
* Explain how `this` works in JavaScript
  * `this` is a reference to the current element being targeted in a function or loop. It's an easy way to target active elements in the DOM on a case-by-case basis. For example, for click events on `.element` selector, using `this` will only effect the element the user clicked on, not every `.element` selected in the DOM. Plus for each loops going through every `.element` in the DOM, using `this` will only target the element in the individual loop.
* Explain how prototypal inheritance works
  * PI is similar to how classes are inherited in CSS - if an element has two classes, it inherits the styles from both. PI works similarly, but for objects - setting Object1 as a prototype for Object2 means Object2 inherits the properties of Object1. So if a value or function being called from Object2 isn't there, it'll then look in its prototype, Object1, and use it if it's there. More specifics on using it can be found [here](http://javascript.info/tutorial/inheritance). 
* What do you think of AMD vs CommonJS?
  * I've used only CommonJS for my javascript work, mainly since it heavily inspired how Node.JS manages dependencies and is a frequent tool of mine (also Browserify, which I've used but less often). I've researched AMD and still prefer CommonJS for its simpler syntax and integrated dependency management. However if asynchronous module loading becomes a project priority, I would try moving to AMD for it since that's the main difference between the two.
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`. What needs to be changed to properly make it an IIFE?
  * This doesn't work as an Immediately-Invoked Function Expression since their syntax requires parenthesis to be wrapped around it. In this case you could write the function as `(function foo(){ }());` or `(function foo(){ })();` and it would then work as an IIFE.
* What's the difference between a variable that is: `null`, `undefined` or undeclared? How would you go about checking for any of these states?
  * **Null:** a purposeful value assigned to a variable, synonymous with "empty." Simple check: `if ( var === null )`.
  * **Undefined:** a variable that's been declared but not defined, so it has no value associated with it at all. Simple check: `if ( var == undefined )`.
  * **Undeclared:** a variable that's been created without the `var` keyword, and will usually operate on the global scope instead of any intended limited scope, such as a function. Will usually throw an error, or can be checked with `console.log(var)` to test returned value.
* What is a closure, and how/why would you use one?
  * A (closure)[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures] is a function that have the same body and functions, but in different environments (different variable values). Two different closures may have the same functions and math, but one or more variables have different values. I would use them a similar function with specific different values would be needed - a simple example would be multiple functions that each add or subtract a specific number. Especially if each needs to maintain their environment stable and separate from each other. I already use something similar with how I containerize certain component's JS code, since it's very helpful for modular JS. So I would likely use closures the most for JS around pattern and component libraries.
* What's a typical use case for anonymous functions?
  * A typical use case that I've also often used is for calculating and returning new values for variables. For example I'd start with variable A, and then use an anonymous function to create a new value, or array of values, that I'd save as variable B. I use anonymous functions for this unless I want to use it in other areas of the code as well.
* How do you organize your code? (module pattern, classical inheritance?)
  * I prefer to use the module pattern for the better organization, especially for more complex Javascript and is useful for Pattern Libraries. It's also similar to how I've written Javascript whenever I've used Node.JS, which makes it more familiar and uniform across the code I write.
* What's the difference between host objects and native objects?
  * **Host Objects** are objects given based on how the site's being hosted, such as window width if it's a browser or info related to a Node.JS server being used. **Native Objects** are ones provided by Javascript, such as `Date` and `Math`, and Javascript makes natively available.
* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
  * `function Person(){}` is the standard way to declare and use a new function.
  * `var person = Person()` also declares a function but does so inside a variable. This is mostly a syntax difference, but can allow for extra complexity.
  * `var person = new Person()` is calling a function, and storing the output of that function in a variable. If `Person()` returns a value, that value will be stored in the `person` var. This makes it easier to create more variables or arrays with certain values, since the functions will do the work of calculating them.
* What's the difference between `.call` and `.apply`?
  * Both of them are ways to use function functions which [are called in the scope of the first argument given.](http://hangar.runway7.net/javascript/difference-call-apply) So if a function uses values from one variable that's out of its scope, both let that function be called as if that variable was within its scope.
  * The main difference is when adding additional arguments. `.call` requires the different arguments to be explicitly named and listed. `.apply` accepts a basic array that can contain any number of values.
* Explain `Function.prototype.bind`.
  * This is a method that sets the `'this'` value in a function to a provided value. So if we wanted to run a function while setting the `'this'` value at `x`, we would use `functionName.bind(x)`. This is great for [controlling values at the local scope of a function.](https://www.smashingmagazine.com/2014/01/understanding-javascript-function-prototype-bind/)
* When would you use `document.write()`?
  * `document.write()` has [few approved uses](http://lucybain.com/blog/2015/js-document-write/), due to several flaws: it doesn't work on XHTML pages, using it after page load overwrites the entire page, and isn't a fast way to load more assets into the DOM. Most often it's used for adding in 3rd-party code, such as ads, since it works independent of whatever Javascript code and events the site is running.
* What's the difference between feature detection, feature inference, and using the UA string?
  * **Feature detection** is checking if a specific feature is supported in a browser before using it, such as flexbox, which is generally the preferred practice. One of the most popular tools for this is Modernizr.
  * **Feature inference** is seeing if one feature is supported, and then making an inference off this that another one also is. However there may always be exceptions, which creates risk and is seen as a bad practice.
  * **Using the UA string** means checking the user agent to see what specific browser and version a person is using, and basing your code off this. This also has risks, as future versions of browsers that you can't check for may or may not support certain features. Plus the UA string may not be written the same for all users, or it will change in the future.
* Explain AJAX in as much detail as possible.
  * **Asynchronous JavaScript and XML** is a faster way to load more content to a webpage. Before, adding new HTML meant the entire page had to refresh. AJAX lets new HTML, which can include and respond to different data, load without refreshing the page. Now it's possible to charge large amount of the page's front-end with a much faster response time and with much more convenience.
* Explain how JSONP works (and how it's not really AJAX).
  * JSONP is an answer to the issue of getting data from other servers. AJAX normally just lets you query data from your own server. Devs can instead call this data using a script tag, similar to how they'd get Google webfonts. The script can then use a `callback` function to pull and manage the data for your own use. This explains the name **JSONP**, as the data is 'padded' in a callback function.
  * This also explains why JSONP isn't technically AJAX - AJAX was made for requests in the same domain, while JSONP is from different domains.
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
  * **REVISIT THIS!**
* Explain "hoisting".
  * [Hoisting](http://lucybain.com/blog/2014/hoisting/) is when a variable or function declaration is "hoisted," or brought to the top of, its scope. So if a variable is used or defined before it gets declared, the JS interprets it to add a blank declaration to the top of the scope. This can override variables with the same name in the global scope, and variables are usually hoisted before functions are. This is all important to know since it can often change where a dev thinks their variables and functions are being declared.
* Describe event bubbling.
  * This is when the event triggered by one event "bubbles up" to above elements, triggering it for them as well. So a click event on some marked text will also activate a click event on all the parent and ancestor elements. A way to prevent this is using this code: `event.stopPropagation();`.
* What's the difference between an "attribute" and a "property"?
  * Properties are defined in the HTML DOM tree, while attributes are defined in the HTML file. This means that attributes will always return the default value through JS, while properties will show changed values. Plus, attributes can only be strings. For this reason, it's generally better practice to use properties, not attributes, whenever possible.
* Why is extending built-in JavaScript objects not a good idea?
  * Extending built-in JS objects depends heavily on the features already implemented in the browser, which risks these features changing or being removed in the future. Therefore not extending built-in objects adds stability and doesn't risk any silent browser updates throwing an entire site or app into sudden disarray. 
* Difference between document load event and document ready event?
  * `doc ready` fires when all the HTML has finished loading, and `doc load` fires when all the content on the page has finished loading, such as images and CSS. This makes the latter much slower to kick in, but useful if the JS specifically refers to content that needs to load first.
* What is the difference between `==` and `===`?
  - `==` checks if the values are equal, while `===` checks if the values and type of value are equal. So `1 == '1` would return true, since the values are equal despite being different types (number and string). However `1 === '1'` would be false unless the first value became a string, or the second became a number.
* Explain the same-origin policy with regards to JavaScript.
  * The same-origin policy is for security, to ensure that no malicious code from other sites is executed on another. It defines the origin as being the same if the sites have the same:
    1) Security protocol (https, for example)
    2) Domain name
    3) Port number 
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
* Why is it called a Ternary expression, what does the word "Ternary" indicate?
  * A Ternary expression is an operation is an operan that accepts three parameters. The ternary syntax for Javascript breaks this into the condition, the action if the condition is true, and the action if the condition is false. A simple example of a ternary expression is `2 > 1 ? 'true' : 'false'`. Since two is greater than one, this operation returns the `'true'` string, not the `'false'` one. They can also incorporate variables and be used as conditionals for assigning variable values. Best used with less complex logic.
* What is `"use strict";`? what are the advantages and disadvantages to using it?
  * Putting this above any code evaluates it in "Strict Mode," which throws additional errors to enforce code using better practices, such as throwing errors when access to the global object, or simply disabling confusing JS features.
  * The obvious advantages are better enforcement of clearer, more robust JS. The disadvantages are less, mainly that mixing strict and non-strict modes can lead to confusion, and some developers may be more reliant, or have code that's already more reliant, on certain features that would no longer be allowed.
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
  ```javascript
  function isFizz(num) {
    return num % 3 === 0;
  }
  
  function isBuzz(num) {
    return num % 5 === 0;
  }
  
  function toFizzBuzzString(num) {
    let fizz = isFizz(num) ? 'fizz' : '';
    let buzz = isBuzz(num) ? 'buzz' : '';
    return `${fizz}${buzz}`;
  }
  
  function * fizzBuzz(start, end) {
    for (let num = start; num <= end; num++) {
      yield {num, label: toFizzBuzzString(num)};
    }
  }
  
  for (let { num, label } of fizzBuzz(0, 100)) {
    console.log(`${num} ${label}`);
  }
  ```
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
  * Avoiding the global scope is generally a good practice for several reasons, and the common theme is structure. Having variables in the global scope usually makes them harder to organize and more likely to have name clashes and overrides. It's simply more practical to limit the scope to where it's needed to avoided any unneeded consequences like above. JS global variables are particularly important, since unless variables are properly defined in a certain scope, they default to global scope. So ensuring no global variables is of special importance since it's more likely to happen by accident.
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
  * The `onload` event triggers once an element has been completely loaded in the DOM. This is usually used when the event in question needs the element to be fully loaded first, to check browser information, or deal with cookies. However this can get difficult to manage, as it must be attached to HTML elements, such as the `<body>` tag, when there's many functions to include. However a way around this is to use a function to more easily [combine them into a single function](http://www.webreference.com/programming/javascript/onloads/index.html). An alternative I frequently use is adding jQuery and using the `$(document).ready()` function to contain all my Javascript, since it has the same effect and avoids the risk of forgetting to include all needed functions in the `onload` function.
* Explain what a single page app is and how to make one SEO-friendly.
  * A SPA is a web application that works on a single HTML files that updates as the user interacts with it. Instead of going to different pages for login, profile, and other content, they all appear on the same page and load with techniques such as AJAX for a smooth user experience. Ways to [improve the SEO for these](https://www.getambassador.com/blog/single-page-webapp-seo) include more focused URLs, caching your site's content, and indexing all your pages in a sitemap.
* What is the extent of your experience with Promises and/or their polyfills?
  * RETURN TO THIS
* What are the pros and cons of using Promises instead of callbacks?
  * The [main difference between promises and callbacks](https://www.quora.com/Whats-the-difference-between-a-promise-and-a-callback-in-Javascript) is that, when making different calls for values, a promise is a proxy value not known when used - when the value arrives, or the promise is fulfilled, then the next step is executed.
  * The main benefits of promises are that the code is often written cleaner and simpler, and is better for asynchronous operations (since there's no need to nest a great amount of callbacks). However, callbacks are best used for short, local reactions since there's no data being managed or that needs a placeholder.
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
  * [Advantages:](http://buildnewgames.com/compiling-to-javascript/) static and strong typing which help maintainability in large codebases, easier debugging, static analysis for better organization.
  * Disadvantages: adds an extra step in compiling, lower performance speed, added complexity if the new syntax isn't fully understood.
* What tools and techniques do you use debugging JavaScript code?
  * My most used technique to debugging Javascript is simply using console.log to keep track of expected values and operations through the browser and spot any errors. This recently helped me debug an issue with a component that was supposed to fix an element on certain screen positions by telling me how and when the conditions to trigger it were being missed. Otherwise I use [JSHint](http://jshint.com/) as an external checker.
* What language constructions do you use for iterating over object properties and array items?
* Explain the difference between mutable and immutable objects.
  * What is an example of an immutable object in JavaScript?
  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?
* Explain the difference between synchronous and asynchronous functions.
  * Synchronous functions block the next function in line until the next one is complete. Asynchronous ones will process in the background while the next function is also processed.
* What is event loop?
  * What is the difference between call stack and task queue?

#### Testing Questions:

1. What are some advantages/disadvantages to testing your code?
* What tools would you use to test your code's functionality?
* What is the difference between a unit test and a functional/integration test?
* What is the purpose of a code style linting tool?

#### Performance Questions:

1. What tools would you use to find a performance bug in your code?
* What are some ways you may improve your website's scrolling performance?
* Explain the difference between layout, painting and compositing.

#### Network Questions:

1. Traditionally, why has it been better to serve site assets from multiple domains?
* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
* What are the differences between Long-Polling, Websockets and Server-Sent Events?
* Explain the following request and response headers:
  * Diff. between Expires, Date, Age and If-Modified-...
  * Do Not Track
  * Cache-Control
  * Transfer-Encoding
  * ETag
  * X-Frame-Options
* What are HTTP actions? List all HTTP actions that you know, and explain them.

#### Coding Questions:

*Question: What is the value of `foo`?*
```javascript
var foo = 10 + '20';
```
**Answer: 1020.** Because adding a value with a string, because they're different data types, will result in them just sticking together.

*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```

*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```

*Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```

*Question: What is the value of `foo.x`?*
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```

*Question: What does the following code print?*
```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
```

#### Fun Questions:

1. What's a cool project that you've recently worked on?
* What are some things you like about the developer tools you use?
* Do you have any pet projects? What kind?
* What's your favorite feature of Internet Explorer?
* How do you like your coffee?

#### Relative Questions:

1. What did you learn yesterday/this week?
    * This is an indented answer!
* What excites or interests you about coding?
* What is a recent technical challenge you experienced and how did you solve it?
* Talk about your preferred development environment.
* Can you describe your workflow when you create a web page?
* If you jumped on a project and they used tabs and you used spaces, what would you do?
* If you could master one technology this year, what would it be?
* Have you used different HTML templating languages before?
* Have you ever used a grid system, and if so, what do you prefer?

#### Contributors:

This document started in 2009 as a collaboration of [@paul_irish](https://twitter.com/paul_irish) [@bentruyman](https://twitter.com/bentruyman) [@cowboy](https://twitter.com/cowboy) [@ajpiano](https://twitter.com/ajpiano)  [@SlexAxton](https://twitter.com/slexaxton) [@boazsender](https://twitter.com/boazsender) [@miketaylr](https://twitter.com/miketaylr) [@vladikoff](https://twitter.com/vladikoff) [@gf3](https://twitter.com/gf3) [@jon_neal](https://twitter.com/jon_neal) [@sambreed](https://twitter.com/sambreed) and [@iansym](https://twitter.com/iansym).

It has since received contributions from over [100 developers](https://github.com/h5bp/Front-end-Developer-Interview-Questions/graphs/contributors).
