
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
| 19. Calculator               | Arithmetic operations             |
| 20. Calculation Utility      | Validation, functions and DOM     |

Exam tip: For each program, practise writing the HTML structure first, then the CSS if required, and finally the JavaScript. Remember that Program 6 needs two files, and Programs 14–15 use the demo login `student` / `kit123`.
