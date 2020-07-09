# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)  SOFTWARE ENGINEERING IMMERSIVE

## Dom Manipulation w/ Forms

### The Text Input

Mouse (and other various) keyboard events are a good first attempt to process user interactions and update the DOM in process, but there are many more and potentially richer methods at our disposal.  _Input_ tags are one of these methods.

Perhaps the most commonly recognized is the "text" input:

```html
<input type="text" />
```

Notice that it is a self-closing tag.  It has no children or inner content exposed directly.  Text inputs manage the state of the text inside them automatically.  Forms can manage several inputs, text or others, using the `name` attribute on the element, but for now let's just extract the value of the input with javascript.

```js
const input = document.querySelector('input');
const value = input.value;
```

The `input` element returned by `querySelector` includes a `value` property that can either be read or updated:

```js
input.value = 'doggo';
console.log(input.value);
```

All we need is a button or click event to trigger some code to fetch the value out of the input and then perform a given action with it, e.g., creating a new element and appending it to the DOM.

##### Mini-Exercise

Let's write up a form with a text input and a button:

- Create a ```<form></form>``` element.
	- All form attributes are optional. You can build a form without the ```<form>``` tag just using ```inputs``` and ```buttons``` but you won't have access to some features specifically designed for ```forms```.
	- Forms have a built-in action attribute that causes forms to reload a page, and the reason we often have to use ```preventDefault()``` when submitting data. If you decide to build a form without using ```<form>``` tags then you won't need ```preventDefault()``` later on. 

- Add a text input to the html: `<input />`. Notice how this tag is self closing.
	- ```inputs``` have have a ```type``` attribute. The most common is ```text```.
	- The ```value``` attribute keeps track of the content (or state) inside the input field. This will be very important later.
- Add a ```<button></button>```
	- Inside a form, a ```button``` and an ```<input type='submit'>``` can be used almost interchangeably. If you use a submit input for this exercise, be sure to assign it a specific class or ID so we can destinguish between inputs later on with JavaScript. In this instance, we'll add a type of "submit" to our button.
- For good measure, let's create a ```<section>``` tag. This is where our to-do list will be rendered, so let's give it an id name 'todo-list'. Within this section tag, we'll put a list tag (you can choose ordered or unordered list).

Now let's jump into the our JS file:

- Query select for all of the elements we just created (form, button, list). Remember, if you used a submit input instead of a button, you'll need to grab your inputs by ID or class, not by tag name.


#### Add a Todo

Register a click event listener on the ```button``` or ```submit```. This click needs to call a function that should:
- prevent a page refresh
- create a list item
- create a paragraph tag
- extract the value of the text input
- append the paragraph tag to the list item
- add the value to the `todo list` 
- For good measure let's reset the value of our text input on the click event function as well.

If we've done this correctly, all items we enter into the input field should appear on the page!

#### Bonus

Try to add an additional button for deleting a Todo.
