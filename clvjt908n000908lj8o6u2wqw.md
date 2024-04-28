---
title: "0 to 1: A Gentle introduction to CSS Flex box"
seoTitle: "CSS Flexbox Basics"
seoDescription: "Learn the basics of CSS Flexbox for responsive web design. Understand layout, interactions, and practical implementation without media queries"
datePublished: Sun Apr 28 2024 17:34:44 GMT+0000 (Coordinated Universal Time)
cuid: clvjt908n000908lj8o6u2wqw
slug: 0-to-1-a-gentle-introduction-to-css-flex-box
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714210135998/b8260196-cebe-4713-abb0-2b1a541109c0.png
tags: flexbox, css3, css, learning, coding, flex, codingnewbies

---

**CSS Flexbox** is a way to specify the *layout* and *interactions* of HTML elements in a webpage. It is a container with HTML elements inside it called items.

Flexbox is about how to distribute items along a row or column.

Why do we need Flexbox? Due to its ability to adjust size based on the device it is viewed on and content it has. Therefore, It is always a prime Layout Algorithm for responsive design.

Have a look at this [Demo](https://codepen.io/argyleink/pen/LYEegOO) by Adam Argyle, ***It uses no media queries to adjust size and position.*** Yet, It is able to change and adjust based on size of page.

So,

## Let's make a flexbox!!

1. Make an HTML file named `index.html` and copy and paste the below code.
    
    ```javascript
    <!DOCTYPE html>
    <html lang="en">
      <head>
        <title>Flexbox</title>
        <link rel="stylesheet" href="style.css" />
      </head>
      <body>
        <div class="container">
          <div class="item" id="zero">0</div>
          <div class="item">1</div>
          <div class="item">2</div>
          <div class="item">3</div>
          <div class="item">4</div>
        </div>
      </body>
    </html>
    ```
    
2. Make a CSS file named `style.css` in the same directory and add the default styles into the file. This resets the browser default styles.
    
    ```css
    *,
    *::after,
    *::before {
      padding: 0;
      margin: 0;
      box-sizing: border-box;
    }
    
    body{
     height: 100vh;
    }
    ```
    
3. To make the items visible, let's add a border to it.
    
    ```css
    .item {
      padding: 5px;
      border: 1px;
      border-style: solid;
    }
    ```
    
4. Open up the HTML using file explorer or Live Server
    
    > Remember, editing this way, you always have to refresh the browser after you make any changes in the code.
    > 
    > If you are using VSCode use [Live Server Extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) to automatically updates changes. Just click on `Go Live` the button in the Status bar.
    
    The Browser Page should look something like this.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714315326293/620ea2ee-d0c4-48f1-af7b-460bb9aaa93d.png align="left")
    
5. Make the container a flexbox by changing the `display` property of container to `flex`
    
    ```css
    .container {
      display: flex;
    }
    ```
    
    Congratulations! This is your FIRST FLEXBOX!!!
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714316128962/3cfac480-16f9-41b1-b488-7d0206692255.png align="left")
    

By default, all elements have the property `display: flow;` When we change the display property to `flex`, We change how the elements behave.

> Tip: You can Zoom in for a closer look.

## Flex direction

By default, the items are stacked side-by-side. Or another way of looking at this is that, The items are stacked on the **Main Axis.** Which is controlled by `flex-direction` property on the container. By default, `flex-direction: row`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714316606903/c54f0479-d8a5-4306-a027-edb548e54cbc.png align="center")

The direction of the axis, tells us in which order the elements are stacked.

The possible values of `flex-direction` are:

* `row`
    
* `row-reversed`
    
* `column`
    
* `column-reversed`
    

The direction and position of **Main Axis** as per `flex-direction`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714317295212/bd9ef04b-4946-49e1-bde0-1888c1fd60f8.png align="center")

## Justify content

You might have noticed that the items don't take up all the space in the flex box.

How this extra space is distributed along the **Main Axis** is controlled by `justify-content` By default, `justify-content: flex-start;`

What is flex-start? It is the "top" position along the **Main Axis** and similarly there is flex-end which is the "bottom" position along the **Main Axis,** this is where the flex box ends.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714317894609/68201f11-1645-47dc-89eb-9788a846125b.png align="center")

When we change the `justify-content` to `flex-end`. This is the result.

```css
.container{
    /*code before*/
    justify-content: flex-end;
}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714318719529/fd7bd90c-16c1-48f3-abe9-af7dff537a45.png align="center")

The possible values of `justify-content` are:

* `flex-start`
    
* `flex-end`
    
* `center`
    
* `space-between`
    
* `space-around`
    
* `space-evenly`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714319548459/81811a35-0a18-41bd-8b0b-676f2d85839d.png align="center")

To have more control over how much space should be between items, use [gap](https://developer.mozilla.org/en-US/docs/Web/CSS/gap).

## Align Items

Since every item has the same height, our flexbox also has the same height. What happens if one of the items is taller/shorter than the rest of the items.

Let's set the height of item zero with a height of `50px`

```css
#zero{
 height: 50px;
}
```

This is the result.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714320310794/230c3b47-97f0-46b0-a501-966c9bd2b600.png align="left")

Why are other items have increased their size? This is due to `align-items` property which defines how the items are distributed along **the Cross Axis.**

By default, it is set to `stretch` which expands all items to the height of the flex box.

The height flex box by default is set to the maximum height of items. Let's change that and set it to height of the body.

```css
.container{
    height: 100%;
    /*Rest of code*/
}
```

Now, our items should take up the height of the page except item0

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714321254750/9fb31fe1-7ef2-4b65-a377-2a8f45aac23b.png align="center")

Let's remove the `#zero` CSS to avoid further confusion.

`align-items` has the same purpose as `justify-content` but it controls the **Cross Axis,** instead of **Main Axis.**

Confusingly, the "top" of the **Cross Axis** is also called `flex-start` and the "bottom" is also called `flex-end`. Remember that these values have different meaning depending on where it is used.

Let us set the `align-items` to `flex-start`

```css
.container{
    /*Rest of Code*/
    align-items: flex-start;
}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714321678256/9a214144-84f2-4159-97c3-8db86081cb4f.png align="center")

The possible values of `align-items` are:

* `stretch`
    
* `flex-start`
    
* `flex-end`
    
* `center`
    
* `baseline` This aligns all the items based on the contents of the items such that all item content is aligned.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714322239137/04c480c9-86c4-4998-b07f-788c895c1993.png align="center")

## Align self

Every item has a `align-self` that is used to align itself along the **Cross Axis.** Infact `align-items` is a shorthand that sets all items `align-self` to property mentioned.

For Example,

```css
#zero{
    align-self: flex-start;
}
.container{
    /*Rest of Code*/
    align-items: center;
}
```

This sets all items alignment to `center` and item0 alignment as `flex-start`. Below is the result.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714323070633/b7f27f8f-0e27-46d6-a113-e29bdb8b5a77.png align="center")

## How to center a div?

Using flex box, we can center a div by setting the parent's `justify-content: center;` and `align-items: center;`

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

This is the result. This remains centered even when the size of screen changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714323643734/d41a92be-81f6-4a9b-9a65-547c93a2f344.png align="center")

## 1 to 100: Advanced Topics

* wrap
    
* gap
    
* flex-grow
    
* flex-shrink
    
* order
    

## Further Reading

* [A Complete Guide to Flexbox - CSSTricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
    
* [An Interactive Guide to Flexbox - Josh w Comeau](https://www.joshwcomeau.com/css/interactive-guide-to-flexbox/)