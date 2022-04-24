## JSX

### What is JSX ?

JSX is a syntax extension to JavaScript that allows you to wirte a HTML inside the javascript.

- JSX stands for JavaScript XML.

- JSX allows us to write HTML in React.

- JSX makes it easier to write and add HTML in React.

## DOM

The Document Object Model (DOM) is a cross-platform and language-independent interface that treats an XML or HTML document as a tree structure wherein each node is an object representing a part of the document. The DOM represents a document with a logical tree. Each branch of the tree ends in a node, and each node contains objects. DOM methods allow programmatic access to the tree; with them one can change the structure, style or content of a document.[2] Nodes can have event handlers attached to them. Once an event is triggered, the event handlers get executed

### Updating the Rendered Element

React elements are immutable. Once you create an element, you can’t change its children or attributes. An element is like a single frame in a movie: it represents the UI at a certain point in time.

### React Only Updates What’s Necessary

React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.
