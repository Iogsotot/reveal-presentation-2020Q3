# Presentation about virtuas DOM


### Task description: https://github.com/rolling-scopes-school/tasks/blob/master/tasks/presentation.md
### Video: https://youtu.be/WHChNmbu9hk
### Slides: https://iogsotot-virtual-dom.netlify.app/
<hr></hr>


### Text:
#### Slide 0
Hello, everybody! My name is Anna and today I want to tell you about virtual DOM.  
#### Slide 1
What is DOM?
#### Slides 1.1 - 1.4
**Simple definition** – DOM – stands for Document Object Model. The key-word is Object, because DOM - It’s a way of   representing a structured document via   objects.
**Hard definition** - It is a cross-platform and language-independent convention for representing and interacting with data in HTML, XML, and others.  
#### Slides 2.1 - 2.3     
When we send HTML to the browser for rendering, the browser first parses that HTML and creates the DOM. Each tag from HTML turns into an object. All of these objects are collected together into a tree of objects. And based on these objects the browser creates visualization, what we are used to seeing when we open any page on the Internet. 
#### Slide 3
In the past, when developers were building mostly static applications, direct interaction with the DOM was a good way to write programs. 
But with the development of technologies and user needs, it became necessary to work with dynamically changing data that must be dynamically rendered into the page.
#### Slide 3.1
In order to draw a change in the DOM, the browser redraws all the objects on the page in general, this is such a time-consuming operation that it can be visible to the eye.
For example, the page can blink.

Of course, it was necessary to find a way to avoid such an expensive and inelegant behavior when changing data on a page.
#### Slides 3.2 - 3.3
The solution to exactly this problem was proposed by React - this solution was the virtual DOM, which allows you to implement control over DOM elements.
Now virtual Dom is used not only in React, but also in Vue.js.
#### Slide 4
Before we move on to a more detailed study of virtual Dom, it is necessary to say a few words about Shadow DOM, because sometimes these concepts get confused in people's heads. 
#### Slide 4.1
**Shadow DOM** – is used for encapsulation. Thanks to it, the component has its own "shadow" DOM tree, which cannot be simply accessed from the main document, it can have isolated CSS rules, etc.
Shadow DOM is a tool used to build component-based apps and websites. Shadow DOM doesn’t represent the whole Document Object Model, but it represents an element. 
#### Slide 4.2
 We can see it as a subtree or as a separate DOM for an element. Shadow DOM can be imaged like bricks from which the DOM is created.  
The main difference between DOM and Shadow DOM is how it’s created and how it behaves. Normally DOM nodes which we create are placed inside other elements.
In the case of Shadow DOM, we create a scoped tree, which is connected to the element but separated from the children elements. 
It’s called shadow tree and the element it’s attached to -  is called shadow host. 
Everything which we will add to Shadow DOM is local, even styles. It’s a very important point of Shadow DOM.
#### Slides 4.3 - 4.6
Let’s explain why Shadow DOM is so useful and what issues it solves. 
1) First of all, it isolates the DOM, so the DOM of the component is a separate element which won’t appear in a global DOM. 
2) Another issue it helps with is scoping of the CSS, which means styles created inside the single Shadow DOM element are isolated and stays in the scope of that Shadow DOM. It simplifies styling a lot, because we don’t have to worry so much about naming space and we can use simple selectors and class names. 
Also, we can think of the application as it is built from components and not as a one massive, global object. 
**Shadow DOM can affect the performance of the application.** There are a lot of performance issues while we want to manipulate the DOM, because every change will make a re-rendering of the whole object. In the case of Shadow DOM, the browser knows which part should be updated.
#### Slides 5 - 5.1
Differences between Shadow DOM and Virtual DOM
The only thing which is common for both is that they help with performance issues. Both create a separate instance of the Document Object Model; besides this, both concepts are different. Virtual DOM is creating a copy of the whole DOM object, and Shadow DOM creates small pieces of the DOM object, and each of these has their own, isolated scope for the element they represEnt.
#### Slides 6 - 6.1
How does virtual DOM work?
Virtual dom is an intermediate set of primitive objects, a simplified DOM clone. Changes to the Virtual DOM do not automatically redraw the DOM. Changes to the state of the component also do not cause the DOM to be redrawn, as is usually the case in native JS, 
Instead a new version of the virtual DOM is created (we remember that creating a VDOM is much easier and cheaper than creating a DOM). 
#### Slide 6.2
Before sending the changes of vdom for redrawing in the DOM, the framework performs the reconciliation procedure, essentially comparing the new and old objects and looking for differences between them. 
After finding a specific change, the framework accesses the DOM and makes point changes. Which, of course, wastes several times less resources than a complete redrawing of the DOM. This is a very quick and economical procedure. If no changes have occurred, then there is no need to redraw the DOM.
#### Slide 7
***Summary***
The virtual DOM (VDOM) is a programming concept where an ideal, or “virtual”, representation of an UI is kept in memory and synced with the “real” DOM by a library for example ReactDOM. This process is called reconciliation.

### Sources
 - https://reactjs.org/docs/faq-internals.html#what-is-the-virtual-dom
 - https://habr.com/ru/post/256965/
 - https://ichi.pro/ru/podozdite-react-eto-ne-virtual-naa-model-dom-198566713080451
 - https://www.freecodecamp.org/news/a-quick-guide-to-learn-react-and-how-its-virtual-dom-works-c869d788cd44/
 - https://vuejsfeed.com/blog/learn-the-differences-between-shadow-dom-and-virtual-dom
 - and other
