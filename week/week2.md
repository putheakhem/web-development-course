### Week II

* PHP form
* PHP Sessions and Cookies
* PHP Error and Exception Handling
* Lab 2. Simple User Registration and Login with PHP
* Introduction to OOP
* PHP File and Directories
* PHP Date Time
* Database Normalization
* MySQL Database
* MySQL Connect
* MySQL Create DB
* My SQL Create Table
* Lab 3. Create Simple Blog using PHP, MySQL 



### PHP Form 

PHP Simple form 

>index.php

```bash
<html>
    <body>

    <form action="welcome.php" method="post">
    Name: <input type="text" name="name"><br>
    E-mail: <input type="text" name="email"><br>
    <input type="submit">
    </form>

    </body>
</html>

```

> welcome.php

```bash
    <html>
        <body>

        Welcome <?php echo $_POST["name"]; ?><br>
        Your email address is: <?php echo $_POST["email"]; ?>
        </body>
    </html>

```

* `$_GET` is an array of variables passed to the current script via the `URL` parameters.

* `$_POST` is an array of variables passed to the current script via the HTTP `POST` method.

1. PHP Form Validation 

> Think SECURITY when processing PHP forms!

> These pages will show how to process PHP forms with security in mind. Proper validation of form data is important to protect your form from hackers and spammers!

* Text Fields

    ```bash 
        Name: <input type="text" name="name">
        E-mail: <input type="text" name="email">
        Website: <input type="text" name="website">
        Comment: <textarea name="comment" rows="5" cols="40"></textarea>
    ```
* Radio Buttons

    ```bash
        Gender:
        <input type="radio" name="gender" value="female">Female
        <input type="radio" name="gender" value="male">Male
        <input type="radio" name="gender" value="other">Other
    ```
* Validate Form Data With PHP

```bash
    <?php
    // define variables and set to empty values
    $name = $email = $gender = $comment = $website = "";

    if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $name = test_input($_POST["name"]);
    $email = test_input($_POST["email"]);
    $website = test_input($_POST["website"]);
    $comment = test_input($_POST["comment"]);
    $gender = test_input($_POST["gender"]);
    }

    function test_input($data) {
    $data = trim($data);
    $data = stripslashes($data);
    $data = htmlspecialchars($data);
    return $data;
    }
    ?>

```

#### Lab 2 

In this Lab 2, I will explain how to make the simplest user login with session id cookies on PHP.

> How do authorization work? 

* User submit login form. Form sends data into PHP. 
* PHP validate data, generate random string(session id), saves it to closed server storage in pair with user login, and send session id into browser in response as cookies. Browser stores cookies. 
* User visits any page on this domain and browser sends a cookie to server for each request.
* PHP checks if cookie has been sent, if such cookie exists in server storage with pair with login. Identifies user, provides access to his private content.
* Logout button removes the cookie from browser and session id-login pair from server storage. Browser does not send cookies, server does not see it and does not see session id-login pair.


> index.php

```bash
    <?php

        session_start(); //gets session id from cookies, or prepa

        if (session_id() == '' || !isset($_SESSION['login'])) { //if sid exists and login for sid exists
    
    ?>

    <a href="/login.php">Login</a>

    <?php

        } else {

        echo "Hi, " . $_SESSION['login'];

        ?>

    <a href="/logout.php">Logout</a>

        <?php 

         }

        ?>

```

> loing.php

```bash
    <?php

    session_start();

    //TODO: do not hardcode, get from database
    const login = 'admin';
    const password = 'admin';

    if (isset($_POST['login']) && isset($_POST['password'])) //when form submitted
    {
    if ($_POST['login'] === login && $_POST['password'] === password)
    {
        $_SESSION['login'] = $_POST['login']; //write login to server storage
        header('Location: /'); //redirect to main
    }
    else
    {
        echo "<script>alert('Wrong login or password');</script>";
        echo "<noscript>Wrong login or password</noscript>";
    }
    }

    ?>

    <form method="post">
        Login:<br><input name="login"><br>
        Password:<br><input name="password"><br>
        <input type="submit">
    </form>


```

> logout.php


```bash
    <?php

    session_start();
    setcookie(session_name(), "", time() - 3600); //send browser command remove sid from cookie
    session_destroy(); //remove sid-login from server storage
    session_write_close();
    header('Location: /');

?>

```