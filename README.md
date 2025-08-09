<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>GitHub Profile — Manimaran</title>
  <style>
    :root{
      --bg1: #0f172a;
      --bg2: #071029;
      --accent1: #7c3aed;
      --accent2: #06b6d4;
      --glass: rgba(255,255,255,0.06);
      --glass-2: rgba(255,255,255,0.03);
      --card-w: 980px;
    }
    *{box-sizing:border-box}
    body{
      margin:0;min-height:100vh;display:grid;place-items:center;padding:4rem;background:radial-gradient(1200px 600px at 10% 10%, rgba(124,58,237,0.12), transparent), radial-gradient(1000px 450px at 90% 90%, rgba(6,182,212,0.08), transparent), linear-gradient(180deg,var(--bg1),var(--bg2));font-family:Inter,ui-sans-serif,system-ui,-apple-system,'Segoe UI',Roboto,'Helvetica Neue',Arial;
      color:#e6eef8;
      -webkit-font-smoothing:antialiased;
    }

    .stage{
      width:100%;max-width:var(--card-w);perspective:1400px;
      display:flex;gap:2rem;align-items:center;justify-content:center;
    }

    /* 3D Card */
    .card-wrap{width:640px;height:380px;transform-style:preserve-3d;transition:transform 700ms cubic-bezier(.2,.9,.2,1);}
    .card{
      width:100%;height:100%;border-radius:18px;padding:28px;background:linear-gradient(135deg, rgba(255,255,255,0.03), rgba(255,255,255,0.01));backdrop-filter: blur(8px);box-shadow: 0 12px 40px rgba(2,6,23,0.6), inset 0 1px 0 rgba(255,255,255,0.02);
      transform-style:preserve-3d;position:relative;overflow:hidden;border:1px solid rgba(255,255,255,0.04);
    }

    .card::before{content:'';position:absolute;inset:0;background:linear-gradient(60deg, rgba(124,58,237,0.06), rgba(6,182,212,0.04));mix-blend-mode:overlay;pointer-events:none}

    .card-tilt{transform:translateZ(30px)}

    .avatar{
      width:120px;height:120px;border-radius:18px;overflow:hidden;display:inline-grid;place-items:center;margin-bottom:8px;border:1px solid rgba(255,255,255,0.06);box-shadow:0 8px 24px rgba(2,6,23,0.6);
    }

    .header{display:flex;gap:18px;align-items:center}

    h1{margin:0;font-size:28px;letter-spacing:0.4px}
    p.lead{margin:6px 0 0;color:rgba(230,238,248,0.75)}

    .tech-row{display:flex;gap:10px;flex-wrap:wrap;margin-top:14px}
    .tech-row img{width:46px;height:46px;border-radius:10px;background:linear-gradient(180deg, rgba(255,255,255,0.015), transparent);padding:6px;border:1px solid rgba(255,255,255,0.03)}

    .stats{
      margin-top:18px;display:flex;gap:12px;align-items:center;flex-wrap:wrap
    }
    .badge{background:linear-gradient(90deg,var(--accent1),var(--accent2));padding:8px 12px;border-radius:999px;font-weight:600;color:white;font-size:13px;box-shadow:0 6px 18px rgba(12,8,32,0.5);}

    /* floating neon orbs */
    .orb{position:absolute;border-radius:999px;filter:blur(28px);opacity:0.7;mix-blend-mode:screen}
    .orb.one{width:220px;height:220px;left:-80px;top:-60px;background:linear-gradient(135deg,#7c3aed,#06b6d4)}
    .orb.two{width:120px;height:120px;right:-50px;bottom:-30px;background:linear-gradient(135deg,#06b6d4,#7c3aed);opacity:0.45}

    /* right column - info panel */
    .panel{width:320px;background:linear-gradient(180deg,var(--glass),var(--glass-2));border-radius:16px;padding:18px;border:1px solid rgba(255,255,255,0.03);box-shadow:0 8px 30px rgba(2,6,23,0.5)}

    .panel h3{margin:0 0 8px 0}
    .links{display:flex;flex-direction:column;gap:10px}
    .link{display:flex;gap:10px;align-items:center;padding:8px;border-radius:10px;background:linear-gradient(180deg, rgba(255,255,255,0.01), transparent);border:1px solid rgba(255,255,255,0.02);text-decoration:none;color:inherit}
    .link img{width:22px;height:22px}

    .powers{display:grid;grid-template-columns:repeat(2,1fr);gap:10px;margin-top:14px}
    .power{padding:10px;border-radius:10px;background:linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border:1px solid rgba(255,255,255,0.02)}

    /* 3D hover interactive */
    .stage:hover .card-wrap{transform:rotateY(calc((var(--mx,0) - 50) * 0.6deg)) rotateX(calc((50 - var(--my,0)) * 0.35deg)) translateZ(0)}

    /* floating icons orbit */
    .orbit-icons{position:absolute;left:18px;bottom:18px;display:flex;gap:10px}
    .orbit{width:46px;height:46px;border-radius:10px;display:grid;place-items:center;background:rgba(255,255,255,0.03);border:1px solid rgba(255,255,255,0.02);transform-origin:50% -60px;animation:spin 12s linear infinite}
    .orbit:nth-child(2){animation-duration:16s}
    @keyframes spin{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}

    /* small responsive */
    @media (max-width:980px){.stage{flex-direction:column;padding:1rem}.card-wrap{width:92vw;height:56vw}.panel{width:92vw}}

    /* subtle entry animations */
    .fade-up{transform:translateY(8px);opacity:0;animation:enter 800ms cubic-bezier(.2,.9,.2,1) forwards}
    .delay-1{animation-delay:120ms}.delay-2{animation-delay:220ms}.delay-3{animation-delay:320ms}
    @keyframes enter{to{transform:none;opacity:1}}

    .cta{margin-top:18px;display:inline-flex;gap:10px}
    .btn{padding:10px 14px;border-radius:10px;background:linear-gradient(90deg,var(--accent2),var(--accent1));color:white;font-weight:700;text-decoration:none;border:0;box-shadow:0 10px 30px rgba(8,10,30,0.5);}

    /* small neat footer */
    .footer{margin-top:14px;color:rgba(230,238,248,0.6);font-size:13px}
  </style>
</head>
<body>
  <div class="stage" id="stage">

    <div class="card-wrap fade-up delay-1" id="cardWrap">
      <div class="card">
        <div class="orb one"></div>
        <div class="orb two"></div>

        <div class="header">
          <div style="display:flex;flex-direction:column;align-items:flex-start">
            <div class="avatar card-tilt">
              <!-- Avatar placeholder - replace with your image -->
              <img src="https://avatars.githubusercontent.com/u/116?u=placeholder&s=200" alt="avatar" style="width:100%;height:100%;object-fit:cover"/>
            </div>
          </div>
          <div style="flex:1">
            <h1>Hey Iam 👋 MANIMARAN</h1>
            <p class="lead">3rd year EEE • Full-stack enthusiast • Frontend & Embedded projects</p>

            <div class="tech-row">
              <!-- keep your devicons here -->
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg" alt="cpp"/>
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="py"/>
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" alt="java"/>
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="html"/>
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="css"/>
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="js"/>
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt="react"/>
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" alt="node"/>
            </div>

            <div class="stats">
              <div class="badge">Frontend • React • HTML/CSS</div>
              <div class="badge">Embedded • ESP32 • IoT</div>
              <div class="badge">Open Source Contributor</div>
            </div>

            <div class="orbit-icons" aria-hidden="true">
              <div class="orbit"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" style="width:24px;height:24px"/></div>
              <div class="orbit"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg" style="width:24px;height:24px"/></div>
              <div class="orbit"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/twitter/twitter-original.svg" style="width:24px;height:24px"/></div>
            </div>

          </div>
        </div>

        <div style="display:flex;gap:18px;margin-top:20px;align-items:flex-end;justify-content:space-between">
          <div style="max-width:58%">
            <p style="margin:0 0 6px 0;color:rgba(230,238,248,0.7)">I build beautiful and functional web apps, landing pages, and IoT dashboards. Currently working on a Smart Greenhouse Monitoring System using ESP32.</p>
            <div class="cta">
              <a class="btn" href="#">View Portfolio</a>
              <a class="btn" href="#">Contact</a>
            </div>
          </div>

          <div style="width:36%">
            <!-- small cards inside -->
            <div style="display:flex;flex-direction:column;gap:8px">
              <div style="padding:10px;border-radius:10px;background:linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border:1px solid rgba(255,255,255,0.02)">
                <strong>Current Project</strong>
                <div style="font-size:13px;color:rgba(230,238,248,0.7)">Smart Greenhouse • ESP32 • ThingSpeak</div>
              </div>

              <div style="padding:10px;border-radius:10px;background:linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border:1px solid rgba(255,255,255,0.02)">
                <strong>Top Repo</strong>
                <div style="font-size:13px;color:rgba(230,238,248,0.7)">MANIMARAN-ENCRYPTiX</div>
              </div>
            </div>
          </div>
        </div>

        <div class="footer">Custom README design • Replace images & links with your real ones</div>

      </div>
    </div>

    <div class="panel fade-up delay-2" id="panel">
      <h3>Connect with me</h3>
      <div class="links">
        <a class="link" href="#"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt="gh"/> GitHub</a>
        <a class="link" href="#"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg" alt="ln"/> LinkedIn</a>
        <a class="link" href="#"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/twitter/twitter-original.svg" alt="tw"/> Twitter</a>
        <a class="link" href="#"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/gmail/gmail-original.svg" alt="gm"/> Email</a>
      </div>

      <h3 style="margin-top:14px">Quick highlights</h3>
      <div class="powers">
        <div class="power"><strong>Languages</strong><div style="font-size:13px;color:rgba(230,238,248,0.7)">C++, Python, Java, JS</div></div>
        <div class="power"><strong>Frameworks</strong><div style="font-size:13px;color:rgba(230,238,248,0.7)">React, Node, Express</div></div>
        <div class="power"><strong>Tools</strong><div style="font-size:13px;color:rgba(230,238,248,0.7)">VSCode, Git, MongoDB</div></div>
        <div class="power"><strong>Interests</strong><div style="font-size:13px;color:rgba(230,238,248,0.7)">IoT, Web, Open Source</div></div>
      </div>

      <h3 style="margin-top:14px">GitHub stats</h3>
      <div style="display:flex;gap:8px;margin-top:8px;flex-wrap:wrap">
        <img src="https://github-readme-stats.vercel.app/api?username=Manimaran23102004&show_icons=true&theme=dracula&count_private=true" alt="stats" style="width:100%;border-radius:8px;border:1px solid rgba(255,255,255,0.03)"/>
      </div>
    </div>

  </div>

  <script>
    // Interactive tilt based on mouse position
    const stage = document.getElementById('stage');
    const cardWrap = document.getElementById('cardWrap');
    stage.addEventListener('mousemove', (e)=>{
      const r = stage.getBoundingClientRect();
      const mx = (e.clientX - r.left) / r.width * 100;
      const my = (e.clientY - r.top) / r.height * 100;
      stage.style.setProperty('--mx', mx);
      stage.style.setProperty('--my', my);
      // subtle translate
      cardWrap.style.transform = `translateZ(10px) rotateY(${(mx-50)*0.6}deg) rotateX(${(50-my)*0.35}deg)`;
    });
    stage.addEventListener('mouseleave', ()=>{cardWrap.style.transform='none';stage.style.setProperty('--mx',50);stage.style.setProperty('--my',50)});
  </script>
</body>
</html>
