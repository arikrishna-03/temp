<!-- Web Application Development Lab — GitHub README -->

# Web Application Development Lab — 20 Programs with Output

**KIT | AI & DS**

This README contains 20 Web Application Development Lab programs with their aims, source code, expected outputs, and explanations. Each program is formatted for GitHub Markdown with syntax-highlighted code blocks.

## Table of Contents

1. [Department Profile Webpage](#experiment-1-department-profile-webpage)
2. [Library Catalogue](#experiment-2-library-catalogue-using-tables-and-lists)
3. [Student Registration Form](#experiment-3-student-registration-form)
4. [Campus Placement Registration](#experiment-4-campus-placement-registration)
5. [College Navigation Menu](#experiment-5-college-navigation-menu-with-hover)
6. [Internal and External CSS](#experiment-6-internal-and-external-css)
7. [Online Bookstore Layout](#experiment-7-online-bookstore-layout)
8. [Student Portal Menu](#experiment-8-student-portal-menu-hover-effects)
9. [Mandatory Field Validation](#experiment-9-validate-mandatory-examination-form-fields)
10. [Email and Phone Validation](#experiment-10-validate-email-and-phone-number)
11. [Update Student Marks](#experiment-11-update-student-marks-without-reloading)
12. [Live Character Counter](#experiment-12-live-character-counter)
13. [Dynamic Shopping Price](#experiment-13-dynamic-shopping-price)
14. [Login Validation](#experiment-14-login-with-predefined-credentials)
15. [Student Dashboard](#experiment-15-student-dashboard)
16. [Tic-Tac-Toe](#experiment-16-tic-tac-toe-game)
17. [Sudoku Solver](#experiment-17-sudoku-solver)
18. [Unit Converter](#experiment-18-unit-converter)
19. [Basic Calculator](#experiment-19-basic-calculator)
20. [Calculation and Conversion Utility](#experiment-20-single-page-calculation-and-conversion-utility)

> **How to use:** Copy each program into its own `.html` file and open it in a browser. Experiment 6 requires two files, `exp06.html` and `exp06.css`, saved in the same folder.

---

## Experiment 1: Department Profile Webpage

Aim: To create a department webpage using headings, paragraphs, hyperlinks, lists, bold text and highlighted announcements.

Program (`exp01.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>AI & DS Department</title>
</head>
<body>
    <h1>KIT - Department of AI &amp; DS</h1>

    <nav>
        <a href="#about">About</a> |
        <a href="#news">Announcements</a>
    </nav>

    <section id="about">
        <h2>About Us</h2>
        <p>Welcome to <b>Artificial Intelligence and Data Science</b>.</p>
        <p>We study machine learning, analytics and computing.</p>
    </section>

    <h2>Focus Areas</h2>
    <ul>
        <li>Machine Learning</li>
        <li>Data Science</li>
        <li>Web Development</li>
    </ul>

    <section id="news">
        <h2>Announcements</h2>
        <p><mark>Workshop registration is open.</mark></p>
    </section>

    <p>Contact:
        <a href="mailto:aidsoffice@example.com">Department Office</a>
    </p>
</body>
</html>
```

Expected output:

## KIT - Department of AI & DS

About | Announcements

### About Us

Welcome to Artificial Intelligence and Data Science.

We study machine learning, analytics and computing.

### Focus Areas

- Machine Learning
- Data Science
- Web Development
  ### Announcements
  Workshop registration is open.

Contact: Department Office

Explanation: `<h1>` and `<h2>` create headings, `<p>` creates paragraphs, `<ul>` and `<li>` create a list, `<a>` creates links, `<b>` makes text bold, and `<mark>` highlights text.

---

## Experiment 2: Library Catalogue Using Tables and Lists

Aim: To display book titles, authors, categories and availability using HTML tables and lists.

Program (`exp02.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Library Catalogue</title>
</head>
<body>
    <h1>College Library</h1>

    <h2>Categories</h2>
    <ul>
        <li>Computer Science</li>
        <li>Mathematics</li>
        <li>General Reading</li>
    </ul>

    <h2>Book Details</h2>
    <table border="1" cellpadding="8">
        <tr>
            <th>Title</th>
            <th>Author</th>
            <th>Category</th>
            <th>Status</th>
        </tr>
        <tr>
            <td>Python Basics</td>
            <td>John Smith</td>
            <td>Computer Science</td>
            <td>Available</td>
        </tr>
        <tr>
            <td>Data Science Intro</td>
            <td>R. Kumar</td>
            <td>Computer Science</td>
            <td>Issued</td>
        </tr>
        <tr>
            <td>Applied Mathematics</td>
            <td>A. Sharma</td>
            <td>Mathematics</td>
            <td>Available</td>
        </tr>
    </table>
</body>
</html>
```

Expected output:

## College Library

Categories

- Computer Science
- Mathematics
- General Reading

Book Details

| Title               | Author     | Category         | Status    |
| ------------------- | ---------- | ---------------- | --------- |
| Python Basics       | John Smith | Computer Science | Available |
| Data Science Intro  | R. Kumar   | Computer Science | Issued    |
| Applied Mathematics | A. Sharma  | Mathematics      | Available |

Explanation: `<table>` creates a table, `<tr>` creates a row, `<th>` creates a heading cell, and `<td>` creates a data cell. `<ul>` creates an unordered list.

---

## Experiment 3: Student Registration Form

Aim: To create a student registration form with name, register number, email, phone, department and date of birth.

Program (`exp03.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Student Registration</title>
</head>
<body>
    <h1>Student Registration</h1>

    <form id="f">
        Name:
        <input type="text" id="name" required><br><br>

        Register No:
        <input type="text" id="reg" required><br><br>

        Email:
        <input type="email" required><br><br>

        Phone:
        <input type="tel" pattern="[0-9]{10}"
               title="Enter 10 digits" required><br><br>

        Department:
        <select required>
            <option value="">Choose Department</option>
            <option>AI & DS</option>
            <option>CSE</option>
            <option>ECE</option>
            <option>IT</option>
        </select><br><br>

        Date of Birth:
        <input type="date" required><br><br>

        <button type="submit">Register</button>
        <button type="reset">Reset</button>
    </form>

    <p id="msg"></p>

    <script>
        document.getElementById("f").addEventListener("submit", function(e) {
            e.preventDefault();
            document.getElementById("msg").textContent =
                "Registration details validated successfully.";
        });
    </script>
</body>
</html>
```

Expected output:

## Student Registration

Name

Enter your name

Register No

Enter register number

Email

Enter email address

Phone

Enter 10-digit phone number

Department

Choose Department

Date of Birth

Select date

Register

Reset

On valid submission, the message “Registration details validated successfully.” appears below the form.

Explanation: HTML form controls collect student information. The `required` attribute prevents empty submissions, `type="email"` checks email format, and JavaScript displays the success message.

---

## Experiment 4: Campus Placement Registration

Aim: To create a placement form using radio buttons, checkboxes, a dropdown, Submit and Reset buttons.

Program (`exp04.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Placement Registration</title>
</head>
<body>
    <h1>Placement Registration</h1>

    <form id="f">
        Name:
        <input id="name" required><br><br>

        Interview Mode:
        <input type="radio" name="mode" value="Online" required>Online
        <input type="radio" name="mode" value="Offline">Offline

        <p>Skills:</p>
        <input type="checkbox" name="skill" value="Python">Python
        <input type="checkbox" name="skill" value="Java">Java
        <input type="checkbox" name="skill" value="Web">Web

        <p>
            Company:
            <select id="company" required>
                <option value="">Choose Company</option>
                <option>Company A</option>
                <option>Company B</option>
            </select>
        </p>

        <button type="submit">Submit</button>
        <button type="reset">Reset</button>
    </form>

    <p id="out"></p>

    <script>
        document.getElementById("f").addEventListener("submit", function(e) {
            e.preventDefault();

            let n = document.getElementById("name").value;
            let mode = document.querySelector(
                'input[name="mode"]:checked'
            ).value;
            let company = document.getElementById("company").value;
            let skills = [...document.querySelectorAll(
                'input[name="skill"]:checked'
            )].map(x => x.value);

            document.getElementById("out").textContent =
                "Registered: " + n + "; " + mode + "; " + company +
                "; Skills: " + (skills.join(", ") || "None");
        });
    </script>
</body>
</html>
```

Expected output:

- Name field
- Online and Offline radio buttons
- Python, Java and Web checkboxes
- Company dropdown
- Submit and Reset buttons

Example after submission:

```
Registered: Arjun; Online; Company A; Skills: Python, Web
```

Explanation: Radio buttons select one option, checkboxes allow multiple selections, and JavaScript displays the submitted details.

---

## Experiment 5: College Navigation Menu With Hover

Aim: To create a navigation menu with CSS hover effects.

Program (`exp05.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>College Navigation</title>
    <style>
        body {
            font-family: Arial;
            margin: 0;
        }

        nav {
            background: navy;
            padding: 15px;
            display: flex;
            gap: 10px;
        }

        nav a {
            color: white;
            text-decoration: none;
            padding: 10px;
        }

        nav a:hover {
            background: orange;
            color: black;
        }

        main {
            padding: 20px;
        }
    </style>
</head>
<body>
    <nav>
        <a href="#home">Home</a>
        <a href="#dept">Departments</a>
        <a href="#faculty">Faculty</a>
        <a href="#courses">Courses</a>
        <a href="#contact">Contact</a>
    </nav>

    <main>
        <h1 id="home">College Website</h1>
        <h2 id="dept">Departments</h2>
        <h2 id="faculty">Faculty</h2>
        <h2 id="courses">Courses</h2>
        <h2 id="contact">Contact</h2>
    </main>
</body>
</html>
```

Expected output:

Home

Departments

Faculty

Courses

Contact

## College Website

Departments

Faculty

Courses

Contact

Moving the mouse over a menu link changes its background to orange.

Explanation: CSS `:hover` applies styles when the pointer moves over an element.

---

## Experiment 6: Internal and External CSS

Aim: To style a webpage using both internal CSS and external CSS.

Create two files in the same folder.

File 1: `exp06.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Department Page</title>
    <link rel="stylesheet" href="exp06.css">

    <style>
        .notice {
            background: lightyellow;
            border-left: 5px solid orange;
            padding: 12px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Department of AI &amp; DS</h1>
    </header>

    <main>
        <h2>About</h2>
        <p>We teach computing, analytics and intelligent systems.</p>
        <p class="notice">Project registration is open.</p>
    </main>
</body>
</html>
```

File 2: `exp06.css`

```css
body {
    font-family: Arial;
    line-height: 1.6;
    margin: 0;
    color: #243447;
    background: #f4f7fb;
}

header {
    background: navy;
    color: white;
    padding: 20px;
    text-align: center;
}

main {
    max-width: 850px;
    margin: 25px auto;
    padding: 20px;
    background: white;
}

h2 {
    color: navy;
}
```

Expected output:

## Department of AI & DS

## About

We teach computing, analytics and intelligent systems.

Project registration is open.

Explanation: Internal CSS is written inside the `<style>` tag. External CSS is stored in a separate `.css` file and connected using `<link>`.

---

## Experiment 7: Online Bookstore Layout

Aim: To create a bookstore layout using CSS fonts, backgrounds, borders, margins and padding.

Program (`exp07.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Online Bookstore</title>
    <style>
        body {
            font-family: Arial;
            background: #f2f4f7;
            margin: 0;
        }

        header {
            background: #243447;
            color: white;
            padding: 20px;
            text-align: center;
        }

        .books {
            display: flex;
            gap: 18px;
            flex-wrap: wrap;
            padding: 22px;
        }

        .book {
            background: white;
            border: 1px solid gray;
            padding: 18px;
            width: 210px;
        }

        .book h2 {
            color: navy;
            font-size: 19px;
        }

        .price {
            color: green;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <header>
        <h1>Campus Bookstore</h1>
    </header>

    <main class="books">
        <section class="book">
            <h2>Python Basics</h2>
            <p>Programming</p>
            <p class="price">₹450</p>
        </section>

        <section class="book">
            <h2>HTML &amp; CSS</h2>
            <p>Web Development</p>
            <p class="price">₹350</p>
        </section>

        <section class="book">
            <h2>Data Science Guide</h2>
            <p>Data Science</p>
            <p class="price">₹550</p>
        </section>
    </main>
</body>
</html>
```

Expected output:

## Campus Bookstore

Python Basics

Programming

₹450

HTML & CSS

Web Development

₹350

Data Science Guide

Data Science

₹550

Explanation: CSS `display: flex` arranges book cards in a row. `padding`, `border`, `background` and `margin` control the layout and appearance.

---

## Experiment 8: Student Portal Menu Hover Effects

Aim: To create a student portal sidebar with hover effects.

Program (`exp08.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Student Portal</title>
    <style>
        body {
            font-family: Arial;
            margin: 0;
            background: #eef2f7;
        }

        .sidebar {
            width: 230px;
            min-height: 100vh;
            background: #172b4d;
            padding: 18px;
        }

        .sidebar h2 {
            color: white;
        }

        .sidebar a {
            display: block;
            color: white;
            text-decoration: none;
            padding: 13px;
            margin: 5px 0;
        }

        .sidebar a:hover {
            background: #4c9aff;
            transform: translateX(4px);
        }
    </style>
</head>
<body>
    <nav class="sidebar">
        <h2>Student Portal</h2>
        <a href="#profile">Profile</a>
        <a href="#attendance">Attendance</a>
        <a href="#marks">Internal Marks</a>
        <a href="#time">Timetable</a>
    </nav>
</body>
</html>
```

Expected output:

## Student Portal

Profile

Attendance

Internal Marks

Timetable

Explanation: `display: block` stacks links vertically. The `:hover` selector changes their background and shifts the link slightly.

---

## Experiment 9: Validate Mandatory Examination Form Fields

Aim: To check that mandatory fields are filled before submitting an examination registration form.

Program (`exp09.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Exam Registration</title>
</head>
<body>
    <h1>Exam Registration</h1>

    <form id="f" novalidate>
        Name:
        <input id="name"><br><br>

        Register No:
        <input id="reg"><br><br>

        Email:
        <input id="email"><br><br>

        <button type="submit">Submit</button>
    </form>

    <p id="msg"></p>

    <script>
        document.getElementById("f").addEventListener("submit", function(e) {
            e.preventDefault();

            let n = document.getElementById("name").value.trim();
            let r = document.getElementById("reg").value.trim();
            let m = document.getElementById("email").value.trim();
            let o = document.getElementById("msg");

            if (!n || !r || !m) {
                o.textContent = "Error: Fill in all mandatory fields.";
                return;
            }

            if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(m)) {
                o.textContent = "Enter a valid email.";
                return;
            }

            o.textContent = "Registration submitted successfully.";
        });
    </script>
</body>
</html>
```

Expected output:

When fields are empty:

```
Error: Fill in all mandatory fields.
```

When all fields are filled with a valid email:

```
Registration submitted successfully.
```

Explanation: JavaScript checks whether any field is empty. The regular expression checks the email format before showing success.

---

## Experiment 10: Validate Email and Phone Number

Aim: To validate an email address and a 10-digit phone number using JavaScript.

Program (`exp10.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Admission Form</title>
</head>
<body>
    <h1>Admission Form</h1>

    <form id="f" novalidate>
        Email:
        <input id="email"><br><br>

        Phone:
        <input id="phone" maxlength="10"><br><br>

        <button type="submit">Validate</button>
    </form>

    <p id="msg"></p>

    <script>
        function validateEmail(x) {
            return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(x);
        }

        function validatePhone(x) {
            return /^[0-9]{10}$/.test(x);
        }

        document.getElementById("f").addEventListener("submit", function(e) {
            e.preventDefault();

            let email = document.getElementById("email").value.trim();
            let phone = document.getElementById("phone").value.trim();
            let msg = document.getElementById("msg");

            if (!validateEmail(email)) {
                msg.textContent = "Invalid email address.";
            } else if (!validatePhone(phone)) {
                msg.textContent = "Phone must be exactly 10 digits.";
            } else {
                msg.textContent = "Email and phone are valid.";
            }
        });
    </script>
</body>
</html>
```

Expected output:

Invalid email:

```
Invalid email address.
```

Invalid phone:

```
Phone must be exactly 10 digits.
```

Valid email and phone:

```
Email and phone are valid.
```

Explanation: The `validateEmail()` and `validatePhone()` functions use regular expressions to check input formats.

---

## Experiment 11: Update Student Marks Without Reloading

Aim: To update student marks dynamically using JavaScript DOM manipulation.

Program (`exp11.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Student Result</title>
</head>
<body>
    <h1>Student Result</h1>

    <p>Student: Arjun</p>
    <p>Mark: <span id="mark">72</span></p>

    <input id="newMark" type="number"
           min="0" max="100" placeholder="Enter new mark">

    <button id="btn">Update</button>
    <p id="msg"></p>

    <script>
        document.getElementById("btn").addEventListener("click", function() {
            let f = document.getElementById("newMark");
            let n = Number(f.value);
            let m = document.getElementById("msg");

            if (f.value === "" || n < 0 || n > 100) {
                m.textContent = "Enter a mark from 0 to 100.";
                return;
            }

            document.getElementById("mark").textContent = n;
            m.textContent = "Marks updated.";
        });
    </script>
</body>
</html>
```

Expected output:

Initially:

```
Student: Arjun
Mark: 72
```

Enter `85` and click Update:

```
Student: Arjun
Mark: 85
Marks updated.
```

Explanation: JavaScript reads the new mark and updates the `<span>` using `textContent`. The page does not reload.

---

## Experiment 12: Live Character Counter

Aim: To count the number of characters typed into a feedback textarea.

Program (`exp12.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Feedback Form</title>
</head>
<body>
    <h1>Feedback</h1>

    <textarea id="feedback" maxlength="200"
              rows="6" cols="40"></textarea>

    <p>Characters: <span id="count">0</span>/200</p>

    <script>
        let f = document.getElementById("feedback");

        f.addEventListener("input", function() {
            document.getElementById("count").textContent =
                f.value.length;
        });
    </script>
</body>
</html>
```

Expected output:

## Feedback

Good college facilities

Characters: 23/200

The displayed count updates as the user types or deletes characters.

Explanation: The `input` event runs whenever the textarea changes. The `.length` property counts the characters.

---

## Experiment 13: Dynamic Shopping Price

Aim: To calculate the total shopping price whenever the quantity changes.

Program (`exp13.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Shopping Cart</title>
</head>
<body>
    <h1>Wireless Mouse</h1>

    <p>Price per item: ₹500</p>

    <label>
        Quantity:
        <input id="qty" type="number" min="1" max="99" value="1">
    </label>

    <h2>Total: ₹<span id="total">500</span></h2>
    <p id="msg"></p>

    <script>
        let q = document.getElementById("qty");

        function update() {
            let n = Number(q.value);
            let m = document.getElementById("msg");

            if (!Number.isInteger(n) || n < 1 || n > 99) {
                m.textContent = "Enter quantity 1–99.";
                return;
            }

            document.getElementById("total").textContent = n * 500;
            m.textContent = "";
        }

        q.addEventListener("input", update);
    </script>
</body>
</html>
```

Expected output:

For quantity `1`:

```
Price per item: ₹500
Quantity: 1
Total: ₹500
```

For quantity `3`:

```
Price per item: ₹500
Quantity: 3
Total: ₹1500
```

Explanation: The JavaScript function multiplies the quantity by the unit price. The `input` event recalculates the total automatically.

---

## Experiment 14: Login With Predefined Credentials

Aim: To validate a username and password using predefined credentials.

Program (`exp14.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>College Login</title>
</head>
<body>
    <h1>College Portal Login</h1>

    <form id="f">
        Username:
        <input id="user" required><br><br>

        Password:
        <input id="pass" type="password" required><br><br>

        <button type="submit">Login</button>
    </form>

    <p id="msg"></p>

    <script>
        document.getElementById("f").addEventListener("submit", function(e) {
            e.preventDefault();

            let u = document.getElementById("user").value;
            let p = document.getElementById("pass").value;
            let m = document.getElementById("msg");

            if (u === "student" && p === "kit123") {
                m.textContent = "Login successful!";
                m.style.color = "green";
            } else {
                m.textContent = "Invalid username or password.";
                m.style.color = "red";
            }
        });
    </script>
</body>
</html>
```

Expected output:

## College Portal Login

Username

student

Password

••••••

&#x20;Login successful!

Demo credentials:

- Username: `student`
- Password: `kit123`

Explanation: The `if` condition compares the entered username and password with the predefined values. This is only a classroom demonstration, not secure real-world authentication.

---

## Experiment 15: Login and Student Dashboard

Aim: To display a student dashboard after successful login.

Program (`exp15.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Student Dashboard</title>
    <style>
        .hidden {
            display: none;
        }

        section {
            padding: 10px;
            background: lightblue;
            margin: 8px 0;
        }

        nav a {
            margin-right: 12px;
        }
    </style>
</head>
<body>
    <h1>Student Portal</h1>

    <form id="f">
        <input id="user" placeholder="Username" required>
        <input id="pass" type="password"
               placeholder="Password" required>
        <button type="submit">Login</button>
    </form>

    <p id="msg"></p>

    <div id="dash" class="hidden">
        <h2>Dashboard</h2>

        <nav>
            <a href="#att">Attendance</a>
            <a href="#marks">Internal Marks</a>
            <a href="#time">Timetable</a>
            <a href="#materials">Course Materials</a>
        </nav>

        <section id="att">Attendance details</section>
        <section id="marks">Internal marks</section>
        <section id="time">Timetable</section>
        <section id="materials">Course materials</section>
    </div>

    <script>
        document.getElementById("f").addEventListener("submit", function(e) {
            e.preventDefault();

            let u = document.getElementById("user").value;
            let p = document.getElementById("pass").value;
            let ok = u === "student" && p === "kit123";

            document.getElementById("msg").textContent =
                ok ? "Login successful" : "Invalid login";

            document.getElementById("dash").classList.toggle("hidden", !ok);
        });
    </script>
</body>
</html>
```

Expected output:

Before login, only the login form appears.

After entering `student` and `kit123`:

```
Login successful

Dashboard
Attendance
Internal Marks
Timetable
Course Materials
```

Explanation: CSS hides the dashboard using `.hidden`. JavaScript validates the login and reveals the dashboard when the credentials match.

---

## Experiment 16: Two-Player Tic-Tac-Toe

Aim: To develop a two-player Tic-Tac-Toe game using JavaScript, including winner detection, draw detection and reset.

Program (`exp16.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Tic-Tac-Toe</title>
    <style>
        body {
            text-align: center;
            font-family: Arial;
        }

        #board {
            display: grid;
            grid-template-columns: repeat(3, 75px);
            gap: 5px;
            justify-content: center;
        }

        .cell {
            height: 75px;
            font-size: 28px;
        }
    </style>
</head>
<body>
    <h1>Tic-Tac-Toe</h1>
    <p id="status">Player X's turn</p>

    <div id="board"></div>
    <button id="reset">Reset</button>

    <script>
        let board = document.getElementById("board");
        let cells, turn, over;

        const wins = [
            [0,1,2], [3,4,5], [6,7,8],
            [0,3,6], [1,4,7], [2,5,8],
            [0,4,8], [2,4,6]
        ];

        function init() {
            board.innerHTML = "";
            cells = Array(9).fill("");
            turn = "X";
            over = false;

            document.getElementById("status").textContent =
                "Player X's turn";

            cells.forEach((_, i) => {
                let b = document.createElement("button");
                b.className = "cell";
                b.onclick = () => play(i, b);
                board.appendChild(b);
            });
        }

        function play(i, b) {
            if (over || cells[i]) return;

            cells[i] = turn;
            b.textContent = turn;

            if (wins.some(line => line.every(j => cells[j] === turn))) {
                document.getElementById("status").textContent =
                    "Player " + turn + " wins!";
                over = true;
            } else if (cells.every(Boolean)) {
                document.getElementById("status").textContent = "Draw!";
                over = true;
            } else {
                turn = turn === "X" ? "O" : "X";
                document.getElementById("status").textContent =
                    "Player " + turn + "'s turn";
            }
        }

        document.getElementById("reset").onclick = init;
        init();
    </script>
</body>
</html>
```

Expected output:

## Tic-Tac-Toe

Player X's turn

# X

#

# O

#

# X

#

# O

#

# X

Player X wins!

Illustrative winning arrangement

Explanation: An array stores the moves. The program checks eight winning combinations after each move, switches players and detects a draw when all cells are filled.

---

## Experiment 17: Sudoku Solver

Aim: To solve a Sudoku puzzle using JavaScript recursion and backtracking.

Program (`exp17.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Sudoku Solver</title>
    <style>
        body {
            text-align: center;
            font-family: Arial;
        }

        #grid {
            display: grid;
            grid-template-columns: repeat(9, 34px);
            justify-content: center;
        }

        #grid input {
            width: 32px;
            height: 32px;
            box-sizing: border-box;
            text-align: center;
        }
    </style>
</head>
<body>
    <h1>Sudoku Solver</h1>
    <p>Blank cells are empty. Sample puzzle is preloaded.</p>

    <div id="grid"></div>

    <p>
        <button id="solve">Solve</button>
        <button id="clear">Clear</button>
    </p>

    <p id="msg"></p>

    <script>
        const puzzle = [
            "530070000", "600195000", "098000060",
            "800060003", "400803001", "700020006",
            "060000280", "000419005", "000080079"
        ];

        const grid = document.getElementById("grid");
        const fields = [];

        for (let r = 0; r < 9; r++) {
            for (let c = 0; c < 9; c++) {
                let x = document.createElement("input");
                x.maxLength = 1;
                x.value = puzzle[r][c] === "0" ? "" : puzzle[r][c];

                x.oninput = () => {
                    x.value = /^[1-9]$/.test(x.value) ? x.value : "";
                };

                fields.push(x);
                grid.appendChild(x);
            }
        }

        function read() {
            return Array.from({length: 9}, (_, r) =>
                fields.slice(r * 9, r * 9 + 9)
                      .map(x => Number(x.value) || 0)
            );
        }

        function valid(b, r, c, n) {
            for (let i = 0; i < 9; i++) {
                if (b[r][i] === n || b[i][c] === n) return false;
            }

            let sr = Math.floor(r / 3) * 3;
            let sc = Math.floor(c / 3) * 3;

            for (let i = sr; i < sr + 3; i++) {
                for (let j = sc; j < sc + 3; j++) {
                    if (b[i][j] === n) return false;
                }
            }

            return true;
        }

        function solve(b) {
            for (let r = 0; r < 9; r++) {
                for (let c = 0; c < 9; c++) {
                    if (b[r][c] === 0) {
                        for (let n = 1; n <= 9; n++) {
                            if (valid(b, r, c, n)) {
                                b[r][c] = n;

                                if (solve(b)) return true;

                                b[r][c] = 0;
                            }
                        }

                        return false;
                    }
                }
            }

            return true;
        }

        document.getElementById("solve").onclick = () => {
            let b = read();

            if (solve(b)) {
                b.flat().forEach((n, i) => fields[i].value = n);
                document.getElementById("msg").textContent = "Puzzle solved!";
            } else {
                document.getElementById("msg").textContent = "No solution found.";
            }
        };

        document.getElementById("clear").onclick = () => {
            fields.forEach(x => x.value = "");
            document.getElementById("msg").textContent = "";
        };
    </script>
</body>
</html>
```

Expected output:

Initially, a 9 × 9 grid appears with a sample puzzle. Clicking Solve fills the grid with a solution and displays:

```
Puzzle solved!
```

Explanation: Backtracking tries numbers from 1 to 9 in empty cells. If a choice causes a conflict, it removes that number and tries another.

---

## Experiment 18: Measurement Unit Converter

Aim: To convert kilometres, miles, kilograms, pounds and temperatures using JavaScript.

Program (`exp18.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Unit Converter</title>
</head>
<body>
    <h1>Unit Converter</h1>

    <input id="value" type="number" value="1">

    <select id="type">
        <option value="km-mi">Kilometres to Miles</option>
        <option value="mi-km">Miles to Kilometres</option>
        <option value="kg-lb">Kilograms to Pounds</option>
        <option value="lb-kg">Pounds to Kilograms</option>
        <option value="c-f">Celsius to Fahrenheit</option>
        <option value="f-c">Fahrenheit to Celsius</option>
    </select>

    <button id="go">Convert</button>
    <h2 id="result"></h2>

    <script>
        document.getElementById("go").onclick = function() {
            let raw = document.getElementById("value").value;

            if (raw.trim() === "") {
                document.getElementById("result").textContent =
                    "Enter a number";
                return;
            }

            let n = Number(raw);
            let v, u;

            switch (document.getElementById("type").value) {
                case "km-mi":
                    v = n * 0.621371;
                    u = "miles";
                    break;
                case "mi-km":
                    v = n / 0.621371;
                    u = "km";
                    break;
                case "kg-lb":
                    v = n * 2.20462;
                    u = "lb";
                    break;
                case "lb-kg":
                    v = n / 2.20462;
                    u = "kg";
                    break;
                case "c-f":
                    v = n * 9 / 5 + 32;
                    u = "°F";
                    break;
                case "f-c":
                    v = (n - 32) * 5 / 9;
                    u = "°C";
                    break;
            }

            document.getElementById("result").textContent =
                v.toFixed(2) + " " + u;
        };
    </script>
</body>
</html>
```

Expected output:

For input `1` and option `Kilometres to Miles`:

```
0.62 miles
```

For input `25` and option `Celsius to Fahrenheit`:

```
77.00 °F
```

Explanation: The `switch` statement selects the appropriate conversion formula based on the dropdown selection. `toFixed(2)` displays two decimal places.

---

## Experiment 19: Basic Calculator

Aim: To perform addition, subtraction, multiplication and division using JavaScript.

Program (`exp19.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Basic Calculator</title>
</head>
<body>
    <h1>Calculator</h1>

    <input id="a" type="number" step="any"
           placeholder="First number">

    <input id="b" type="number" step="any"
           placeholder="Second number">

    <br><br>

    <button data-op="+">Add</button>
    <button data-op="-">Subtract</button>
    <button data-op="*">Multiply</button>
    <button data-op="/">Divide</button>

    <h2 id="out">Result: —</h2>

    <script>
        document.querySelectorAll("[data-op]").forEach(btn => {
            btn.onclick = function() {
                let x = document.getElementById("a").value;
                let y = document.getElementById("b").value;
                let out = document.getElementById("out");

                if (x === "" || y === "") {
                    out.textContent = "Enter both numbers";
                    return;
                }

                x = Number(x);
                y = Number(y);

                let r;

                switch (btn.dataset.op) {
                    case "+":
                        r = x + y;
                        break;
                    case "-":
                        r = x - y;
                        break;
                    case "*":
                        r = x * y;
                        break;
                    case "/":
                        if (y === 0) {
                            out.textContent =
                                "Division by zero is not allowed";
                            return;
                        }
                        r = x / y;
                        break;
                }

                out.textContent = "Result: " + r;
            };
        });
    </script>
</body>
</html>
```

Expected output:

Enter `10` and `5`.

| Operation | Output     |
| --------- | ---------- |
| Add       | Result: 15 |
| Subtract  | Result: 5  |
| Multiply  | Result: 50 |
| Divide    | Result: 2  |

If the second number is zero during division:

```
Division by zero is not allowed
```

Explanation: Each button represents an arithmetic operation. JavaScript uses `switch` to calculate the result and prevents division by zero.

---

## Experiment 20: Single-Page Calculation and Conversion Utility

Aim: To create a single-page utility that performs calculations and unit conversion with input validation.

Program (`exp20.html`):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Calculation Utility</title>
    <style>
        body {
            font-family: Arial;
            max-width: 500px;
            margin: 30px auto;
        }

        label {
            display: block;
            margin-top: 12px;
        }

        input, select, button {
            padding: 8px;
        }

        #out {
            background: #eef4fb;
            padding: 12px;
        }
    </style>
</head>
<body>
    <h1>Calculation Utility</h1>

    <label>
        Operation:
        <select id="op">
            <option value="add">Add</option>
            <option value="sub">Subtract</option>
            <option value="mul">Multiply</option>
            <option value="div">Divide</option>
            <option value="convert">Kilometres to Miles</option>
        </select>
    </label>

    <label>
        First Value:
        <input id="a" type="number" step="any">
    </label>

    <label>
        Second Value:
        <input id="b" type="number" step="any">
    </label>

    <br>
    <button id="go">Calculate</button>

    <p id="out">Result appears here.</p>

    <script>
        function calculate() {
            let op = document.getElementById("op").value;
            let x = document.getElementById("a").value;
            let y = document.getElementById("b").value;
            let out = document.getElementById("out");

            if (x.trim() === "") {
                out.textContent = "Enter a first value";
                return;
            }

            let a = Number(x);
            let b = Number(y);
            let r;

            if (op !== "convert" && y.trim() === "") {
                out.textContent = "Enter a second value";
                return;
            }

            switch (op) {
                case "add":
                    r = a + b;
                    break;
                case "sub":
                    r = a - b;
                    break;
                case "mul":
                    r = a * b;
                    break;
                case "div":
                    if (b === 0) {
                        out.textContent =
                            "Division by zero is not allowed";
                        return;
                    }
                    r = a / b;
                    break;
                case "convert":
                    r = a * 0.621371;
                    break;
            }

            out.textContent = "Result: " + Number(r.toFixed(4));
        }

        document.getElementById("go").addEventListener("click", calculate);
    </script>
</body>
</html>
```

Expected output:

For Add, enter `10` and `5`:

```
Result: 15
```

For Kilometres to Miles, enter `10`:

```
Result: 6.2137
```

For division by zero:

```
Division by zero is not allowed
```

Explanation: The program validates inputs, uses a function and `switch` to perform the selected operation, and displays the result without reloading the page.

# Quick revision before the practical exam

| Program                      | Main concept to remember          |
| ---------------------------- | --------------------------------- |
| 1. Department Profile        | Headings, links, lists            |
| 2. Library Catalogue         | Tables and lists                  |
| 3. Student Registration      | Forms and input types             |
| 4. Placement Registration    | Radio, checkbox, select           |
| 5. Navigation Menu           | CSS `:hover`                      |
| 6. Internal and External CSS | `<style>` and `.css`              |
| 7. Bookstore                 | Margin, padding, borders, Flexbox |
| 8. Portal Menu               | Hover effects                     |
| 9. Mandatory Fields          | DOM and form validation           |
| 10. Email and Phone          | Functions and regular expressions |
| 11. Update Marks             | `textContent`                     |
| 12. Character Counter        | `input` event and `.length`       |
| 13. Shopping Price           | Quantity × price                  |
| 14. Login                    | `if...else`                       |
| 15. Dashboard                | Login and show/hide               |
| 16. Tic-Tac-Toe              | Arrays and winning combinations   |
| 17. Sudoku                   | Recursion and backtracking        |
| 18. Unit Converter           | `switch` and formulas             |
| 19. Calculator               | Arithmetic operations             |
| 20. Calculation Utility      | Validation, functions and DOM     |

Exam tip: For each program, practise writing the HTML structure first, then the CSS if required, and finally the JavaScript. Remember that Program 6 needs two files, and Programs 14–15 use the demo login `student` / `kit123`.
