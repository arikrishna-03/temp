## 1. Department Profile

**Aim:** Use headings, paragraphs, bold text, links and highlighted
announcements.

``` html
<!DOCTYPE html>
<html>
<head>
<title>AI & DS Department</title>
</head><body>
<h1>KIT - Department of AI &amp; DS</h1>
<nav><a href="#about">About</a> | <a href="#news">Announcements</a></nav>
<section id="about">
<h2>About Us</h2>
<p>Welcome to <b>Artificial Intelligence and Data Science</b>.</p>
<p>We study machine learning, analytics and computing.</p>
</section>
<h2>Focus Areas</h2>
<ul><li>Machine Learning</li>
<li>Data Science</li>
<li>Web Development</li>
</ul>
<section id="news"><h2>Announcements</h2>
<p><mark>Workshop registration is open.</mark></p></section>
<p>Contact: <a href="mailto:aidsoffice@example.com">Department Office</a></p></body></html>
```
## 2. Library Catalogue Using Tables and Lists

**Aim:** Display book titles, authors, categories and availability.

``` html
<!DOCTYPE html>
<html>
<head><title>Library</title></head>
<body><h1>College Library</h1>
<h2>Categories</h2>
<ul><li>Computer Science</li>
<li>Mathematics</li>
<li>General Reading</li></ul>
<table border="1" cellpadding="8">
<tr><th>Title</th>
<th>Author</th>
<th>Category</th>
<th>Status</th></tr>
<tr><td>Python Basics</td>
<td>John Smith</td>
<td>Computer Science</td>
<td>Available</td></tr>
<tr><td>Data Science Intro</td>
<td>R. Kumar</td>
<td>Computer Science</td>
<td>Issued</td></tr>
<tr><td>Applied Mathematics</td>
<td>A. Sharma</td>
<td>Mathematics</td>
<td>Available</td>
</tr></table>
</body></html>
```
## 3. Student Registration Form

**Aim:** Collect name, register number, email, phone, department and
DOB.

``` html
<!DOCTYPE html>
<html>
<head><title>Registration</title></head>
<body>
<h1>Student Registration</h1>
<form id="f"><label>Name <input required id="name"></label><br><br>
<label>Register No. <input required id="reg"></label><br><br>
<label>Email <input type="email" required></label><br><br>
<label>Phone <input type="tel" pattern="[0-9]{10}" title="10 digits" required></label><br><br>
<label>Department <select required><option value="">Choose</option><option>AI &amp; DS</option><option>CSE</option><option>ECE</option><option>IT</option></select></label><br><br>
<label>DOB <input type="date" required></label><br><br><button>Register</button><button type="reset">Reset</button></form>
<p id="msg"></p><script>document.getElementById('f').addEventListener('submit',e=>{e.preventDefault();document.getElementById('msg').textContent='Registration details validated successfully.'})</script>
</body></html>
```
## 4. Campus Placement Registration

**Aim:** Demonstrate radio buttons, checkboxes, dropdown, submit/reset.

``` html
<!DOCTYPE html>
<html><head><title>Placement</title></head>
<body><h1>Placement Registration</h1>
<form id="f"><label>Name <input id="name" required></label><p>Interview mode:</p>
<label><input type="radio" name="mode" value="Online" required>Online</label><label><input type="radio" name="mode" value="Offline">Offline</label>
<p>Skills:</p><label><input type="checkbox" name="skill" value="Python">Python</label><label><input type="checkbox" name="skill" value="Java">Java</label><label><input type="checkbox" name="skill" value="Web">Web</label>
<p><select id="company" required><option value="">Choose company</option><option>Company A</option><option>Company B</option></select></p>
<button>Submit</button><button type="reset">Reset</button></form><p id="out"></p>
<script>document.getElementById('f').addEventListener('submit',e=>{e.preventDefault();let skills=[...document.querySelectorAll('[name=skill]:checked')].map(x=>x.value);document.getElementById('out').textContent='Registered: '+name.value+'; '+document.querySelector('[name=mode]:checked').value+'; '+company.value+'; Skills: '+(skills.join(', ')||'None')})</script>
</body></html>
```

