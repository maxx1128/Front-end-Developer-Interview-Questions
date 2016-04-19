# Front-end Job Interview Questions

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

* Explain the importance of standards and standards bodies.
  * **A broader explanation of web standards and why they matter [can be found here](http://www.sitepoint.com/importance-web-standards/), but the main points of the article are:**
  1. Makes websites more stable and easy to maintain
  2. The familiar patterns and structures of standards makes development faster and debugging easier
  3. Increases backward compatability
  4. Improves site ranking in search engines
  5. Makes it easier for other developers to read, understand, and customize others' code.

* What is Flash of Unstyled Content? How do you avoid FOUC?
  * The [FOUC](http://www.techrepublic.com/blog/web-designer/how-to-prevent-flash-of-unstyled-content-on-your-websites/) is when a page first loads and you see all the elements and markup before the CSS loads. This can alienate site visitors since they see a raw, jumbled version of your website and not the one you've made for them. The biggest way to avoid the FOUC is putting the <link> to your stylesheet in the document's <head> tag. The older, less common way of avoiding it is using javascript to hide page elements until the styles can be loaded.
  
* Explain what ARIA and screenreaders are, and how to make a website accessible.
  * **ARIA (Accessible Rich Internet Applications)** is a set of HTML attributes to make web content more accessible to those with disabilities, such as people using screenreaders for webpages. It allows easier access to navigation, widgets, content, and other important landmarks. **Screenreaders** allow users with visual impairments to use computers, such as by taking a webpage's code and translating information into speech (TTS). It can also give information in Braille. This technology is now more common with computers today and therefore is a higher priority for developers who want their sites to be accessible. One of the best ways to use ARIA for better accessibility is simply assigning ARIA and role attributes to elements, which give more information about them to assistive technology so they're easier to use and manage. They can even be used in CSS targeting for more accurate styling, as their values can't be repeated and provide better CSS "hooks."

* Explain some of the pros and cons for CSS animations versus JavaScript animations.
  * [CSS animations](https://css-tricks.com/myth-busting-css-animations-vs-javascript/) are excellent for simple animations such as transitions, can be easily integrated into many current workflows, and are fast on most browsers. However, JavaScript animations are also fast, if not faster, when not using jQuery, give more control and flexibility for playback and effects, and have more old browser support. A [quick overview](https://developers.google.com/web/fundamentals/design-and-ui/animations/css-vs-javascript?hl=en) is that CSS animations are better for simple, straightforward animations; JavaScript animations are better for more advanced and controlled animations.
* What does CORS stand for and what issue does it address?

#### HTML Questions:

* What does a `doctype` do?
* What's the difference between standards mode and quirks mode?
* What's the difference between HTML and XHTML?
* Are there any problems with serving pages as `application/xhtml+xml`?
* How do you serve a page with content in multiple languages?
* What kind of things must you be wary of when design or developing for multilingual sites?
* What are `data-` attributes good for?
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
* What is progressive rendering?

#### CSS Questions:

1. What is the difference between classes and ID's in CSS?
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
* Describe Floats and how they work.
* Describe z-index and how stacking context is formed.
* Describe BFC(Block Formatting Context) and how it works.
* What are the various clearing techniques and which is appropriate for what context?
* Explain CSS sprites, and how you would implement them on a page or site.
* What are your favourite image replacement techniques and which do you use when?
* How would you approach fixing browser-specific styling issues?
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
* What are the different ways to visually hide content (and make it available only for screen readers)?
* Have you used or implemented media queries or mobile specific layouts/CSS?
* Are you familiar with styling SVG?
* How do you optimize your webpages for print?
* What are some of the "gotchas" for writing efficient CSS?
* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.
* How would you implement a web design comp that uses non-standard fonts?
* Explain how a browser determines what elements match a CSS selector.
* Describe pseudo-elements and discuss what they are used for. 
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
* List as many values for the display property that you can remember.
* What's the difference between inline and inline-block?
* What's the difference between a relative, fixed, absolute and statically positioned element?
* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
* Have you played around with the new CSS Flexbox or Grid specs?
* How is responsive design different from adaptive design?
* Have you ever worked with retina graphics? If so, when and what techniques did you use?
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?

#### JS Questions:

1. Explain event delegation
* Explain how `this` works in JavaScript
* Explain how prototypal inheritance works
* What do you think of AMD vs CommonJS?
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
  * What needs to be changed to properly make it an IIFE?
* What's the difference between a variable that is: `null`, `undefined` or undeclared?
  * How would you go about checking for any of these states?
* What is a closure, and how/why would you use one?
* What's a typical use case for anonymous functions?
* How do you organize your code? (module pattern, classical inheritance?)
* What's the difference between host objects and native objects?
* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
* What's the difference between `.call` and `.apply`?
* Explain `Function.prototype.bind`.
* When would you use `document.write()`?
* What's the difference between feature detection, feature inference, and using the UA string?
* Explain AJAX in as much detail as possible.
* Explain how JSONP works (and how it's not really AJAX).
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
* Explain "hoisting".
* Describe event bubbling.
* What's the difference between an "attribute" and a "property"?
* Why is extending built-in JavaScript objects not a good idea?
* Difference between document load event and document ready event?
* What is the difference between `==` and `===`?
* Explain the same-origin policy with regards to JavaScript.
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
1. Why is it called a Ternary expression, what does the word "Ternary" indicate?
* What is `"use strict";`? what are the advantages and disadvantages to using it?
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
* What is the extent of your experience with Promises and/or their polyfills?
* What are the pros and cons of using Promises instead of callbacks?
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
* What tools and techniques do you use debugging JavaScript code?
* What language constructions do you use for iterating over object properties and array items?
* Explain the difference between mutable and immutable objects.
  * What is an example of an immutable object in JavaScript?
  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?
* Explain the difference between synchronous and asynchronous functions.
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
