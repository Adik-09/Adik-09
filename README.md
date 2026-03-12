<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<title>Aditya Kasture | Space Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Share+Tech+Mono&display=swap" rel="stylesheet"/>
<style>
:root{--pur:#a78bfa;--dpur:#7c3aed;--cyan:#22d3ee;--bg:#06061a;}
*{margin:0;padding:0;box-sizing:border-box;}
body{background:var(--bg);color:#fff;font-family:'Share Tech Mono',monospace;overflow-x:hidden;}
#starfield{position:fixed;top:0;left:0;width:100%;height:100%;z-index:0;pointer-events:none;}

/* NEBULA */
.neb{position:fixed;border-radius:50%;filter:blur(90px);opacity:.07;pointer-events:none;z-index:0;animation:nebDrift 18s ease-in-out infinite alternate;}
@keyframes nebDrift{from{transform:translate(0,0)}to{transform:translate(25px,-25px)}}

/* BINARY SIDES */
.bin{position:fixed;top:0;font-family:'Share Tech Mono',monospace;font-size:9px;color:rgba(34,211,238,.12);pointer-events:none;z-index:0;writing-mode:vertical-rl;height:100vh;overflow:hidden;letter-spacing:2px;}
.binL{left:8px;} .binR{right:8px;}

/* HERO */
.hero{position:relative;min-height:100vh;display:flex;flex-direction:column;align-items:center;padding-top:56px;z-index:1;overflow:hidden;}
.sub-line{display:flex;align-items:center;gap:12px;font-family:'Orbitron',sans-serif;font-size:10px;letter-spacing:5px;color:#64748b;margin-bottom:14px;}
.sub-line::before,.sub-line::after{content:'';width:100px;height:1px;background:linear-gradient(90deg,transparent,var(--pur));}
.sub-line::after{background:linear-gradient(90deg,var(--pur),transparent);}
.hero-title{font-family:'Orbitron',sans-serif;font-size:clamp(22px,4.5vw,58px);font-weight:900;letter-spacing:5px;text-align:center;background:linear-gradient(135deg,#fff 0%,var(--pur) 50%,var(--cyan) 100%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;animation:tPulse 3s ease-in-out infinite;padding:0 20px;}
@keyframes tPulse{0%,100%{filter:drop-shadow(0 0 18px rgba(167,139,250,.4))}50%{filter:drop-shadow(0 0 36px rgba(167,139,250,.8))}}
.hero-name{font-family:'Orbitron',sans-serif;font-size:clamp(16px,2.5vw,32px);font-weight:700;letter-spacing:10px;color:var(--cyan);text-shadow:0 0 20px var(--cyan),0 0 40px var(--cyan);margin-top:22px;animation:nPulse 2s ease-in-out infinite;}
@keyframes nPulse{0%,100%{text-shadow:0 0 20px var(--cyan),0 0 40px var(--cyan)}50%{text-shadow:0 0 30px var(--cyan),0 0 70px var(--cyan)}}
.hero-role{font-size:12px;letter-spacing:4px;color:#475569;margin-top:10px;animation:fadeSlide .8s ease .3s both;}
@keyframes fadeSlide{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}

/* SCROLL CARET */
.scroll-cue{position:absolute;bottom:164px;left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:6px;animation:bounce 2s ease-in-out infinite;z-index:10;cursor:pointer;}
.scroll-cue span{font-family:'Orbitron',sans-serif;font-size:8px;letter-spacing:3px;color:#334155;}
.scroll-line{width:1px;height:36px;background:linear-gradient(to bottom,var(--pur),transparent);}
@keyframes bounce{0%,100%{transform:translateX(-50%) translateY(0)}50%{transform:translateX(-50%) translateY(8px)}}

/* ASTRONAUT */
.astro{position:absolute;bottom:268px;left:50%;transform:translateX(-50%);z-index:10;animation:floatAstro 4s ease-in-out infinite;cursor:pointer;user-select:none;}
@keyframes floatAstro{0%,100%{transform:translateX(-50%) translateY(0) rotate(-4deg)}50%{transform:translateX(-50%) translateY(-22px) rotate(4deg)}}

/* CTA */
.cta{position:absolute;bottom:192px;left:50%;transform:translateX(-50%);font-family:'Orbitron',sans-serif;font-size:11px;letter-spacing:4px;color:var(--cyan);cursor:pointer;z-index:10;white-space:nowrap;}
.cta-inner{padding:14px 26px;border:1px solid rgba(34,211,238,.4);position:relative;transition:all .3s;background:rgba(34,211,238,.04);}
.cta-inner:hover{background:rgba(34,211,238,.1);box-shadow:0 0 24px rgba(34,211,238,.2);}
.cta-inner .c{position:absolute;width:10px;height:10px;border-color:var(--cyan);border-style:solid;}
.c.tl{top:-1px;left:-1px;border-width:2px 0 0 2px}
.c.tr{top:-1px;right:-1px;border-width:2px 2px 0 0}
.c.bl{bottom:-1px;left:-1px;border-width:0 0 2px 2px}
.c.br{bottom:-1px;right:-1px;border-width:0 2px 2px 0}
.cta-blink{animation:blink 1.5s ease-in-out infinite;}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.5}}

/* PLANET */
.planet-wrap{position:absolute;bottom:-220px;left:50%;transform:translateX(-50%);width:680px;height:680px;pointer-events:none;}
.planet{width:100%;height:100%;border-radius:50%;background:radial-gradient(ellipse at 28% 28%,#1e88e5 0%,#0d47a1 35%,#0a2a6e 65%,#061a45 100%);box-shadow:0 0 70px rgba(34,211,238,.45),0 0 140px rgba(34,211,238,.18),inset -30px -30px 60px rgba(0,0,0,.5);position:relative;overflow:hidden;}
.planet::before{content:'';position:absolute;top:18%;left:14%;width:55%;height:35%;background:rgba(255,255,255,.035);border-radius:50%;transform:rotate(-18deg);}
.pland{position:absolute;background:rgba(34,139,34,.38);border-radius:40% 60% 50% 50%;}
.glow-ring{position:absolute;bottom:-230px;left:50%;transform:translateX(-50%);width:880px;height:880px;border-radius:50%;border:1px solid rgba(34,211,238,.07);box-shadow:0 0 60px rgba(34,211,238,.06);pointer-events:none;z-index:0;}

/* DIVIDER */
.div-line{width:100%;height:1px;background:linear-gradient(90deg,transparent,rgba(167,139,250,.25),transparent);position:relative;z-index:2;}

/* SECTIONS */
section{position:relative;z-index:2;padding:70px 32px;max-width:1080px;margin:0 auto;}
.sec-tag{font-family:'Orbitron',sans-serif;font-size:10px;letter-spacing:6px;color:var(--pur);text-align:center;margin-bottom:6px;opacity:.65;}
.sec-h{font-family:'Orbitron',sans-serif;font-size:clamp(16px,2.5vw,28px);font-weight:700;text-align:center;color:#fff;margin-bottom:44px;position:relative;}
.sec-h::after{content:'';display:block;width:50px;height:2px;background:linear-gradient(90deg,var(--pur),var(--cyan));margin:10px auto 0;border-radius:2px;}

/* CODE CARD */
.code-card{background:rgba(8,8,32,.85);border:1px solid rgba(167,139,250,.25);border-radius:16px;padding:28px 32px;backdrop-filter:blur(20px);position:relative;overflow:hidden;box-shadow:0 0 40px rgba(124,58,237,.08),inset 0 1px 0 rgba(255,255,255,.04);}
.code-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,var(--pur),var(--cyan),transparent);}
.code-hdr{display:flex;align-items:center;gap:7px;margin-bottom:18px;padding-bottom:14px;border-bottom:1px solid rgba(167,139,250,.12);}
.dot{width:10px;height:10px;border-radius:50%;}
.dr{background:#ff5f57} .dy{background:#febc2e} .dg{background:#28c840}
.cf{font-size:11px;color:#475569;margin-left:6px;}
.cl{font-family:'Share Tech Mono',monospace;font-size:13px;line-height:1.85;color:#94a3b8;}
.kw{color:#c792ea} .cn{color:#ffcb6b} .st{color:#c3e88d} .cm{color:#415060} .vr{color:#82aaff} .cy{color:#89ddff}

/* SKILLS */
.sk-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:14px;}
.sk-card{background:rgba(8,8,32,.75);border:1px solid rgba(167,139,250,.18);border-radius:12px;padding:18px 14px;text-align:center;transition:all .3s;cursor:default;position:relative;overflow:hidden;}
.sk-card:hover{border-color:var(--pur);transform:translateY(-5px);box-shadow:0 8px 28px rgba(167,139,250,.18);}
.sk-card::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,var(--pur),transparent);opacity:0;transition:opacity .3s;}
.sk-card:hover::before{opacity:1;}
.sk-icon{font-size:28px;margin-bottom:8px;}
.sk-name{font-family:'Orbitron',sans-serif;font-size:9px;letter-spacing:2px;color:var(--pur);}
.sk-bar-wrap{margin-top:8px;height:3px;background:rgba(255,255,255,.08);border-radius:2px;overflow:hidden;}
.sk-bar{height:100%;background:linear-gradient(90deg,var(--dpur),var(--cyan));border-radius:2px;width:0;transition:width 1.4s ease-out;}

/* PROJECTS */
.proj-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(270px,1fr));gap:18px;}
.proj-card{background:rgba(8,8,32,.8);border:1px solid rgba(167,139,250,.18);border-radius:14px;padding:26px;transition:all .3s;cursor:pointer;position:relative;overflow:hidden;}
.proj-card::after{content:'';position:absolute;top:0;left:-100%;width:100%;height:100%;background:linear-gradient(90deg,transparent,rgba(167,139,250,.05),transparent);transition:left .5s;}
.proj-card:hover{border-color:var(--cyan);transform:translateY(-6px);box-shadow:0 12px 36px rgba(34,211,238,.12);}
.proj-card:hover::after{left:100%;}
.proj-icon{font-size:26px;margin-bottom:10px;}
.proj-title{font-family:'Orbitron',sans-serif;font-size:12px;letter-spacing:2px;color:#fff;margin-bottom:8px;}
.proj-desc{font-size:12px;color:#475569;line-height:1.65;margin-bottom:14px;}
.proj-lang{display:inline-flex;align-items:center;gap:5px;font-size:10px;color:var(--pur);letter-spacing:1px;}
.ldot{width:7px;height:7px;border-radius:50%;}

/* STATS */
.stats-wrap{display:grid;grid-template-columns:1fr 1fr;gap:18px;}
.stats-wrap img{width:100%;border-radius:12px;border:1px solid rgba(167,139,250,.18);}

/* CONTACT */
.contact{text-align:center;padding:50px 32px 90px;position:relative;z-index:2;}
.contact-title{font-family:'Orbitron',sans-serif;font-size:clamp(13px,2vw,20px);letter-spacing:4px;color:var(--pur);margin-bottom:28px;}
.socials{display:flex;gap:14px;justify-content:center;flex-wrap:wrap;}
.soc-btn{font-family:'Orbitron',sans-serif;font-size:10px;letter-spacing:3px;color:#fff;background:rgba(167,139,250,.08);border:1px solid rgba(167,139,250,.25);padding:12px 22px;border-radius:8px;cursor:pointer;text-decoration:none;transition:all .3s;display:inline-flex;align-items:center;gap:7px;}
.soc-btn:hover{background:rgba(167,139,250,.18);border-color:var(--pur);box-shadow:0 0 18px rgba(167,139,250,.18);transform:translateY(-2px);}
.quote{font-size:12px;color:#2d3a4a;font-style:italic;margin-top:44px;letter-spacing:.5px;line-height:2;}

/* FADE IN */
.fi{opacity:0;transform:translateY(28px);transition:opacity .75s ease,transform .75s ease;}
.fi.vis{opacity:1;transform:translateY(0);}

/* SPACER */
.sp{height:110px;}

/* TERMINAL CURSOR */
.cursor{display:inline-block;width:8px;height:14px;background:var(--cyan);animation:blink 1s step-end infinite;vertical-align:text-bottom;margin-left:2px;}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
</style>
</head>
<body>

<!-- NEBULA BG -->
<div class="neb" style="width:550px;height:550px;background:radial-gradient(circle,#7c3aed,transparent);top:-80px;left:-80px;"></div>
<div class="neb" style="width:450px;height:450px;background:radial-gradient(circle,#0e7490,transparent);bottom:25%;right:-80px;animation-delay:-9s;"></div>
<div class="neb" style="width:380px;height:380px;background:radial-gradient(circle,#3b0764,transparent);top:42%;left:22%;animation-delay:-4s;"></div>

<!-- BINARY SIDES -->
<div class="bin binL" id="bL"></div>
<div class="bin binR" id="bR"></div>

<!-- STARS -->
<canvas id="starfield"></canvas>

<!-- ═══════════════════ HERO ═══════════════════ -->
<div class="hero">
  <div class="sub-line">A MESSAGE FROM EARTH</div>
  <h1 class="hero-title">HELLO FELLOW GALAXY MEMBER</h1>
  <div class="sub-line" style="margin-top:8px;">TRANSMISSION ORIGIN : PUNE, INDIA</div>
  <div class="hero-name">I AM ADITYA</div>
  <div class="hero-role">3RD YEAR · CS ENGINEERING · GAME DEV + WEB DEV + ML</div>

  <div class="glow-ring"></div>

  <!-- ASTRONAUT SVG -->
  <div class="astro">
    <svg width="90" height="110" viewBox="0 0 90 110" fill="none" xmlns="http://www.w3.org/2000/svg">
      <!-- suit body -->
      <ellipse cx="45" cy="72" rx="26" ry="28" fill="#dde6f0" stroke="#b0c4d8" stroke-width="1.5"/>
      <!-- helmet -->
      <circle cx="45" cy="36" r="22" fill="#eef2f7" stroke="#b0c4d8" stroke-width="1.5"/>
      <!-- visor -->
      <ellipse cx="45" cy="37" rx="14" ry="13" fill="#1a1a4e" stroke="#22d3ee" stroke-width="1.2" opacity=".9"/>
      <!-- visor glow -->
      <ellipse cx="40" cy="33" rx="5" ry="3.5" fill="rgba(34,211,238,.2)"/>
      <!-- backpack -->
      <rect x="19" y="55" width="10" height="18" rx="3" fill="#c8d4e0" stroke="#b0c4d8" stroke-width="1"/>
      <!-- arms -->
      <ellipse cx="18" cy="72" rx="7" ry="14" fill="#dde6f0" stroke="#b0c4d8" stroke-width="1.5" transform="rotate(-15 18 72)"/>
      <ellipse cx="72" cy="72" rx="7" ry="14" fill="#dde6f0" stroke="#b0c4d8" stroke-width="1.5" transform="rotate(15 72 72)"/>
      <!-- laptop in hands -->
      <rect x="28" y="88" width="34" height="20" rx="3" fill="#1a1a4e" stroke="#22d3ee" stroke-width="1.2"/>
      <rect x="30" y="90" width="30" height="14" rx="2" fill="#0d0d2b"/>
      <!-- laptop screen code lines -->
      <line x1="32" y1="93" x2="44" y2="93" stroke="#a78bfa" stroke-width="1.5" stroke-linecap="round"/>
      <line x1="32" y1="96" x2="50" y2="96" stroke="#22d3ee" stroke-width="1" stroke-linecap="round"/>
      <line x1="32" y1="99" x2="40" y2="99" stroke="#c3e88d" stroke-width="1" stroke-linecap="round"/>
      <!-- legs -->
      <ellipse cx="35" cy="100" rx="7" ry="10" fill="#dde6f0" stroke="#b0c4d8" stroke-width="1.5"/>
      <ellipse cx="55" cy="100" rx="7" ry="10" fill="#dde6f0" stroke="#b0c4d8" stroke-width="1.5"/>
      <!-- boots -->
      <ellipse cx="34" cy="109" rx="9" ry="4" fill="#aab8c6"/>
      <ellipse cx="56" cy="109" rx="9" ry="4" fill="#aab8c6"/>
      <!-- helmet antenna -->
      <line x1="45" y1="14" x2="45" y2="6" stroke="#94a3b8" stroke-width="2"/>
      <circle cx="45" cy="5" r="3" fill="#22d3ee" opacity=".8"/>
      <!-- suit patches -->
      <circle cx="63" cy="65" r="5" fill="none" stroke="#22d3ee" stroke-width="1" opacity=".6"/>
      <text x="60" y="68.5" font-size="5" fill="#22d3ee" opacity=".7">CS</text>
    </svg>
  </div>

  <div class="scroll-cue" onclick="scrollDown()">
    <span>EXPLORE</span>
    <div class="scroll-line"></div>
  </div>

  <div class="cta cta-blink" onclick="scrollDown()">
    <div class="cta-inner">
      <span class="c tl"></span><span class="c tr"></span><span class="c bl"></span><span class="c br"></span>
      CLICK TO OPEN
    </div>
  </div>

  <div class="planet-wrap">
    <div class="planet">
      <div class="pland" style="width:110px;height:72px;top:18%;left:18%;transform:rotate(-14deg);"></div>
      <div class="pland" style="width:75px;height:56px;top:38%;left:50%;transform:rotate(18deg);"></div>
      <div class="pland" style="width:95px;height:65px;top:22%;left:52%;transform:rotate(-6deg);"></div>
      <div class="pland" style="width:60px;height:45px;top:55%;left:28%;transform:rotate(30deg);"></div>
    </div>
  </div>
</div>

<div class="sp"></div>
<div class="div-line"></div>

<!-- ═══════════════════ ABOUT ═══════════════════ -->
<section class="fi">
  <div class="sec-tag">// TRANSMISSION RECEIVED</div>
  <div class="sec-h">MISSION PROFILE</div>
  <div class="code-card">
    <div class="code-hdr">
      <div class="dot dr"></div><div class="dot dy"></div><div class="dot dg"></div>
      <span class="cf">~ /space/AstronautDev.py</span>
    </div>
    <div class="cl"><span class="kw">class</span> <span class="cn">AstronautDev</span><span class="cy">:</span></div>
    <div class="cl">&nbsp;&nbsp;&nbsp;&nbsp;<span class="vr">name</span><span class="cy"> = </span><span class="st">"Aditya Kasture"</span></div>
    <div class="cl">&nbsp;&nbsp;&nbsp;&nbsp;<span class="vr">alias</span><span class="cy"> = </span><span class="st">"Adik-09"</span></div>
    <div class="cl">&nbsp;&nbsp;&nbsp;&nbsp;<span class="vr">coords</span><span class="cy"> = </span><span class="st">"Pune, India 🌏"</span></div>
    <div class="cl">&nbsp;&nbsp;&nbsp;&nbsp;<span class="vr">year</span><span class="cy"> = </span><span class="st">"3rd Year · CS Engineering"</span></div>
    <div class="cl">&nbsp;</div>
    <div class="cl">&nbsp;&nbsp;&nbsp;&nbsp;<span class="cm"># ── Active Mission Tracks ──────────────────</span></div>
    <div class="cl">&nbsp;&nbsp;&nbsp;&nbsp;<span class="vr">game_dev</span><span class="cy"> = [</span><span class="st">"Unreal Engine 5"</span><span class="cy">, </span><span class="st">"C++"</span><span class="cy">, </span><span class="st">"3D Level Design"</span><span class="cy">]</span></div>
    <div class="cl">&nbsp;&nbsp;&nbsp;&nbsp;<span class="vr">web_dev</span><span class="cy"> = [</span><span class="st">"Django"</span><span class="cy">, </span><span class="st">"REST APIs"</span><span class="cy">, </span><span class="st">"PostgreSQL"</span><span class="cy">]</span></div>
    <div class="cl">&nbsp;&nbsp;&nbsp;&nbsp;<span class="vr">ml</span><span class="cy"> = [</span><span class="st">"Python"</span><span class="cy">, </span><span class="st">"Scikit-Learn"</span><span class="cy">, </span><span class="st">"Numpy"</span><span class="cy">]</span></div>
    <div class="cl">&nbsp;</div>
    <div class="cl">&nbsp;&nbsp;&nbsp;&nbsp;<span class="vr">mission</span><span class="cy"> = </span><span class="st">"Building things that didn't exist yesterday 🛸"</span></div>
    <div class="cl">&nbsp;&nbsp;&nbsp;&nbsp;<span class="vr">fun_fact</span><span class="cy"> = </span><span class="st">"I debug at 2AM with lo-fi music 🎵"</span><span class="cursor"></span></div>
  </div>
</section>

<div class="div-line"></div>

<!-- ═══════════════════ SKILLS ═══════════════════ -->
<section class="fi">
  <div class="sec-tag">// TECH ARSENAL</div>
  <div class="sec-h">SKILL CONSTELLATION</div>
  <div class="sk-grid" id="skGrid">
    <div class="sk-card"><div class="sk-icon">🐍</div><div class="sk-name">PYTHON</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="85"></div></div></div>
    <div class="sk-card"><div class="sk-icon">⚙️</div><div class="sk-name">C++</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="78"></div></div></div>
    <div class="sk-card"><div class="sk-icon">🎮</div><div class="sk-name">UNREAL ENGINE</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="72"></div></div></div>
    <div class="sk-card"><div class="sk-icon">🌐</div><div class="sk-name">DJANGO</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="80"></div></div></div>
    <div class="sk-card"><div class="sk-icon">🤖</div><div class="sk-name">ML / AI</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="68"></div></div></div>
    <div class="sk-card"><div class="sk-icon">🗄️</div><div class="sk-name">SQL</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="74"></div></div></div>
    <div class="sk-card"><div class="sk-icon">📝</div><div class="sk-name">HTML/CSS</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="82"></div></div></div>
    <div class="sk-card"><div class="sk-icon">🔧</div><div class="sk-name">GIT</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="77"></div></div></div>
  </div>
</section>

<div class="div-line"></div>

<!-- ═══════════════════ PROJECTS ═══════════════════ -->
<section class="fi">
  <div class="sec-tag">// ACTIVE MISSIONS</div>
  <div class="sec-h">LAUNCH PADS</div>
  <div class="proj-grid">
    <div class="proj-card" onclick="open('https://github.com/Adik-09/ML_LABS','_blank')">
      <div class="proj-icon">🤖</div>
      <div class="proj-title">ML LABS</div>
      <div class="proj-desc">Machine learning experiments, algorithms & data science notebooks. Exploring neural frontiers of AI.</div>
      <div class="proj-lang"><div class="ldot" style="background:#f7df1e"></div>JUPYTER NOTEBOOK</div>
    </div>
    <div class="proj-card" onclick="open('https://github.com/Adik-09/Project_Stock','_blank')">
      <div class="proj-icon">📈</div>
      <div class="proj-title">PROJECT STOCK</div>
      <div class="proj-desc">Real-time stock tracker with live data feeds and visual analytics dashboard.</div>
      <div class="proj-lang"><div class="ldot" style="background:#264de4"></div>CSS / HTML</div>
    </div>
    <div class="proj-card" onclick="open('https://github.com/Adik-09/Project_Chat','_blank')">
      <div class="proj-icon">💬</div>
      <div class="proj-title">PROJECT CHAT</div>
      <div class="proj-desc">Real-time chat application with WebSocket communication and live user presence.</div>
      <div class="proj-lang"><div class="ldot" style="background:#e34c26"></div>HTML / JS</div>
    </div>
    <div class="proj-card" onclick="open('https://github.com/Adik-09/ssa-compiler','_blank')">
      <div class="proj-icon">⚙️</div>
      <div class="proj-title">SSA COMPILER</div>
      <div class="proj-desc">Static Single Assignment form compiler in C++. Deep dive into compiler design theory.</div>
      <div class="proj-lang"><div class="ldot" style="background:#a97bff"></div>C++</div>
    </div>
    <div class="proj-card" onclick="open('https://github.com/Adik-09/project_ecommerce','_blank')">
      <div class="proj-icon">🛒</div>
      <div class="proj-title">E-COMMERCE</div>
      <div class="proj-desc">Full-stack e-commerce platform with product listings, cart and order management.</div>
      <div class="proj-lang"><div class="ldot" style="background:#f7df1e"></div>JAVASCRIPT</div>
    </div>
    <div class="proj-card" onclick="open('https://github.com/Adik-09/strix_19_fusion','_blank')">
      <div class="proj-icon">🚀</div>
      <div class="proj-title">STRIX 19 FUSION</div>
      <div class="proj-desc">Fusion project combining multiple tech stacks into a unified interactive web experience.</div>
      <div class="proj-lang"><div class="ldot" style="background:#e34c26"></div>HTML</div>
    </div>
  </div>
</section>

<div class="div-line"></div>

<!-- ═══════════════════ STATS ═══════════════════ -->
<section class="fi">
  <div class="sec-tag">// MISSION CONTROL</div>
  <div class="sec-h">COMMAND STATS</div>
  <div class="stats-wrap">
    <img src="https://github-readme-stats.vercel.app/api?username=Adik-09&show_icons=true&theme=tokyonight&bg_color=0d0d2b&title_color=a78bfa&icon_color=7c3aed&text_color=94a3b8&border_color=3b0764&rank_icon=github&count_private=true" alt="GitHub Stats"/>
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Adik-09&layout=donut&theme=tokyonight&bg_color=0d0d2b&title_color=a78bfa&text_color=94a3b8&border_color=3b0764&langs_count=6" alt="Top Languages"/>
  </div>
</section>

<!-- ═══════════════════ CONTACT ═══════════════════ -->
<div class="contact fi">
  <div class="contact-title">📡 OPEN COMMUNICATION CHANNEL</div>
  <div class="socials">
    <a href="https://github.com/Adik-09" target="_blank" class="soc-btn">⬡ GITHUB</a>
    <a href="#" class="soc-btn">◈ LINKEDIN</a>
    <a href="#" class="soc-btn">✉ EMAIL</a>
  </div>
  <p class="quote">
    "The cosmos is within us. We are made of star-stuff." — Carl Sagan<br/>
    <span style="color:#1e293b;display:block;margin-top:6px">// Building the next big thing... one commit at a time 🌌</span>
  </p>
</div>

<div style="background:linear-gradient(to bottom,transparent,rgba(124,58,237,.08));height:60px;position:relative;z-index:2;"></div>

<script>
// ── STARFIELD ──────────────────────────────────
const cv = document.getElementById('starfield');
const cx = cv.getContext('2d');
function rsz(){cv.width=window.innerWidth;cv.height=document.body.scrollHeight||window.innerHeight;}
rsz(); window.addEventListener('resize',rsz);

const stars = Array.from({length:320},()=>({
  x:Math.random()*window.innerWidth, y:Math.random()*window.innerHeight*3,
  r:Math.random()*1.4+.3, a:Math.random(), d:(Math.random()-.5)*.018,
  spd:Math.random()*.06
}));
const shoots=[];
setInterval(()=>{
  shoots.push({x:Math.random()*window.innerWidth*.65,y:Math.random()*window.innerHeight*.35,
    len:Math.random()*110+70,spd:Math.random()*7+5,a:1,ang:Math.PI/4+(Math.random()-.5)*.28});
},2800);

function drawStars(){
  cx.clearRect(0,0,cv.width,cv.height);
  stars.forEach(s=>{
    s.a+=s.d; if(s.a<=0||s.a>=1)s.d*=-1;
    s.x-=s.spd; if(s.x<0)s.x=cv.width;
    cx.beginPath(); cx.arc(s.x,s.y,s.r,0,Math.PI*2);
    cx.fillStyle=`rgba(255,255,255,${Math.max(.1,s.a)})`; cx.fill();
  });
  for(let i=shoots.length-1;i>=0;i--){
    const s=shoots[i];
    const g=cx.createLinearGradient(s.x,s.y,s.x-Math.cos(s.ang)*s.len,s.y-Math.sin(s.ang)*s.len);
    g.addColorStop(0,`rgba(255,255,255,${s.a})`);
    g.addColorStop(.4,`rgba(167,139,250,${s.a*.5})`);
    g.addColorStop(1,'rgba(0,0,0,0)');
    cx.beginPath(); cx.moveTo(s.x,s.y);
    cx.lineTo(s.x-Math.cos(s.ang)*s.len,s.y-Math.sin(s.ang)*s.len);
    cx.strokeStyle=g; cx.lineWidth=1.8; cx.stroke();
    s.x+=Math.cos(s.ang)*s.spd; s.y+=Math.sin(s.ang)*s.spd; s.a-=.014;
    if(s.a<=0)shoots.splice(i,1);
  }
  requestAnimationFrame(drawStars);
}
drawStars();

// ── BINARY SIDES ───────────────────────────────
const gen=n=>Array.from({length:n},()=>Math.random()>.5?'1':'0').join(' ');
document.getElementById('bL').textContent=gen(300);
document.getElementById('bR').textContent=gen(300);

// ── SCROLL FADE ────────────────────────────────
const obs=new IntersectionObserver(es=>es.forEach(e=>{if(e.isIntersecting)e.target.classList.add('vis');}),{threshold:.1});
document.querySelectorAll('.fi').forEach(el=>obs.observe(el));

// ── SKILL BARS ─────────────────────────────────
const skObs=new IntersectionObserver(es=>{
  es.forEach(e=>{
    if(e.isIntersecting){
      e.target.querySelectorAll('.sk-bar').forEach(b=>{
        b.style.width=b.dataset.w+'%';
      });
    }
  });
},{threshold:.2});
document.querySelectorAll('#skGrid').forEach(el=>skObs.observe(el));

// ── SCROLL HELPER ──────────────────────────────
function scrollDown(){window.scrollTo({top:window.innerHeight*.9,behavior:'smooth'});}

// ── CURSOR TRAIL ───────────────────────────────
document.addEventListener('mousemove',e=>{
  const t=document.createElement('div');
  t.style.cssText=`position:fixed;left:${e.clientX}px;top:${e.clientY}px;width:5px;height:5px;background:rgba(167,139,250,.55);border-radius:50%;pointer-events:none;z-index:9999;transition:opacity .5s;`;
  document.body.appendChild(t);
  setTimeout(()=>t.style.opacity='0',80);
  setTimeout(()=>t.remove(),580);
});
</script>
</body>
</html>