**Expected output:** Submission displays chosen interview mode, company
and skills.\
**Explanation:** Radio selects one option; checkboxes allow multiple
options.

## 5. College Navigation Menu With Hover

**Aim:** Create a navigation menu with CSS hover effects.

``` html
<!DOCTYPE html><html><head><title>Navigation</title><style>
body{font-family:Arial;margin:0}nav{background:#173b63;padding:15px;display:flex;gap:10px;flex-wrap:wrap}
nav a{color:white;text-decoration:none;padding:10px;border-radius:5px}nav a:hover{background:#f0b429;color:#111}main{padding:20px}
</style></head><body><nav><a href="#home">Home</a><a href="#dept">Departments</a><a href="#faculty">Faculty</a><a href="#courses">Courses</a><a href="#contact">Contact</a></nav>
<main><h1 id="home">College Website</h1><h2 id="dept">Departments</h2><h2 id="faculty">Faculty</h2><h2 id="courses">Courses</h2><h2 id="contact">Contact</h2></main></body></html>
```

**Expected output:** Horizontal blue navigation bar; links change
appearance on hover.\
**Explanation:** `:hover` applies CSS while the pointer is over an
element.

## 6. Internal and External CSS

**Aim:** Improve readability and maintainability using internal and
external styles. **File `exp06.html`:**

``` html
<!DOCTYPE html><html><head><title>Department</title><link rel="stylesheet" href="exp06.css">
<style>.notice{background:#fff3cd;border-left:5px solid #e0a800;padding:12px}</style></head><body>
<header><h1>Department of AI &amp; DS</h1></header><main><h2>About</h2><p>We teach computing, analytics and intelligent systems.</p><p class="notice">Project registration is open.</p></main></body></html>
```

**File `exp06.css`:**

``` css
body{font-family:Arial;line-height:1.6;margin:0;color:#243447;background:#f4f7fb}
header{background:#173b63;color:white;padding:20px;text-align:center}
main{max-width:850px;margin:25px auto;padding:20px;background:white;border-radius:8px}
h2{color:#173b63}
```

**Expected output:** Blue header, readable content and highlighted
notice.\
**Explanation:** Internal CSS uses `<style>`; external CSS is linked
with `<link>`. Keep both files in the same folder.

## 7. Online Bookstore Layout

**Aim:** Style book sections with fonts, backgrounds, borders, margins
and padding.

``` html
<!DOCTYPE html><html><head><title>Bookstore</title><style>
body{font-family:Arial;background:#f2f4f7;margin:0}header{background:#243447;color:white;padding:20px;text-align:center}
.books{display:flex;gap:18px;flex-wrap:wrap;padding:22px}.book{background:white;border:1px solid #ccd3dc;border-radius:8px;padding:18px;margin:4px;width:210px}
.book h2{font-size:19px;color:#174a7e}.price{font-weight:bold;color:green}</style></head><body>
<header><h1>Campus Bookstore</h1></header><main class="books"><section class="book"><h2>Python Basics</h2><p>Programming</p><p class="price">₹450</p></section>
<section class="book"><h2>HTML &amp; CSS</h2><p>Web Development</p><p class="price">₹350</p></section>
<section class="book"><h2>Data Science Guide</h2><p>Data Science</p><p class="price">₹550</p></section></main></body></html>
```

**Expected output:** Three book cards in a flexible row.\
**Explanation:** CSS controls spacing, typography, borders and flex
layout.

## 8. Student Portal Menu Hover Effects

**Aim:** Change menu appearance when the pointer moves over links.

