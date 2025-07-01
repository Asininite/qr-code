
# Project Changes: QR Code Component

This document outlines the step-by-step changes made to the project to transform the initial HTML into a styled component that matches the design.

## 1. Creating the Stylesheet (`style.css`)

To keep our styling separate from our HTML structure, we created a new file called `style.css`. This is a common practice in web development that makes the code easier to manage.

Here's a breakdown of the styles we added:

### Body Styling

```css
body {
    background-color: hsl(212, 45%, 89%);
    font-family: 'Outfit', sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    margin: 0;
}
```

-   `background-color`: We set a light grayish-blue background color for the entire page.
-   `font-family`: We would ideally use a font named 'Outfit', with a fallback to a generic `sans-serif` font if 'Outfit' isn't available.
-   `display: flex`, `justify-content: center`, `align-items: center`: This is a modern CSS technique to center the content (our QR code card) both horizontally and vertically on the page.
-   `min-height: 100vh`: This ensures that the body takes up at least the full height of the browser window, which is necessary for vertical centering to work correctly.
-   `margin: 0`: This removes any default margin that the browser might apply to the body.

### Container Styling

```css
.container {
    background-color: hsl(0, 0%, 100%);
    border-radius: 20px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    padding: 16px;
    width: 320px;
    text-align: center;
}
```

-   We created a class called `.container` which acts as the white card holding our content.
-   `background-color`: We set the background to white.
-   `border-radius`: This gives the container its rounded corners.
-   `box-shadow`: This adds a subtle shadow around the container, making it appear to "lift" off the page.
-   `padding`: This adds some space between the content and the edge of the container.
-   `width`: We set a fixed width for the container.
-   `text-align: center`: This centers the text inside the container.

### Image Styling

```css
.container img {
    width: 100%;
    border-radius: 10px;
}
```

-   `width: 100%`: This makes the image take up the full width of its container.
-   `border-radius`: This gives the image slightly rounded corners, matching the design.

### Text Styling

```css
.container h1 {
    color: hsl(218, 44%, 22%);
    font-size: 22px;
    margin: 20px 0 15px;
}

.container p {
    color: hsl(220, 15%, 55%);
    font-size: 15px;
    margin: 0 15px 20px;
}
```

-   We styled the `<h1>` (main heading) and `<p>` (paragraph) elements.
-   `color`: We set the specific text colors as defined in the style guide.
-   `font-size`: We set the font sizes for the heading and paragraph.
-   `margin`: We added margins to create space around the text elements for better readability.

## 2. Updating the HTML (`index.html`)

After creating our styles, we needed to update the `index.html` file to use them and to structure the content correctly.

### Linking the Stylesheet

The first change was to tell the HTML file to use our new CSS file. We replaced the inline `<style>` block with a `<link>` tag in the `<head>` section:

```html
<link rel="stylesheet" href="style.css">
```

This line tells the browser to load and apply the styles from `style.css`.

### Structuring the Content

Next, we updated the `<body>` of the HTML to structure the content in a way that our CSS could target. We replaced the old `<center>` tag with a more semantic structure:

```html
  <div class="container">
    <img src="images/image-qr-code.png" alt="QR code">
    <h1>Improve your front-end skills by building projects</h1>
    <p>Scan the QR code to visit Frontend Mentor and take your coding skills to the next level</p>
  </div>
```

-   We wrapped everything in a `<div>` and gave it the class `container`. This is the element that our `.container` styles in the CSS file apply to.
-   We placed the QR code image inside an `<img>` tag. The `alt` attribute provides alternative text for screen readers and if the image fails to load.
-   We used an `<h1>` for the main, bold heading.
-   We used a `<p>` for the smaller, gray-ish paragraph text.

These changes result in a webpage that is structured correctly and styled to match the provided design.
