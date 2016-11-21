#Interview Questions: Full Stack

- Ice breaker question: Why are Man Hole Covers round? 

or

- Can you estimate how many Commercial Aircraft are in flight around the Earth right now?
	- How would you go about making this estimation?

Note: because this may be a culturally specific question you may have to illustrate and explain (via Google Images) what a Man Hole Cover is.

Tip: look for enthusiam in attempting to answer, indicative of a passionate problem solver. Also look for individuals that make no attempt at providing an answer or candidates that give up easily.

Potential Answers: They are round because they are typically heavy and may require to be rolled into place. Round covers can not fall into the drain. 

##Internet

1. Imagine you are sitting in front of a browser and you type the address www.facebook.com and press return in the URL bar.

Explain all the steps required for the browser to display the resulting page from the Internet, in as much detail as you feel comfortable with.

Answer: e.g. TCP/IP (Packets, Frames, Checksum), IP Address, Address Translation (converting domain to IP address), HTTP (Handshake, headers, request, response, GET), DNS Lookup, DNS Entries, Facebook Servers (Edge Cache, CDN, Load Balancers), HTTP Response, Cache Expiry, E-Tags, Transfer Encoding, Mime-types, HTML (Text), Browser Parsing (CSS, JS, HTML), Resource Loading and Parallelisation of downloads (different in each browser), JavaScript parsing and execution - Abstract Syntax Tree (AST), Critical Render Path, Blocking vs Non Blocking of Rendering (e.g. Scripts at bottom of page - because they don't block rendering on load), browser Re-flow and Redrawing (typically when paddings or margins are set or when element widths are queried in JavaScript), DOMContentLoaded and Page Load events.

2. Explain the difference between a HTTP GET and POST. 

Answer: 

3. What is REST?

Answer: Representational State Transfer. In API Design HTTP Verbs (GET, PUT, POST, DELETE, PATCH) are used in order to support CRUD operations with clear named paths to 'resources' within a Web Application made available through URL Paths. Bonus: In regard to REST HTTP Verbs - Read operations are performed by a HTTP Get, destructive operations (that alter Application State) like save / remove are performed by a HTTP POST, PUT or DELETE.

	GET 	- Equivalent to CRUD "Read". GET is read only and used to access a resource.
	PUT* 	- Equivalent to CRUD "Update". PUT is idempotent. Putting the same data multiple times to the same resource, should not result in different resources. 
	POST*	- Equivalent to CRUD "Create". POSTing to the same resource can result in the creation of multiple resources. 
	PATCH 	- can be used to update partial resources.
	DELETE  - to remove a resource

* PUT and POST can be used interchangably to create / update resource.

##HTML

4. What is HTML?

Answer: Hyper Text Markup Language. Tag based instructions that provide structure and meaning to a HTML document, that can be styled in CSS and have behaviour applied via JavaScript. Typical Markup Patterns for HTML5 include: header, footer, aside, article, nav etc.

5. What is a browser doctype?

Answer: browser doctypes are used to indicate which parsing and rendering model to apply to a page. Typically examples of a doctype are XHTML and HTML5. We now have a standardised renderer for HTML5 documents, previously this did not exist which resulted in many problems with page rendering. HTML5 includes a 'minimal doctype' because no human could remember how to manual type out a typical XHTML (Strict or Transitional) doctype.

6. What is Semantic HTML?

Answer: Semantic HTML is the use of the correct HTML tags that convey the correct meaning (Semantics) for the page element you are 'Marking Up'. For example, a list of product should be coded using a HTML list element, a list of search results should be coded using a HTML ordered list. HTML5 now provide a larger vocabulary of HTML Semantics. Bonus: Tim Berner's Lee gave a talk 20 years ago on the Semantic Web describing how standardised approaches to coding HTML can create a Database of human knowledge on the Internet, essentially increase interoperability and the ability for 'machines' to understand the meaning of content. This vision never happened because most Web developers ignore Semantic HTML. Tim created another Web technology to achieve his vision, called RDF and RDFa. Bonus: for mentioning Plain Old Semantic HTML (POSH).

##CSS

7. What is the difference between an ID and a Class?

Anwser: IDs are unique identifiers and should not be repeated. Modern CSS practices say no styles should be applied to IDs (e.g. OOCSS and BEM). Bonus: In HTML5 IDs can start with a number (according to the spec), previously IDs had to start with an Alpha character. Classes are 'Classification', which support 'CSS hooks' into elements for styling.  Multiple, repeated classes are permitted. Bonus: Modern practices (e.g. BEM) encourage we follow a naming convention decribing what component the CSS is on and what it does.

8. What is CSS specifity?

CSS declarations typically include refereces to parent and child elements, the more detailed this list of 'targetted' elements the more specific the selector, which allows styles to be overideen. Bonus: IDs have a high specifity and are very difficult to override (hence the new recommendation not to use them for styling). Inline styles overidde imported CSS. Note: the use of CSS '!important' is an anti-pattern.

9 What is CSS3?

Answer: CSS3 provides a new set of styling and animation options not previously available which includes:

	- transform3d to support the display of 3D objects like Cubes and Polygons
	- flexbox for more adaptive fluid layout control
	- nth-child pseudo class selector for greater selector control
	- CSS calc for greater selector control and pre-computation without the need of a CSS transpiler.


##JavaScript

10. How do you rate your JavaScript knowledge from 1 to 10?

Answer: This exploits the Dunning Kruger effect, where inexperienced individuals will over estimate their skills (typically in the high 9 - 10 range). Referred to a "Illusiory Superiority". This question can be a good filter for how junior / midweight a candidate really is.  Experienced developers typically rate their skills in the 6 - 8 range, because they are very aware of what they don't know and how quickly technology is moving forward.

11. What are the 4 Principles of Object Orientation?

Answer: The 4 Principles of Object Orientation are:

	11.1 Abstraction
	This is used to manage complexity. For example software developers use abstraction to decompose complex systems into smaller components (reducing complexity) by hiding implementation details.

	11.2 Encapsulation
	Hiding of data implementation by restricting access to an object, typically through explicit interfaces. Bonus: The Revealing Module Pattern allows JavaScript to handle encapsulation within Modules via it's return statement where all Public members are 'exported'.

	11.3 Inheritance
	Objects can relate to each other with either a “has a”, “uses a” or an “is a” relationship. Prototypal inheritence provides a similar feature in core JavaScript. Bonus: Classes have been introduced in ES6. Bonus: if "Favour Composition over Inheritence" is mentioned.

	11.4 Polymorphism
	Polymorphism manifests itself by having multiple methods all with the same name, but slightly different functionality. Bonus: Unlike Java, JavaScript does not support Polymorphism.


12. Can you explain what a JavaScript Closure is?

Answer: a function that maintains the execution context (of code execution) after the block is excited. Essentially holding on to variables within the function. Hidden costs are they hold on to memory and do not get garbage collected unless specifically de-referenced. Also in older version of Internet Explorer Closures created Memory Leaks.

10. Can you explain what variable hoisting is in JavaScript?

Answer: For example, JavaScript does not have block scope in For Loops, when variables are defined in For Loops they will be hoisted out of the declaration within the scope of the function they exist within. This can create subtle collisions, especially if multiple loops are used and the variable names are re-used. Bonus: Function Assignments vs Function Declarations have different effects in regard to hoisting.

11. Can you explain what JSONP is?

Answer: JSONP (JSON with Padding), essentially abuses how a script tag loads JavaScript and allows JavaScript from another domain to supply data into a Web Application (avoiding Cross Domain restrictions). Typically a callback function is provided allowing the requestor to make use of data / functionality from the external site.  Bonus: this is now considered a serious XSS vector and security risk. Cross Origin Request Sharing (CORS) is now recommended instead.

12. Explain why the following doesn't work as an IIFE: 

function() { 

}();

12.1 What needs to be changed to properly make it an IIFE?

Answer: Immediately Invoking Function Expressions require an evaluation typically via parenthesis in order to invoke e.g.

(function() {
	console.log('IIFE');
}());

Bonus: you can also do this (if you're a Twitter Front End 'Hypster' developer):

!function() {
	console.log('IIFE');
}();

Bonusx2: if you can explain how the above works.

13. Why is extending built-in JavaScript objects not a good idea?

Answer: Modifying built-in JavaScript objects often results in difficult and hard to trace errors. By altering foundational aspects of JavaScript you can introduce unexpected results in-consistent with the original API design by the browser vendor.  For example, by adding new properties to the prototype of an Array you can create problems for certain types of object enuneration, where the additional properties will also become enumerated depending on the method used.

14. Describe what an Isomorphic or Universal Application in JavaScript is?

Answer: 

15. What would you consider to be your strengths?

Tip: look for honest self appraisal and signs of over confidence

16. What would you consider to be your weaknesses?

Tip: Look for honest answers and an indication of self awareness

Debugging