``` html
<!DOCTYPE html><html><head><title>Student Portal</title><style>
body{font-family:Arial;margin:0;background:#eef2f7}.sidebar{width:230px;min-height:100vh;background:#172b4d;padding:18px}
.sidebar h2{color:white}.sidebar a{display:block;color:white;text-decoration:none;padding:13px;margin:5px 0;border-radius:5px}
.sidebar a:hover{background:#4c9aff;transform:translateX(4px)}</style></head><body>
<nav class="sidebar"><h2>Student Portal</h2><a href="#profile">Profile</a><a href="#attendance">Attendance</a><a href="#marks">Internal Marks</a><a href="#time">Timetable</a></nav>
</body></html>
```

**Expected output:** Vertical menu links change colour and shift
slightly on hover.\
**Explanation:** `display:block` stacks links; `:hover` adds an
interactive effect.

## 9. Validate Mandatory Examination Form Fields

**Aim:** Prevent submission when required fields are empty.

``` html
<!DOCTYPE html><html><head><title>Exam Registration</title></head><body><h1>Exam Registration</h1>
<form id="f" novalidate><label>Name <input id="name"></label><br><br><label>Register No. <input id="reg"></label><br><br><label>Email <input id="email"></label><br><br><button>Submit</button></form><p id="msg"></p>
<script>document.getElementById('f').addEventListener('submit',e=>{e.preventDefault();let n=document.getElementById('name').value.trim(),r=document.getElementById('reg').value.trim(),m=document.getElementById('email').value.trim(),o=document.getElementById('msg');
if(!n||!r||!m){o.textContent='Error: Fill in all mandatory fields.';return}
if(!/^[^\\s@]+@[^\\s@]+\\.[^\\s@]+$/.test(m)){o.textContent='Enter a valid email.';return}o.textContent='Registration submitted successfully.'})</script></body></html>
```

**Expected output:** Empty fields show an error; valid data shows
success.\
**Explanation:** DOM values are checked before accepting submission.

## 10. Validate Email and Phone

**Aim:** Reject invalid emails and phone numbers containing letters.

``` html
<!DOCTYPE html><html><head><title>Admission Validation</title></head><body><h1>Admission Form</h1>
<form id="f" novalidate><label>Email <input id="email"></label><br><br><label>Phone (10 digits) <input id="phone" maxlength="10"></label><br><br><button>Validate</button></form><p id="msg"></p>
<script>
function validateEmail(x){return /^[^\\s@]+@[^\\s@]+\\.[^\\s@]+$/.test(x)}
function validatePhone(x){return /^[0-9]{10}$/.test(x)}
document.getElementById('f').addEventListener('submit',e=>{e.preventDefault();let m=document.getElementById('msg'),email=document.getElementById('email').value.trim(),phone=document.getElementById('phone').value.trim();
if(!validateEmail(email))m.textContent='Invalid email address.';else if(!validatePhone(phone))m.textContent='Phone must be exactly 10 digits.';else m.textContent='Email and phone are valid.'})
</script></body></html>
```

**Expected output:** Error for invalid input; success for a valid email
and ten-digit phone.\
**Explanation:** Functions use regular expressions to validate formats.

## 11. Update Student Marks Without Reloading

**Aim:** Update displayed marks with a button and DOM manipulation.

``` html
<!DOCTYPE html><html><head><title>Student Result</title></head><body><h1>Student Result</h1><p>Student: Arjun</p>
<p>Mark: <span id="mark">72</span></p><input id="newMark" type="number" min="0" max="100" placeholder="New mark"><button id="btn">Update</button><p id="msg"></p>
<script>document.getElementById('btn').addEventListener('click',()=>{let f=document.getElementById('newMark'),n=Number(f.value),m=document.getElementById('msg');
if(f.value===''||n<0||n>100){m.textContent='Enter a mark from 0 to 100.';return}
document.getElementById('mark').textContent=n;m.textContent='Marks updated.'})</script></body></html>
```

**Expected output:** Entering 85 changes the mark from 72 to 85 without
page reload.\
**Explanation:** `textContent` updates the DOM element.

## 12. Live Character Counter

**Aim:** Update a character count while typing or deleting feedback.

