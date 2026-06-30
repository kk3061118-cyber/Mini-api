# Mini-api
mini-api/
│── index.php
│── style.css
│── api/
│   ├── greet.php
│   └── list.php

index.php

<?php
session_start();

$result = [];
$error = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {

    try {

        $name = urlencode($_POST["name"]);
        $url = "http://localhost/mini-api/api/greet.php?name=" . $name;

        $response = @file_get_contents($url);

        if ($response === false) {
            throw new Exception("Unable to connect to API.");
        }

        $result = json_decode($response, true);

        if (!$result) {
            throw new Exception("Invalid JSON received.");
        }

    } catch (Exception $e) {
        $error = $e->getMessage();
    }
}
?>

<!DOCTYPE html>
<html>
<head>

//<!--kk306118@gmail.com -->

<meta charset="UTF-8">
<title>Mini API Project</title>
<link rel="stylesheet" href="style.css">

</head>

<body>

<div class="container">

<h1>Mini API Demo</h1>

<form method="post">

<input
type="text"
name="name"
placeholder="Enter your name"
required>

<button type="submit">
Get Greeting
</button>

</form>

<?php if($error!=""){ ?>

<p class="error">
<?php echo htmlspecialchars($error); ?>
</p>

<?php } ?>

<?php if(!empty($result)){ ?>

<h2>API Response</h2>

<p>
<?php echo htmlspecialchars($result["message"]); ?>
</p>

<?php } ?>

</div>

</body>
</html>

---

api/greet.php

<?php

header("Content-Type: application/json");

$name = "Guest";

if(isset($_GET["name"]) && $_GET["name"]!=""){
    $name = $_GET["name"];
}

$data = [
    "success" => true,
    "message" => "Hello, $name! Welcome to the Mini API."
];

echo json_encode($data);

?>

---

api/list.php

<?php

header("Content-Type: application/json");

$tips = [
    "Practice coding daily",
    "Use comments in code",
    "Debug step by step",
    "Read documentation",
    "Build small projects"
];

echo json_encode($tips);

?>

---

style.css

body{
    font-family: Arial, sans-serif;
    background:#f4f4f4;
}

.container{
    width:400px;
    margin:60px auto;
    background:white;
    padding:20px;
    border-radius:10px;
    box-shadow:0 0 10px rgba(0,0,0,.2);
}

h1{
    text-align:center;
}

input{
    width:100%;
    padding:10px;
    margin:10px 0;
}

button{
    padding:10px 20px;
    background:#007bff;
    color:white;
    border:none;
    cursor:pointer;
}

button:hover{
    background:#0056b3;
}

.error{
    color:red;
}mini-api/
│── index.php
│── style.css
│── api/
│   ├── greet.php
│   └── list.php

index.php

<?php
session_start();

$result = [];
$error = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {

    try {

        $name = urlencode($_POST["name"]);
        $url = "http://localhost/mini-api/api/greet.php?name=" . $name;

        $response = @file_get_contents($url);

        if ($response === false) {
            throw new Exception("Unable to connect to API.");
        }

        $result = json_decode($response, true);

        if (!$result) {
            throw new Exception("Invalid JSON received.");
        }

    } catch (Exception $e) {
        $error = $e->getMessage();
    }
}
?>

<!DOCTYPE html>
<html>
<head>

<!-- your-email@example.com -->

<meta charset="UTF-8">
<title>Mini API Project</title>
<link rel="stylesheet" href="style.css">

</head>

<body>

<div class="container">

<h1>Mini API Demo</h1>

<form method="post">

<input
type="text"
name="name"
placeholder="Enter your name"
required>

<button type="submit">
Get Greeting
</button>

</form>

<?php if($error!=""){ ?>

<p class="error">
<?php echo htmlspecialchars($error); ?>
</p>

<?php } ?>

<?php if(!empty($result)){ ?>

<h2>API Response</h2>

<p>
<?php echo htmlspecialchars($result["message"]); ?>
</p>

<?php } ?>

</div>

</body>
</html>

---

api/greet.php

<?php

header("Content-Type: application/json");

$name = "Guest";

if(isset($_GET["name"]) && $_GET["name"]!=""){
    $name = $_GET["name"];
}

$data = [
    "success" => true,
    "message" => "Hello, $name! Welcome to the Mini API."
];

echo json_encode($data);

?>

---

api/list.php

<?php

header("Content-Type: application/json");

$tips = [
    "Practice coding daily",
    "Use comments in code",
    "Debug step by step",
    "Read documentation",
    "Build small projects"
];

echo json_encode($tips);

?>

---

style.css

body{
    font-family: Arial, sans-serif;
    background:#f4f4f4;
}

.container{
    width:400px;
    margin:60px auto;
    background:white;
    padding:20px;
    border-radius:10px;
    box-shadow:0 0 10px rgba(0,0,0,.2);
}

h1{
    text-align:center;
}

input{
    width:100%;
    padding:10px;
    margin:10px 0;
}

button{
    padding:10px 20px;
    background:#007bff;
    color:white;
    border:none;
    cursor:pointer;
}

button:hover{
    background:#0056b3;
}

