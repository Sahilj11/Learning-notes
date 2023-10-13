Certainly! Here's an example of a login page and a registration page using HTML tables:

**Login Page (`login.html`):**
![[Pasted image 20230927200625.png]]

```html
<!DOCTYPE html>
<html>
<head>
    <title>Login</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        table {
            border-collapse: collapse;
            width: 300px;
        }
        th, td {
            padding: 10px;
            text-align: left;
        }
        th {
            background-color: #4CAF50;
            color: white;
        }
        td {
            border-bottom: 1px solid #ddd;
        }
        .form-container {
            text-align: center;
        }
        .form-container a {
            text-decoration: none;
            color: #4CAF50;
        }
    </style>
</head>
<body>
    <div class="container">
        <table>
            <tr>
                <th colspan="2">Login</th>
            </tr>
            <tr>
                <td>Username:</td>
                <td><input type="text" name="username"></td>
            </tr>
            <tr>
                <td>Password:</td>
                <td><input type="password" name="password"></td>
            </tr>
            <tr>
                <td colspan="2">
                    <input type="submit" value="Login">
                </td>
            </tr>
            <tr>
                <td colspan="2">
                    Don't have an account? <a href="registration.html">Register</a>
                </td>
            </tr>
        </table>
    </div>
</body>
</html>
```

**Registration Page (`registration.html`):**
![[Pasted image 20230927200559.png]]

```html
<!DOCTYPE html>
<html>
<head>
    <title>Registration</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        table {
            border-collapse: collapse;
            width: 300px;
        }
        th, td {
            padding: 10px;
            text-align: left;
        }
        th {
            background-color: #4CAF50;
            color: white;
        }
        td {
            border-bottom: 1px solid #ddd;
        }
        .form-container {
            text-align: center;
        }
        .form-container a {
            text-decoration: none;
            color: #4CAF50;
        }
    </style>
</head>
<body>
    <div class="container">
        <table>
            <tr>
                <th colspan="2">Registration</th>
            </tr>
            <tr>
                <td>Username:</td>
                <td><input type="text" name="username"></td>
            </tr>
            <tr>
                <td>Email:</td>
                <td><input type="text" name="email"></td>
            </tr>
            <tr>
                <td>Password:</td>
                <td><input type="password" name="password"></td>
            </tr>
            <tr>
                <td colspan="2">
                    <input type="submit" value="Register">
                </td>
            </tr>
            <tr>
                <td colspan="2">
                    Already have an account? <a href="login.html">Login</a>
                </td>
            </tr>
        </table>
    </div>
</body>
</html>
```

In these examples:

- Each page (login and registration) is enclosed within a `<div>` with the class `container` to center it vertically and horizontally on the page.
- The forms are organized using HTML tables for tabular layout.
- CSS styles are used to format the tables and links.
- The "Register" link on the login page points to the registration page (`registration.html`), and the "Login" link on the registration page points to the login page (`login.html`).