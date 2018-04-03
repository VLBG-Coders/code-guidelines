# JS Guidelines

Here are some general code guidelines which should be respected when coding on any project. The most important ones are listed here:

- Do not use JavaScript if you can solve your problem with CSS.  
- Think modular and try to make things reusable.
- If using plain javascript use namespaces for your code.
- Split your code up into standalone modules eg. newsletter.js, followus.js
- Use Functions docs: [JSDoc](http://usejsdoc.org/)
- Element selectors should always be `js-` prefixed.
- Avoid using ids as selectors if possible.
- Declare variables and constants on top of a block.

## 1 Function docs

Function docs are well known from other programming languages. For javascript use the [JSDoc](http://usejsdoc.org/) ruleset. This will help you to maintain the your code and it will help you and others to easily look over a function and see which parameters are required and what you expect it to return.

**Example**

```js
/**
 * This function returns a list of items by a given id.
 *
 * @params {String} id
 *
 * @returns {(Array|null)} 
 */
function getItemsById(id) {
    var items = this.itemsService.getById(id);
    
    if (items) {
        return items;
    }
    
    return null;
}
```

**Start types with a capital letter:**

- `String`
- `Number`
- `Boolean`
- `Array`
- `Object`

You can also use custom object types instead of `Object`. See also the [JSDoc types documentation](http://usejsdoc.org/tags-type.html).


## 2 Variables should be on top of a block

All variable declarations should be placed at the top of the block with one statement for each variable.

**Good Example**

```js
function() {
    var variableOne = 'string';
    var variableTwo = 'another string';
    var variableThree;

    // function implementation
}
```

**Bad Example:**

```js
function() {
    var variableOne = 'string',
        variableTwo = 'another string';
    createApiEntity();
    
    if (this.itemExists()) {
        this.doThat();
    }

    var variableThree;
    // function implementation
}
```

## 3 Prefix all selectors with `js-`

Have you ever had the problem, that you removed some html code and found yourself wondering why in hell some of your javascript is not working any more? This is a common error which occurs when refactoring html code. The reason is simple, someone who is editing the html often does not know that there is some javascript magic happening in for this code. The solution is for this is very simple: prefix all selectors with `js-`.

However there are some more things to keep in mind:

- Never ever add style for a `js-` class or id.
- As you should always think modular and reusable avoid using ids as selectors if they are not unique.
- Avoid event bindings to html elements without a selector class (eg all `a` tags)

**Bad example**  

```js
$('.my-class').hide();
$('.my-class').text('foo-bar');
$('.some-otherclass').show();
```

**Good example**  

```js
$('.js-my-selector-class').hide();
$('.js-my-selector-class').text('foo-bar');
$('.js-some-other-selector-class').show();
```