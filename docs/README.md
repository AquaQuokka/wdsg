
# WDSG: The Web Development Style Guide

#### 1
Use lowercase letters for all HTML tags and attributes, except for special cases where uppercase letters are required (e.g. DOCTYPE).

#### 2
Use double quotes (`"`) for all HTML attribute values.

#### 3
Indent all child elements with 4 spaces or 1 tab character, but do not use these interchangably.

#### 4
Group tags of the same name, and tags of similar names, unless they function differently, or if one contains text and the other does not contain text.

#### 5
Indent each child codeblock with a single line on the top and bottom before adding child elements.

#### 6
If a tag contains text that is not an attribute that spans over multiple lines, then it must be indented with a single line on the top and bottom, and must be indented with 4 spaces or 1 tab inwards. However, if it contains text that is not an attribute but spans over only one line, then it must stay on the same line as the tags that surround it, and must be indented with 1 space on each side of the text, between the text and the tags that surround it.

E.g.

```html
<!DOCTYPE html>
<html lang="en">

    <head>

        <link rel="preload" href="..." as="document">

        <link rel="preload" href="..." as="style">

        <link rel="preload" href="..." as="script">

        <script type="text/javascript" src="..."></script>
        <script type="text/javascript" src="..."></script>
        
        <link type="text/css" rel="stylesheet" href="...">
        <link type="text/css" rel="stylesheet" href="...">

    </head>


    <body>

        <h1> ... </h1>

        <div class="..."></div>

        <div class="..."> ... </div>

        <div class="...">

            ...
            ...

        </div>

    </body>

</html>
```


#### 7
Use semantic HTML where possible. For example, use `<nav>` instead of `<div class="nav">` or `<article>` instead of `<div class="article">`.

#### 8
Use descriptive but concise names for your classes and IDs. Avoid using single letters or abbreviations that may not be obvious to others.

#### 9
Include `alt` attributes for all `<img>` tags, and provide meaningful descriptions of the image, so that your page is accessible to everyone.

#### 10
Use the `type` attribute for all `<script>`, `<style>`, and `<link>` tags.

#### 11
Use `utf-8` encoding, as this is the standard HTML encoding across the web.

#### 12
Avoid using `while` loops in your JavaScript, as this can cause browser performance issues or hanging.

#### 13
Avoid using inline styles and scripts, as this makes your website harder to debug and read.Instead, use a separate `.css` file containing your styles, and use a `<link>` tag in your `<head>`. For scripts, use a separate `.js` file containing your JavaScript scripts, and use a `<script>` tag in your head or after the rest of your page, but before the `</html>` tag.

E.g.

Wrong:

```html
<!DOCTYPE html>
<html lang="en">

    <body>

        <p style="color: red;">

            This paragraph has inline styles applied to it. Don't do this!

        </p>


        <button onclick="alert('This button uses inline scripting. This is not recommended.')">Click me!</button>

    </body>

</html>
```


Good, but not recommended:

```html
<!DOCTYPE html>
<html lang="en">

    <head>

        <style>

            #para1 {
                color: red;
            }

        </style>
    
    </head>


    <body>

        <p id="para1">

            This paragraph doesn't use inline styles. However, it uses script tags, which is only slightly better. You should always use a separate `.css` file containing your styles.
        
        </p>

        
        <button onclick="buttonClick()"> Click me! </button>

        <script>

            function buttonClick() {

                alert("This button uses <script> tags. This is only slightly better. You should always use a separate .js file containing your scripts.");

            }

        </script>

    </body>

</html>
```


Correct:

`index.html`:

```html
<!DOCTYPE html>
<html lang="en">

    <head>

        <link type="text/css" rel="stylesheet" href="index.css">
    
    </head>


    <body>

        <p id="para1">

            This paragraph is using a separate file for styling. You should do the same.
        
        </p>

        
        <button onclick="buttonClick()"> Click me! </button>

        <script type="text/javascript" src="index.js"></script>

    </body>

</html>
```


`index.css`:

```css
#para1 {
    color: red;
}
```


`index.js`:

```js
function buttonClick() {
    alert("This button uses a separate file for scripting. You should do the same.");
}
```

#### 14
Your primary `.html` file should always be called `index.html`. This is because when a browser navigates to a webpage, it will always display the content from the `index.html` file.

#### 15
Use a separate `.css` file for each `.html` file in your website. This is because this allows each `.html` file to have different styles.

#### 16
Your `.css` file should always have the same name as the file that it provides styles for, but with a `.css` extension instead of a `.html` extension. This is because it makes it easier to tell which styles are for which page.

#### 17
Don't call your `.js` file `script.js`. This is because it doesn't describe what the script does. If you use the same script across mutliple pages, call it `core.js` instead. If you have different scripts for different pages, give it the same name as the page that it provides scripting for, but with a `.js` extension instead of a `.html` extension.

