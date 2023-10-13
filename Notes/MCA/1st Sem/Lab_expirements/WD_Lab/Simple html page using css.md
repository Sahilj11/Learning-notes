Here's a simple homepage created without using an external CSS file. This example includes basic HTML markup to structure the page and style the content using inline styles:
![[Pasted image 20230927201626.png]]


```html
<!DOCTYPE html>
<html>
<head>
    <title>Simple Homepage</title>
</head>
<body>
    <header style="background-color: #333; color: #fff; text-align: center; padding: 10px;">
        <h1>Welcome to My Simple Homepage</h1>
    </header>

    <nav style="background-color: #444; color: #fff; padding: 10px;">
        <ul style="list-style: none; padding: 0; text-align: center;">
            <li style="display: inline; margin-right: 20px;"><a href="#">Home</a></li>
            <li style="display: inline; margin-right: 20px;"><a href="#">About</a></li>
            <li style="display: inline; margin-right: 20px;"><a href="#">Services</a></li>
            <li style="display: inline;"><a href="#">Contact</a></li>
        </ul>
    </nav>

    <main style="padding: 20px;">
        <h2>About Us</h2>
        <p>We are a simple homepage without any external CSS.</p>

        <h2>Our Services</h2>
        <ul>
            <li>Web Design</li>
            <li>Graphic Design</li>
            <li>Content Writing</li>
        </ul>

        <h2>Contact Us</h2>
        <p>Email: example@example.com</p>
        <p>Phone: +1 123-456-7890</p>
    </main>

    <footer style="background-color: #333; color: #fff; text-align: center; padding: 10px;">
        &copy; 2023 Simple Homepage
    </footer>
</body>
</html>
```

In this example:

- Inline styles are used within the `style` attribute of HTML elements to set background colors, text colors, padding, text alignment, and more.
- The `<header>` element contains the website title.
- The `<nav>` element contains a navigation menu.
- The `<main>` element holds the main content of the homepage, including information about the site, services, and contact details.
- The `<footer>` element is used for the footer text.
