 <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Saad Ahmad Fazal — Data Science Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#07070f;--c1:#ff3cac;--c2:#784ba0;--c3:#2b86c5;
  --c4:#00f5a0;--c5:#f7971e;--c6:#ffd200;
  --text:#ffffff;--muted:#a0a0c0;--dim:#3a3a5c;
}
html{scroll-behavior:smooth}
body{font-family:'Space Grotesk',sans-serif;background:var(--bg);color:var(--text);overflow-x:hidden}
canvas#bg{position:fixed;top:0;left:0;width:100%;height:100%;z-index:0;pointer-events:none}
.page{position:relative;z-index:1}

.blobs{position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:0;overflow:hidden}
.blob{position:absolute;border-radius:50%;filter:blur(90px);opacity:0.09;animation:blobFloat 10s ease-in-out infinite}
.b1{width:420px;height:420px;background:var(--c1);top:-120px;left:-100px;animation-delay:0s}
.b2{width:360px;height:360px;background:var(--c3);top:35%;right:-90px;animation-delay:3.5s}
.b3{width:300px;height:300px;background:var(--c4);bottom:8%;left:28%;animation-delay:6s}
@keyframes blobFloat{0%,100%{transform:translateY(0) scale(1)}50%{transform:translateY(-45px) scale(1.12)}}

nav{display:flex;justify-content:space-between;align-items:center;padding:1rem 2.5rem;
  background:rgba(7,7,15,0.75);backdrop-filter:blur(22px);
  border-bottom:1px solid rgba(255,255,255,0.06);position:sticky;top:0;z-index:200}
.logo{font-family:'Syne',sans-serif;font-size:1.25rem;font-weight:800;
  background:linear-gradient(90deg,var(--c1),var(--c3),var(--c4));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;text-decoration:none}
.nav-links{display:flex;gap:1.75rem;align-items:center}
.nav-links a{text-decoration:none;color:var(--muted);font-size:0.77rem;
  letter-spacing:0.1em;text-transform:uppercase;transition:color 0.2s}