#### 18
If you use multiple JavaScript files for the same page, or multiple pages with multiple scripts, then make sure that each script has a descriptive and concise name. This makes it clear what each script does.

#### 19
Use the correct HTML element/tag for the content that is being served. For example, use `<h1>` for top-level headings, and use `<p>` for paragraphs.

#### 20
Use the `title` attribute to provide additional information about an element, such as a tooltip or a longer description. However, note that this is visible to everyone who uses the page. This is not to be confused with the `<title>` element/tag.

#### 21
Use classes and IDs for their specific use-cases. Only use classes for elements that require the same styling or scripting, since classes can be used on more than one element. Only use IDs for a single element.

#### 22
Avoid using deprecated HTML elements and attributes where possible. Use CSS instead of `<center>` where possible. Only use non-semantic HTML elements where the CSS/JS alternative is much harder to implement. E.g. `<marquee>` is acceptable, but is not recommended to use in most cases.

#### 23
Specify a language for your HTML pages. This can be achieved by using the `lang` attribute of the `<html>` tag.

E.g.

```html
<!DOCTYPE html>
<html lang="en">

    ...

</html>
```

#### 24
Use shorthand properties where possible to reduce the amount of code that you need to write. For example, use `padding: 10px 20px 10px 20px` instead of `padding-top: 10px; padding-right: 20px; padding-bottom: 10px; padding-left: 20px;`.

#### 25
Use relative units such as `em` and `rem` instead of `px` or `pt` where possible. This will make your page more responsive to changes in screen size and font size.

#### 26
Use CSS preprocessors such as SCSS or LESS to make your CSS code more modular and easier to maintain.

#### 27
Add comments to your HTML, CSS and JavaScript code. This makes it easier to understand how your code works.

#### 28
Avoid using `!important` in your CSS code, as it can make your code harder to maintain and override.

#### 29
Don't use overly vibrant colors in your CSS code, as it can make your page ugly and hard to read, which overall degrades the user experience.

#### 30
Add scripts into the `<head>` instead of after all other HTML elements where possible, as it is a more organized way to import scripts. However, this is not possible with all scripts, so make sure that your scripts are being imported properly.

#### 31
Don't use variables to define functions, except for cases where it is required, for example the `window.onload` event function.

E.g.

Wrong:

```js
alertBox = function() {
    alert("Hello, world!");
};
```

Correct:

```js
function alertBox() {
    alert("Hello, world!");
};
```


#### 32
Don't use unnamed functions in your JavaScript code, as it makes your code harder to read.

Wrong:

```js
window.onload = () => {
    alert("Hello, world!");
};
```

Correct:

```js
window.onload = function() {
    alert("Hello, world!");
};
```


#### 33
Don't assign styles to elements, except for cases where it is required. Instead, assign styles to specific classes or IDs, as they are separate from root elements.

#### 34
Do not assign IDs or classes to the `<head>` or `<body>` elements/tags, as they are very important tags. Instead, create a separate `<span>`, `<p>`, or `<div>` element/tag with an ID/class.

E.g.

Wrong:

`index.html`:

```html
<!DOCTYPE html>
<html lang="en">

    <body>

        Hello, world!

    </body>

</html>
```


`index.css`:

```css
body {
    background-color: red;
}
```

Correct:

`index.html`:

```html
<!DOCTYPE html>
<html lang="en">

    <body>

        <div id="red-body">

            Hello, world!

        </div>
    
    </body>

</html>
```


`index.css`:

```css
#red-body {
    color: red;
}
```


#### 35
Do not use words that are keywords in HTML, CSS, or JavaScript as IDs or class names. This can make your code harder to read and build upon.

#### 36
Link internal functions where possible. This allows better understanding of what each function does. This also allows you to call functions that are used internally.

E.g.

```js
function showMessage() {
    alert("Hello, world!");
};

window.onload = showMessage;
```

However, it is worth noting that there are some cases where using an unnamed function is appropriate, such as with immediately-invoked function expressions (IIFE). In these cases, using a named function would not make sense, as the function is only intended to be used once and immediately discarded.


#### 37
Always validate user input to avoid security vulnerabilities and errors in your code.
Without proper validation, user input can lead to security vulnerabilities, such as SQL injection, cross-site scripting (XSS), and command injection.

#### 38
Never validate user input on the client-side. Use a server-side approach for secure authentication.
Client-side validation means that user credentials, such as passwords and/or tokens, are validated in the user's web browser. This approach is insecure because it exposes the authentication logic and secrets to the client-side, making you and your client vulnerable to attacks such as code injection.

#### 39
Implement rate limiting to prevent brute-force attacks on login pages and other sensitive areas of your website/app.

#### 40
Encrypt sensitive data, such as credit card information and personal identification numbers (PINs), both in transit and at rest.




Well done! You've reached the end of the guidelines! These guidelines will expand, so make sure to check back regularly.

#### End