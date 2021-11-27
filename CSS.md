# CSS 
⏮️ [HTML](#)


- CSS is used to customize the appearance of a website.
- While we’re just getting, started, we can add a style attribute to any HTML element in order to apply some CSS to it.
- We change style by altering the CSS properties of an element, writing something like `color: blue` or `text-align: center`
- In this example below, we make a slight change to our very first file to give it a colorful heading:
```

    <!DOCTYPE html>
    <html lang="en">
        <head>
            <title>Hello!</title>
        </head>
        <body>
            <h1 style="color: blue;">A Colorful Heading!</h1>
            Hello, world!
        </body>
    <html>
![blue heading](https://cs50.harvard.edu/web/2020/notes/0/images/style0.png)
```
- If we style an outer element, all of the inner elements automatically take on that style. We can see this if we move the styling we just applied from the header tag to the body tag:
```

    <!DOCTYPE html>
    <html lang="en">
        <head>
            <title>Hello!</title>
        </head>
        <body style="color: blue; text-align: center;">
            <h1 >A Colorful Heading!</h1>
            Hello, world!
        </body>
    <html>
![blue everywhere](https://cs50.harvard.edu/web/2020/notes/0/images/style1.png)
```
- While we can style our web page as we’ve done above, to achieve better design, we should be able to move our styling away from the individual lines.
    - One way of doing this is to add your styling between `<style>` tags in the `head`. Inside these tags, we write which types of elements we want to be style, and the styling we wish to apply to them. For example:

```
      <html lang="en">
      <!DOCTYPE html>
      <head>
          <title>Hello!</title>
          <style>
              h1 {
                  color: blue;
                  text-align: center;
              }
          </style>
      </head>
      <body>
          <h1 >A Colorful Heading!</h1>
          Hello, world!
      </body>
      </html>
 ```   
    - Another way is to include in a `<link>` element in your `head` with a link to a styles.css file that contains some styling. This means the HTML file would look like:

```
      <html lang="en">
      <!DOCTYPE html>
      <head>
          <title>Hello!</title>
          <link rel="stylesheet" href="styles.css">
      </head>
      <body>
          <h1 >A Colorful Heading!</h1>
          Hello, world!
      </body>
      </html>
      
```
- And our file called `styles.css` would look like:
```

      h1 {
          color: blue;
          text-align: center;
      }
 ```
- There are far too many CSS properties to go over here, but just like HTML elements, it’s typically easy to Google something along the lines of “change font to blue CSS” to get the result. Some of the most common ones though are:

```
- `color`: the color of text
- `text-align`: where elements are placed on the page
- `background-color`: can be set to any color
- `width`: in pixels or percent of a page
- `height`: in pixels or percent of a page
- `padding`: how much space should be left inside an element
- `margin`: how much space should be left outside an element
- `font-family`: type of font for text on page
- `font-size`: in pixels
- `border`: size type (solid, dashed, etc) color
```

- Let’s use some of what we just learned to improve upon our oceans table from above. Here’s some HTML to start us off:

```
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <title>Nicer Table</title>
        </head>
        <body>
            <table>
                <thead>
                    <th>Ocean</th>
                    <th>Average Depth</th>
                    <th>Maximum Depth</th>
                </thead>
                <tbody>
                    <tr>
                        <td>Pacific</td>
                        <td>4280 m</td>
                        <td>10911 m</td>
                    </tr>
                    <tr>
                        <td>Atlantic</td>
                        <td>3646 m</td>
                        <td>8486 m</td>
                    </tr>
                </tbody>
            </table>
        </body>
    <html>
![table bad](https://cs50.harvard.edu/web/2020/notes/0/images/table0.png)
```

- The above looks a lot like what we had before, but now, either by including a `style` tag or a `link` to a stylesheet in the head element, we add the following css:

```
    table {
        border: 1px solid black;
        border-collapse: collapse;
    }
    
    td {
        border: 1px solid black;
        padding: 2px;
    }
    
    th {
        border: 1px solid black;
        padding: 2px;
    }
```
Which leaves us with this nicer-looking table:

![table good](https://cs50.harvard.edu/web/2020/notes/0/images/table1.png)

- You may already be thinking that there’s some needless repetition in our CSS at the moment, as `td` and `th` have the same styling. We can (and should) condense this down to the following code, using a comma to show the styling should apply to more than one element type.
```

    table {
        border: 1px solid black;
        border-collapse: collapse;
    }
    
    td, th {
        border: 1px solid black;
        padding: 2px;
    }
```

- This is a good introduction into what are known as [CSS selectors](https://www.w3schools.com/cssref/css_selectors.asp). There are many ways to determine which HTML elements you are styling, some of which we’ll mention here:
    - **element type**: this is what we’ve been doing so far: styling all elements of the same type.
    - **id**: Another option is to give our HTML elements an id like so: `<h1 id="first-header">Hello!</h1>` and then applying styling using `#first-header{...}` using the hashtag to show that we’re searching by id. Importantly, no two elements can have the same id, and no element can have more than one id.
    - **class**: This is similar to id, but a class can be shared by more than one element, and a single element can have more than one class. We add classes to an HTML element like this: `<h1 class="page-text muted">Hello!</h1>` (note that we just added two classes to the element: `page-text` and `muted`). We then style based on class using a period instead of a hashtag: `.muted {...}`


- Now, we also have to deal with the problem of potentially conflicting CSS. What happens when a header should be red based on its class but blue based on its id? CSS has a specificity order that goes:
    1. In-line styling
    2. id
    3. class
    4. element type
- In addition to the comma for multiple selectors, there are several other ways to specify which elements you would like to style. This table from lecture provides a few, and we’ll go through a few examples below:
![selectors](https://cs50.harvard.edu/web/2020/notes/0/images/selectors.png)


**Descendant Selector**: Here, we use the descendant selector to only apply styling to list items found within an unordered list:
```
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <title>Using Selectors</title>
            <style>
                ul li {
                    color: blue;
                }
            </style>
        </head>
        <body>
            <ol>
                <li>foo</li>
                <li> bar
                    <ul>
                        <li>hello</li>
                        <li>goodbye</li>
                        <li>hello</li>
                    </ul>
                </li>
                <li>baz</li>
            </ol>
    
        </body>
    <html>
![list selector](https://cs50.harvard.edu/web/2020/notes/0/images/selectors0.png)
```

**Attributes as Selectors**: We can also narrow down our selection based on the attributes we assign to HTML elements using brackets. For example, in the following list of links, we choose to only make the link to Amazon red:
```

    <!DOCTYPE html>
    <html lang="en">
        <head>
            <title>Using Selectors</title>
            <style>
                a[href="https://www.amazon.com/"] {
                    color: red;
                }
            </style>
        </head>
        <body>
            <ol>
                <li><a href="https://www.google.com/">Google</a></li>
                <li><a href="https://www.amazon.com/">Amazon</a> </li>
                <li><a href="https://www.facebook.com/">Facebook</a></li>
            </ol>
    
        </body>
    <html>
![link selectors](https://cs50.harvard.edu/web/2020/notes/0/images/selectors2.png)
```
- Not only can we use CSS to change what an element looks like permanently, but also what it looks like under certain conditions. For example, what if we wanted a button to change color when we hover over it? We can acheive this using a [CSS pseudoclass](https://www.w3schools.com/css/css_pseudo_classes.asp), which provides additional styling during special circumstances. We write this by adding a colon after our selector, and then adding the circumstance after that colon.
- In the case of the button, we would add `:hover` to the button selector to specify the design only when hovering:

```
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <title>Pseudoclasses</title>
            <style>
                button {
                    background-color: red;
                    width: 200px;
                    height: 50px;
                    font-size: 24px;
                }
    
                button:hover {
                    background-color: green;
                }
            </style>
        </head>
        <body>
            <button>Button 1</button>
            <button>Button 2</button>
            <button>Button 3</button>
    
        </body>
    <html>
![buttons](https://cs50.harvard.edu/web/2020/notes/0/images/buttons.gif)
```

Color Picker:  [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Colors/Color_picker_tool](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Colors/Color_picker_tool).

⏮️ [HTML](#)
⏭️ [Practise](#)

