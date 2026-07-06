<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>WorldNexus.cc | International News, Religion & Culture</title>
<meta name="description" content="WorldNexus.cc - International News, Religion and Culture.">

<style>
:root{
--bg:#f5f5f2;
--card:#ffffff;
--text:#222;
--muted:#666;
--line:#ddd;
--accent:#8B5E3C;
--accent2:#C08A5B;
--shadow:0 10px 30px rgba(0,0,0,.08);
--radius:14px;
--max:1200px;
}

*{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth}
body{
font-family:Inter,Segoe UI,Arial,sans-serif;
background:var(--bg);
color:var(--text);
line-height:1.6;
}

img{max-width:100%}
a{text-decoration:none;color:inherit}

.container{
width:min(92%,var(--max));
margin:auto;
}

header{
position:sticky;
top:0;
z-index:99;
background:rgba(245,245,242,.95);
backdrop-filter:blur(10px);
border-bottom:1px solid var(--line);
}

.nav{
display:flex;
justify-content:space-between;
align-items:center;
padding:16px 0;
}

.logo{
font-size:1.6rem;
font-weight:800;
letter-spacing:.5px;
}

.logo span{
color:var(--accent);
}

nav{
display:flex;
gap:24px;
}

nav a{
color:var(--muted);
transition:.25s;
}

nav a:hover{
color:var(--accent);
}

.hero{
padding:80px 0 50px;
display:grid;
grid-template-columns:1.3fr .9fr;
gap:40px;
align-items:center;
}

.hero h1{
font-size:clamp(2.5rem,5vw,4.5rem);
line-height:1;
margin-bottom:20px;
}

.hero p{
color:var(--muted);
max-width:650px;
margin-bottom:30px;
}

.search-box{
background:var(--card);
padding:24px;
border-radius:var(--radius);
box-shadow:var(--shadow);
}

.search-bar{
display:flex;
gap:12px;
margin-bottom:18px;
}

.search-bar input{
flex:1;
padding:14px;
border:1px solid var(--line);
border-radius:10px;
outline:none;
font-size:1rem;
}

.search-bar input:focus{
border-color:var(--accent);
}

.options{
display:flex;
gap:10px;
flex-wrap:wrap;
}

.option{
flex:1;
min-width:100px;
padding:12px;
border:none;
border-radius:10px;
cursor:pointer;
background:#eee;
transition:.25s;
font-weight:600;
}

.option.active,
.option:hover{
background:var(--accent);
color:white;
transform:translateY(-2px);
}

.hero-card{
background:linear-gradient(135deg,#d9c3ad,#fff);
border-radius:var(--radius);
min-height:340px;
display:flex;
justify-content:center;
align-items:center;
font-size:5rem;
box-shadow:var(--shadow);
}

.section{
padding:40px 0;
}

.section-title{
display:flex;
justify-content:space-between;
align-items:center;
margin-bottom:25px;
}

.section-title h2{
font-size:2rem;
}

.filters{
display:flex;
gap:10px;
flex-wrap:wrap;
}

.filter{
padding:10px 18px;
border:none;
cursor:pointer;
border-radius:999px;
background:white;
border:1px solid var(--line);
transition:.25s;
}

.filter.active,
.filter:hover{
background:var(--accent);
color:white;
}

.grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
gap:22px;
}

.card{
background:white;
border-radius:var(--radius);
overflow:hidden;
box-shadow:var(--shadow);
transition:.35s;
display:none;
}

.card:hover{
transform:translateY(-8px);
}

