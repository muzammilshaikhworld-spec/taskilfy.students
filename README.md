<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>taskilyfy Site —for all u need  </title>
  <style>
    :root{
      --bg: rgba(255,255,255,0.03);
      --glass: rgba(255,255,255,0.06);
      --accent: 40,200,255;
      --accent2: 120, 60, 240;
      --text: rgba(255,255,255,0.95);
      --card-radius: 14px;
      --max-balls: 8;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;font-family:Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial}
    body{
      background: linear-gradient(180deg, rgba(10,12,20,0.6), rgba(6,7,10,0.6));
      color:var(--text);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      overflow:hidden;
    }
    .stage{position:fixed;inset:0;pointer-events:none;z-index:0;}
    .balls{position:absolute;inset:0;overflow:hidden;perspective:800px;transform-style:preserve-3d;}
    .ball{position:absolute;left:50%;top:50%;border-radius:50%;filter:blur(18px) saturate(120%);mix-blend-mode:screen;will-change:transform,opacity;pointer-events:none;opacity:0.85;transform:translate3d(-50%,-50%,0) scale(1);background: radial-gradient(circle at 30% 30%, rgba(var(--accent),0.95) 0%, rgba(var(--accent),0.55) 30%, rgba(var(--accent),0.12) 60%, rgba(255,255,255,0) 100%);}
    .ball.alt{background: radial-gradient(circle at 30% 30%, rgba(var(--accent2),0.95) 0%, rgba(var(--accent2),0.45) 30%, rgba(var(--accent2),0.08) 60%, rgba(255,255,255,0) 100%);} 
    @keyframes floatUp {0%{ transform: translate3d(-50%, 20vh, 0) scale(var(--s,1)); opacity:0 }10%{ opacity:0.85 }50%{ transform: translate3d(calc(-50% + var(--dx,0px)), calc(-40vh + var(--dz,0px)), 0) scale(calc(var(--s,1) * 1.05)) }90%{ opacity:0.5 }100%{ transform: translate3d(calc(-50% + var(--dx2,0px)), -120vh, 0) scale(var(--s,1)); opacity:0 }}
    header{position:fixed;top:0;left:0;right:0;z-index:10;display:flex;justify-content:center;background:rgba(0,0,0,0.3);backdrop-filter:blur(6px);padding:12px 24px;}
    nav ul{list-style:none;margin:0;padding:0;display:flex;gap:24px;}
    nav a{color:var(--text);text-decoration:none;font-weight:500;transition:color .2s;}
    nav a:hover{color:rgb(var(--accent));}
    .wrap{position:relative;z-index:5;min-height:100vh;display:flex;align-items:center;justify-content:center;padding:48px;}
    .card{width:min(980px,94vw);backdrop-filter: blur(8px) saturate(120%);background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.02));border-radius:var(--card-radius);padding:48px;box-shadow:0 10px 30px rgba(2,6,23,0.6);color:var(--text);pointer-events:auto;}
    h1{font-weight:700;margin:0 0 12px;font-size:clamp(22px,4vw,44px);line-height:1.02}
    p.lead{margin:0 0 20px;color:rgba(255,255,255,0.85);font-size:clamp(14px,1.8vw,18px)}
    .btn{display:inline-block;padding:12px 18px;border-radius:10px;background:rgba(255,255,255,0.06);color:var(--text);text-decoration:none;border:1px solid rgba(255,255,255,0.06);}
    footer{position:fixed;left:18px;bottom:18px;font-size:13px;color:rgba(255,255,255,0.6);z-index:6}
    @media (prefers-reduced-motion: reduce){.ball{animation:none;opacity:0.6}}
    @media (max-width:520px){.card{padding:28px}h1{font-size:28px}nav ul{gap:12px;}}
  </style>
</head>
<body>
  <div class="stage" aria-hidden="true"><div class="balls" id="balls"></div></div>

  <header>
    <nav>
      <ul>
        <li><a href="home.html">Home</a></li>
        <li><a href="About.html">About Us</a></li>
        <li><a href="services.html">Services</a></li>
        <li><a href="contact us.html">Contact Us</a></li>
        <li><a href="creator.html">Creator</a></li>
      </ul>
    </nav>
  </header>

  <main class="wrap">
    <section class="card" id="home">
      <h1>taskilyfy Site —for all u need  </h1>
      <p class="lead">A soft, modern landing style with animated translucent orbs drifting in the background — lightweight, accessible, and smooth on lower-end devices.</p>
      <p><a class="btn" href="fk.html">Explore</a></p>
    </section>
  </main>

  <footer>Made by gammersroomyt </footer>

  <script>
    (function(){
      const container = document.getElementById('balls');
      const max = Math.min(8, parseInt(getComputedStyle(document.documentElement).getPropertyValue('--max-balls')) || 6);
      const w = window.innerWidth;
      for(let i=0;i<max;i++){
        const el = document.createElement('div');
        el.className = 'ball ' + (Math.random()>.6? 'alt':'');
        const size = Math.round((Math.random()*160) + 60);
        el.style.width = size + 'px'; el.style.height = size + 'px';
        const left = Math.random()*100; el.style.left = left + 'vw';
        const top = 60 + Math.random()*35; el.style.top = top + 'vh';
        el.style.setProperty('--s', (0.6 + Math.random()*1.4).toFixed(2));
        const dx = Math.round((Math.random()-0.5) * (w * 0.4));
        const dx2 = Math.round((Math.random()-0.5) * (w * 0.4));
        const dz = Math.round((Math.random()-0.5) * 100);
        el.style.setProperty('--dx', dx+'px'); el.style.setProperty('--dx2', dx2+'px'); el.style.setProperty('--dz', dz+'px');
        const dur = (20 + Math.random()*20).toFixed(2);
        const delay = (Math.random()*-20).toFixed(2);
        el.style.animation = `floatUp ${dur}s linear ${delay}s infinite`;
        const blur = Math.round(6 + Math.random()*14);
        el.style.filter = `blur(${blur}px) saturate(110%)`;
        container.appendChild(el);
      }
    })();
  </script>
</body>
</html>
