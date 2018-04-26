# General Guidelines

Here are some general code guidelines which should be respected when coding on any project. The most important ones are listed here:

- Only use English in your code.
- Use 4 whitespaces to indent your code.
- No function may be longer than 50 lines of code. If it is you really need to consider refactoring it to separate components.
- Do not let your lines get too long, break them after 120 characters.
- Make things reusable and modular.
- Readability goes first, you and others need to understand your code. Use Speaking function- and variable-names and clean indentation.
- Add a comment if things are unclear or could be understood wrong by others. Especially if you did not write the code yourself and had to figure its purpose out on your own.
- Use single quotes whenever possible.
- Remove unused code. No you wont use it some day in the future!
- TODO code must not be merged into develop or master branches. Either you do it, or you remove the comment.

## 1 Language to use in your code

**Recommended:** `English`

**Why should I do this?**

All variables, functions and all comments should be in **English**. Because you never know who is joining your project some day and you do not want to rewrite things later on.

## 2 Code indentations

**Recommended:** `4 Spaces`

**Why should I do this?**

The main goal is to be consistent within your project. No matter if you are working on a project as a lone soldier, or if you are part of a team. It is crucial to keep things consistent and make it easy for people to read your code and contribute to it.

The reason we recommend four spaces for indentation is not that simple. There are many different ways to indent your code. Some prefer 2 whitespaces, some even use tabs. However, what is the main goal you want to achieve when writing code? Correct, you want to have it without any bugs and you want to write code which is easy to read and understand so other people (and your future self) can easily understand it and participate. Overall, four spaces have shown to be a stable solution to achieve this.

## 2 Empty Line and whitespaces

- Avoid whitespaces at line endings or in empty lines.
- Never add more than one empty line or whitespace to seperate things.

## 3 Function complexity

**Recommended:** `50 lines`

**Why should I do this?**

What does make you happy when writing code? Yes, if you can reuse some or a lot of your code instead of writing it again in some way, or even worse, duplicate it as it is. To help you think in a modular way, you should keep your functions as simple as possible. Also you should sort your code within a controller or class from initially called functions to helper functions. This way you will be able to easily understand what your code is doing or what it was expected to do.

**Example:**

```js

function initController() {
    var items = getItemsFromApi();
    extendItemsByName(items);
    reportUsage();
}

function getItemsFromApi() {
    // There would be some fancy code here.
    return [];
}

function extendItemsByName(items) {
    // There would be some fancy code here.
    for (var i = 0; i < items.length; i++) {
        items.name = 'foo-' + i;
    }
}

function reportUsage() {
    // There would be some fancy code here.
    return true;
}
```

## 4 Line length

**Recommended:** `<= 120 characters`

**Why should I do this?**

Do not let your lines of code get too long. Keep in mind that code version tools for `git` like Github, Gitlab, Bitbucket will wrap the lines of code which makes it harder to review for other people. Also code is easier to read if you break it into smaller parts.

## 5 Readability for simplicity

There are many ways to reduce lines of code but this should never be done if the result is a reduction of the readability of your code. Especially when writing code wich will be compiled, minified and or uglified in order to release it. Programmers including yourself should easily be able to read and understand your code.

**Good Example:**

```js
var a = 0;
var c = 1;
var b = {
    "foo": 1,
    "bar": "dummy"
};

if (this.foo > 0) {
    return a + this.foo;
}
return a;

```

**Bad Example:**

```js
var a=0,
      b={"foo":1,"bar":"dummy"},
      c=1;
if b.foo > 0 ? return a + b.foo; : return c;
```

## 6 Quotation

**Recommended:** `'single quotes'`

**Why should I do this?**

Some languages like json, xml or html assume you use double quotes. However, in every other language you should use single quotes whenever possible. You will see once you start doing this, it is easier to read your code. Consistency is key for easy readability and creation of code throughout several languages. As you are probably reading thousands lines of code each day you do not want to focus on quotes but the important part - your code. Single quotes reduce the amount of characters you have to read. Also many big open source projects follow this convention.

**Example:**

Double Quotes:

```js
var foo = {
    "some": "value",
    "someOther": "value",
    "someMore": "value",
};

this.variable["some"]["property"] = "Foo";
```

Single Quotes:

```js
var foo = {
    'some': 'value',
    'someOther': 'value',
    'someMore': 'value',
};

this.variable['some']['property'] = 'Foo';
```

## 7 Comments

**Dos**

- Add comments to your code if it is not fully clear what and why things are done.
- Add function docs to describe parameters and return values. (eg. [JSDoc](http://usejsdoc.org/) or [phpDoc](https://www.phpdoc.org/))
- Start comments with a capital letter and add a dot at the end, if it is a full sentence.

**Don'ts**

- Do not comment out code. Yes, you might need it some day, but this is the wrong place to store it. Remove unused code from your projects.

### 7.1 Single line comments

**Recommended:** ```//```

- Use ```//``` to comment a single line. Also add a whitespace after the ```//```.
- Add comments in front of the line you want to comment.
- Avoid adding comments next to code lines.
- Avoid adding comments inline the code lines.

**Good Example:**

```php
private function foo()
{
    // This is needs to be set on a default value.
    $foo = 'bar';
}
```

**Bad Example:**

```php
private function foo()
{
    $foo = 'bar'; // dont do this.
}

private function fooFoo()
{
    $foo = 'bar';
    // This line do that
}
```

### 7.2 Multi line comments

**Recommended:** ```/** */```

- Use multi line comments for function or class documentations.

**Example:**

```php
/**
 * This function does the magic.
 *
 * @returns string
 */
private function foo()
{
    // This is needs to be set on a default value.
    $foo = 'bar';

    return $foo;
}
```

## 8 File Names

Each programming language has its special rules or best practices in how you should name your files. For example in php you would write controller files of a symfony project in camelcase. However there are some rules which can be recommended for the rest of the files:

- Respect the guideline of the programming language you use.
- Never ever use whitespaces in file names.
- Use lowercase characters only if possible.
- Avoid underscores and use hyphens instead.

## 9 Translations

Translation keys are very important because they seem to be everywhere in your project. As there are so many translation tools out there it is hard to define specific rules for them. Just keep one thing in mind: Keep it simple and clean!

- Your translation key should be self explanatory as they are part of the code.
- Try to cluster them in namespaces to make them reusable. (eg. `general_headline`, `general_subheadline`, `input_firstname`, `input_lastname`...)
- Translation keys should be lowercase.
- Translation keys should be seperated with underscores or dots. Avoid using hyphens..