.error{
    color:red;
}mini-api/
│── index.php
│── style.css
│── api/
│   ├── greet.php
│   └── list.php

index.php

<?php
session_start();

$result = [];
$error = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {

    try {

        $name = urlencode($_POST["name"]);
        $url = "http://localhost/mini-api/api/greet.php?name=" . $name;

        $response = @file_get_contents($url);

        if ($response === false) {
            throw new Exception("Unable to connect to API.");
        }

        $result = json_decode($response, true);

        if (!$result) {
            throw new Exception("Invalid JSON received.");
        }

    } catch (Exception $e) {
        $error = $e->getMessage();
    }
}
?>

<!DOCTYPE html>
<html>
<head>

<!-- your-email@example.com -->

<meta charset="UTF-8">
<title>Mini API Project</title>
<link rel="stylesheet" href="style.css">

</head>

<body>

<div class="container">

<h1>Mini API Demo</h1>

<form method="post">

<input
type="text"
name="name"
placeholder="Enter your name"
required>

<button type="submit">
Get Greeting
</button>

</form>

<?php if($error!=""){ ?>

<p class="error">
<?php echo htmlspecialchars($error); ?>
</p>

<?php } ?>

<?php if(!empty($result)){ ?>

<h2>API Response</h2>

<p>
<?php echo htmlspecialchars($result["message"]); ?>
</p>

<?php } ?>

</div>

</body>
</html>

---

api/greet.php

<?php

header("Content-Type: application/json");

$name = "Guest";

if(isset($_GET["name"]) && $_GET["name"]!=""){
    $name = $_GET["name"];
}

$data = [
    "success" => true,
    "message" => "Hello, $name! Welcome to the Mini API."
];

echo json_encode($data);

?>

---

api/list.php

<?php

header("Content-Type: application/json");

$tips = [
    "Practice coding daily",
    "Use comments in code",
    "Debug step by step",
    "Read documentation",
    "Build small projects"
];

echo json_encode($tips);

?>

---

style.css

body{
    font-family: Arial, sans-serif;
    background:#f4f4f4;
}

.container{
    width:400px;
    margin:60px auto;
    background:white;
    padding:20px;
    border-radius:10px;
    box-shadow:0 0 10px rgba(0,0,0,.2);
}

h1{
    text-align:center;
}

input{
    width:100%;
    padding:10px;
    margin:10px 0;
}

button{
    padding:10px 20px;
    background:#007bff;
    color:white;
    border:none;
    cursor:pointer;
}

button:hover{
    background:#0056b3;
}

.error{
    color:red;
}mini-api/
│── index.php
│── style.css
│── api/
│   ├── greet.php
│   └── list.php

index.php

<?php
session_start();

$result = [];
$error = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {

    try {

        $name = urlencode($_POST["name"]);
        $url = "http://localhost/mini-api/api/greet.php?name=" . $name;

        $response = @file_get_contents($url);

        if ($response === false) {
            throw new Exception("Unable to connect to API.");
        }

        $result = json_decode($response, true);

        if (!$result) {
            throw new Exception("Invalid JSON received.");
        }

    } catch (Exception $e) {
        $error = $e->getMessage();
    }
}
?>

<!DOCTYPE html>
<html>
<head>

<!-- your-email@example.com -->

<meta charset="UTF-8">
<title>Mini API Project</title>
<link rel="stylesheet" href="style.css">

</head>

<body>

<div class="container">

<h1>Mini API Demo</h1>

<form method="post">

<input
type="text"
name="name"
placeholder="Enter your name"
required>

<button type="submit">
Get Greeting
</button>

</form>

<?php if($error!=""){ ?>

<p class="error">
<?php echo htmlspecialchars($error); ?>
</p>

<?php } ?>

<?php if(!empty($result)){ ?>

<h2>API Response</h2>

<p>
<?php echo htmlspecialchars($result["message"]); ?>
</p>

<?php } ?>

</div>

</body>
</html>

---

api/greet.php

<?php

header("Content-Type: application/json");

$name = "Guest";

if(isset($_GET["name"]) && $_GET["name"]!=""){
    $name = $_GET["name"];
}

$data = [
    "success" => true,
    "message" => "Hello, $name! Welcome to the Mini API."
];

echo json_encode($data);

?>

---

api/list.php

<?php

header("Content-Type: application/json");

$tips = [
    "Practice coding daily",
    "Use comments in code",
    "Debug step by step",
    "Read documentation",
    "Build small projects"
];

echo json_encode($tips);

?>

---

style.css

body{
    font-family: Arial, sans-serif;
    background:#f4f4f4;
}

.container{
    width:400px;
    margin:60px auto;
    background:white;
    padding:20px;
    border-radius:10px;
    box-shadow:0 0 10px rgba(0,0,0,.2);
}

h1{
    text-align:center;
}

input{
    width:100%;
    padding:10px;
    margin:10px 0;
}

button{
    padding:10px 20px;
    background:#007bff;
    color:white;
    border:none;
    cursor:pointer;
}

button:hover{
    background:#0056b3;
}

.error{
    color:red;
}