.thumb{
height:190px;
background:linear-gradient(135deg,#d5d5d5,#ececec);
}

.content{
padding:20px;
}

.badge{
display:inline-block;
padding:5px 10px;
background:#eee;
border-radius:999px;
font-size:.75rem;
margin-bottom:10px;
}

.content h3{
margin-bottom:10px;
}

.content p{
color:var(--muted);
font-size:.95rem;
}

.empty{
background:white;
padding:80px 20px;
text-align:center;
border-radius:var(--radius);
border:2px dashed #ccc;
}

.empty h3{
margin-bottom:12px;
}

footer{
margin-top:70px;
border-top:1px solid var(--line);
padding:35px 0;
color:var(--muted);
text-align:center;
}

@media(max-width:850px){

.hero{
grid-template-columns:1fr;
}

nav{
display:none;
}

.hero-card{
min-height:220px;
font-size:4rem;
}

.search-bar{
flex-direction:column;
}

.option{
flex:auto;
}

}
</style>
</head>
<body>

<header>
<div class="container nav">
<div class="logo">World<span>Nexus</span>.cc</div>

<nav>
<a href="#">Home</a>
<a href="#">News</a>
<a href="#">Religion</a>
<a href="#">Culture</a>
</nav>
</div>
</header>

<section class="container hero">

<div>

<h1>International News.<br>Religion.<br>Culture.</h1>

<p>
A clean and modern publication focused on global stories, faith, and cultural perspectives.
</p>

<div class="search-box">

<div class="search-bar">
<input id="searchInput" type="text" placeholder="Search articles...">
</div>

<div class="options">
<button class="option active" data-search="news">News</button>
<button class="option" data-search="religion">Religion</button>
<button class="option" data-search="culture">Culture</button>
</div>

</div>

</div>

<div class="hero-card">
🌍
</div>

</section>

<section class="container section">

<div class="section-title">
<h2>Latest Articles</h2>

<div class="filters">
<button class="filter active" data-filter="all">All</button>
<button class="filter" data-filter="news">News</button>
<button class="filter" data-filter="religion">Religion</button>
<button class="filter" data-filter="culture">Culture</button>
</div>

</div>

<div class="grid" id="articles">

<!-- ===================================================== -->
<!-- PASTE FUTURE ARTICLES BELOW THIS COMMENT ONLY          -->
<!-- Duplicate ONE .card block and change its data-category -->
<!-- Example categories: news / religion / culture          -->
<!-- Remove display:none by simply adding cards here.       -->
<!-- ===================================================== -->

<!-- Example (DELETE THIS COMMENT, KEEP EMPTY FOR NOW)
<div class="card" data-category="news">
<div class="thumb"></div>
<div class="content">
<span class="badge">News</span>
<h3>Article Title</h3>
<p>Article description...</p>
</div>
</div>
-->

</div>

<div class="empty" id="emptyState">
<h3>No Articles Yet</h3>
<p>Your future articles will automatically appear here.</p>
</div>

</section>

<footer>
<div class="container">
© <span id="year"></span> WorldNexus.cc
</div>
</footer>

<script>

const filters=document.querySelectorAll(".filter");
const cards=document.querySelectorAll(".card");
const empty=document.getElementById("emptyState");

function updateEmpty(){
empty.style.display=cards.length===0?"block":"none";
}
updateEmpty();

filters.forEach(btn=>{
btn.onclick=()=>{

filters.forEach(b=>b.classList.remove("active"));
btn.classList.add("active");

const category=btn.dataset.filter;

cards.forEach(card=>{
const show=category==="all"||card.dataset.category===category;
card.style.display=show?"block":"none";
});

};
});

const options=document.querySelectorAll(".option");

options.forEach(btn=>{
btn.onclick=()=>{

options.forEach(o=>o.classList.remove("active"));
btn.classList.add("active");

document.getElementById("searchInput").placeholder=
"Search "+btn.dataset.search+"...";
};
});

const search=document.getElementById("searchInput");

search.addEventListener("input",function(){

const term=this.value.toLowerCase();

cards.forEach(card=>{

const text=card.innerText.toLowerCase();

card.style.display=text.includes(term)?"block":"none";

});

});

document.getElementById("year").textContent=new Date().getFullYear();

</script>

</body>
</html>
