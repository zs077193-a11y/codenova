<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CodeNova | Learn Coding</title>

<style>
*{margin:0;padding:0;box-sizing:border-box}

body{
    font-family:Arial,sans-serif;
    background:#0f172a;
    color:white;
    min-height:100vh
}

.app{
    max-width:500px;
    margin:auto;
    padding:20px 16px 90px
}

.page{
    display:none;
    animation:fadeIn .3s ease
}

.page.active{display:block}

@keyframes fadeIn{
    from{opacity:0;transform:translateY(10px)}
    to{opacity:1;transform:translateY(0)}
}

.logo{
    font-size:29px;
    font-weight:bold;
    margin-bottom:5px
}

.subtitle{
    color:#94a3b8;
    margin-bottom:25px
}

.welcome{
    background:linear-gradient(135deg,#2563eb,#7c3aed);
    padding:25px;
    border-radius:22px;
    margin-bottom:25px
}

.welcome h1{
    font-size:25px;
    margin-bottom:10px
}

.welcome p{
    color:#e2e8f0;
    line-height:1.5
}

.section-title{
    margin:22px 0 14px;
    font-size:21px
}

.courses{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:13px
}

.course{
    background:#1e293b;
    border:1px solid #334155;
    padding:18px;
    border-radius:18px;
    cursor:pointer;
    transition:.25s
}

.course:hover{
    transform:translateY(-4px);
    border-color:#60a5fa
}

.course-icon{
    font-size:30px;
    margin-bottom:8px
}

.course p,.course-item p{
    color:#94a3b8;
    font-size:13px;
    margin-top:5px;
    line-height:1.5
}

.progress-card{
    background:#1e293b;
    padding:20px;
    border-radius:20px;
    margin-top:20px
}

.progress-bar{
    height:10px;
    background:#334155;
    border-radius:10px;
    margin-top:12px;
    overflow:hidden
}

.progress-fill{
    width:0%;
    height:100%;
    background:#3b82f6;
    border-radius:10px;
    transition:.4s
}

.course-list,.lesson-list{
    display:grid;
    gap:14px
}

.course-item{
    background:#1e293b;
    padding:20px;
    border-radius:18px;
    border:1px solid #334155
}

.course-item h3{margin-bottom:8px}

.btn{
    margin-top:15px;
    border:none;
    padding:12px 18px;
    border-radius:12px;
    background:#2563eb;
    color:white;
    font-weight:bold;
    cursor:pointer
}

.btn:disabled{
    opacity:.6;
    cursor:not-allowed
}

.back-btn{
    background:#334155;
    margin-bottom:18px
}

.lesson-item{
    background:#1e293b;
    padding:18px;
    border-radius:16px;
    border:1px solid #334155;
    cursor:pointer;
    transition:.2s
}

.lesson-item:hover{
    border-color:#60a5fa;
    transform:translateY(-2px)
}

.lesson-item p{
    color:#94a3b8;
    font-size:13px;
    margin-top:6px
}

.lesson-item.completed{
    border-color:#22c55e;
    background:#14251d
}

.lesson-status{
    color:#22c55e;
    font-size:13px;
    margin-top:7px;
    display:none
}

.lesson-item.completed .lesson-status{display:block}

.lesson-card{
    background:#1e293b;
    padding:22px;
    border-radius:20px;
    border:1px solid #334155
}

.lesson-card h2{margin-bottom:15px}

.lesson-card p{
    color:#cbd5e1;
    line-height:1.7;
    margin-bottom:15px
}

.code-box{
    background:#020617;
    padding:16px;
    border-radius:12px;
    overflow-x:auto;
    margin:15px 0;
    border:1px solid #334155
}

.code-box code{
    color:#93c5fd;
    font-family:monospace;
    line-height:1.6
}

/* QUIZ */

.quiz-card{
    background:#1e293b;
    padding:22px;
    border-radius:20px;
    margin-top:15px
}

.quiz-top{
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:10px;
    margin-bottom:18px
}

.quiz-counter{
    color:#60a5fa;
    font-size:14px;
    font-weight:bold
}

.quiz-question{
    font-size:19px;
    margin-bottom:18px;
    line-height:1.5
}

.option{
    width:100%;
    padding:14px;
    margin:7px 0;
    border-radius:12px;
    border:1px solid #475569;
    background:#0f172a;
    color:white;
    text-align:left;
    cursor:pointer;
    transition:.2s;
    font-size:15px
}

.option:hover{border-color:#60a5fa}

.option.correct{
    border-color:#22c55e;
    background:#14351f
}

.option.wrong{
    border-color:#ef4444;
    background:#351919
}

.option:disabled{cursor:default}

.quiz-result{
    margin-top:15px;
    font-weight:bold;
    line-height:1.5
}

.next-btn{
    width:100%;
    display:none
}

.quiz-score{
    margin-top:20px;
    padding:22px;
    background:#0f172a;
    border-radius:18px;
    text-align:center
}

.quiz-score h2{margin-bottom:10px}

.big-score{
    font-size:42px;
    font-weight:bold;
    margin:10px 0;
    color:#60a5fa
}

.pass-text{
    color:#22c55e;
    font-weight:bold
}

.fail-text{
    color:#f87171;
    font-weight:bold
}

/* PROFILE */

.profile-card{
    background:#1e293b;
    padding:25px;
    border-radius:22px;
    text-align:center
}

.avatar{
    width:80px;
    height:80px;
    margin:auto;
    border-radius:50%;
    background:#2563eb;
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:35px;
    margin-bottom:15px
}

.stats{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:10px;
    margin-top:20px
}

.stat{
    background:#0f172a;
    padding:15px 5px;
    border-radius:14px
}

.stat strong{
    display:block;
    font-size:20px
}

.stat span{
    color:#94a3b8;
    font-size:11px
}

.badge-card{
    margin-top:20px;
    padding:18px;
    background:#0f172a;
    border-radius:18px
}

.badge{
    font-size:45px;
    margin-bottom:8px
}

/* NAV */

.bottom-nav{
    position:fixed;
    bottom:0;
    left:50%;
    transform:translateX(-50%);
    width:min(500px,100%);
    height:70px;
    background:#111827;
    border-top:1px solid #334155;
    display:flex;
    justify-content:space-around;
    align-items:center;
    z-index:100
}

.nav-btn{
    background:none;
    border:none;
    color:#94a3b8;
    font-size:12px;
    cursor:pointer;
    padding:8px 14px
}

.nav-btn span{
    display:block;
    font-size:23px;
    margin-bottom:3px
}

.nav-btn.active{color:#60a5fa}
</style>
</head>

<body>

<div class="app">

<!-- HOME -->
<section id="home" class="page active">

<div class="logo">🚀 CodeNova</div>

<div class="subtitle">
Learn. Practice. Build.
</div>

<div class="welcome">
<h1>Welcome to CodeNova 👋</h1>
<p>
Learn coding step by step and become a better developer.
</p>
</div>

<h2 class="section-title">📚 Popular Courses</h2>

<div class="courses">

<div class="course" onclick="openHtmlCourse()">
<div class="course-icon">🌐</div>
<h3>HTML</h3>
<p>Learn web structure</p>
</div>

<div class="course">
<div class="course-icon">🎨</div>
<h3>CSS</h3>
<p>Coming soon</p>
</div>

<div class="course">
<div class="course-icon">⚡</div>
<h3>JavaScript</h3>
<p>Coming soon</p>
</div>

<div class="course">
<div class="course-icon">🐍</div>
<h3>Python</h3>
<p>Coming soon</p>
</div>

</div>

<div class="progress-card">

<h2>📊 Your Progress</h2>

<p style="color:#94a3b8;margin-top:8px">
Complete HTML lessons to increase your progress.
</p>

<div class="progress-bar">
<div id="homeProgress" class="progress-fill"></div>
</div>

<p id="homeProgressText"
style="color:#60a5fa;margin-top:8px">
0% completed
</p>

</div>

</section>


<!-- COURSES -->
<section id="coursesPage" class="page">

<h1>📚 Courses</h1>

<p class="subtitle">
Choose a course and start learning.
</p>

<div class="course-list">

<div class="course-item">
<h3>🌐 HTML</h3>
<p>Learn HTML from the basics and create your first web page.</p>
<button class="btn" onclick="openHtmlCourse()">Start Learning</button>
</div>

<div class="course-item">
<h3>🎨 CSS</h3>
<p>Learn CSS and create beautiful designs.</p>
<button class="btn" disabled>Coming Soon</button>
</div>

<div class="course-item">
<h3>⚡ JavaScript</h3>
<p>Learn programming and web interaction.</p>
<button class="btn" disabled>Coming Soon</button>
</div>

<div class="course-item">
<h3>🐍 Python</h3>
<p>Learn Python programming from basics.</p>
<button class="btn" disabled>Coming Soon</button>
</div>

</div>

</section>


<!-- HTML COURSE -->
<section id="htmlCourse" class="page">

<button class="btn back-btn"
onclick="showPage('coursesPage')">
← Back to Courses
</button>

<h1>🌐 HTML Course</h1>

<p class="subtitle">
Beginner level • 4 Lessons
</p>

<div class="lesson-list">

<div id="lesson1Item"
class="lesson-item"
onclick="openLesson(1)">
<h3>📖 Lesson 1 — What is HTML?</h3>
<p>Learn the basics of HTML.</p>
<div class="lesson-status">✅ Completed</div>
</div>

<div id="lesson2Item"
class="lesson-item"
onclick="openLesson(2)">
<h3>🏷️ Lesson 2 — HTML Tags</h3>
<p>Understand HTML tags and elements.</p>
<div class="lesson-status">✅ Completed</div>
</div>

<div id="lesson3Item"
class="lesson-item"
onclick="openLesson(3)">
<h3>📝 Lesson 3 — Headings & Paragraphs</h3>
<p>Learn headings and text paragraphs.</p>
<div class="lesson-status">✅ Completed</div>
</div>

<div id="lesson4Item"
class="lesson-item"
onclick="openLesson(4)">
<h3>🔗 Lesson 4 — Links & Images</h3>
<p>Learn links and images.</p>
<div class="lesson-status">✅ Completed</div>
</div>

</div>

<div class="progress-card">

<h3>HTML Progress</h3>

<div class="progress-bar">
<div id="htmlProgress" class="progress-fill"></div>
</div>

<p id="htmlProgressText"
style="color:#60a5fa;margin-top:8px">
0 / 4 lessons completed
</p>

</div>

</section>


<!-- LESSON -->
<section id="lessonPage" class="page">

<button class="btn back-btn"
onclick="openHtmlCourse()">
← Back to Lessons
</button>

<div class="lesson-card">

<h2 id="lessonTitle"></h2>

<div id="lessonContent"></div>

<button id="completeBtn"
class="btn"
onclick="completeLesson()">
✅ Complete Lesson
</button>

</div>

</section>


<!-- QUIZ -->
<section id="quiz" class="page">

<h1>🧠 HTML Quiz</h1>

<p class="subtitle">
Test your HTML knowledge.
</p>

<div class="quiz-card">

<div class="quiz-top">
<strong>HTML Challenge</strong>

<span id="quizCounter"
class="quiz-counter">
Question 1 / 10
</span>
</div>

<div id="quizQuestion"
class="quiz-question"></div>

<div id="quizOptions"></div>

<p id="quizResult"
class="quiz-result"></p>

<button id="nextQuizBtn"
class="btn next-btn"
onclick="nextQuestion()">
Next Question →
</button>

<div id="quizScore"
class="quiz-score"
style="display:none">

<h2>🎉 Quiz Complete!</h2>

<div id="bigScore"
class="big-score">
0 / 10
</div>

<p id="percentageText">0%</p>

<p id="passText" style="margin-top:10px"></p>

<button class="btn" onclick="startQuiz()">
🔄 Retake Quiz
</button>

</div>

</div>

</section>


<!-- PROFILE -->
<section id="profile" class="page">

<h1>👤 Profile</h1>

<p class="subtitle">
Your CodeNova learning profile.
</p>

<div class="profile-card">

<div class="avatar">👨‍💻</div>

<h2>CodeNova Student</h2>

<p style="color:#94a3b8;margin-top:7px">
Future Developer 🚀
</p>

<div class="stats">

<div class="stat">
<strong>4</strong>
<span>Lessons</span>
</div>

<div class="stat">
<strong id="profileProgress">0%</strong>
<span>Progress</span>
</div>

<div class="stat">
<strong id="profileBadges">0</strong>
<span>Badges</span>
</div>

</div>

<div class="badge-card">

<div class="badge">🏆</div>

<h3>Badges</h3>

<p id="badgeText"
style="color:#94a3b8;margin-top:7px">
Complete lessons and quizzes to unlock badges.
</p>

</div>

<div class="progress-card">

<h3>🧠 Best Quiz Score</h3>

<p id="bestScore"
style="color:#60a5fa;font-size:25px;margin-top:10px">
0 / 10
</p>

</div>

</div>

</section>

</div>


<!-- BOTTOM NAV -->
<nav class="bottom-nav">

<button class="nav-btn active"
onclick="showPage('home',this)">
<span>🏠</span>
Home
</button>

<button class="nav-btn"
onclick="showPage('coursesPage',this)">
<span>📚</span>
Courses
</button>

<button class="nav-btn"
onclick="showPage('quiz',this)">
<span>🧠</span>
Quiz
</button>

<button class="nav-btn"
onclick="showPage('profile',this)">
<span>👤</span>
Profile
</button>

</nav>


<script>

/* =========================
   DATA
========================= */

let completedLessons =
Number(localStorage.getItem("codeNovaCompletedLessons")) || 0;

let bestQuizScore =
Number(localStorage.getItem("codeNovaBestQuizScore")) || 0;

let currentLesson = 1;
let currentQuestion = 0;
let currentScore = 0;


/* =========================
   LESSONS
========================= */

const lessons = {

1:{
title:"📖 Lesson 1 — What is HTML?",
content:`
<p>HTML stands for <strong>HyperText Markup Language</strong>.</p>

<p>HTML is used to create the structure of web pages.</p>

<div class="code-box">
<code>&lt;h1&gt;Hello World&lt;/h1&gt;</code>
</div>

<p>This creates a main heading on a web page.</p>
`
},

2:{
title:"🏷️ Lesson 2 — HTML Tags",
content:`
<p>HTML uses tags to tell the browser what each element means.</p>

<div class="code-box">
<code>
&lt;h1&gt;Heading&lt;/h1&gt;<br>
&lt;p&gt;Paragraph&lt;/p&gt;<br>
&lt;button&gt;Button&lt;/button&gt;
</code>
</div>

<p>HTML tags are used to structure content.</p>
`
},

3:{
title:"📝 Lesson 3 — Headings & Paragraphs",
content:`
<p>Headings are created using h1 to h6.</p>

<div class="code-box">
<code>
&lt;h1&gt;My Website&lt;/h1&gt;<br>
&lt;h2&gt;About Me&lt;/h2&gt;
</code>
</div>

<p>Paragraphs use the p tag.</p>

<div class="code-box">
<code>&lt;p&gt;Welcome to my website.&lt;/p&gt;</code>
</div>
`
},

4:{
title:"🔗 Lesson 4 — Links & Images",
content:`
<p>The a tag creates links.</p>

<div class="code-box">
<code>
&lt;a href="https://example.com"&gt;<br>
Visit Website<br>
&lt;/a&gt;
</code>
</div>

<p>The img tag displays images.</p>

<div class="code-box">
<code>
&lt;img src="image.jpg" alt="My Image"&gt;
</code>
</div>
`
}

};


/* =========================
   QUIZ QUESTIONS
========================= */

const quizQuestions=[

{
question:"What does HTML stand for?",
options:[
"Hyper Trainer Marking Language",
"HyperText Markup Language",
"HighText Machine Language",
"Hyper Tool Multi Language"
],
answer:1
},

{
question:"Which tag is used for the largest heading?",
options:[
"<heading>",
"<h6>",
"<h1>",
"<head>"
],
answer:2
},

{
question:"Which tag is used to create a paragraph?",
options:[
"<p>",
"<paragraph>",
"<text>",
"<para>"
],
answer:0
},

{
question:"Which tag is used to create a link?",
options:[
"<link>",
"<a>",
"<url>",
"<href>"
],
answer:1
},

{
question:"Which attribute specifies an image source?",
options:[
"href",
"link",
"src",
"source"
],
answer:2
},

{
question:"Which tag is used to display an image?",
options:[
"<picture>",
"<image>",
"<img>",
"<src>"
],
answer:2
},

{
question:"Which tag creates an unordered list?",
options:[
"<ol>",
"<ul>",
"<list>",
"<li>"
],
answer:1
},

{
question:"Which tag represents a list item?",
options:[
"<item>",
"<list>",
"<li>",
"<ul>"
],
answer:2
},

{
question:"Which HTML tag creates a button?",
options:[
"<button>",
"<btn>",
"<click>",
"<inputbutton>"
],
answer:0
},

{
question:"Which declaration defines an HTML5 document?",
options:[
"<html5>",
"<doctype html>",
"<!DOCTYPE html>",
"<document>"
],
answer:2
}

];


/* =========================
   NAVIGATION
========================= */

function showPage(pageId,button){

document.querySelectorAll(".page").forEach(page=>{
page.classList.remove("active");
});

const page=document.getElementById(pageId);

if(!page)return;

page.classList.add("active");

document.querySelectorAll(".nav-btn").forEach(btn=>{
btn.classList.remove("active");
});

if(button){
button.classList.add("active");
}

window.scrollTo({
top:0,
behavior:"smooth"
});

if(pageId==="profile"){
updateProfile();
}

/*
IMPORTANT FIX:
Quiz is started only when Quiz page is opened.
*/

if(pageId==="quiz"){
startQuiz();
}

}


/* =========================
   HTML COURSE
========================= */

function openHtmlCourse(){

showPage("htmlCourse");

updateProgress();

}


/* =========================
   LESSON
========================= */

function openLesson(number){

currentLesson=number;

const lesson=lessons[number];

document.getElementById("lessonTitle").innerHTML=lesson.title;

document.getElementById("lessonContent").innerHTML=lesson.content;

const completeBtn=document.getElementById("completeBtn");

const item=document.getElementById("lesson"+number+"Item");

if(item.classList.contains("completed")){

completeBtn.textContent="✅ Lesson Completed";
completeBtn.disabled=true;

}else{

completeBtn.textContent="✅ Complete Lesson";
completeBtn.disabled=false;

}

showPage("lessonPage");

}


function completeLesson(){

const item=document.getElementById(
"lesson"+currentLesson+"Item"
);

if(!item.classList.contains("completed")){

item.classList.add("completed");

completedLessons++;

if(completedLessons>4){
completedLessons=4;
}

localStorage.setItem(
"codeNovaCompletedLessons",
completedLessons
);

updateProgress();

}

const btn=document.getElementById("completeBtn");

btn.textContent="✅ Lesson Completed";
btn.disabled=true;

}


function updateProgress(){

const percentage=Math.round(
(completedLessons/4)*100
);

document.getElementById("htmlProgress").style.width=
percentage+"%";

document.getElementById("htmlProgressText").textContent=
completedLessons+" / 4 lessons completed";

document.getElementById("homeProgress").style.width=
percentage+"%";

document.getElementById("homeProgressText").textContent=
percentage+"% completed";

updateProfile();

}


function loadSavedProgress(){

for(let i=1;i<=4;i++){

const item=document.getElementById(
"lesson"+i+"Item"
);

if(i<=completedLessons && item){
item.classList.add("completed");
}

}

updateProgress();

}


/* =========================
   QUIZ
========================= */

function startQuiz(){

currentQuestion=0;
currentScore=0;

document.getElementById("quizScore").style.display="none";

document.getElementById("quizResult").textContent="";

showQuestion();

}


function showQuestion(){

const question=quizQuestions[currentQuestion];

if(!question)return;

document.getElementById("quizCounter").textContent=
"Question "+
(currentQuestion+1)+
" / "+
quizQuestions.length;

document.getElementById("quizQuestion").textContent=
question.question;

const container=document.getElementById("quizOptions");

container.innerHTML="";

question.options.forEach((option,index)=>{

const button=document.createElement("button");

button.className="option";

button.textContent=
String.fromCharCode(65+index)+". "+option;

button.addEventListener("click",function(){

selectAnswer(button,index);

});

container.appendChild(button);

});

document.getElementById("quizResult").textContent="";

document.getElementById("nextQuizBtn").style.display="none";

}


function selectAnswer(button,selectedIndex){

const question=quizQuestions[currentQuestion];

const options=document.querySelectorAll(
"#quizOptions .option"
);

options.forEach(option=>{
option.disabled=true;
});

if(selectedIndex===question.answer){

button.classList.add("correct");

currentScore++;

document.getElementById("quizResult").textContent=
"🎉 Correct!";

}else{

button.classList.add("wrong");

if(options[question.answer]){
options[question.answer].classList.add("correct");
}

document.getElementById("quizResult").textContent=
"❌ Wrong answer.";

}

if(currentQuestion<quizQuestions.length-1){

document.getElementById("nextQuizBtn").style.display=
"block";

}else{

finishQuiz();

}

}


function nextQuestion(){

currentQuestion++;

showQuestion();

}


function finishQuiz(){

const total=quizQuestions.length;

const percentage=Math.round(
(currentScore/total)*100
);

if(currentScore>bestQuizScore){

bestQuizScore=currentScore;

localStorage.setItem(
"codeNovaBestQuizScore",
bestQuizScore
);

}

document.getElementById("quizScore").style.display="block";

document.getElementById("bigScore").textContent=
currentScore+" / "+total;

document.getElementById("percentageText").textContent=
percentage+"%";

const passText=document.getElementById("passText");

if(percentage>=70){

passText.textContent=
"🏆 Excellent! You passed the quiz.";

passText.className="pass-text";

}else{

passText.textContent=
"📚 Keep learning and try again.";

passText.className="fail-text";

}

updateProfile();

}


/* =========================
   PROFILE
========================= */

function updateProfile(){

const percentage=Math.round(
(completedLessons/4)*100
);

document.getElementById("profileProgress").textContent=
percentage+"%";

let badges=0;

if(completedLessons>=4)badges++;

if(bestQuizScore>=7)badges++;

document.getElementById("profileBadges").textContent=
badges;

document.getElementById("bestScore").textContent=
bestQuizScore+" / 10";

const badgeText=document.getElementById("badgeText");

if(completedLessons>=4 && bestQuizScore>=7){

badgeText.innerHTML=
"🏆 HTML Beginner<br>🥇 Quiz Master";

}else if(completedLessons>=4){

badgeText.innerHTML=
"🏆 HTML Beginner unlocked!";

}else if(bestQuizScore>=7){

badgeText.innerHTML=
"🥇 Quiz Master unlocked!";

}else{

badgeText.innerHTML=
"Complete lessons and score 70%+ in the quiz to unlock badges.";

}

}


/* =========================
   START APP
========================= */

loadSavedProgress();
updateProfile();

</script>

</body>
</html>
