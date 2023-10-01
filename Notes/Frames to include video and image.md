
Here's an example of how you can create a basic web page with framesets to include videos and images. Keep in mind that this is for educational purposes, and it's not a recommended practice for real-world web development:
![[Pasted image 20230927203207.png]]


```html
<!DOCTYPE html>
<html>
<head>
    <title>Frameset Example</title>
</head>
<frameset cols="50%, 50%">
    <frame src="images_frame.html">
    <frame src="videos_frame.html">
</frameset>
</html>
```

Now, you would need to create two separate HTML files for the content of each frame:

**`images_frame.html`:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Images Frame</title>
</head>
<body>
    <h1>Images Frame</h1>
    <img src="image1.jpg" alt="Image 1" height="200" width="200">
    <img src="image2.jpg" alt="Image 2" height="200" width="200">
</body>
</html>
```

**`videos_frame.html`:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Videos Frame</title>
</head>
<body>
    <h1>Videos Frame</h1>
    <video width="640" height="360" controls>
        <source src="video1.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <video width="640" height="360" controls>
        <source src="video2.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
</body>
</html>
```

In this example:

- We use the `<frameset>` element to create a two-column layout where one frame (`images_frame.html`) contains images, and the other frame (`videos_frame.html`) contains videos.
- Each frame content is in a separate HTML file.
- Images are displayed using the `<img>` element, and videos are embedded using the `<video>` element with the `controls` attribute for playback controls.