``` html
<!DOCTYPE html><html><head><title>Feedback</title></head><body><h1>Feedback</h1><textarea id="feedback" maxlength="200" rows="6" cols="40"></textarea>
<p>Characters: <span id="count">0</span>/200</p><script>
let f=document.getElementById('feedback');f.addEventListener('input',()=>document.getElementById('count').textContent=f.value.length)
</script></body></html>
```

**Expected output:** Counter updates immediately, from 0 up to 200.\
**Explanation:** The `input` event fires when the field's value changes;
`.length` counts characters.

## 13. Dynamic Shopping Price

**Aim:** Update total price when quantity changes.

``` html
<!DOCTYPE html><html><head><title>Shopping Cart</title></head><body><h1>Wireless Mouse</h1><p>Price per item: ₹500</p>
<label>Quantity <input id="qty" type="number" min="1" max="99" value="1"></label><h2>Total: ₹<span id="total">500</span></h2><p id="msg"></p>
<script>let q=document.getElementById('qty');function update(){let n=Number(q.value),m=document.getElementById('msg');if(!Number.isInteger(n)||n<1||n>99){m.textContent='Enter quantity 1–99.';return}
document.getElementById('total').textContent=n*500;m.textContent=''}q.addEventListener('input',update)</script></body></html>
```

**Expected output:** Quantity 3 displays ₹1500.\
**Explanation:** The `input` event recalculates unit price × quantity.

## 14. Login With Predefined Credentials

**Aim:** Check username and password and show a status message.

``` html
<!DOCTYPE html><html><head><title>Portal Login</title></head><body><h1>College Portal Login</h1>
<form id="f"><label>Username <input id="user" required></label><br><br><label>Password <input id="pass" type="password" required></label><br><br><button>Login</button></form><p id="msg"></p>
<script>document.getElementById('f').addEventListener('submit',e=>{e.preventDefault();let ok=document.getElementById('user').value==='student'&&document.getElementById('pass').value==='kit123',m=document.getElementById('msg');m.textContent=ok?'Login successful!':'Invalid username or password.';m.style.color=ok?'green':'red'})</script></body></html>
```

**Expected output:** Demo username `student`, password `kit123` shows
success; other values show an error.\
**Explanation:** Uses an `if` condition to compare credentials.
Client-side credentials are not secure for real authentication.

## 15. Login and Student Dashboard

**Aim:** Validate login and reveal Attendance, Internal Marks, Timetable
and Course Materials.

``` html
<!DOCTYPE html><html><head><title>Dashboard</title><style>.hidden{display:none}section{padding:10px;background:#eef4fb;margin:8px 0}nav a{margin-right:12px}</style></head><body>
<h1>Student Portal</h1><form id="f"><input id="user" placeholder="Username" required><input id="pass" type="password" placeholder="Password" required><button>Login</button></form><p id="msg"></p>
<div id="dash" class="hidden"><h2>Dashboard</h2><nav><a href="#att">Attendance</a><a href="#marks">Internal Marks</a><a href="#time">Timetable</a><a href="#materials">Course Materials</a></nav>
<section id="att">Attendance details</section><section id="marks">Internal marks</section><section id="time">Timetable</section><section id="materials">Course materials</section></div>
<script>document.getElementById('f').addEventListener('submit',e=>{e.preventDefault();let ok=user.value==='student'&&pass.value==='kit123';document.getElementById('msg').textContent=ok?'Login successful':'Invalid login';document.getElementById('dash').classList.toggle('hidden',!ok)})</script></body></html>
```

**Expected output:** Correct demo login reveals dashboard and section
links.\
**Explanation:** CSS hides the dashboard until JavaScript validates the
login.

## 16. Two-Player Tic-Tac-Toe

**Aim:** Alternate turns, detect wins/draws and reset the game.

