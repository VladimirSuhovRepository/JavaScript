<pre><b>Summary</b></pre>
Given a DOM node, we can go to its immediate neighbours using navigation properties.

There are two main sets of them:

For all nodes: parentNode, childNodes, firstChild, lastChild, previousSibling, nextSibling.
For element nodes only: parentElement, children, firstElementChild, lastElementChild, previousElementSibling, nextElementSibling.
Some types of DOM elements, e.g. tables, provide additional properties and collections to access their content.


Summary
There are 6 main methods to search for nodes in DOM:

Method	Searches by...	Can call on an element?	Live?
getElementById	id	-	-
getElementsByName	name	-	✔
getElementsByTagName	tag or '*'	✔	✔
getElementsByClassName	class	✔	✔
querySelector	CSS-selector	✔	-
querySelectorAll	CSS-selector	✔	-
Please note that methods getElementById and getElementsByName can only be called in the context of the document: document.getElementById(...). But not on an element: elem.getElementById(...) would cause an error.

Other methods can be called on elements too. For instance elem.querySelectorAll(...) will search inside elem (in the DOM subtree).

Besides that:

There is elem.matches(css) to check if elem matches the given CSS selector.
There is elem.closest(css) to look for the nearest ancestor that matches the given CSS-selector. The elem itself is also checked.
And let’s mention one more method here to check for the child-parent relationship:

elemA.contains(elemB) returns true if elemB is inside elemA (a descendant of elemA) or when elemA==elemB.

Summary
Each DOM node belongs to a certain class. The classes form a hierarchy. The full set of properties and methods come as the result of inheritance.

Main DOM node properties are:

nodeType
We can get nodeType from the DOM object class, but often we need just to see if it is a text or element node. The nodeType property is good for that. It has numeric values, most important are: 1 – for elements,3 – for text nodes. Read-only.
nodeName/tagName
For elements, tag name (uppercased unless XML-mode). For non-element nodes nodeName describes what it is. Read-only.
innerHTML
The HTML content of the element. Can be modified.
outerHTML
The full HTML of the element. A write operation into elem.outerHTML does not touch elem itself. Instead it gets replaced with the new HTML in the outer context.
nodeValue/data
The content of a non-element node (text, comment). These two are almost the same, usually we use data. Can be modified.
textContent
The text inside the element, basically HTML minus all <tags>. Writing into it puts the text inside the element, with all special characters and tags treated exactly as text. Can safely insert user-generated text and protect from unwanted HTML insertions.
hidden
When set to true, does the same as CSS display:none.
DOM nodes also have other properties depending on their class. For instance, <input> elements (HTMLInputElement) support value, type, while <a> elements (HTMLAnchorElement) support href etc. Most standard HTML attributes have a corresponding DOM property.

But HTML attributes and DOM properties are not always the same, as we’ll see in the next chapter.
