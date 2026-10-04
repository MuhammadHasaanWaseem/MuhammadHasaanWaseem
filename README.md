<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Muhammad Hasaan · React Native & Full Stack Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,500;12..96,700;12..96,800&family=Figtree:wght@400;500;600&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#F2F5FB; --surface:#FFFFFF; --ink:#101833; --muted:#55607E; --line:#DDE3F0;
  --accent:#2F5BFF; --accent-ink:#FFFFFF; --mint:#0FA37F; --chip:#E8EEFF; --phone:#101833;
  --display:'Bricolage Grotesque','Segoe UI',system-ui,sans-serif;
  --body:'Figtree','Segoe UI',system-ui,sans-serif;
  box-sizing:border-box;
  padding-top:env(safe-area-inset-top,0px);
  padding-bottom:env(safe-area-inset-bottom,0px);
}
@media (prefers-color-scheme:dark){
  :root:not([data-theme="light"]){
    --bg:#0D1226; --surface:#151B36; --ink:#EEF1FB; --muted:#9AA5C8; --line:#262E52;
    --accent:#6C8BFF; --accent-ink:#0D1226; --mint:#3FD6AE; --chip:#1E2750; --phone:#05081A;
  }
}
:root[data-theme="dark"]{
  --bg:#0D1226; --surface:#151B36; --ink:#EEF1FB; --muted:#9AA5C8; --line:#262E52;
  --accent:#6C8BFF; --accent-ink:#0D1226; --mint:#3FD6AE; --chip:#1E2750; --phone:#05081A;
}
html{scroll-padding-top:env(safe-area-inset-top,0px);scroll-behavior:smooth}
*,*::before,*::after{box-sizing:inherit}
body{margin:0;background:var(--bg);color:var(--ink);font:400 17px/1.6 var(--body);-webkit-font-smoothing:antialiased}
a{color:inherit}
:focus-visible{outline:3px solid var(--accent);outline-offset:3px;border-radius:6px}
.wrap{max-width:1080px;margin:0 auto;padding:0 24px}
h1,h2,h3{font-family:var(--display);line-height:1.1;margin:0;letter-spacing:-.02em}

/* nav */
header.top{display:flex;align-items:center;justify-content:space-between;padding:20px 0}
.brand{font:800 20px var(--display);text-decoration:none}
.top nav{display:flex;gap:20px;align-items:center;font-size:15px;font-weight:500}
.top nav a{text-decoration:none;color:var(--muted)}
.top nav a:hover{color:var(--ink)}
#theme{background:var(--surface);border:1px solid var(--line);color:var(--ink);border-radius:999px;width:38px;height:38px;cursor:pointer;font-size:16px}

/* hero */
.hero{display:grid;grid-template-columns:1.15fr .85fr;gap:48px;align-items:center;padding:48px 0 88px}
.hero h1{font-size:clamp(40px,6.4vw,76px);font-weight:800}
.hero p.lead{font-size:20px;color:var(--muted);max-width:34em;margin:22px 0 30px}
.btns{display:flex;gap:12px;flex-wrap:wrap}
.btn{display:inline-block;padding:13px 22px;border-radius:12px;font-weight:600;text-decoration:none;border:1px solid var(--line);background:var(--surface)}
.btn.primary{background:var(--accent);color:var(--accent-ink);border-color:var(--accent)}
.facts{display:flex;gap:28px;flex-wrap:wrap;margin-top:34px;color:var(--muted);font-size:15px}
.facts b{display:block;color:var(--ink);font:700 22px var(--display)}