``` html
<!DOCTYPE html><html><head><title>Tic-Tac-Toe</title><style>body{text-align:center;font-family:Arial}#board{display:grid;grid-template-columns:repeat(3,75px);gap:5px;justify-content:center}.cell{height:75px;font-size:28px}</style></head><body>
<h1>Tic-Tac-Toe</h1><p id="status">Player X's turn</p><div id="board"></div><button id="reset">Reset</button>
<script>let board=document.getElementById('board'),cells,turn,over;const wins=[[0,1,2],[3,4,5],[6,7,8],[0,3,6],[1,4,7],[2,5,8],[0,4,8],[2,4,6]];
function init(){board.innerHTML='';cells=Array(9).fill('');turn='X';over=false;status.textContent="Player X's turn";cells.forEach((_,i)=>{let b=document.createElement('button');b.className='cell';b.onclick=()=>play(i,b);board.appendChild(b)})}
function play(i,b){if(over||cells[i])return;cells[i]=turn;b.textContent=turn;if(wins.some(line=>line.every(j=>cells[j]===turn))){status.textContent='Player '+turn+' wins!';over=true}else if(cells.every(Boolean)){status.textContent='Draw!';over=true}else{turn=turn==='X'?'O':'X';status.textContent="Player "+turn+"'s turn"}}
document.getElementById('reset').onclick=init;init();</script></body></html>
```

**Expected output:** 3×3 board, alternating X/O turns, winner/draw
message and reset.\
**Explanation:** Array stores moves; winning combinations are checked
after every turn.

## 17. Sudoku Solver

**Aim:** Enter a Sudoku grid and solve it with JavaScript backtracking.

``` html
<!DOCTYPE html><html><head><title>Sudoku Solver</title><style>body{text-align:center;font-family:Arial}#grid{display:grid;grid-template-columns:repeat(9,34px);justify-content:center}#grid input{width:32px;height:32px;box-sizing:border-box;text-align:center}</style></head><body>
<h1>Sudoku Solver</h1><p>Blank cells are empty. Sample puzzle is preloaded.</p><div id="grid"></div><p><button id="solve">Solve</button><button id="clear">Clear</button></p><p id="msg"></p>
<script>const puzzle=['530070000','600195000','098000060','800060003','400803001','700020006','060000280','000419005','000080079'],grid=document.getElementById('grid'),fields=[];
for(let r=0;r<9;r++)for(let c=0;c<9;c++){let x=document.createElement('input');x.maxLength=1;x.value=puzzle[r][c]==='0'?'':puzzle[r][c];x.oninput=()=>x.value=/^[1-9]$/.test(x.value)?x.value:'';fields.push(x);grid.appendChild(x)}
function read(){return Array.from({length:9},(_,r)=>fields.slice(r*9,r*9+9).map(x=>Number(x.value)||0))}
function valid(b,r,c,n){for(let i=0;i<9;i++)if(b[r][i]===n||b[i][c]===n)return false;let sr=Math.floor(r/3)*3,sc=Math.floor(c/3)*3;for(let i=sr;i<sr+3;i++)for(let j=sc;j<sc+3;j++)if(b[i][j]===n)return false;return true}
function solve(b){for(let r=0;r<9;r++)for(let c=0;c<9;c++)if(!b[r][c]){for(let n=1;n<=9;n++)if(valid(b,r,c,n)){b[r][c]=n;if(solve(b))return true;b[r][c]=0}return false}return true}
document.getElementById('solve').onclick=()=>{let b=read();if(solve(b)){b.flat().forEach((n,i)=>fields[i].value=n);msg.textContent='Puzzle solved!'}else msg.textContent='No solution found.'};
document.getElementById('clear').onclick=()=>{fields.forEach(x=>x.value='');msg.textContent=''};</script></body></html>
```

**Expected output:** The preloaded puzzle fills with a solution when
Solve is clicked.\
**Explanation:** Recursive backtracking tries valid numbers in empty
cells and backtracks when a choice fails.

## 18. Measurement Unit Converter

**Aim:** Convert common units based on user-selected options.

