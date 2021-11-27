# HTML

- HTML is a markup language that defines the structure of a web page. It is interpreted by your web browser (Safari, Google Chrome, Firefox, etc.) in order to display content on your screen.
- Let’s get started by writing a simple HTML file!
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <title>Hello!</title>
        </head>
        <body>
            Hello, world!
        </body>
    <html>
- When we open up this file in our browser, we get:
![Hello Page](https://cs50.harvard.edu/web/2020/notes/0/images/hello0.png)

- Now, let’s take some time to talk about the file we just wrote, which seems to be pretty complicated for such a simple page.
    - In the first line, we are declaring (to the web browser) that we are writing the document in the latest version of HTML: HTML5.
    - After that, the page consists of nested **HTML elements** (such as html and body), each with an **opening and closing tag** marked with either `<element>` for an opening and `</element>` for a closing.
    - Notice how each of the inner elements is indented just a bit further than the last. While this is not necessarily required by the browser, it will be very helpful to keep this up in your own code.
    - HTML elements can include **attributes**, which give the browser extra information about the element. For example, when we include `lang="en"` in our initial tag, we are telling the browser that we are using English as our primary language.
    - Inside the HTML element, we typically want to include both a `head` and a `body` tag. The head element will include information about your page that is not necessarily displayed, and the body element will contain what is actually visible to users who visit the site.
    - Within the head, we have included a `title` for our webpage, which you’ll notice is displayed in the tab at the top of our web browser.
    - Finally, we’ve included the text “Hello, world!” in the body, which is the visible part of our page.

[**Document Object Model (DOM)**](https://cs50.harvard.edu/web/2020/notes/0/#document-object-model-dom)

![DOM](https://cs50.harvard.edu/web/2020/notes/0/images/dom.png)

- The DOM is a convenient way of visualizing the way HTML elements relate to each other using a tree-like structure. Above is an example of the DOM layout for the page we just wrote.

[**More HTML Elements**](https://cs50.harvard.edu/web/2020/notes/0/#more-html-elements)

- There are many HTML elements you may want to use to customize your page, including headings, lists, and bolded sections. In this next example, we’ll see a few of of these in action.
- One more thing to note: `<!-- -->` gives us a comment in HTML, so we’ll use that below to explain some of the elements.


    <!DOCTYPE html>
    <html lang="en">
        <head>
            <title>HTML Elements</title>
        </head>
        <body>
            <!-- We can create headings using h1 through h6 as tags. -->
            <h1>A Large Heading</h1>
            <h2>A Smaller Heading</h2>
            <h6>The Smallest Heading</h6>
    
            <!-- The strong and i tags give us bold and italics respectively. -->
            A <strong>bold</strong> word and an <i>italicized</i> word!
    
            <!-- We can link to another page (such as ydev's page) using a. -->
            View the <a href="https://ydev.academy">ydev Website</a>!
    
            <!-- We used ul for an unordered list and ol for an ordered one. both ordered and unordered lists contain li, or list items. -->
            An unordered list:
            <ul>
                <li>foo</li>
                <li>bar</li>
                <li>baz</li>
            </ul>
            An ordered list:
            <ol>
                <li>foo</li>
                <li>bar</li>
                <li>baz</li>
            </ol>
    
            <!-- Images require a src attribute, which can be either the path to a file on your computer or the link to an image online. It also includes an alt attribute, which gives a description in case the image can't be loaded. -->
            An image:
            <img src="../../images/duck.jpeg" alt="Rubber Duck Picture">
            <!-- We can also see above that for some elements that don't contain other ones, closing tags are not necessary. -->
    
            <!-- Here, we use a br tag to add white space to the page. -->
            <br/> <br/>
    
            <!-- A few different tags are necessary to create a table. -->
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

This page, when rendered, looks something like this:

![](https://paper-attachments.dropbox.com/s_8EE11E0529CFF25BFDAC5DE09745448607A2C10B8CBB73085205F4593973A66D_1599663599697_Screen+Shot+2020-09-09+at+3.59.04+PM.png)

- In case you’re worried about it, know that you’ll never have to memorize these elements. It’s very easy to simply search something like “image in HTML” to find the `img` tag. One resource that’s especially helpful for learning about these elements is [W3 Schools](https://www.w3schools.com/html/html_elements.asp).

[**Forms**](https://cs50.harvard.edu/web/2020/notes/0/#forms)

- Another set of elements that is really important when creating a website is how to collect information from users. You can allow users to enter information using an HTML form, which can contain several different types of input. Later in the course, we’ll learn about how to handle information once a form has been submitted.
- Just as with other HTML elements, there’s no need to memorize these, and W3 Schools is a great resource for learning about them!
- 
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <title>Forms</title>
    </head>
    <body>
        <form>
            <input type="text" placeholder="First Name" name="first">
            <input type="password" placeholder="Password" name="password">
            <div>
                Favorite Color:
                <input name="color" type="radio" value="blue"> Blue
                <input name="color" type="radio" value="green"> Green
                <input name="color" type="radio" value="yellow"> Yellow
                <input name="color" type="radio" value="red"> Red
    
            </div>
            <input type="submit">
        </form>
    </body>
    </html>
![form](https://cs50.harvard.edu/web/2020/notes/0/images/form.png)


⏭️ [CSS](https://www.dropbox.com/scl/fi/heyj468i5we8xm5gjzti0/CSS.paper?dl=0&rlkey=zzpuxwva50iw1t3cibzlgtwdn)

