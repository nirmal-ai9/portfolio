<!DOCTYPE html>
<html lang="en" style="scroll-behavior: smooth; font-size: 16px;">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nirmal — Frontend & UI Developer | Cyberpunk Edition</title>
<!-- Include a futuristic font -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Russo+One&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  /* Reset + things HTML attributes cannot express: pseudo-classes, pseudo-elements, keyframes, media queries */
  * { margin: 0; padding: 0; box-sizing: border-box; }

  ::selection { background: rgba(0, 255, 255, 0.08); color: #00ffff; }

  body::after {
    content: "";
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    background: repeating-linear-gradient(
      0deg,
      rgba(0, 0, 0, 0.15),
      rgba(0, 0, 0, 0.15) 1px,
      transparent 1px,
      transparent 2px
    );
    pointer-events: none;
    z-index: 1000;
  }

  @media (prefers-reduced-motion: reduce) {
    * { animation-duration: 0.01ms !important; transition-duration: 0.01ms !important; scroll-behavior: auto !important; }
  }

  a:hover { color: #00ffff; }
  .nav-links a:hover { color: #ffffff; text-shadow: 0 0 10px rgba(0, 255, 255, 0.3); }

  @keyframes wave {
    0%, 60%, 100% { transform: rotate(0deg); }
    10% { transform: rotate(14deg); }
    20% { transform: rotate(-8deg); }
    30% { transform: rotate(14deg); }
    40% { transform: rotate(-4deg); }
    50% { transform: rotate(10deg); }
  }

  .btn-primary:hover {
    transform: translateY(-3px) scale(1.02);
    box-shadow: 0 0 20px rgba(0, 255, 255, 0.6), 0 8px 22px rgba(0, 255, 255, 0.3);
    background: #00ffff;
    color: #030303;
  }

  .btn-secondary:hover {
    transform: translateY(-3px) scale(1.02);
    box-shadow: 0 0 20px rgba(255, 0, 255, 0.6), 0 8px 22px rgba(255, 0, 255, 0.3);
    background: #ff00ff;
    color: #030303;
  }

  .info-item:hover {
    transform: translateY(-4px);
    box-shadow: 0 0 15px rgba(0, 255, 255, 0.2);
    border-color: rgba(0, 255, 255, 0.25);
  }

  .skill-chip:hover {
    transform: translateY(-5px);
    scale: 1.05;
    box-shadow: 0 0 20px rgba(0, 255, 255, 0.6);
    border-color: rgba(0, 255, 255, 0.4);
  }

  .quote-card::before, .quote-card::after {
    content: '';
    position: absolute;
    width: 20px; height: 20px;
    border-style: solid;
    border-color: #00ffff;
    box-shadow: 0 0 10px rgba(0, 255, 255, 0.3);
  }
  .quote-card::before { top: -2px; left: -2px; border-width: 2px 0 0 2px; }
  .quote-card::after { bottom: -2px; right: -2px; border-width: 0 2px 2px 0; }

  .project-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 0 20px rgba(0, 255, 255, 0.6);
    border-color: rgba(0, 255, 255, 0.4);
  }
  .project-card::before, .project-card::after {
    content: '';
    position: absolute;
    width: 15px; height: 15px;
    border-style: solid;
    border-color: #00ffff;
    box-shadow: 0 0 10px rgba(0, 255, 255, 0.3);
    opacity: 0.1;
    transition: opacity 0.3s cubic-bezier(0.16, 1, 0.3, 1);
  }
  .project-card:hover::before, .project-card:hover::after { opacity: 1; }
  .project-card::before { top: -2px; left: -2px; border-width: 2px 0 0 2px; }
  .project-card::after { bottom: -2px; right: -2px; border-width: 0 2px 2px 0; }

  .visit-btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 0 20px rgba(0, 255, 255, 0.6);
    background: #00ffff;
    color: #030303;
  }
  .repo-btn:hover {
    transform: translateY(-3px);
    border-color: rgba(255, 255, 255, 0.4);
    box-shadow: 0 0 10px rgba(255, 255, 255, 0.2);
  }

  .community-card::before, .community-card::after {
    content: '';
    position: absolute;
    width: 25px; height: 25px;
    border-style: solid;
    border-color: #ff00ff;
    box-shadow: 0 0 20px rgba(255, 0, 255, 0.6);
  }
  .community-card::before { top: -2px; left: -2px; border-width: 2px 0 0 2px; }
  .community-card::after { bottom: -2px; right: -2px; border-width: 0 2px 2px 0; }

  .stats-card:hover { border-color: rgba(0, 255, 255, 0.3); box-shadow: 0 0 10px rgba(0, 255, 255, 0.3); }
  .stats-card::before {
    content: '';
    position: absolute;
    width: 10px; height: 10px;
    top: -2px; left: -2px;
    border-top: 2px solid #00ffff;
    border-left: 2px solid #00ffff;
    box-shadow: 0 0 10px rgba(0, 255, 255, 0.3);
  }

  @media (max-width: 900px) {
    .nav-inner { max-width: 100%; }
    main { max-width: 100%; }
  }

  @media (max-width: 720px) {
    .nav-links { display: none; }
    .hero-content-wrapper { grid-template-columns: 1fr; text-align: center; gap: 20px; }
    .hero-text-col { order: 2; }
    .hero-image-col { order: 1; }
    .hero-actions { justify-content: center; }
    .hero-typing { justify-content: center; }
    .about-grid { grid-template-columns: 1fr; }
    .project-grid { grid-template-columns: 1fr; }
    .stats-grid { grid-template-columns: 1fr; }
    section { padding: 64px 0 !important; }
    .hero { padding: 88px 0 64px !important; }
  }
</style>
</head>
<body style="font-family: 'Space Grotesk', sans-serif; background: #030303; color: #ffffff; line-height: 1.5; -webkit-font-smoothing: antialiased; background-image: linear-gradient(rgba(17, 17, 17, 0.98) 1px, transparent 1px), linear-gradient(90deg, rgba(17, 17, 17, 0.98) 1px, transparent 1px); background-size: 20px 20px;">

<nav class="nav" style="position: sticky; top: 0; z-index: 100; display: flex; justify-content: center; padding: 14px 24px; background: rgba(3, 3, 3, 0.85); backdrop-filter: blur(10px); -webkit-backdrop-filter: blur(10px); border-bottom: 2px solid #111111; box-shadow: 0 4px 15px rgba(0, 255, 255, 0.15);">
  <div class="nav-inner" style="display: flex; align-items: center; justify-content: space-between; width: 100%; max-width: 1100px;">
    <span style="font-family: 'Russo One', sans-serif; font-size: 18px; font-weight: 400; letter-spacing: 0.05em; color: #00ffff; text-shadow: 0 0 20px rgba(0, 255, 255, 0.6);">nirmal-ai9</span>
    <div class="nav-links" style="display: flex; gap: 28px;">
      <a href="#about" style="font-size: 14px; color: #aaaaaa; font-weight: 500; text-transform: uppercase; letter-spacing: 0.1em; text-decoration: none; transition: color 0.2s cubic-bezier(0.16, 1, 0.3, 1);">About</a>
      <a href="#skills" style="font-size: 14px; color: #aaaaaa; font-weight: 500; text-transform: uppercase; letter-spacing: 0.1em; text-decoration: none; transition: color 0.2s cubic-bezier(0.16, 1, 0.3, 1);">Arsenal</a>
      <a href="#projects" style="font-size: 14px; color: #aaaaaa; font-weight: 500; text-transform: uppercase; letter-spacing: 0.1em; text-decoration: none; transition: color 0.2s cubic-bezier(0.16, 1, 0.3, 1);">Work</a>
      <a href="#community" style="font-size: 14px; color: #aaaaaa; font-weight: 500; text-transform: uppercase; letter-spacing: 0.1em; text-decoration: none; transition: color 0.2s cubic-bezier(0.16, 1, 0.3, 1);">Community</a>
      <a href="#stats" style="font-size: 14px; color: #aaaaaa; font-weight: 500; text-transform: uppercase; letter-spacing: 0.1em; text-decoration: none; transition: color 0.2s cubic-bezier(0.16, 1, 0.3, 1);">Analytics</a>
    </div>
  </div>
</nav>

<main style="max-width: 1100px; margin: 0 auto; padding: 0 24px;">

  <section class="hero" style="padding: 120px 0 96px; border-bottom: 2px solid #111111; position: relative; overflow: hidden;">
    <div class="hero-content-wrapper" style="display: grid; grid-template-columns: 1.1fr 0.9fr; gap: 40px; align-items: center;">
      <div class="hero-text-col" style="display: flex; flex-direction: column; justify-content: center;">
        <span style="display: inline-block; font-size: 48px; animation: wave 2.4s ease-in-out infinite; transform-origin: 70% 70%; margin-bottom: 20px; filter: drop-shadow(0 0 5px rgba(0, 255, 255, 0.5));">👋</span>
        <h1 style="font-family: 'Russo One', sans-serif; font-size: clamp(44px, 8vw, 72px); font-weight: 400; letter-spacing: -0.03em; color: #00ffff; text-shadow: 0 0 20px rgba(0, 255, 255, 0.6);">Hi, I'm Nirmal</h1>
        <p style="margin-top: 18px; font-size: clamp(17px, 2.8vw, 21px); color: #ffffff; font-weight: 600; text-shadow: 0 0 8px rgba(255, 255, 255, 0.3);">Frontend & UI Developer | Hacking Web Realms | Aspiring Full-Stack</p>
        <div class="hero-typing" style="margin-top: 32px; display: flex;">
          <img
            src="https://readme-typing-svg.demolab.com?font=Space+Grotesk&weight=600&size=20&pause=1000&color=FF00FF&background=00000000&center=false&vCenter=true&width=520&height=40&lines=Compiling+Frontend+%26+UI+protocols...;Deploying+Single-File+Web+Modules...;Injecting+Clean+Code+%26+Core+Design...;Accessing+Backend+Development+Nodes..."
            alt="Typing animation of Nirmal's focus areas"
            style="max-width: 100%; height: auto; filter: drop-shadow(0 0 6px rgba(255, 0, 255, 0.4));"
          />
        </div>
        <div class="hero-actions" style="margin-top: 48px; display: flex; gap: 16px; flex-wrap: wrap;">
          <a class="btn-primary" href="mailto:nirmal942894@gmail.com" style="display: inline-flex; align-items: center; gap: 10px; padding: 14px 26px; border-radius: 980px; font-size: 15px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; transition: transform 0.35s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.35s cubic-bezier(0.16, 1, 0.3, 1), background 0.2s; text-decoration: none; background: #0a0a0c; color: #00ffff; border: 2px solid #00ffff; box-shadow: 0 0 10px rgba(0, 255, 255, 0.3);">Initialize mail</a>
          <a class="btn-secondary" href="https://discord.gg/dKa2wEJGF9" target="_blank" rel="noopener" style="display: inline-flex; align-items: center; gap: 10px; padding: 14px 26px; border-radius: 980px; font-size: 15px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; transition: transform 0.35s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.35s cubic-bezier(0.16, 1, 0.3, 1), background 0.2s; text-decoration: none; background: #0a0a0c; color: #ff00ff; border: 2px solid #ff00ff; box-shadow: 0 0 10px rgba(255, 0, 255, 0.3);">Connect Discord</a>
        </div>
        <div style="margin-top: 36px; display: inline-block; opacity: 0.9;">
          <img src="https://komarev.com/ghpvc/?username=nirmal-ai9&style=flat-square&color=2F80ED&label=PROFILE+VIEWS" alt="Profile views" style="border-radius: 4px; height: 24px; filter: drop-shadow(0 0 5px rgba(0, 255, 255, 0.4));" />
        </div>
      </div>
      <div class="hero-image-col" style="display: flex; justify-content: center; align-items: center; position: relative;">
        <img src="anime.png" alt="Nirmal's digital avatar" style="max-width: 100%; height: auto; border-radius: 8px; filter: drop-shadow(0 0 15px rgba(0, 255, 255, 0.3)) drop-shadow(0 0 30px rgba(148, 0, 211, 0.3)); mask-image: linear-gradient(to bottom, transparent, black 10%, black 90%, transparent); -webkit-mask-image: linear-gradient(to bottom, transparent, black 10%, black 90%, transparent);" />
      </div>
    </div>
  </section>

  <section id="about" style="padding: 88px 0; border-bottom: 2px solid #111111;">
    <span style="font-size: 12px; font-weight: 600; letter-spacing: 0.15em; text-transform: uppercase; color: #9400d3; margin-bottom: 12px; display: block; text-shadow: 0 0 10px rgba(148, 0, 211, 0.5);">Data segment_</span>
    <h2 style="font-family: 'Russo One', sans-serif; font-size: clamp(30px, 5vw, 42px); font-weight: 400; letter-spacing: -0.02em; margin-bottom: 48px; color: #ffffff; text-shadow: 0 0 15px rgba(255, 255, 255, 0.4);">Design first. Function always.</h2>
    <div class="about-grid" style="display: grid; grid-template-columns: 1.1fr 0.9fr; gap: 32px;">
      <div>
        <p style="font-size: 18px; color: #aaaaaa; margin-bottom: 24px;">I'm a <strong style="color: #ffffff; font-weight: 600; text-shadow: 0 0 5px rgba(255, 255, 255, 0.2);">Frontend & UI Developer</strong> with a strong focus on minimal aesthetics, semantic HTML, and accessible web design. My philosophy revolves around writing clean, duplication-free code and shipping highly functional web applications.</p>
        <p style="font-size: 18px; color: #aaaaaa; margin-bottom: 24px;">Lately I've been deepening my knowledge in <strong style="color: #ffffff; font-weight: 600; text-shadow: 0 0 5px rgba(255, 255, 255, 0.2);">Node.js, databases, and server-side development</strong> — bridging the gap toward full-stack engineering, one project at a time.</p>
        <div class="quote-card" style="background: #0a0a0c; border: 2px solid rgba(0, 255, 255, 0.15); border-radius: 8px; padding: 28px; font-size: 16px; font-style: italic; color: #aaaaaa; position: relative; box-shadow: 0 0 10px rgba(0, 255, 255, 0.1);">"No dead code, no duplication, nothing left half-finished."</div>
      </div>
      <div style="display: flex; flex-direction: column; gap: 18px;">
        <div class="info-item" style="background: #0a0a0c; border: 2px solid #111111; border-radius: 8px; padding: 20px 22px; transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s;">
          <span style="font-size: 12px; font-weight: 600; color: #9400d3; text-transform: uppercase; letter-spacing: 0.1em; display: block; margin-bottom: 8px; text-shadow: 0 0 8px rgba(148, 0, 211, 0.4);">Current protocol focus_</span>
          <span style="font-size: 15.5px; color: #ffffff; text-shadow: 0 0 5px rgba(255, 255, 255, 0.2);">Perfecting UI architecture & single-file HTML apps</span>
        </div>
        <div class="info-item" style="background: #0a0a0c; border: 2px solid #111111; border-radius: 8px; padding: 20px 22px; transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s;">
          <span style="font-size: 12px; font-weight: 600; color: #9400d3; text-transform: uppercase; letter-spacing: 0.1em; display: block; margin-bottom: 8px; text-shadow: 0 0 8px rgba(148, 0, 211, 0.4);">Learning stack_</span>
          <span style="font-size: 15.5px; color: #ffffff; text-shadow: 0 0 5px rgba(255, 255, 255, 0.2);">Node.js, databases & backend fundamentals</span>
        </div>
        <div class="info-item" style="background: #0a0a0c; border: 2px solid #111111; border-radius: 8px; padding: 20px 22px; transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s;">
          <span style="font-size: 12px; font-weight: 600; color: #9400d3; text-transform: uppercase; letter-spacing: 0.1em; display: block; margin-bottom: 8px; text-shadow: 0 0 8px rgba(148, 0, 211, 0.4);">Contact for data exchange_</span>
          <span style="font-size: 15.5px; color: #ffffff; text-shadow: 0 0 5px rgba(255, 255, 255, 0.2);">UI polishing, frontend collabs, JS challenges</span>
        </div>
      </div>
    </div>
  </section>

  <section id="skills" style="padding: 88px 0; border-bottom: 2px solid #111111;">
    <span style="font-size: 12px; font-weight: 600; letter-spacing: 0.15em; text-transform: uppercase; color: #9400d3; margin-bottom: 12px; display: block; text-shadow: 0 0 10px rgba(148, 0, 211, 0.5);">Hacker Arsenal_</span>
    <h2 style="font-family: 'Russo One', sans-serif; font-size: clamp(30px, 5vw, 42px); font-weight: 400; letter-spacing: -0.02em; margin-bottom: 48px; color: #ffffff; text-shadow: 0 0 15px rgba(255, 255, 255, 0.4);">Technical loadout</h2>
    <div style="margin-bottom: 40px;">
      <div style="font-size: 14px; font-weight: 600; color: #aaaaaa; margin-bottom: 18px; text-transform: uppercase; letter-spacing: 0.1em;">Frontend_cores</div>
      <div style="display: flex; flex-wrap: wrap; gap: 16px;">
        <div class="skill-chip" style="display: flex; align-items: center; justify-content: center; width: 60px; height: 60px; background: #0a0a0c; border: 2px solid #111111; border-radius: 4px; box-shadow: 0 0 5px rgba(0, 255, 255, 0.1); transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s, scale 0.3s cubic-bezier(0.16, 1, 0.3, 1);"><img src="https://skillicons.dev/icons?i=html" alt="HTML" style="width: 32px; height: 32px; filter: drop-shadow(0 0 2px rgba(255, 255, 255, 0.4));"></div>
        <div class="skill-chip" style="display: flex; align-items: center; justify-content: center; width: 60px; height: 60px; background: #0a0a0c; border: 2px solid #111111; border-radius: 4px; box-shadow: 0 0 5px rgba(0, 255, 255, 0.1); transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s, scale 0.3s cubic-bezier(0.16, 1, 0.3, 1);"><img src="https://skillicons.dev/icons?i=css" alt="CSS" style="width: 32px; height: 32px; filter: drop-shadow(0 0 2px rgba(255, 255, 255, 0.4));"></div>
        <div class="skill-chip" style="display: flex; align-items: center; justify-content: center; width: 60px; height: 60px; background: #0a0a0c; border: 2px solid #111111; border-radius: 4px; box-shadow: 0 0 5px rgba(0, 255, 255, 0.1); transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s, scale 0.3s cubic-bezier(0.16, 1, 0.3, 1);"><img src="https://skillicons.dev/icons?i=js" alt="JavaScript" style="width: 32px; height: 32px; filter: drop-shadow(0 0 2px rgba(255, 255, 255, 0.4));"></div>
      </div>
    </div>
    <div>
      <div style="font-size: 14px; font-weight: 600; color: #aaaaaa; margin-bottom: 18px; text-transform: uppercase; letter-spacing: 0.1em;">Backend & Tooling_engines</div>
      <div style="display: flex; flex-wrap: wrap; gap: 16px;">
        <div class="skill-chip" style="display: flex; align-items: center; justify-content: center; width: 60px; height: 60px; background: #0a0a0c; border: 2px solid #111111; border-radius: 4px; box-shadow: 0 0 5px rgba(0, 255, 255, 0.1); transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s, scale 0.3s cubic-bezier(0.16, 1, 0.3, 1);"><img src="https://skillicons.dev/icons?i=nodejs" alt="Node.js" style="width: 32px; height: 32px; filter: drop-shadow(0 0 2px rgba(255, 255, 255, 0.4));"></div>
        <div class="skill-chip" style="display: flex; align-items: center; justify-content: center; width: 60px; height: 60px; background: #0a0a0c; border: 2px solid #111111; border-radius: 4px; box-shadow: 0 0 5px rgba(0, 255, 255, 0.1); transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s, scale 0.3s cubic-bezier(0.16, 1, 0.3, 1);"><img src="https://skillicons.dev/icons?i=mongodb" alt="MongoDB" style="width: 32px; height: 32px; filter: drop-shadow(0 0 2px rgba(255, 255, 255, 0.4));"></div>
        <div class="skill-chip" style="display: flex; align-items: center; justify-content: center; width: 60px; height: 60px; background: #0a0a0c; border: 2px solid #111111; border-radius: 4px; box-shadow: 0 0 5px rgba(0, 255, 255, 0.1); transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s, scale 0.3s cubic-bezier(0.16, 1, 0.3, 1);"><img src="https://skillicons.dev/icons?i=git" alt="Git" style="width: 32px; height: 32px; filter: drop-shadow(0 0 2px rgba(255, 255, 255, 0.4));"></div>
        <div class="skill-chip" style="display: flex; align-items: center; justify-content: center; width: 60px; height: 60px; background: #0a0a0c; border: 2px solid #111111; border-radius: 4px; box-shadow: 0 0 5px rgba(0, 255, 255, 0.1); transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s, scale 0.3s cubic-bezier(0.16, 1, 0.3, 1);"><img src="https://skillicons.dev/icons?i=github" alt="GitHub" style="width: 32px; height: 32px; filter: drop-shadow(0 0 2px rgba(255, 255, 255, 0.4));"></div>
        <div class="skill-chip" style="display: flex; align-items: center; justify-content: center; width: 60px; height: 60px; background: #0a0a0c; border: 2px solid #111111; border-radius: 4px; box-shadow: 0 0 5px rgba(0, 255, 255, 0.1); transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s, scale 0.3s cubic-bezier(0.16, 1, 0.3, 1);"><img src="https://skillicons.dev/icons?i=vscode" alt="VS Code" style="width: 32px; height: 32px; filter: drop-shadow(0 0 2px rgba(255, 255, 255, 0.4));"></div>
      </div>
    </div>
  </section>

  <section id="projects" style="padding: 88px 0; border-bottom: 2px solid #111111;">
    <span style="font-size: 12px; font-weight: 600; letter-spacing: 0.15em; text-transform: uppercase; color: #9400d3; margin-bottom: 12px; display: block; text-shadow: 0 0 10px rgba(148, 0, 211, 0.5);">Projects segment_</span>
    <h2 style="font-family: 'Russo One', sans-serif; font-size: clamp(30px, 5vw, 42px); font-weight: 400; letter-spacing: -0.02em; margin-bottom: 48px; color: #ffffff; text-shadow: 0 0 15px rgba(255, 255, 255, 0.4);">Selected work logs</h2>
    <div class="project-grid" style="display: grid; grid-template-columns: repeat(2, 1fr); gap: 20px;">
      <div class="project-card" style="background: #0a0a0c; border: 2px solid #111111; border-radius: 8px; padding: 28px; box-shadow: 0 0 10px rgba(0, 255, 255, 0.1); transition: transform 0.35s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.35s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s; position: relative;">
        <h3 style="font-family: 'Space Grotesk', sans-serif; font-size: 18px; font-weight: 700; margin-bottom: 10px; letter-spacing: -0.01em; color: #ffffff; text-shadow: 0 0 5px rgba(255, 255, 255, 0.2);">JavaScript Challenges</h3>
        <p style="font-size: 14.5px; color: #aaaaaa;">A terminal-based collection of JavaScript challenges — solve problems, auto-generate solution templates, run tests, and contribute solutions through pull requests.</p>
        <div style="display: flex; gap: 12px; margin-top: 20px; flex-wrap: wrap;">
          <a class="repo-btn" href="https://github.com/nirmal-ai9/JavaScript-challenges" target="_blank" rel="noopener" style="display: inline-flex; align-items: center; gap: 6px; font-size: 13px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; padding: 10px 16px; border-radius: 980px; transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), background 0.2s; text-decoration: none; background: transparent; color: #ffffff; border: 2px solid #111111;">View repo_</a>
        </div>
      </div>
      <div class="project-card" style="background: #0a0a0c; border: 2px solid #111111; border-radius: 8px; padding: 28px; box-shadow: 0 0 10px rgba(0, 255, 255, 0.1); transition: transform 0.35s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.35s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s; position: relative;">
        <h3 style="font-family: 'Space Grotesk', sans-serif; font-size: 18px; font-weight: 700; margin-bottom: 10px; letter-spacing: -0.01em; color: #ffffff; text-shadow: 0 0 5px rgba(255, 255, 255, 0.2);">TypeFlow</h3>
        <p style="font-size: 14.5px; color: #aaaaaa;">Practice typing smarter, faster, and more accurately — a browser-based typing speed test with a clean, distraction-free interface.</p>
        <div style="display: flex; gap: 12px; margin-top: 20px; flex-wrap: wrap;">
          <a class="visit-btn" href="https://nirmal-ai9.github.io/TypeFlow/" target="_blank" rel="noopener" style="display: inline-flex; align-items: center; gap: 6px; font-size: 13px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; padding: 10px 16px; border-radius: 980px; transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), background 0.2s; text-decoration: none; background: transparent; color: #00ffff; border: 2px solid #00ffff; box-shadow: 0 0 10px rgba(0, 255, 255, 0.3);">Visit site_</a>
          <a class="repo-btn" href="https://github.com/nirmal-ai9/TypeFlow" target="_blank" rel="noopener" style="display: inline-flex; align-items: center; gap: 6px; font-size: 13px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; padding: 10px 16px; border-radius: 980px; transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), background 0.2s; text-decoration: none; background: transparent; color: #ffffff; border: 2px solid #111111;">View repo_</a>
        </div>
      </div>
      <div class="project-card" style="background: #0a0a0c; border: 2px solid #111111; border-radius: 8px; padding: 28px; box-shadow: 0 0 10px rgba(0, 255, 255, 0.1); transition: transform 0.35s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.35s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s; position: relative;">
        <h3 style="font-family: 'Space Grotesk', sans-serif; font-size: 18px; font-weight: 700; margin-bottom: 10px; letter-spacing: -0.01em; color: #ffffff; text-shadow: 0 0 5px rgba(255, 255, 255, 0.2);">Inflation Calculator</h3>
        <p style="font-size: 14.5px; color: #aaaaaa;">A modern web-based inflation calculator that shows how money changes in value over time using compound inflation.</p>
        <div style="display: flex; gap: 12px; margin-top: 20px; flex-wrap: wrap;">
          <a class="visit-btn" href="https://nirmal-ai9.github.io/Inflation-calculator/" target="_blank" rel="noopener" style="display: inline-flex; align-items: center; gap: 6px; font-size: 13px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; padding: 10px 16px; border-radius: 980px; transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), background 0.2s; text-decoration: none; background: transparent; color: #00ffff; border: 2px solid #00ffff; box-shadow: 0 0 10px rgba(0, 255, 255, 0.3);">Visit site_</a>
          <a class="repo-btn" href="https://github.com/nirmal-ai9/Inflation-calculator" target="_blank" rel="noopener" style="display: inline-flex; align-items: center; gap: 6px; font-size: 13px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; padding: 10px 16px; border-radius: 980px; transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), background 0.2s; text-decoration: none; background: transparent; color: #ffffff; border: 2px solid #111111;">View repo_</a>
        </div>
      </div>
      <div class="project-card" style="background: #0a0a0c; border: 2px solid #111111; border-radius: 8px; padding: 28px; box-shadow: 0 0 10px rgba(0, 255, 255, 0.1); transition: transform 0.35s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.35s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s; position: relative;">
        <h3 style="font-family: 'Space Grotesk', sans-serif; font-size: 18px; font-weight: 700; margin-bottom: 10px; letter-spacing: -0.01em; color: #ffffff; text-shadow: 0 0 5px rgba(255, 255, 255, 0.2);">Chess Clock</h3>
        <p style="font-size: 14.5px; color: #aaaaaa;">Chess clock for over-the-board play — monochrome flip theme, custom time controls, Fischer increment, single HTML file.</p>
        <div style="display: flex; gap: 12px; margin-top: 20px; flex-wrap: wrap;">
          <a class="visit-btn" href="https://nirmal-ai9.github.io/Chess-clock/" target="_blank" rel="noopener" style="display: inline-flex; align-items: center; gap: 6px; font-size: 13px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; padding: 10px 16px; border-radius: 980px; transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), background 0.2s; text-decoration: none; background: transparent; color: #00ffff; border: 2px solid #00ffff; box-shadow: 0 0 10px rgba(0, 255, 255, 0.3);">Visit site_</a>
          <a class="repo-btn" href="https://github.com/nirmal-ai9/Chess-clock" target="_blank" rel="noopener" style="display: inline-flex; align-items: center; gap: 6px; font-size: 13px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; padding: 10px 16px; border-radius: 980px; transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1), background 0.2s; text-decoration: none; background: transparent; color: #ffffff; border: 2px solid #111111;">View repo_</a>
        </div>
      </div>
    </div>
  </section>

  <section id="community" style="padding: 88px 0; border-bottom: 2px solid #111111;">
    <span style="font-size: 12px; font-weight: 600; letter-spacing: 0.15em; text-transform: uppercase; color: #9400d3; margin-bottom: 12px; display: block; text-shadow: 0 0 10px rgba(148, 0, 211, 0.5);">Network segment_</span>
    <h2 style="font-family: 'Russo One', sans-serif; font-size: clamp(30px, 5vw, 42px); font-weight: 400; letter-spacing: -0.02em; margin-bottom: 48px; color: #ffffff; text-shadow: 0 0 15px rgba(255, 255, 255, 0.4);">Build in public</h2>
    <div class="community-card" style="background: linear-gradient(135deg, rgba(148, 0, 211, 0.15), rgba(0, 255, 255, 0.15), transparent 70%); border: 2px solid rgba(0, 255, 255, 0.2); border-radius: 12px; padding: 50px 40px; text-align: center; position: relative; box-shadow: 0 0 15px rgba(148, 0, 211, 0.2), 0 0 15px rgba(0, 255, 255, 0.2);">
      <h3 style="font-family: 'Space Grotesk', sans-serif; font-size: 20px; font-weight: 700; color: #ffffff; text-shadow: 0 0 5px rgba(255, 255, 255, 0.2);">Frontend & UI Developers Discord</h3>
      <p style="color: #aaaaaa; font-size: 16px; max-width: 520px; margin: 14px auto 32px;">Share feedback on projects, debug JavaScript together, and talk about modern web tech with a community of builders.</p>
      <div style="display: flex; justify-content: center; gap: 32px; flex-wrap: wrap; margin-bottom: 36px;">
        <div style="font-size: 14px; color: #aaaaaa; font-weight: 500; text-shadow: 0 0 5px rgba(255, 255, 255, 0.1);">🚀 Code reviews</div>
        <div style="font-size: 14px; color: #aaaaaa; font-weight: 500; text-shadow: 0 0 5px rgba(255, 255, 255, 0.1);">💡 Learning together</div>
        <div style="font-size: 14px; color: #aaaaaa; font-weight: 500; text-shadow: 0 0 5px rgba(255, 255, 255, 0.1);">🛠️ Build in public</div>
      </div>
      <a class="btn-primary" href="https://discord.gg/dKa2wEJGF9" target="_blank" rel="noopener" style="display: inline-flex; align-items: center; gap: 10px; padding: 14px 26px; border-radius: 980px; font-size: 15px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; transition: transform 0.35s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.35s cubic-bezier(0.16, 1, 0.3, 1), background 0.2s; text-decoration: none; background: #0a0a0c; color: #00ffff; border: 2px solid #00ffff; box-shadow: 0 0 10px rgba(0, 255, 255, 0.3);">Connect Discord server</a>
    </div>
  </section>

  <section id="stats" style="padding: 88px 0;">
    <span style="font-size: 12px; font-weight: 600; letter-spacing: 0.15em; text-transform: uppercase; color: #9400d3; margin-bottom: 12px; display: block; text-shadow: 0 0 10px rgba(148, 0, 211, 0.5);">Analytics segment_</span>
    <h2 style="font-family: 'Russo One', sans-serif; font-size: clamp(30px, 5vw, 42px); font-weight: 400; letter-spacing: -0.02em; margin-bottom: 48px; color: #ffffff; text-shadow: 0 0 15px rgba(255, 255, 255, 0.4);">GitHub activity feed</h2>
    <div class="stats-grid" style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">
      <div class="stats-card" style="background: #0a0a0c; border: 2px solid #111111; border-radius: 8px; padding: 16px; box-shadow: 0 0 10px rgba(0, 255, 255, 0.1); display: flex; align-items: center; justify-content: center; overflow: hidden; min-height: 180px; position: relative; transition: border-color 0.3s;">
        <img src="https://stats-three-mu.vercel.app/api?username=nirmal-ai9&show_icons=true&theme=transparent&hide_border=true&count_private=true&title_color=00ffff&icon_color=00ffff" alt="GitHub stats" style="width: 100%; height: auto; display: block; filter: drop-shadow(0 0 5px rgba(0, 255, 255, 0.3));">
      </div>
      <div class="stats-card" style="background: #0a0a0c; border: 2px solid #111111; border-radius: 8px; padding: 16px; box-shadow: 0 0 10px rgba(0, 255, 255, 0.1); display: flex; align-items: center; justify-content: center; overflow: hidden; min-height: 180px; position: relative; transition: border-color 0.3s;">
        <img src="https://stats-three-mu.vercel.app/api/top-langs/?username=nirmal-ai9&layout=compact&theme=transparent&hide_border=true&title_color=00ffff" alt="Top languages" style="width: 100%; height: auto; display: block; filter: drop-shadow(0 0 5px rgba(0, 255, 255, 0.3));">
      </div>
      <div class="stats-card" style="background: #0a0a0c; border: 2px solid #111111; border-radius: 8px; padding: 16px; box-shadow: 0 0 10px rgba(0, 255, 255, 0.1); display: flex; align-items: center; justify-content: center; overflow: hidden; min-height: 180px; position: relative; transition: border-color 0.3s; grid-column: 1 / -1;">
        <img src="https://streak-stats.demolab.com?user=nirmal-ai9&theme=transparent&hide_border=true&fire=00ffff&ring=00ffff" alt="GitHub streak" style="width: 100%; height: auto; display: block; filter: drop-shadow(0 0 5px rgba(0, 255, 255, 0.3));">
      </div>
    </div>
  </section>

</main>

<footer style="text-align: center; padding: 48px 24px 64px; color: #aaaaaa; font-size: 14px; border-top: 2px solid #111111; margin-top: 64px;">
  Constructed by Nirmal::ai9 · Frontend & UI Developer · Cyberpunk ed.
</footer>

</body>
</html>