``` html
<!DOCTYPE html><html><head><title>Unit Converter</title></head><body><h1>Unit Converter</h1>
<input id="value" type="number" value="1"><select id="type"><option value="km-mi">Kilometres to Miles</option><option value="mi-km">Miles to Kilometres</option><option value="kg-lb">Kilograms to Pounds</option><option value="lb-kg">Pounds to Kilograms</option><option value="c-f">Celsius to Fahrenheit</option><option value="f-c">Fahrenheit to Celsius</option></select><button id="go">Convert</button><h2 id="result"></h2>
<script>document.getElementById('go').onclick=()=>{let raw=value.value,n=Number(raw);if(raw.trim()===''){result.textContent='Enter a number';return}let v,u;switch(type.value){case'km-mi':v=n*.621371;u='miles';break;case'mi-km':v=n/.621371;u='km';break;case'kg-lb':v=n*2.20462;u='lb';break;case'lb-kg':v=n/2.20462;u='kg';break;case'c-f':v=n*9/5+32;u='°F';break;case'f-c':v=(n-32)*5/9;u='°C'}result.textContent=v.toFixed(2)+' '+u}</script></body></html>
```

**Expected output:** `1` kilometre converts to approximately
`0.62 miles`.\
**Explanation:** `switch` selects a formula according to the dropdown.

## 19. Basic Calculator

**Aim:** Addition, subtraction, multiplication and division with
zero-division handling.

``` html
<!DOCTYPE html><html><head><title>Calculator</title></head><body><h1>Calculator</h1>
<input id="a" type="number" step="any" placeholder="First number"><input id="b" type="number" step="any" placeholder="Second number"><br>
<button data-op="+">Add</button><button data-op="-">Subtract</button><button data-op="*">Multiply</button><button data-op="/">Divide</button><h2 id="out">Result: —</h2>
<script>document.querySelectorAll('[data-op]').forEach(btn=>btn.onclick=()=>{let x=a.value,y=b.value;if(x===''||y===''){out.textContent='Enter both numbers';return}x=Number(x);y=Number(y);let r;switch(btn.dataset.op){case'+':r=x+y;break;case'-':r=x-y;break;case'*':r=x*y;break;case'/':if(y===0){out.textContent='Division by zero is not allowed';return}r=x/y}out.textContent='Result: '+r})</script></body></html>
```

**Expected output:** Inputs 10 and 5 yield 15, 5 or 50 or 2 according to
operation; division by zero shows an error.\
**Explanation:** Buttons select an operator and JavaScript computes the
result.

## 20. Single-Page Calculation/Conversion Utility

**Aim:** Validate input, calculate or convert, and display results
dynamically.

``` html
<!DOCTYPE html><html><head><title>Utility</title><style>body{font-family:Arial;max-width:500px;margin:30px auto}label{display:block;margin-top:12px}input,select,button{padding:8px}#out{background:#eef4fb;padding:12px}</style></head><body>
<h1>Calculation Utility</h1><label>Operation <select id="op"><option value="add">Add</option><option value="sub">Subtract</option><option value="mul">Multiply</option><option value="div">Divide</option><option value="convert">Kilometres to miles</option></select></label>
<label>First value <input id="a" type="number" step="any"></label><label>Second value (not needed for conversion) <input id="b" type="number" step="any"></label><button id="go">Calculate</button><p id="out">Result appears here.</p>
<script>function calculate(){let op=document.getElementById('op').value,x=document.getElementById('a').value,y=document.getElementById('b').value,o=document.getElementById('out');if(x.trim()===''){o.textContent='Enter a first value';return}let a=Number(x),b=Number(y),r;if(op!=='convert'&&y.trim()===''){o.textContent='Enter a second value';return}
switch(op){case'add':r=a+b;break;case'sub':r=a-b;break;case'mul':r=a*b;break;case'div':if(b===0){o.textContent='Division by zero is not allowed';return}r=a/b;break;case'convert':r=a*.621371}
o.textContent='Result: '+Number(r.toFixed(4))}
document.getElementById('go').addEventListener('click',calculate)</script></body></html>
```
