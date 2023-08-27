- Imagine you have a toy that you can customize. You have different parts like the head, body, arms, and legs. Now, think of Jinja as a tool that helps you combine these parts to create your own unique toy.
- In this case, the toy parts are like templates, which are like special files with empty spaces. These empty spaces are where you can put different things, like words or numbers. Jinja helps you fill in these empty spaces with the right words or numbers to make the toy look the way you want.
- For example, let's say you have a template for a greeting card with a blank space for the name of the person you want to send it to. With Jinja, you can tell it the name you want to use, and it will put that name in the right place on the greeting card template.
- Jinja also lets you do more than just put in words. You can use it to make decisions too. For instance, you can tell Jinja to put a smiley face on the greeting card if the person's name starts with the letter "A", or a sad face if it starts with any other letter.
- So, Jinja is like a magical tool that helps you create customized things by filling in blanks with the right words or numbers, and even making decisions based on certain conditions. It's used by computer programmers to make websites and other applications look and behave exactly how they want them to.

## extending html to multiple html files
- add `{% block body %} {% endblock %}` in body tag of the layout.html
````
{% extends 'layout.html' %}
{% block body %}
 ---- content of other pages 
{% endblock %}`
```