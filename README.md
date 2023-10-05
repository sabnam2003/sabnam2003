#################11 program############

<!DOCTYPE html>
<html lang="{{ str_replace('_', '-', app()->getLocale()) }}">
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">

        <title>Laravel</title>

        <!-- Fonts -->
        <link rel="preconnect" href="https://fonts.bunny.net">
        <link href="https://fonts.bunny.net/css?family=figtree:400,600&display=swap" rel="stylesheet" />

        <!-- Styles -->
        <style>
                <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            margin: 0;
            padding: 0;
        }

        .container {
            background-color: #fff;
            max-width: 400px;
            margin: 20px auto;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        h2 {
            text-align: center;
        }

        label {
            display: block;
            margin-bottom: 5px;
        }

        input[type="text"], input[type="email"], select {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 3px;
        }

        input[type="submit"] {
            background-color: #007BFF;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }

        input[type="submit"]:hover {
            background-color: #0056b3;
        }
        </style>
    </head>
    <body class="antialiased">
    <h1>Student Registration Form</h1>
    <form action="process_registration.php" method="POST">
        <label for="first_name">First Name:</label>
        <input type="text" id="first_name" name="first_name" required><br><br>

        <label for="last_name">Last Name:</label>
        <input type="text" id="last_name" name="last_name" required><br><br>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required><br><br>

        <label for="dob">Date of Birth:</label>
        <input type="date" id="dob" name="dob" required><br><br>

        <label for="gender">Gender:</label>
        <input type="radio" id="male" name="gender" value="Male"> <label for="male">Male</label>
        <input type="radio" id="female" name="gender" value="Female"> <label for="female">Female</label>
        <input type="radio" id="other" name="gender" value="Other"> <label for="other">Other</label><br><br>

        <label for="courses">Select Courses:</label>
        <select id="courses" name="courses[]" multiple>
            <option value="math">Math</option>
            <option value="science">Science</option>
            <option value="history">History</option>
            <option value="english">English</option>
        </select><br><br>

        <label for="comments">Comments:</label><br>
        <textarea id="comments" name="comments" rows="4" cols="50"></textarea><br><br>

        <input type="submit" value="Submit">
    </form>
    </body>
</html>




################################################################10###10 database connectivity

CREATE TABLE `student` (
	`ID` INT(100) NOT NULL AUTO_INCREMENT,
	`NAME` VARCHAR(100) NOT NULL COLLATE 'latin1_swedish_ci',
	`CITY` VARCHAR(100) NOT NULL COLLATE 'latin1_swedish_ci',
	PRIMARY KEY (`ID`) USING BTREE
)
;

CHANGING NAME APPLE 

<?php
$db_host = 'localhost';
$db_user = 'root';
$db_pass = '';
$db_name = 'apple';
try {
//    echo "initializing conn";
    $connection = mysqli_connect($db_host, $db_user, $db_pass, $db_name);
} catch (Exception $exception) {
    echo $exception;
}



###1###
PROGRAM-1: Simple Web Page using HTML Tags
#########################################Ex1.php
<html>
<head>
<title>Basic Form Controls in PHP</title>
</head>
<body>
<h1>Basic Form Controls in PHP</h1>
<form method="post" action="process_form.php">
<label for="name">Name:</label>
<input type="text" id="name" name="name" required><br>
<label for="email">Email:</label>
<input type="email" id="email" name="email" required><br>
<label>Gender:</label>
<input type="radio" id="male" name="gender" value="male" required>
<label for="male">Male</label>
<input type="radio" id="female" name="gender" value="female" required>
<label for="female">Female</label><br>
<label>Programming Languages:</label>
<input type="checkbox" id="java" name="languages[]" value="Java Programming">
<label for="java">Java</label>
<input type="checkbox" id="python" name="languages[]" value="Python Programming">
<label for="python">Python</label>
<input type="checkbox" id="php" name="languages[]" value="PHP Programming">
<label for="php">PHP</label><br>
<input type="submit" name="submit" value="Submit">
</form>
</body>
</html>


####process_form.php

<html>
<head>
<title>Form Submission Results</title>
</head>
<body>
<?php
if ($_SERVER["REQUEST_METHOD"] === "POST") {
$name = $_POST["name"];
$email = $_POST["email"];
$gender = $_POST["gender"];
$languages = isset($_POST["languages"]) ? $_POST["languages"] : [];
echo "<h2>Form Submission Results:</h2>";
echo "<p><strong>Name:</strong> $name</p>";
echo "<p><strong>Email:</strong> $email</p>";
echo "<p><strong>Gender:</strong> $gender</p>";
if (!empty($languages)) {
echo "<p><strong>Programming Languages Known:</strong></p>";
echo "<ul>";
foreach ($languages as $language) {
echo "<li>$language</li>";
}
echo "</ul>";
} else {
echo "<p>No programming languages selected.</p>";
}
} else {
echo "<p>Form not submitted yet.</p>";
}
?>
</body>
</html>

###################################################PROGRAM-2: Design Web Page using CSS

CODING:
#######################################Ex2.php
<html>
<head>
<title>Colorful and Attractive PHP Web Page</title>
<link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
<header>
<h1>Welcome to ColorfulWeb</h1>
</header>
<main>
<section class="featured">
<h2>Discover the Magic of Colors</h2>
<p>
Experience a world of vivid hues and captivating designs. ColorfulWeb
brings your imagination to life with eye-catching web development solutions.
</p>
<a href="#" class="cta-btn">Explore Now</a>
</section>
<section class="contact-form">
<h2>Contact Us</h2>
<form action="contact.php" method="post">
<label for="name">Name:</label>
<input type="text" id="name" name="name" required>
<label for="email">Email:</label>
<input type="email" id="email" name="email" required>
<label for="message">Message:</label>
<textarea id="message" name="message" rows="4" required></textarea>
<input type="submit" value="Send Message">
</form>
</section>
</main>
<footer>
<p>&copy; <?php echo date("Y"); ?> ColorfulWeb. All rights reserved.</p>
</footer>
</body>
</html>
styles.css
body, h1, h2, p, ul, li, a, label, input, textarea {
margin: 0;
padding: 0;
box-sizing: border-box;
}
/* Set some global styles */
body {
font-family: Arial, sans-serif;
line-height: 1.6;
background-color: #f6f6f6;
color: #333;
}
header {
background-color: #ffa500;
color: #fff;
text-align: center;
padding: 20px;
}
header h1 {
font-size: 48px;
margin-bottom: 10px;
}
main {
margin: 20px;
}
section {
margin-bottom: 30px;
padding: 20px;
background-color: #fff;
box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
border-radius: 5px;
}
section h2 {
font-size: 28px;
margin-bottom: 20px;
color: #ffa500;
}
section p {
font-size: 18px;
line-height: 1.8;
}
.contact-form form {
display: flex;
flex-direction: column;
}
.contact-form label {
margin-bottom: 5px;
color: #ffa500;
}
.contact-form input,
.contact-form textarea {
padding: 10px;
margin-bottom: 10px;
border: 1px solid #ffa500;
border-radius: 5px;
}
.contact-form textarea {
resize: vertical;
}
.contact-form input[type="submit"] {
background-color: #ffa500;
color: #fff;
cursor: pointer;
border: none;
border-radius: 5px;
}
.contact-form input[type="submit"]:hover {
background-color: #ff8c00;
}
.cta-btn {
display: inline-block;
background-color: #ff8c00;
color: #fff;
padding: 10px 20px;
text-decoration: none;
border-radius: 5px;
transition: background-color 0.3s ease;
}
.cta-btn:hover {
background-color: #ff4500;
}
footer {
background-color: #ffa500;
color: #fff;
padding: 20px;
text-align: center;
}
footer p {
font-size: 16px;
}



########################################3PROGRAM-3: Control Structures and Loops - ARITHMETIC
#################CALCULATOR
CODING:
<?php
if(isset($_POST['disp']))
{
$f=$_POST['f'];
$s=$_POST['s'];
$ch=$_POST['ch'];
switch($ch)
{
case 'ADDITION':
$res=$f+$s;
break;
case 'SUBTRACTION':
$res=$f-$s;
break;
case 'MULTIPLICATION':
$res=$f*$s;
break;
case 'DIVISION':
$res=$f/$s;
break;
}
}
?>
<html>
<body bgcolor="gold">
<form action="" method="post">
<table align="center" border="3" width="20%"><br><br>
<tr bgcolor="forestgreen"><td align="center" colspan="2">
<font color="white" face="arial black" size="5">CALCULATOR</font></td></tr>
<tr><td><input type="button" value="Enter First Input "></td>
<td><input type="text" name="f"></td></tr>
<tr><td><input type="button" value="Enter Second Input"></td>
<td><input type="text" name="s"></td></tr>
<tr><td><input type="button" value="Select Your Choice"></td>
<td><center><select name="ch">
<option>ADDITION</option>
<option>SUBTRACTION</option>
<option>MULTIPLICATION</option>
<option>DIVISION</option>
</center></select></td></tr>
<tr><td><input type="submit" value=" RESULT " name="disp"></td>
<td><input type="text" value="<?php echo @$res; ?>" readonly="true"/>
</td></tr></table>
</body></html>



#######################################PROGRAM-4: String Handling
##########CODING:
<?php
if(isset($_POST['disp']))
{
$s=$_POST['s'];
$ch=$_POST['ch'];
switch($ch)
{
case 'STRING LENGTH':
$res= strlen($s);
break;
case 'WORD COUNT':
$res= str_word_count($s);
break;
case 'STRING REVERSE':
$res=strrev($s);
break;
case 'POSITION OF A CHARACTER':
$res=strpos($s,"a");
break;
case 'STRING REPLACE':
$res=str_replace($s,"hello","world");
break;
case 'STRING SPLIT':
$res=str_split($s,3);
$res=implode(",",$res);
break;
case 'PASSWORD GENERATOR':
$data="1234567890ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz";
$res= substr(str_shuffle($data),0,7);
break;
}
}
?>
<html>
<body bgcolor="cyan">
<form action="" method="post">
<table align="center" border="3" width="20%"><br><br>
<tr bgcolor="forestgreen"><td align="center" colspan="2">
<font color="white" face="arial black" size="5">STRING HANDLING</font></td></tr>
<tr><td><input type="button" value="Enter String"></td>
<td><input type="text" name="s"></td></tr>
<tr><td><input type="button" value="Select Your Choice"></td>
<td><center><select name="ch">
<option>STRING LENGTH</option>
<option>WORD COUNT</option>
<option>STRING REVERSE</option>
<option>POSITION OF A CHARACTER</option>
<option>STRING REPLACE</option>
<option>STRING SPLIT</option>
<option>PASSWORD GENERATOR</option>
</center></select></td></tr>
<tr><td><input type="submit" value=" RESULT " name="disp"></td>
<td><input type="text" value="<?php echo @$res;?>" readonly="true"/>
</td></tr></table>
</body></html>



######################################PROGRAM-5: Using Arrays and Functions – Quiz Application
#################CODING:
<!DOCTYPE html>
<html>
<head>
<title>Quiz Application</title>
</head>
<body>
<h1>Quiz Application</h1>
<form method="post">
<p>Question 1: Which is the largest animal in the world?</p>
<input type="radio" name="q1" value="Camel" required> Camel<br>
<input type="radio" name="q1" value="Giraffe"> Giraffe<br>
<input type="radio" name="q1" value="Blue whale"> Blue whale<br>
<p>Question 2: How many colors are there in a rainbow?</p>
<input type="radio" name="q2" value="3"> 3<br>
<input type="radio" name="q2" value="7" required> 7<br>
<input type="radio" name="q2" value="5"> 5<br>
<p> Question 3: What type of bird lays the largest eggs?</p>
<input type="radio" name="q3" value="Ostrich" required> Ostrich <br>
<input type="radio" name="q3" value="Dove"> Dove <br>
<input type="radio" name="q3" value="Wagtail"> Wagtail<br>
<input type="submit" name="submit" value="Submit">
</form>
<?php
// Function to check quiz answers and calculate the score
function checkAnswers($userAnswers) {
$correctAnswers = array('q1' => 'Blue whale', 'q2' => '7', 'q3' => 'Ostrich');
$score = 0;
foreach ($userAnswers as $question => $userAnswer) {
if (isset($correctAnswers[$question]) && $correctAnswers[$question] ===
$userAnswer) {
$score++;
}
}
return $score;
}
// Check if the form has been submitted
if (isset($_POST['submit'])) {
$userAnswers = array(
'q1' => $_POST['q1'],
'q2' => $_POST['q2'],
'q3' => $_POST['q3']
);
$score = checkAnswers($userAnswers);
echo "<h2>Quiz Results:</h2>";
echo "<p>Your Score: $score out of 3</p>";
}
?>
</body>
</html>



###################################PROGRAM-6: Form Handling – Conference
#########################CODING:
<!DOCTYPE html>
<html>
<head>
<title>Conference Registration</title>
<style>
body {
font-family: Arial, sans-serif;
background-color: #FFEBF5; /* Light pink background */
margin: 0;
padding: 0;
display: flex;
justify-content: center;
align-items: center;
height: 100vh;
}
.container {
background-color: #fff;
padding: 20px;
border-radius: 10px;
box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
width: 80%;
max-width: 400px;
}
h1 {
color: #FF69B4; /* Darker pink for headings */
margin-bottom: 20px;
text-align: center;
}
label {
display: block;
margin-bottom: 8px;
color: #FF69B4; /* Pink for labels */
}
input[type="text"],
input[type="email"],
select {
width: 100%;
padding: 10px;
margin-bottom: 15px;
border: 1px solid #FF69B4; /* Pink border for input fields */
border-radius: 4px;
}
select {
height: 100px;
}
input[type="submit"] {
background-color: #FF69B4;
color: #fff;
padding: 10px 20px;
border: none;
border-radius: 4px;
cursor: pointer;
display: block;
margin: 0 auto;
}
input[type="submit"]:hover {
background-color: #E85C9E;
}
h2 {
color: #FF69B4;
margin-bottom: 10px;
text-align: center;
}
ul {
margin-left: 20px;
}
li {
margin-bottom: 5px;
}
</style>
</head>
<body>
<div class="container">
<h1>Conference Registration</h1>
<form method="post">
<label for="name">Name:</label>
<input type="text" id="name" name="name" required>
<label for="email">Email:</label>
<input type="email" id="email" name="email" required>
<label for="organization">Organization:</label>
<input type="text" id="organization" name="organization" required>
<label for="sessions">Select Sessions:</label>
<select id="sessions" name="sessions[]" multiple required>
<option value="session1">Session 1 - Topic 1</option>
<option value="session2">Session 2 - Topic 2</option>
<option value="session3">Session 3 - Topic 3</option>
</select>
<input type="submit" name="submit" value="Register">
</form>
<?php
// Check if the form has been submitted
if (isset($_POST['submit'])) {
$name = $_POST['name'];
$email = $_POST['email'];
$organization = $_POST['organization'];
$selectedSessions = $_POST['sessions'];
// Display the registration details
echo "<h2>Registration Details:</h2>";
echo "<p>Name: $name</p>";
echo "<p>Email: $email</p>";
echo "<p>Organization: $organization</p>";
echo "<p>Selected Sessions:</p>";
echo "<ul>";
foreach ($selectedSessions as $session) {
echo "<li>$session</li>";
}
echo "</ul>";
}
?>
</div>
</body>
</html>




#############PROGRAM-7: Server Side Validation And Page Redirection
#####################CODING:
puzzle_selection.html
<!DOCTYPE html>
<html>
<head>
<title>Puzzle Adventure</title>
</head>
<body>
<h1>Welcome to the Puzzle Adventure!</h1>
<p>Select a puzzle to start:</p>
<ul>
<li><a href="puzzle.php?p=1">Puzzle 1</a></li>
<li><a href="puzzle.php?p=2">Puzzle 2</a></li>
<!-- Add more puzzle options here... -->
</ul>
</body>
</html>
puzzle.php
<?php
session_start();
$puzzles = array(
1 => "What has keys but can't open locks?",
2 => "I speak without a mouth and hear without ears. I have no body, but I come
alive with the wind. What am I?"
// Add more puzzles here...
);
$currentPuzzleNumber = $_GET['p'] ?? null;
if (!array_key_exists($currentPuzzleNumber, $puzzles)) {
header("Location: puzzle_selection.html");
exit();
}
$currentPuzzle = $puzzles[$currentPuzzleNumber];
?>
<!DOCTYPE html>
<html>
<head>
<title>Puzzle Game - Puzzle <?php echo $currentPuzzleNumber; ?></title>
</head>
<body>
<h1>Puzzle <?php echo $currentPuzzleNumber; ?></h1>
<p><?php echo $currentPuzzle; ?></p>
<form action="puzzle_submission.php?p=<?php echo $currentPuzzleNumber; ?>"
method="post">
<input type="text" name="answer" placeholder="Enter your answer">
<input type="submit" value="Submit">
</form>
<a href="puzzle_selection.html">Back to puzzle selection</a>
</body>
</html>
puzzle_submission.php
<?php
session_start();
$puzzleAnswers = array(
1 => "keyboard",
2 => "echo"
// Define correct answers for each puzzle...
);
$currentPuzzleNumber = $_GET['p'] ?? null;
if (!array_key_exists($currentPuzzleNumber, $puzzleAnswers)) {
header("Location: puzzle_selection.html");
exit();
}
$userAnswer = strtolower($_POST['answer'] ?? '');
if ($userAnswer === $puzzleAnswers[$currentPuzzleNumber]) {
$_SESSION['puzzle_success'] = true;
} else {
$_SESSION['puzzle_success'] = false;
}
header("Location: puzzle_result.php?p=$currentPuzzleNumber");
exit();
?>
puzzle_result.php
<?php
session_start();
$puzzles = array(
1 => "What has keys but can't open locks?",
2 => "I speak without a mouth and hear without ears. I have no body, but I come
alive with the wind. What am I?"
// Add more puzzles here...
);
$currentPuzzleNumber = $_GET['p'] ?? null;
if (!array_key_exists($currentPuzzleNumber, $puzzles)) {
header("Location: puzzle_selection.html");
exit();
}
$currentPuzzle = $puzzles[$currentPuzzleNumber];
$puzzleSuccess = $_SESSION['puzzle_success'] ?? null;
unset($_SESSION['puzzle_success']);
?>
<!DOCTYPE html>
<html>
<head>
<title>Puzzle Game - Puzzle Result</title>
</head>
<body>
<h1>Puzzle Result</h1>
<p>Puzzle <?php echo $currentPuzzleNumber; ?>: <?php echo $currentPuzzle; ?></p>
<?php
if ($puzzleSuccess === true) {
echo "<p>Congratulations! You solved the puzzle correctly.</p>";
} elseif ($puzzleSuccess === false) {
echo "<p>Oops! Your answer was incorrect. Keep trying!</p>";
} else {
echo "<p>No result available.</p>";
}
?>
<a href="puzzle_selection.html">Back to puzzle selection</a>
</body>
</html>



#############3PROGRAM-8: Cookies
######################################3CODING:
<?php
if (!isset($_COOKIE['visits'])) $_COOKIE['visits'] = 0;
$visits = $_COOKIE['visits'] + 1;
setcookie('visits',$visits,time()+3600*24*365);
?>
<html>
<head><style type="text/css">
div {font-size:20pt;color:navy;font-family:arial black; width:50%;background-color:white}
p{font-size:18pt;color:lime;font-weight:bold;text-align:center;font-family:bauhus 93}
.groove{border-style:groove}
.dotted{border-style:dotted}
</style></head><body bgcolor="salmon">
<?php
echo'<br><br><center><div class="groove">HIT COUNTER USING COOKIES</div><br>';
echo'<div class="dotted">';
if ($visits > 1) {
echo "<p>This is visit number $visits</p>";}
else {
echo'<p>Welcome to my Website! Click here for a tour!</p>';
}echo"<br></center></div>";
?></body></html>




#########PROGRAM-9: File / Image uploading in PHP
###################################################CODING:
upload.html
<!DOCTYPE html>
<html>
<head>
<title>File Upload</title>
</head>
<body>
<h2>Upload a File</h2>
<form action="upload.php" method="post" enctype="multipart/form-data">
<input type="file" name="fileToUpload" id="fileToUpload">
<input type="submit" value="Upload File" name="submit">
</form>
</body>
</html>
upload.php
<?php
$targetDir = "E:/"; // Specify the directory where uploaded files will be stored
$targetFile = $targetDir . basename($_FILES["fileToUpload"]["name"]);
$uploadOk = 1; // Flag to check if upload is successful
// Check if the file is an actual image or fake image
if(isset($_POST["submit"])) {
$check = getimagesize($_FILES["fileToUpload"]["tmp_name"]);
if($check !== false) {
echo "File is an image - " . $check["mime"] . ".";
$uploadOk = 1;
} else {
echo "File is not an image.";
$uploadOk = 0;
}
}
// Check if the file already exists
if (file_exists($targetFile)) {
echo "Sorry, file already exists.";
$uploadOk = 0;
}
// Check file size
if ($_FILES["fileToUpload"]["size"] > 500000) { // You can adjust the file size limit
echo "Sorry, your file is too large.";
$uploadOk = 0;
}
// Allow only certain file formats
$allowedExtensions = array("jpg", "jpeg", "png", "gif");
$fileExtension = strtolower(pathinfo($targetFile, PATHINFO_EXTENSION));
if (!in_array($fileExtension, $allowedExtensions)) {
echo "Sorry, only JPG, JPEG, PNG & GIF files are allowed.";
$uploadOk = 0;
}
// Check if $uploadOk is set to 0 by an error
if ($uploadOk == 0) {
echo "Sorry, your file was not uploaded.";
// If everything is ok, try to upload file
} else {
if (move_uploaded_file($_FILES["fileToUpload"]["tmp_name"], $targetFile)) {
echo "The file ".
htmlspecialchars(basename($_FILES["fileToUpload"]["name"])) . " has been uploaded.";
} else {
echo "Sorry, there was an error uploading your file.";
}
}
?>





