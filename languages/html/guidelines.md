# HTML Guidelines

Here are some general code guidelines which should be respected when coding on any project. The most important ones are listed here:

- Inline elements should never contain block elements like: `<a href=""><div>foo</div></a>`
- Move the content of an element into a new line.
- Split HTML statements with more than 120 characters to multiple lines
- Avoid self closing tags.
- Avoid inline styling.
- It is recommended to sort your attributes in the following order: id, tag specific attributes (eg href), class.

## 1 Html content goes into a new line

As html code can get really wild once in a while you should keep it as clean as possible. Therefore split your code up and move the content of an html element into a new line. Beside a better readability this gives you an other big advantage when using `git`. Lets say you change the translation key within an element and create a new pull request. If your code is all in the same line everything will be marked as changed in the pull request. The reviewer will have to read carefully to see the actual change. This is no problem for a small single line change but imagine you have to change 15 files and have 20 occurrences in each? 

**Good Example:**

```html
<div class="my-component">
    <div class="my-component-holder">
       <button type="button" class="btn">
           <span class="icon"></span>
           Click Me
        </button>
    </div>
</div>
```

**Bad Example:**

```html
<div class="my-component">
    <div class="my-component-holder">
       <button type="button" class="btn"><span class="icon"></span>Click Me</button>
    </div>
</div>
```

## 2 Multiline HTML statements

Break HTML statements with > 120 characters. Use the position of the first attribute as indention base.

```html
<div id="my-very-longid"
     class="many classes needed for styling"
     data-foo="bar"
     data-foo-bar="foo-bar">
    <div>Next element</div>
    <div>Next element</div>
</div>
```

## 3 Self closing tags

Only use self closing tags with the following elements:

- `<br />`
- `<col />`
- `<embed />`
- `<hr />`
- `<img />`
- `<input />`
- `<keygen />`
- `<link />`
- `<menuitem />`
- `<meta />`
- `<param />`
- `<source />`
- `<track />`
- `<wbr />`

## 4 Attribute Order

**General Order**

- `id`
- tag specific attributes (`href`, `src`, `alt`, `title`, `type`, `value`, `for`, etc)
- `class`
- `style`
- datasets (`data-test`, data-..., etc.) and others

**Examples**

```html
<a id="my-id" href="#" title="Link Title" class="link" data-foo="bar">
<input id="my-id" type="text" value="Text" class="link" data-foo="bar">
<label id="my-id" for="field-id" class="link" data-foo="bar">
<img id="my-id" src="#" alt="Link Text" class="link" data-foo="bar">
<iframe id="my-id" src="#" class="link" data-foo="bar">
```