.nav-links a:hover{color:#fff}
.nav-cta{padding:0.45rem 1.1rem;border-radius:999px;
  background:linear-gradient(135deg,var(--c1),var(--c2));
  color:#fff !important;font-weight:600 !important;font-size:0.72rem !important;
  box-shadow:0 0 16px rgba(255,60,172,0.35);transition:box-shadow 0.2s,transform 0.2s !important}
.nav-cta:hover{box-shadow:0 0 30px rgba(255,60,172,0.6);transform:translateY(-2px) !important}

.hero{min-height:94vh;display:flex;flex-direction:column;justify-content:center;padding:4rem 2.5rem 3rem}
.badge{display:inline-flex;align-items:center;gap:0.5rem;
  background:rgba(255,60,172,0.1);border:1px solid rgba(255,60,172,0.3);
  color:var(--c1);font-size:0.68rem;letter-spacing:0.18em;text-transform:uppercase;
  padding:0.35rem 1rem;border-radius:999px;margin-bottom:1.75rem;width:fit-content;
  opacity:0;animation:riseIn 0.6s 0.1s ease forwards}
.bdot{width:7px;height:7px;border-radius:50%;background:var(--c1);animation:glowDot 1.6s infinite}
@keyframes glowDot{0%,100%{box-shadow:0 0 4px var(--c1)}50%{box-shadow:0 0 16px var(--c1),0 0 32px var(--c1)}}

h1.hname{font-family:'Syne',sans-serif;font-size:clamp(2.6rem,9vw,6.5rem);
  font-weight:800;line-height:0.95;margin-bottom:0.6rem;
  opacity:0;animation:riseIn 0.7s 0.25s ease forwards}
.grad{background:linear-gradient(135deg,var(--c1) 0%,var(--c6) 33%,var(--c4) 66%,var(--c3) 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  background-size:300% 300%;animation:gflow 5s ease infinite}
@keyframes gflow{0%{background-position:0% 50%}50%{background-position:100% 50%}100%{background-position:0% 50%}}

.hrole{font-size:clamp(1rem,2.5vw,1.45rem);color:var(--muted);font-weight:300;margin-bottom:1.5rem;
  opacity:0;animation:riseIn 0.7s 0.4s ease forwards}
.tw{color:var(--c4);font-weight:600;border-right:2px solid var(--c4);padding-right:2px;animation:cur 0.75s step-end infinite}
@keyframes cur{0%,100%{border-color:var(--c4)}50%{border-color:transparent}}

.hbio{max-width:530px;color:var(--muted);font-size:0.9rem;line-height:1.95;margin-bottom:2.5rem;
  opacity:0;animation:riseIn 0.7s 0.55s ease forwards}
.hbio strong{color:#fff}

.hbtns{display:flex;gap:1rem;flex-wrap:wrap;opacity:0;animation:riseIn 0.7s 0.7s ease forwards}
.btn-g{padding:0.85rem 2.2rem;border:none;cursor:pointer;font-family:'Space Grotesk',sans-serif;
  font-size:0.82rem;font-weight:600;letter-spacing:0.08em;border-radius:999px;
  background:linear-gradient(135deg,var(--c1),var(--c2),var(--c3));color:#fff;
  transition:transform 0.2s,box-shadow 0.2s;box-shadow:0 0 22px rgba(255,60,172,0.35);
  text-decoration:none;display:inline-flex;align-items:center;gap:0.4rem}
.btn-g:hover{transform:translateY(-3px) scale(1.03);box-shadow:0 0 44px rgba(255,60,172,0.55)}
.btn-o{padding:0.85rem 2.2rem;border:1px solid var(--dim);background:rgba(255,255,255,0.03);color:var(--muted);
  cursor:pointer;font-family:'Space Grotesk',sans-serif;font-size:0.82rem;font-weight:500;border-radius:999px;
  transition:border-color 0.2s,color 0.2s,transform 0.2s;text-decoration:none;
  display:inline-flex;align-items:center;gap:0.4rem}
.btn-o:hover{border-color:var(--c4);color:var(--c4);transform:translateY(-3px)}

.semrow{margin-top:3rem;display:flex;align-items:center;gap:0.75rem;opacity:0;animation:riseIn 0.7s 0.9s ease forwards}
.sempill{padding:0.3rem 1rem;border-radius:999px;font-size:0.68rem;font-weight:600;letter-spacing:0.1em;
  background:rgba(0,245,160,0.08);border:1px solid rgba(0,245,160,0.28);color:var(--c4)}
.semdiv{width:40px;height:1px;background:var(--dim)}
.semtxt{font-size:0.7rem;color:var(--dim);letter-spacing:0.1em;text-transform:uppercase}

section{padding:5.5rem 2.5rem;border-top:1px solid rgba(255,255,255,0.05)}
.stag{font-size:0.63rem;letter-spacing:0.28em;text-transform:uppercase;margin-bottom:0.8rem;
  display:flex;align-items:center;gap:0.55rem}
.stag::before{content:'//';font-weight:800;font-size:0.7rem}
.sh{font-family:'Syne',sans-serif;font-size:clamp(2rem,5vw,3.5rem);font-weight:800;line-height:1.05;margin-bottom:3rem}

.agrid{display:grid;grid-template-columns:1.1fr 0.9fr;gap:3.5rem;align-items:start}
.ap{color:var(--muted);font-size:0.9rem;line-height:1.95}
.ap+.ap{margin-top:1.1rem}
.ap strong{color:#fff}
.scol{display:flex;flex-direction:column;gap:0.85rem}
.sc{padding:1.3rem 1.6rem;border-radius:18px;border:1px solid rgba(255,255,255,0.07);
  background:rgba(255,255,255,0.025);transition:transform 0.25s,box-shadow 0.25s;cursor:default}
.sc:hover{transform:perspective(700px) rotateX(-4deg) rotateY(7deg) translateY(-4px);
  box-shadow:0 18px 50px rgba(0,0,0,0.5),0 0 25px rgba(255,60,172,0.1)}
.sn{font-family:'Syne',sans-serif;font-size:2.3rem;font-weight:800;
  background:linear-gradient(135deg,var(--c1),var(--c6));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;line-height:1}
.sl{font-size:0.68rem;letter-spacing:0.12em;text-transform:uppercase;color:var(--dim);margin-top:0.2rem}

.skgrid{display:grid;grid-template-columns:repeat(3,1fr);gap:1rem}
.sk{padding:1.6rem;border-radius:18px;border:1px solid rgba(255,255,255,0.06);
  background:rgba(255,255,255,0.02);transition:transform 0.25s,box-shadow 0.25s,border-color 0.25s;cursor:default}
.sk:hover{border-color:rgba(255,255,255,0.14)}
.sk:nth-child(1):hover{box-shadow:0 20px 50px rgba(255,60,172,0.18);transform:translateY(-8px)}
.sk:nth-child(2):hover{box-shadow:0 20px 50px rgba(0,245,160,0.18);transform:translateY(-8px)}
.sk:nth-child(3):hover{box-shadow:0 20px 50px rgba(247,151,30,0.18);transform:translateY(-8px)}
.sk:nth-child(4):hover{box-shadow:0 20px 50px rgba(43,134,197,0.18);transform:translateY(-8px)}
.sk:nth-child(5):hover{box-shadow:0 20px 50px rgba(255,210,0,0.18);transform:translateY(-8px)}
.sk:nth-child(6):hover{box-shadow:0 20px 50px rgba(120,75,160,0.18);transform:translateY(-8px)}
.skim{font-size:1.9rem;margin-bottom:0.8rem}
.skn{font-family:'Syne',sans-serif;font-size:1rem;font-weight:700;margin-bottom:0.4rem}
.skd{font-size:0.78rem;color:var(--muted);line-height:1.75}
.tags{display:flex;flex-wrap:wrap;gap:0.3rem;margin-top:0.8rem}
.tag{font-size:0.58rem;letter-spacing:0.08em;text-transform:uppercase;
  padding:0.2rem 0.6rem;border-radius:999px;border:1px solid rgba(255,255,255,0.1);color:var(--muted)}

.pgrid{display:grid;grid-template-columns:1fr 1fr;gap:1.25rem}
.pj{border-radius:22px;padding:2rem;position:relative;overflow:hidden;
  border:1px solid rgba(255,255,255,0.06);background:rgba(255,255,255,0.02);
  transition:transform 0.3s,box-shadow 0.3s;cursor:pointer}
.pj::before{content:'';position:absolute;inset:0;opacity:0;transition:opacity 0.3s;z-index:0}
.pj:nth-child(1)::before{background:linear-gradient(135deg,rgba(255,60,172,0.13),transparent)}
.pj:nth-child(2)::before{background:linear-gradient(135deg,rgba(0,245,160,0.13),transparent)}
.pj:nth-child(3)::before{background:linear-gradient(135deg,rgba(247,151,30,0.13),transparent)}
.pj:nth-child(4)::before{background:linear-gradient(135deg,rgba(43,134,197,0.13),transparent)}
.pj:hover::before{opacity:1}
.pj:hover{transform:translateY(-7px) scale(1.01);box-shadow:0 28px 65px rgba(0,0,0,0.5)}
.pji{position:relative;z-index:1}
.pjn{font-family:'Syne',sans-serif;font-size:0.68rem;font-weight:800;letter-spacing:0.22em;margin-bottom:1rem}
.pj:nth-child(1) .pjn{color:var(--c1)}.pj:nth-child(2) .pjn{color:var(--c4)}
.pj:nth-child(3) .pjn{color:var(--c5)}.pj:nth-child(4) .pjn{color:var(--c3)}
.pjt{font-family:'Syne',sans-serif;font-size:1.2rem;font-weight:700;margin-bottom:0.6rem}
.pjd{font-size:0.8rem;color:var(--muted);line-height:1.82}
.pjarr{position:absolute;top:1.5rem;right:1.5rem;font-size:1.05rem;color:var(--dim);transition:color 0.2s,transform 0.2s}
.pj:hover .pjarr{color:#fff;transform:translate(3px,-3px)}

.ctbox{max-width:700px;margin:0 auto;text-align:center;padding:3.5rem;border-radius:26px;
  border:1px solid rgba(255,255,255,0.07);background:rgba(255,255,255,0.02);
  position:relative;overflow:hidden}
.ctbox::before{content:'';position:absolute;top:-50%;left:-50%;width:200%;height:200%;
  background:conic-gradient(from 0deg,transparent,rgba(255,60,172,0.05),transparent,rgba(0,245,160,0.05),transparent,rgba(43,134,197,0.04),transparent);
  animation:spinBg 14s linear infinite;z-index:0}
@keyframes spinBg{to{transform:rotate(360deg)}}
.ctin{position:relative;z-index:1}
.cth{font-family:'Syne',sans-serif;font-size:2.1rem;font-weight:800;margin-bottom:0.75rem}
.ctsub{color:var(--muted);font-size:0.88rem;margin-bottom:2rem;line-height:1.85;max-width:480px;margin-left:auto;margin-right:auto}
.ctemail{display:inline-flex;align-items:center;gap:0.6rem;
  font-family:'Syne',sans-serif;font-size:1.1rem;font-weight:700;
  color:var(--c4);text-decoration:none;margin-bottom:2rem;
  border-bottom:1px solid rgba(0,245,160,0.3);padding-bottom:0.25rem;transition:color 0.2s}
.ctemail:hover{color:#fff}
.ctlinks{display:flex;justify-content:center;flex-wrap:wrap;gap:0.85rem;margin-bottom:2rem}
.cl{display:inline-flex;align-items:center;gap:0.5rem;padding:0.6rem 1.3rem;border-radius:999px;
  border:1px solid rgba(255,255,255,0.1);background:rgba(255,255,255,0.04);
  font-size:0.8rem;color:var(--muted);text-decoration:none;
  transition:border-color 0.2s,color 0.2s,background 0.2s,transform 0.2s}
.cl:hover{border-color:var(--c1);color:#fff;background:rgba(255,60,172,0.1);transform:translateY(-2px)}

footer{padding:1.5rem 2.5rem;border-top:1px solid rgba(255,255,255,0.06);
  display:flex;justify-content:space-between;align-items:center;
  font-size:0.68rem;letter-spacing:0.1em;text-transform:uppercase;color:var(--dim)}

@keyframes riseIn{from{opacity:0;transform:translateY(28px)}to{opacity:1;transform:none}}
.reveal{opacity:0;transform:translateY(28px);transition:opacity 0.8s ease,transform 0.8s ease}
.visible{opacity:1;transform:none}

@media(max-width:800px){
  .agrid,.pgrid,.skgrid{grid-template-columns:1fr}
  .nav-links{gap:1rem}
  nav{padding:1rem 1.25rem}
  section{padding:4rem 1.25rem}
  .hero{padding:3rem 1.25rem 2rem}
  .ctbox{padding:2rem 1.25rem}
}
</style>
</head>
<body>
<canvas id="bg"></canvas>
<div class="blobs"><div class="blob b1"></div><div class="blob b2"></div><div class="blob b3"></div></div>

<div class="page">

<nav>
  <a class="logo" href="#top">Saad.DS</a>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="mailto:saaddazal095@gmail.com" class="nav-cta">Hire Me</a>
  </div>
</nav>

<div class="hero" id="top">
  <div class="badge"><div class="bdot"></div>4th Semester &middot; Data Science Student</div>
  <h1 class="hname">
    <div>Hey, I'm</div>
    <div class="grad">Saad Ahmad Fazal</div>
  </h1>
  <p class="hrole">I build <span class="tw" id="tw">cool things</span> with data</p>
  <p class="hbio">A <strong>passionate Data Science student</strong> in my 4th semester, exploring machine learning, statistics, and visualization. I love turning messy data into clear stories &mdash; and I'm just getting started.</p>
  <div class="hbtns">
    <a class="btn-g" href="#projects">See My Projects &#8599;</a>
    <a class="btn-o" href="mailto:saaddazal095@gmail.com">Email Me &#9993;</a>
  </div>
  <div class="semrow">
    <span class="sempill">Semester 4</span>
    <div class="semdiv"></div>
    <div class="semtxt">Currently studying &middot; learning every day</div>
  </div>
</div>

<section id="about">
  <div class="stag" style="color:var(--c1)">About</div>
  <h2 class="sh">Who I <span class="grad">Am</span></h2>
  <div class="agrid reveal">
    <div>
      <p class="ap">I'm <strong>Saad Ahmad Fazal</strong>, a 4th semester Data Science student obsessed with patterns, numbers, and the stories hidden inside data. My journey started with curiosity and a spreadsheet &mdash; now I'm building ML models and interactive dashboards.</p>
      <p class="ap">I enjoy every part of the data lifecycle &mdash; from cleaning and exploration to modeling and visualization. I believe <strong>data science is an art</strong> as much as it is a science, and I bring that mindset to every project.</p>
      <p class="ap">Currently exploring: <strong style="color:var(--c4)">machine learning</strong>, <strong style="color:var(--c1)">data visualization</strong>, and <strong style="color:var(--c5)">NLP</strong>. Always up for a challenge.</p>
      <div style="margin-top:1.75rem">
        <a href="mailto:saaddazal095@gmail.com" class="btn-o">&#9993;&nbsp; saaddazal095@gmail.com</a>
      </div>
    </div>
    <div class="scol">
      <div class="sc"><div class="sn">4th</div><div class="sl">Semester in progress</div></div>
      <div class="sc"><div class="sn">10+</div><div class="sl">Projects &amp; assignments</div></div>
      <div class="sc"><div class="sn">3</div><div class="sl">Programming languages</div></div>
      <div class="sc"><div class="sn">&#8734;</div><div class="sl">Curiosity &amp; drive</div></div>
    </div>
  </div>
</section>

<section id="skills">
  <div class="stag" style="color:var(--c4)">Skills</div>
  <h2 class="sh">What I <span class="grad">Know</span></h2>
  <div class="skgrid reveal">
    <div class="sk">
      <div class="skim">🐍</div><div class="skn">Python</div>
      <div class="skd">My go-to language for everything data &mdash; from scraping to building ML models end to end.</div>
      <div class="tags"><span class="tag">Pandas</span><span class="tag">NumPy</span><span class="tag">Matplotlib</span></div>
    </div>
    <div class="sk">
      <div class="skim">🤖</div><div class="skn">Machine Learning</div>
      <div class="skd">Building and evaluating predictive models &mdash; classification, regression, clustering and more.</div>
      <div class="tags"><span class="tag">Scikit-learn</span><span class="tag">XGBoost</span></div>
    </div>
    <div class="sk">
      <div class="skim">📊</div><div class="skn">Data Visualization</div>
      <div class="skd">Turning numbers into beautiful, informative charts and interactive dashboards.</div>
      <div class="tags"><span class="tag">Plotly</span><span class="tag">Seaborn</span><span class="tag">Tableau</span></div>
    </div>
    <div class="sk">
      <div class="skim">🗄️</div><div class="skn">SQL</div>
      <div class="skd">Querying and structuring data from relational databases to feed analysis pipelines.</div>
      <div class="tags"><span class="tag">MySQL</span><span class="tag">PostgreSQL</span></div>
    </div>
    <div class="sk">
      <div class="skim">📈</div><div class="skn">Statistics</div>
      <div class="skd">Probability, hypothesis testing, and statistical inference &mdash; the backbone of good analysis.</div>
      <div class="tags"><span class="tag">R</span><span class="tag">SciPy</span><span class="tag">StatsModels</span></div>
    </div>
    <div class="sk">
      <div class="skim">💡</div><div class="skn">Problem Solving</div>
      <div class="skd">Breaking down complex real-world problems and finding data-driven, creative solutions.</div>
      <div class="tags"><span class="tag">Critical Thinking</span><span class="tag">Research</span></div>
    </div>
  </div>
</section>

<section id="projects">
  <div class="stag" style="color:var(--c5)">Projects</div>
  <h2 class="sh">My <span class="grad">Work</span></h2>
  <div class="pgrid reveal">
    <div class="pj">
      <div class="pjarr">&#8599;</div>
      <div class="pji">
        <div class="pjn">PROJECT 01</div>
        <div class="pjt">Student Grade Predictor</div>
        <div class="pjd">Built a regression model to predict student grades based on study habits, attendance, and past scores. Achieved 88% accuracy on test data.</div>
        <div class="tags" style="margin-top:1rem"><span class="tag">Python</span><span class="tag">Scikit-learn</span><span class="tag">Pandas</span></div>
      </div>
    </div>
    <div class="pj">
      <div class="pjarr">&#8599;</div>
      <div class="pji">
        <div class="pjn">PROJECT 02</div>
        <div class="pjt">Sales Dashboard</div>
        <div class="pjd">Interactive visualization dashboard for a mock e-commerce dataset &mdash; filters, trends, and KPIs all in one place.</div>
        <div class="tags" style="margin-top:1rem"><span class="tag">Plotly Dash</span><span class="tag">Pandas</span><span class="tag">SQL</span></div>
      </div>
    </div>
    <div class="pj">
      <div class="pjarr">&#8599;</div>
      <div class="pji">
        <div class="pjn">PROJECT 03</div>
        <div class="pjt">Sentiment Analyzer</div>
        <div class="pjd">NLP project classifying product reviews as positive, negative, or neutral using a fine-tuned text classification model.</div>
        <div class="tags" style="margin-top:1rem"><span class="tag">NLTK</span><span class="tag">Python</span><span class="tag">Matplotlib</span></div>
      </div>
    </div>
    <div class="pj">
      <div class="pjarr">&#8599;</div>
      <div class="pji">
        <div class="pjn">PROJECT 04</div>
        <div class="pjt">COVID-19 EDA</div>
        <div class="pjd">Exploratory data analysis on global COVID-19 data &mdash; time-series trends, mortality rates, and regional comparisons visualized clearly.</div>
        <div class="tags" style="margin-top:1rem"><span class="tag">Pandas</span><span class="tag">Seaborn</span><span class="tag">Plotly</span></div>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="ctbox">
    <div class="ctin">
      <div class="stag" style="color:var(--c4);justify-content:center;margin-bottom:1rem">Get in touch</div>
      <div class="cth">Let's <span class="grad">Connect</span></div>
      <p class="ctsub">I'm always open to collaborating on projects, internship opportunities, or just talking about data science. Don't be shy, Saad would love to hear from you!</p>
      <a href="mailto:saaddazal095@gmail.com" class="ctemail">&#9993; saaddazal095@gmail.com</a>
      <div class="ctlinks">
        <a href="mailto:saaddazal095@gmail.com" class="cl">📧 Email</a>
        <a href="https://github.com/" target="_blank" class="cl">🐙 GitHub</a>
        <a href="https://linkedin.com/in/" target="_blank" class="cl">💼 LinkedIn</a>
        <a href="https://kaggle.com/" target="_blank" class="cl">📓 Kaggle</a>
      </div>
      <a href="mailto:saaddazal095@gmail.com" class="btn-g">Say Hello 👋</a>
    </div>
  </div>
</section>

<footer>
  <span>&copy; 2026 Saad Ahmad Fazal</span>
  <span>Data Science &middot; Semester 4</span>
</footer>
</div>

<script>
const canvas=document.getElementById('bg'),ctx=canvas.getContext('2d');
let W,H;
const resize=()=>{W=canvas.width=window.innerWidth;H=canvas.height=window.innerHeight};
resize();window.addEventListener('resize',resize);
const colors=['#ff3cac','#784ba0','#2b86c5','#00f5a0','#f7971e','#ffd200'];
const shapes=[];
for(let i=0;i<20;i++)shapes.push({x:Math.random()*1400,y:Math.random()*900,vx:(Math.random()-.5)*.38,vy:(Math.random()-.5)*.38,size:Math.random()*38+14,type:Math.floor(Math.random()*3),rot:Math.random()*Math.PI*2,vrot:(Math.random()-.5)*.018,color:colors[Math.floor(Math.random()*colors.length)],alpha:Math.random()*.16+.05});
const pts=[];
for(let i=0;i<65;i++)pts.push({x:Math.random()*1400,y:Math.random()*900,vx:(Math.random()-.5)*.22,vy:(Math.random()-.5)*.22,r:Math.random()*1.4+.4});
function hexShape(cx,cy,r,rot){ctx.beginPath();for(let i=0;i<6;i++){const a=rot+(Math.PI/3)*i;i===0?ctx.moveTo(cx+r*Math.cos(a),cy+r*Math.sin(a)):ctx.lineTo(cx+r*Math.cos(a),cy+r*Math.sin(a));}ctx.closePath();}
function loop(){
  ctx.clearRect(0,0,W,H);const sx=W/1400,sy=H/900;
  shapes.forEach(s=>{
    s.x+=s.vx;s.y+=s.vy;s.rot+=s.vrot;
    if(s.x<-70||s.x>1470)s.vx*=-1;if(s.y<-70||s.y>970)s.vy*=-1;
    ctx.save();ctx.translate(s.x*sx,s.y*sy);ctx.rotate(s.rot);
    ctx.globalAlpha=s.alpha;ctx.strokeStyle=s.color;ctx.lineWidth=1.5;ctx.fillStyle=s.color+'1a';
    if(s.type===0){ctx.beginPath();ctx.arc(0,0,s.size,0,Math.PI*2);ctx.stroke();ctx.fill();}
    else if(s.type===1){ctx.beginPath();ctx.moveTo(0,-s.size);ctx.lineTo(s.size*.866,s.size*.5);ctx.lineTo(-s.size*.866,s.size*.5);ctx.closePath();ctx.stroke();ctx.fill();}
    else{hexShape(0,0,s.size,0);ctx.stroke();ctx.fill();}
    ctx.restore();ctx.globalAlpha=1;
  });
  pts.forEach(p=>{p.x+=p.vx;p.y+=p.vy;if(p.x<0||p.x>1400)p.vx*=-1;if(p.y<0||p.y>900)p.vy*=-1;});
  pts.forEach((a,i)=>{
    ctx.beginPath();ctx.arc(a.x*sx,a.y*sy,a.r,0,Math.PI*2);ctx.fillStyle='rgba(190,170,255,0.5)';ctx.fill();
    pts.slice(i+1).forEach(b=>{const dx=a.x-b.x,dy=a.y-b.y,d=Math.sqrt(dx*dx+dy*dy);
      if(d<105){ctx.beginPath();ctx.moveTo(a.x*sx,a.y*sy);ctx.lineTo(b.x*sx,b.y*sy);ctx.strokeStyle=`rgba(110,90,210,${.14*(1-d/105)})`;ctx.lineWidth=.5;ctx.stroke();}});
  });
  requestAnimationFrame(loop);
}
loop();

const words=['cool things','ML models','visual stories','insights','predictions','the future'];
let wi=0,ci=0,del=false;const tw=document.getElementById('tw');
function type(){const w=words[wi];if(!del){tw.textContent=w.slice(0,ci+1);ci++;if(ci===w.length){del=true;setTimeout(type,1500);return;}}else{tw.textContent=w.slice(0,ci-1);ci--;if(ci===0){del=false;wi=(wi+1)%words.length;}}setTimeout(type,del?52:92);}
type();

const obs=new IntersectionObserver(e=>{e.forEach(x=>{if(x.isIntersecting)x.target.classList.add('visible');});},{threshold:.1});
document.querySelectorAll('.reveal').forEach(el=>obs.observe(el));

document.querySelectorAll('.sk').forEach(card=>{
  card.addEventListener('mousemove',e=>{const r=card.getBoundingClientRect();const x=(e.clientX-r.left)/r.width-.5;const y=(e.clientY-r.top)/r.height-.5;card.style.transform=`perspective(600px) rotateY(${x*20}deg) rotateX(${-y*20}deg) translateY(-8px)`;});
  card.addEventListener('mouseleave',()=>{card.style.transform='';});
});

const secs=document.querySelectorAll('section[id]');
const navAs=document.querySelectorAll('.nav-links a:not(.nav-cta)');
window.addEventListener('scroll',()=>{let cur='';secs.forEach(s=>{if(window.scrollY>=s.offsetTop-120)cur=s.id;});navAs.forEach(a=>{a.style.color=a.getAttribute('href')==='#'+cur?'#fff':'';});},{passive:true});
</script>
</body>
</html>
