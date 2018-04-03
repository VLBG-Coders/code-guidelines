# CSS Guidelines

Here are some general code guidelines which should be respected when coding on any project. The most important ones are listed here:

- Avoid using plain css. Use [less](http://lesscss.org/) or [sass](https://sass-lang.com/) instead.
- Do not use the id attribute for styling.
- Classes and ids should be in lowercase.
- Only use hyphens in class and id names and avoid underscore and camel case.
- Think modular and generic in order to reuse your code.
- Split up your code into multiple files containing a single topic eg. forms.less, tablet.less, dashboard.less.

## 2 Coding Standards

- Classes and ids: lowercase, hyphens, no underscores.  
- Do not name classes as the templates they are for.  
- Add a single space after the selector.  
- Add an empty line before every selector except if the selector is the first child.  

## 3 Nesting and Structure

- Max nesting level: 3.  
- Do not structure your file like the div structure of your final HTML.  