/* phone */
.phone{width:min(320px,100%);margin:0 auto;background:var(--phone);border-radius:44px;padding:12px;box-shadow:0 30px 60px -24px rgba(16,24,51,.45)}
.screen{background:linear-gradient(160deg,#2F5BFF 0%,#6A3DF0 55%,#0FA37F 120%);border-radius:34px;padding:22px 18px 18px;min-height:520px;display:flex;flex-direction:column;color:#fff}
.status{display:flex;justify-content:space-between;font-size:12px;font-weight:600;opacity:.9;margin-bottom:22px}
.apps{display:grid;grid-template-columns:repeat(3,1fr);gap:16px 8px}
.app{background:none;border:0;color:inherit;font:inherit;cursor:pointer;text-align:center;padding:0}
.app i{display:grid;place-items:center;width:62px;height:62px;margin:0 auto 6px;border-radius:17px;font:800 22px var(--display);font-style:normal;color:#fff;transition:transform .15s,box-shadow .15s}
.app span{font-size:11.5px;font-weight:500}
.app[aria-pressed="true"] i{transform:scale(1.08);box-shadow:0 0 0 3px #fff}
.sheet{margin-top:auto;background:rgba(255,255,255,.96);color:#101833;border-radius:22px;padding:16px}
.sheet h3{font-size:19px}
.sheet .plat{font-size:12.5px;color:#55607E;margin:2px 0 10px}
.chips{display:flex;flex-wrap:wrap;gap:6px}
.chips span{background:#E8EEFF;color:#1B2B78;border-radius:8px;padding:3px 9px;font-size:12px;font-weight:500}
.hint{font-size:13px;color:var(--muted);text-align:center;margin-top:14px}

/* sections */
section{padding:72px 0;border-top:1px solid var(--line)}
section h2{font-size:clamp(28px,4vw,40px);margin-bottom:34px}
.about{display:grid;grid-template-columns:1fr 1fr;gap:40px}
.about p{margin:0 0 14px;color:var(--muted)}
.about ul{margin:0;padding:0;list-style:none;display:grid;gap:12px}
.about li{background:var(--surface);border:1px solid var(--line);border-radius:14px;padding:14px 16px}
.about li b{font-family:var(--display)}

.timeline{position:relative;margin-left:8px;padding-left:28px;border-left:2px solid var(--line);display:grid;gap:30px}
.job{position:relative}
.job::before{content:"";position:absolute;left:-37px;top:8px;width:14px;height:14px;border-radius:50%;background:var(--accent);box-shadow:0 0 0 4px var(--bg)}
.job h3{font-size:21px}
.job .co{color:var(--mint);font-weight:600;margin:2px 0 8px}
.job p{margin:0;color:var(--muted);max-width:62ch}

.skills{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:18px}
.skill{background:var(--surface);border:1px solid var(--line);border-radius:16px;padding:20px}
.skill h3{font-size:17px;margin-bottom:12px}
.skill .chips span{background:var(--chip);color:var(--ink)}

.edu{background:var(--surface);border:1px solid var(--line);border-radius:16px;padding:24px;display:flex;justify-content:space-between;gap:16px;flex-wrap:wrap}
.edu h3{font-size:21px}
.edu p{margin:4px 0 0;color:var(--muted)}
.cgpa{font:800 40px var(--display);color:var(--accent)}
.cgpa small{display:block;font:500 13px var(--body);color:var(--muted)}

.contact p{color:var(--muted);max-width:46ch;margin:0 0 24px}
footer{padding:30px 0 40px;color:var(--muted);font-size:14px;border-top:1px solid var(--line)}

@media (max-width:820px){
  .hero{grid-template-columns:1fr;padding-bottom:56px}
  .about{grid-template-columns:1fr}
  .top nav a:not(#theme){display:none}
}
@media (prefers-reduced-motion:reduce){*{transition:none!important;scroll-behavior:auto!important}}
</style>
</head>
<body>
<div class="wrap">
  <header class="top">
    <a class="brand" href="#">Hasaan</a>
    <nav>
      <a href="#about">About</a><a href="#experience">Experience</a><a href="#skills">Skills</a><a href="#contact">Contact</a>
      <button id="theme" aria-label="Toggle light and dark theme">◐</button>
    </nav>
  </header>

  <main>
    <div class="hero">
      <div>
        <h1>I build mobile apps people keep on their home screen.</h1>
        <p class="lead">I'm Muhammad Hasaan, a software engineer in Lahore. I build Android and iOS apps with React Native, and the backends behind them.</p>
        <div class="btns">
          <a class="btn primary" href="mailto:muhammadhasaanwork@gmail.com">Email me</a>
          <a class="btn" href="https://github.com/MUHAMMADHASAANWASEEM" target="_blank" rel="noopener">GitHub</a>
          <a class="btn" href="https://www.linkedin.com/in/muhammad-hasaan-0499ba344/" target="_blank" rel="noopener">LinkedIn</a>
        </div>
        <div class="facts">
          <div><b>5</b>apps shipped</div>
          <div><b>3</b>teams</div>
          <div><b>iOS · Android · Web</b>platforms</div>
        </div>
      </div>

      <div>
        <div class="phone" role="group" aria-label="My apps">
          <div class="screen">
            <div class="status"><span>9:41</span><span>Apps by Hasaan</span></div>
            <div class="apps" id="apps"></div>
            <div class="sheet" aria-live="polite">
              <h3 id="pName"></h3>
              <div class="plat" id="pPlat"></div>
              <div class="chips" id="pTech"></div>
            </div>
          </div>
        </div>
        <p class="hint">Tap an app to see what's inside.</p>
      </div>
    </div>

    <section id="about">
      <h2>About</h2>
      <div class="about">
        <div>
          <p>I specialize in mobile (Android and iOS) and web development. I graduated in Software Engineering from Lahore Garrison University, and I like building modern, user-focused applications while learning something new on every project.</p>
          <p>Most of my work is React Native on the front, with Supabase, Firebase or Node.js behind it.</p>
        </div>
        <ul>
          <li><b>Native touches.</b> Home-screen widgets, Apple Watch, HealthKit and Health Connect.</li>
          <li><b>Payments.</b> Subscriptions and in-app purchases with RevenueCat, plus Stripe.</li>
          <li><b>AI features.</b> OpenAI and Gemini inside shipped apps.</li>
        </ul>
      </div>
    </section>

    <section id="experience">
      <h2>Experience</h2>
      <div class="timeline">
        <div class="job">
          <h3>Full Stack Software Developer</h3>
          <div class="co">Tectsoft, Lahore</div>
          <p>Led development of a cross-platform Android and iOS app in React Native, with a scalable architecture and reusable components. Integrated third-party and REST APIs securely, in close collaboration with the team.</p>
        </div>
        <div class="job">
          <h3>Full Stack Developer</h3>
          <div class="co">Upvave, Lahore</div>
          <p>Led end-to-end development with React, React Native and Node.js. Delivered production-ready interfaces and scalable backends, tuned performance, and used Docker for consistent development and deployment.</p>
        </div>
        <div class="job">
          <h3>Full Stack React Native Developer</h3>
          <div class="co">724-one, Lahore</div>
          <p>Built end-to-end solutions with React, React Native, Firebase and Node.js. Shipped multiple full-stack projects with a focus on performance and user experience.</p>
        </div>
      </div>
    </section>

    <section id="skills">
      <h2>Skills</h2>
      <div class="skills" id="skillGrid"></div>
    </section>

    <section id="education">
      <h2>Education</h2>
      <div class="edu">
        <div>
          <h3>Bachelor of Science in Software Engineering</h3>
          <p>Lahore Garrison University · Sep 2021 – Jun 2025</p>
        </div>
        <div class="cgpa">3.47<small>CGPA</small></div>
      </div>
    </section>

    <section id="contact" class="contact">
      <h2>Let's work together</h2>
      <p>Have an app idea or a team that needs a React Native developer? Send me a message.</p>
      <div class="btns">
        <a class="btn primary" href="mailto:muhammadhasaanwork@gmail.com">muhammadhasaanwork@gmail.com</a>
        <a class="btn" href="https://www.instagram.com/hasaan._._" target="_blank" rel="noopener">Instagram</a>
      </div>
    </section>
  </main>

  <footer>© Muhammad Hasaan · Lahore, Pakistan</footer>
</div>

<script>
const projects=[
  {n:"Steppals",c:"#FF8A3D",l:"S",p:"Android · iOS · Apple Watch",t:["React Native","Reanimated","Skia","Sprite Sheets","Push Notifications","Widgets","Swift","Java","HealthKit","Health Connect","RevenueCat","PlayFab"]},
  {n:"GoodActs",c:"#0FA37F",l:"G",p:"Android · iOS · Web",t:["React Native","Supabase","OpenAI","Google Maps","TypeScript","Cron Jobs","Universal Linking","AWS","Algolia","Google Ads","PDF Generation","React"]},
  {n:"Ebiblija",c:"#7A4DFF",l:"E",p:"iOS · Android",t:["React Native","Firebase","WordPress Headless API","Reanimated","OpenAI","Push Notifications","Universal Linking","RevenueCat"]},
  {n:"Minoqtopus",c:"#E5457A",l:"M",p:"Android · iOS",t:["React Native","Supabase","Gemini Flash","LocationIQ","TypeScript","Widgets","Cron Jobs","RevenueCat","React"]},
  {n:"Melodic Minds",c:"#1E88E5",l:"♪",p:"iOS",t:["React Native","Firebase","Reanimated","Sprite Sheets","OpenAI","Stripe","Google Ads","Universal Linking","RevenueCat"]}
];
const skills={
 "Mobile":["React Native","Expo Router","Reanimated","Skia","Widgets","Apple Watch","HealthKit","Health Connect","iOS Deployment"],
 "Web":["React","JavaScript","TypeScript","Tailwind CSS","NativeWind","WebView"],
 "State and data":["Redux","Context API","TanStack Query","REST APIs"],
 "Backend":["Node.js","Firebase","Supabase","Drizzle ORM","Prisma ORM","Cron Jobs"],
 "Cloud and tools":["AWS","Docker","Git","GitHub","JMeter","Jira","ClickUp"],
 "Services":["RevenueCat","Stripe","Algolia","PlayFab","Clerk","Logto","PostHog"]
};
const $=id=>document.getElementById(id);
const apps=$("apps");
function show(i){
  const p=projects[i];
  $("pName").textContent=p.n;$("pPlat").textContent=p.p;
  $("pTech").innerHTML=p.t.map(x=>"<span>"+x+"</span>").join("");
  [...apps.children].forEach((b,j)=>b.setAttribute("aria-pressed",j===i));
}
projects.forEach((p,i)=>{
  const b=document.createElement("button");b.className="app";b.type="button";
  b.innerHTML='<i style="background:'+p.c+'">'+p.l+'</i><span>'+p.n+'</span>';
  b.onclick=()=>show(i);apps.appendChild(b);
});
show(0);
$("skillGrid").innerHTML=Object.entries(skills).map(([k,v])=>'<div class="skill"><h3>'+k+'</h3><div class="chips">'+v.map(x=>"<span>"+x+"</span>").join("")+"</div></div>").join("");
$("theme").onclick=()=>{
  const r=document.documentElement;
  const dark=r.dataset.theme?r.dataset.theme==="dark":matchMedia("(prefers-color-scheme: dark)").matches;
  r.dataset.theme=dark?"light":"dark";
};
</script>
</body>
</html>
