<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Anees Kumar Ghosh | UI/UX Designer & PC Gamer</title>
  <meta name="description" content="Anees Kumar Ghosh — UI/UX Designer, PC Gamer, Creative Thinker. Portfolio and profile." />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />
  <style>
    :root {
      --bg: #06060a;
      --bg-2: #0b0b14;
      --surface: rgba(255, 255, 255, 0.03);
      --border: rgba(255, 255, 255, 0.07);
      --border-2: rgba(255, 255, 255, 0.12);
      --text: #f4f4f8;
      --text-dim: rgba(244, 244, 248, 0.55);
      --text-mute: rgba(244, 244, 248, 0.35);
      --cyan: #22d3ee;
      --violet: #8b5cf6;
      --amber: #fbbf24;
      --emerald: #34d399;
      --ease: cubic-bezier(0.22, 1, 0.36, 1);
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Inter', sans-serif;
      background: var(--bg);
      color: var(--text);
      overflow-x: hidden;
      min-height: 100vh;
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
    }

    h1, h2, h3, h4, h5 {
      font-family: 'Space Grotesk', sans-serif;
      letter-spacing: -0.02em;
      line-height: 1.15;
    }

    a { color: inherit; text-decoration: none; }

    ::-webkit-scrollbar { width: 8px; }
    ::-webkit-scrollbar-track { background: rgba(255,255,255,0.02); }
    ::-webkit-scrollbar-thumb {
      border-radius: 10px;
      background: linear-gradient(180deg, var(--cyan), var(--violet));
    }
    ::-webkit-scrollbar-thumb:hover {
      background: linear-gradient(180deg, var(--cyan), var(--amber));
    }

    /* Aurora background */
    .aurora {
      position: fixed; inset: 0; z-index: 0; overflow: hidden; pointer-events: none;
    }
    .aurora::before, .aurora::after {
      content: ''; position: absolute; border-radius: 50%;
      filter: blur(120px); opacity: 0.45;
      animation: auroraFloat 22s ease-in-out infinite;
    }
    .aurora::before {
      width: 600px; height: 600px;
      background: radial-gradient(circle, rgba(34, 211, 238, 0.35), transparent 70%);
      top: -200px; left: -150px;
    }
    .aurora::after {
      width: 700px; height: 700px;
      background: radial-gradient(circle, rgba(139, 92, 246, 0.3), transparent 70%);
      bottom: -250px; right: -200px; animation-delay: -8s;
    }
    @keyframes auroraFloat {
      0%, 100% { transform: translate(0, 0) scale(1); }
      33% { transform: translate(80px, 60px) scale(1.15); }
      66% { transform: translate(-60px, 40px) scale(0.9); }
    }

    .grid-overlay {
      position: fixed; inset: 0; z-index: 0; pointer-events: none;
      background-image:
        linear-gradient(rgba(255,255,255,0.025) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.025) 1px, transparent 1px);
      background-size: 60px 60px;
      mask-image: radial-gradient(ellipse at center, black 40%, transparent 80%);
      -webkit-mask-image: radial-gradient(ellipse at center, black 40%, transparent 80%);
    }

    /* Container */
    .container {
      position: relative; z-index: 2;
      max-width: 1100px; margin: 0 auto; padding: 0 24px;
    }

    /* Header / Hero */
    .hero {
      position: relative; z-index: 2;
      padding: 80px 24px 60px;
      text-align: center;
    }
    .hero-badge {
      display: inline-flex; align-items: center; gap: 8px;
      padding: 8px 16px; border-radius: 40px;
      background: rgba(52, 211, 153, 0.08);
      border: 1px solid rgba(52, 211, 153, 0.2);
      font-size: 12px; color: var(--emerald); font-weight: 500;
      margin-bottom: 24px;
    }
    .hero-badge .dot {
      width: 7px; height: 7px; border-radius: 50%;
      background: var(--emerald); box-shadow: 0 0 10px var(--emerald);
      animation: pulseDot 2s ease-in-out infinite;
    }
    @keyframes pulseDot {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.5; transform: scale(0.8); }
    }
    .hero-title {
      font-size: clamp(2.4rem, 6vw, 4.2rem);
      font-weight: 700; line-height: 1.05;
      letter-spacing: -0.03em; margin-bottom: 16px;
    }
    .hero-title .line-2 {
      display: block;
      background: linear-gradient(120deg, var(--cyan) 0%, var(--violet) 50%, var(--amber) 100%);
      background-size: 200% auto;
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      background-clip: text;
      animation: gradientShift 6s ease infinite;
    }
    @keyframes gradientShift {
      0%, 100% { background-position: 0% center; }
      50% { background-position: 100% center; }
    }
    .hero-sub {
      font-size: 1.05rem; color: var(--text-dim);
      max-width: 600px; margin: 0 auto 24px; line-height: 1.7;
    }
    .hero-sub .highlight { color: var(--cyan); font-weight: 600; }

    /* Profile stats row */
    .stat-row {
      display: flex; flex-wrap: wrap; justify-content: center;
      gap: 24px; margin: 32px 0 20px;
    }
    .stat-item {
      background: var(--surface); border: 1px solid var(--border);
      border-radius: 16px; padding: 16px 28px;
      min-width: 100px;
    }
    .stat-item .num {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1.8rem; font-weight: 700;
      background: linear-gradient(135deg, var(--cyan), var(--violet));
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      background-clip: text; line-height: 1.2;
    }
    .stat-item .label {
      font-size: 11px; color: var(--text-mute);
      text-transform: uppercase; letter-spacing: 1.5px; margin-top: 4px;
    }

    /* Social badges */
    .badge-row {
      display: flex; flex-wrap: wrap; justify-content: center;
      gap: 10px; margin: 20px 0;
    }
    .badge-row img {
      height: 28px; border-radius: 6px;
      transition: transform 0.3s var(--ease), box-shadow 0.3s var(--ease);
    }
    .badge-row img:hover {
      transform: translateY(-3px) scale(1.05);
      box-shadow: 0 8px 20px rgba(34, 211, 238, 0.2);
    }

    /* Divider */
    .divider {
      height: 2px; width: 100%;
      background: linear-gradient(90deg, transparent, var(--cyan), var(--violet), var(--amber), transparent);
      margin: 40px 0;
      opacity: 0.6;
      border-radius: 2px;
    }

    /* Section */
    .section {
      position: relative; z-index: 2;
      padding: 30px 24px;
    }
    .section-header {
      margin-bottom: 28px;
    }
    .section-eyebrow {
      display: inline-flex; align-items: center; gap: 10px;
      font-family: 'JetBrains Mono', monospace;
      font-size: 11px; letter-spacing: 3px; text-transform: uppercase;
      color: var(--cyan); padding: 6px 14px; border-radius: 40px;
      background: rgba(34, 211, 238, 0.08);
      border: 1px solid rgba(34, 211, 238, 0.15);
      margin-bottom: 12px;
    }
    .section-eyebrow::before {
      content: ''; width: 6px; height: 6px; border-radius: 50%;
      background: var(--cyan); box-shadow: 0 0 10px var(--cyan);
      animation: pulseDot 2s ease-in-out infinite;
    }
    .section-title {
      font-size: clamp(1.6rem, 4vw, 2.4rem);
      font-weight: 700;
      background: linear-gradient(135deg, #fff 30%, rgba(34, 211, 238, 0.9));
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      background-clip: text;
      letter-spacing: -0.03em;
    }
    .section-title .accent {
      background: linear-gradient(135deg, var(--cyan), var(--violet));
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    /* Glass card */
    .glass-card {
      position: relative;
      background: rgba(255, 255, 255, 0.025);
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(20px);
      border: 1px solid var(--border);
      border-radius: 20px;
      transition: all 0.5s var(--ease);
      overflow: hidden;
      padding: 24px;
    }
    .glass-card:hover {
      transform: translateY(-4px);
      border-color: rgba(34, 211, 238, 0.2);
      box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5), 0 0 40px rgba(34, 211, 238, 0.08);
      background: rgba(255, 255, 255, 0.04);
    }

    /* About table */
    .about-table {
      width: 100%; border-collapse: collapse;
    }
    .about-table td {
      vertical-align: top; padding: 0;
    }
    .about-table pre {
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 16px;
      font-family: 'JetBrains Mono', monospace;
      font-size: 12px; line-height: 1.8;
      color: var(--text-dim);
      overflow-x: auto;
      white-space: pre-wrap;
      word-break: break-word;
    }
    .about-table pre .key { color: var(--cyan); }
    .about-table pre .val { color: var(--amber); }
    .about-table pre .str { color: var(--emerald); }

    .about-list {
      list-style: none; padding: 0;
    }
    .about-list li {
      padding: 6px 0; font-size: 14px;
      color: var(--text-dim);
      display: flex; align-items: flex-start; gap: 10px;
    }
    .about-list li i {
      color: var(--cyan); font-size: 14px; margin-top: 3px;
      min-width: 18px;
    }

    /* Tech icons grid */
    .tech-grid {
      display: flex; flex-wrap: wrap; gap: 8px;
      margin: 8px 0;
    }
    .tech-grid img {
      height: 32px;
      transition: transform 0.3s var(--ease);
    }
    .tech-grid img:hover { transform: translateY(-3px) scale(1.1); }

    .tech-sub-label {
      font-size: 11px; text-transform: uppercase;
      letter-spacing: 1.5px; color: var(--text-mute);
      margin: 16px 0 8px;
      font-weight: 600;
    }

    /* Stats images */
    .stats-row {
      display: flex; flex-wrap: wrap; justify-content: center;
      gap: 16px; margin: 16px 0;
    }
    .stats-row img {
      max-width: 100%; height: auto; border-radius: 12px;
    }

    /* Projects grid */
    .project-grid {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 20px;
    }
    .project-card {
      position: relative;
      background: rgba(255, 255, 255, 0.025);
      backdrop-filter: blur(20px);
      border: 1px solid var(--border);
      border-radius: 18px;
      padding: 22px;
      transition: all 0.4s var(--ease);
      display: flex; flex-direction: column;
    }
    .project-card:hover {
      transform: translateY(-5px);
      border-color: rgba(34, 211, 238, 0.25);
      box-shadow: 0 16px 40px rgba(0, 0, 0, 0.4), 0 0 30px rgba(34, 211, 238, 0.06);
      background: rgba(255, 255, 255, 0.04);
    }
    .project-card .icon {
      width: 44px; height: 44px; display: grid; place-items: center;
      border-radius: 12px; font-size: 18px;
      background: linear-gradient(135deg, rgba(34, 211, 238, 0.12), rgba(139, 92, 246, 0.08));
      border: 1px solid rgba(34, 211, 238, 0.15);
      color: var(--cyan); margin-bottom: 14px;
      transition: all 0.4s var(--ease);
    }
    .project-card:hover .icon {
      background: linear-gradient(135deg, rgba(34, 211, 238, 0.25), rgba(139, 92, 246, 0.15));
      transform: rotate(-6deg) scale(1.08);
      box-shadow: 0 0 24px rgba(34, 211, 238, 0.25);
    }
    .project-card h3 {
      font-size: 1.05rem; font-weight: 600; margin-bottom: 6px;
    }
    .project-card .tagline {
      font-size: 12px; color: var(--cyan); font-weight: 500;
      margin-bottom: 8px;
    }
    .project-card p {
      font-size: 0.85rem; color: var(--text-dim); line-height: 1.6;
      flex: 1; margin-bottom: 12px;
    }
    .project-tags {
      display: flex; flex-wrap: wrap; gap: 5px; margin-bottom: 12px;
    }
    .project-tags span {
      font-size: 10px; padding: 3px 10px; border-radius: 30px;
      background: rgba(34, 211, 238, 0.06);
      border: 1px solid rgba(34, 211, 238, 0.1);
      color: var(--text-dim);
    }
    .project-link {
      display: inline-flex; align-items: center; gap: 6px;
      font-size: 12px; font-weight: 600; color: var(--cyan);
      transition: gap 0.3s var(--ease), color 0.3s var(--ease);
    }
    .project-link:hover { gap: 10px; color: #a5f3fc; }

    /* Live sites table */
    .sites-table {
      width: 100%; border-collapse: collapse;
      margin-top: 16px;
    }
    .sites-table th {
      text-align: left; padding: 10px 14px;
      font-size: 11px; text-transform: uppercase;
      letter-spacing: 1.5px; color: var(--text-mute);
      border-bottom: 1px solid var(--border);
      font-weight: 600;
    }
    .sites-table td {
      padding: 12px 14px;
      border-bottom: 1px solid var(--border);
      font-size: 13px; color: var(--text-dim);
    }
    .sites-table tr:last-child td { border-bottom: none; }
    .sites-table td a {
      color: var(--cyan); font-weight: 500;
      transition: color 0.3s var(--ease);
    }
    .sites-table td a:hover { color: #a5f3fc; }

    /* Gamer profile box */
    .gamer-box {
      background: rgba(11, 11, 20, 0.85);
      border: 1px solid rgba(34, 211, 238, 0.15);
      border-radius: 16px;
      padding: 20px 24px;
      font-family: 'JetBrains Mono', monospace;
      font-size: 12.5px; line-height: 1.9;
      color: var(--text-dim);
      white-space: pre-wrap;
      word-break: break-word;
      overflow-x: auto;
      margin: 16px 0;
    }
    .gamer-box .hl { color: var(--amber); }
    .gamer-box .cy { color: var(--cyan); }
    .gamer-box .vi { color: var(--violet); }

    /* Game badges */
    .game-category {
      margin: 16px 0;
    }
    .game-category .cat-label {
      font-size: 11px; text-transform: uppercase;
      letter-spacing: 1.5px; color: var(--text-mute);
      margin-bottom: 8px; font-weight: 600;
    }
    .game-badge-row {
      display: flex; flex-wrap: wrap; gap: 8px;
    }
    .game-badge-row img {
      height: 28px; border-radius: 6px;
      transition: transform 0.3s var(--ease), box-shadow 0.3s var(--ease);
    }
    .game-badge-row img:hover {
      transform: translateY(-3px) scale(1.05);
      box-shadow: 0 8px 20px rgba(139, 92, 246, 0.2);
    }

    /* Experience */
    .exp-card {
      display: flex; gap: 20px;
      background: rgba(255, 255, 255, 0.025);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 22px;
      transition: all 0.4s var(--ease);
    }
    .exp-card:hover {
      border-color: rgba(34, 211, 238, 0.2);
      background: rgba(255, 255, 255, 0.04);
    }
    .exp-icon {
      width: 60px; height: 60px; border-radius: 14px;
      display: grid; place-items: center;
      font-size: 24px; color: var(--cyan);
      background: rgba(34, 211, 238, 0.08);
      border: 1px solid rgba(34, 211, 238, 0.15);
      flex-shrink: 0;
    }
    .exp-content h3 {
      font-size: 1.05rem; font-weight: 600; margin-bottom: 4px;
    }
    .exp-content .company {
      font-size: 12px; color: var(--cyan); font-weight: 500;
      margin-bottom: 8px;
    }
    .exp-content p {
      font-size: 13px; color: var(--text-dim); line-height: 1.7;
      margin-bottom: 12px;
    }
    .exp-tags {
      display: flex; flex-wrap: wrap; gap: 5px;
    }
    .exp-tags span {
      font-size: 10px; padding: 3px 10px; border-radius: 30px;
      background: rgba(34, 211, 238, 0.06);
      border: 1px solid rgba(34, 211, 238, 0.1);
      color: var(--text-dim);
    }

    /* Education table */
    .edu-table {
      width: 100%; border-collapse: collapse;
    }
    .edu-table th {
      text-align: left; padding: 10px 14px;
      font-size: 11px; text-transform: uppercase;
      letter-spacing: 1.5px; color: var(--text-mute);
      border-bottom: 1px solid var(--border);
      font-weight: 600;
    }
    .edu-table td {
      padding: 12px 14px;
      border-bottom: 1px solid var(--border);
      font-size: 13px; color: var(--text-dim);
    }
    .edu-table tr:last-child td { border-bottom: none; }
    .edu-table td strong { color: var(--text); }

    /* Skills bars */
    .skill-item {
      margin-bottom: 14px;
    }
    .skill-head {
      display: flex; justify-content: space-between;
      font-size: 13px; font-weight: 500; margin-bottom: 5px;
    }
    .skill-head .pct {
      color: var(--cyan); font-family: 'JetBrains Mono', monospace;
      font-size: 12px;
    }
    .skill-bar {
      height: 6px; border-radius: 3px;
      background: rgba(255, 255, 255, 0.06);
      overflow: hidden;
    }
    .skill-bar-fill {
      height: 100%; border-radius: 3px;
      background: linear-gradient(90deg, var(--cyan), var(--violet));
      box-shadow: 0 0 12px rgba(34, 211, 238, 0.4);
      width: 0;
      transition: width 1.4s var(--ease);
    }

    /* Soft skill badges */
    .soft-badge-row {
      display: flex; flex-wrap: wrap; gap: 8px;
      margin: 8px 0;
    }
    .soft-badge-row img {
      height: 28px; border-radius: 6px;
      transition: transform 0.3s var(--ease);
    }
    .soft-badge-row img:hover {
      transform: translateY(-3px) scale(1.05);
    }

    /* Testimonials */
    .testi-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 20px;
    }
    .testi-card {
      background: rgba(255, 255, 255, 0.025);
      border: 1px solid var(--border);
      border-radius: 18px;
      padding: 24px;
      position: relative;
      transition: all 0.4s var(--ease);
    }
    .testi-card:hover {
      border-color: rgba(34, 211, 238, 0.2);
      transform: translateY(-4px);
      background: rgba(255, 255, 255, 0.04);
    }
    .testi-quote {
      font-size: 48px; line-height: 1;
      font-family: Georgia, serif;
      color: rgba(34, 211, 238, 0.1);
      position: absolute; top: 12px; right: 18px;
      pointer-events: none;
    }
    .testi-stars {
      display: flex; gap: 3px; margin-bottom: 12px;
      color: var(--amber); font-size: 11px;
    }
    .testi-text {
      font-size: 0.88rem; color: var(--text-dim);
      line-height: 1.7; font-style: italic; margin-bottom: 16px;
    }
    .testi-author {
      display: flex; align-items: center; gap: 10px;
      padding-top: 12px; border-top: 1px solid var(--border);
    }
    .testi-avatar {
      width: 38px; height: 38px; border-radius: 50%;
      background: linear-gradient(135deg, var(--cyan), var(--violet));
      display: grid; place-items: center;
      font-weight: 700; font-size: 14px; color: #06060a;
    }
    .testi-info .name {
      font-size: 13px; font-weight: 600;
    }
    .testi-info .role {
      font-size: 11px; color: var(--text-mute);
    }

    /* Contact */
    .contact-card {
      background: rgba(255, 255, 255, 0.025);
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 36px 28px;
      text-align: center;
      position: relative; overflow: hidden;
    }
    .contact-card::before {
      content: ''; position: absolute; inset: 0;
      background: radial-gradient(circle at 50% 0%, rgba(34, 211, 238, 0.1), transparent 60%);
      pointer-events: none;
    }
    .contact-card h2 {
      font-size: clamp(1.4rem, 3.5vw, 2rem);
      margin-bottom: 10px; position: relative;
    }
    .contact-card h2 .accent {
      background: linear-gradient(135deg, var(--cyan), var(--violet));
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .contact-card p {
      color: var(--text-dim); max-width: 460px;
      margin: 0 auto 24px; position: relative;
      font-size: 0.9rem;
    }
    .contact-links {
      display: flex; flex-wrap: wrap;
      justify-content: center; gap: 12px;
      position: relative;
    }
    .contact-links a {
      display: inline-flex; align-items: center; gap: 8px;
      padding: 10px 20px; border-radius: 40px;
      font-size: 13px; font-weight: 500;
      background: rgba(255, 255, 255, 0.04);
      border: 1px solid var(--border-2);
      color: var(--text-dim);
      transition: all 0.3s var(--ease);
    }
    .contact-links a:hover {
      transform: translateY(-2px);
      border-color: var(--cyan);
      color: var(--cyan);
      box-shadow: 0 0 24px rgba(34, 211, 238, 0.15);
    }
    .contact-links a i { color: var(--cyan); }

    /* Footer */
    .footer {
      position: relative; z-index: 2;
      text-align: center; padding: 40px 24px 30px;
      border-top: 1px solid var(--border);
      margin-top: 20px;
    }
    .footer p {
      font-size: 12px; color: var(--text-mute);
    }
    .footer p span { color: var(--cyan); }
    .footer .random-widgets {
      display: flex; flex-wrap: wrap;
      justify-content: center; gap: 12px;
      margin-bottom: 20px;
    }
    .footer .random-widgets img {
      max-width: 100%; border-radius: 10px;
    }

    /* Utility */
    .mt-1 { margin-top: 8px; }
    .mt-2 { margin-top: 16px; }
    .mt-3 { margin-top: 24px; }
    .mb-1 { margin-bottom: 8px; }
    .mb-2 { margin-bottom: 16px; }
    .mb-3 { margin-bottom: 24px; }
    .text-center { text-align: center; }
    .text-mute { color: var(--text-mute); }
    .text-cyan { color: var(--cyan); }

    @media (max-width: 768px) {
      .hero { padding: 50px 16px 30px; }
      .section { padding: 20px 16px; }
      .exp-card { flex-direction: column; }
      .exp-icon { width: 48px; height: 48px; font-size: 20px; }
      .project-grid { grid-template-columns: 1fr; }
      .testi-grid { grid-template-columns: 1fr; }
    }

    @media (max-width: 480px) {
      .stat-item { padding: 12px 18px; min-width: 80px; }
      .stat-item .num { font-size: 1.4rem; }
      .contact-links a { padding: 8px 14px; font-size: 12px; }
    }
  </style>
</head>
<body>

  <!-- Animated backgrounds -->
  <div class="aurora"></div>
  <div class="grid-overlay"></div>

  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <!-- HEADER / HERO                                                              -->
  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <section class="hero">
    <div class="container">
      <div class="hero-badge">
        <span class="dot"></span>
        Available for freelance & full-time
      </div>

      <h1 class="hero-title">
        <span>Anees Kumar Ghosh</span>
        <span class="line-2">Designer · Gamer · Creator</span>
      </h1>

      <p class="hero-sub">
        I craft <span class="highlight">intuitive, beautiful & user-centric</span> interfaces.
        By day I design pixel-perfect experiences; by night I frag noobs on PC.
        <br />
        <span style="font-family: 'JetBrains Mono', monospace; font-size: 0.8rem; color: var(--text-mute);">
          UI/UX · Figma · Prototyping · Design Systems · PC Gaming
        </span>
      </p>

      <!-- Stats -->
      <div class="stat-row">
        <div class="stat-item">
          <div class="num">40+</div>
          <div class="label">Projects</div>
        </div>
        <div class="stat-item">
          <div class="num">10+</div>
          <div class="label">Clients</div>
        </div>
        <div class="stat-item">
          <div class="num">2+</div>
          <div class="label">Years Exp</div>
        </div>
        <div class="stat-item">
          <div class="num">∞</div>
          <div class="label">GG WP</div>
        </div>
      </div>

      <!-- Social Badges -->
      <div class="badge-row">
        <a href="https://linkedin.com/in/anees-kumar-ghosh-183034258" target="_blank">
          <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
        </a>
        <a href="mailto:aneesghosh98.ag@gmail.com">
          <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
        </a>
        <a href="https://wa.me/918906454507" target="_blank">
          <img src="https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp" />
        </a>
        <a href="https://www.instagram.com/aneeskumarghosh/" target="_blank">
          <img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white" alt="Instagram" />
        </a>
        <a href="https://aneeskumarghosh.github.io/anees-portfolio" target="_blank">
          <img src="https://img.shields.io/badge/Portfolio-22d3ee?style=for-the-badge&logo=googlechrome&logoColor=black" alt="Portfolio" />
        </a>
      </div>

      <!-- Profile views / followers / stars -->
      <div class="badge-row mt-2">
        <img src="https://komarev.com/ghpvc/?username=Aneeskumarghosh&label=Profile%20Views&color=22d3ee&style=for-the-badge" alt="Profile Views" />
        <img src="https://img.shields.io/github/followers/Aneeskumarghosh?label=Followers&style=for-the-badge&color=8b5cf6&labelColor=0d1117" alt="Followers" />
        <img src="https://img.shields.io/github/stars/Aneeskumarghosh?label=Stars&style=for-the-badge&color=fbbf24&labelColor=0d1117" alt="Stars" />
      </div>
    </div>
  </section>

  <div class="divider container"></div>

  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <!-- ABOUT ME                                                                   -->
  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <section class="section" id="about">
    <div class="container">
      <div class="section-header">
        <div class="section-eyebrow">About Me</div>
        <h2 class="section-title">A designer who <span class="accent">cares deeply</span></h2>
      </div>

      <table class="about-table">
        <tr>
          <td width="55%" style="padding-right: 20px;">
            <div class="glass-card">
              <pre><span class="key">name:</span>      <span class="str">Anees Kumar Ghosh</span>
<span class="key">role:</span>      <span class="str">UI/UX Designer</span>
<span class="key">location:</span>  <span class="str">Kolkata, India 🇮🇳</span>
<span class="key">experience:</span> <span class="val">2+ years</span>
<span class="key">focus:</span>     <span class="cy">[UI Design, UX Research, Prototyping, Design Systems]</span>
<span class="key">hobbies:</span>   <span class="vi">[PC Gaming, Graphic Design, Photo Manipulation]</span>
<span class="key">languages:</span> <span class="str">[Bengali, Hindi, English]</span>
<span class="key">status:</span>    <span class="val">Open to freelance & full-time</span></pre>
            </div>
          </td>
          <td width="45%">
            <ul class="about-list">
              <li><i class="fas fa-palette"></i> I craft <strong>intuitive, beautiful & user-centric</strong> interfaces</li>
              <li><i class="fas fa-brain"></i> Research-driven design with a <strong>data-first</strong> mindset</li>
              <li><i class="fas fa-universal-access"></i> Advocate for <strong>accessible (WCAG)</strong> experiences</li>
              <li><i class="fas fa-gamepad"></i> Hardcore <strong>PC Gamer</strong> — frags, strategy & speedruns</li>
              <li><i class="fas fa-rocket"></i> Exploring <strong>AI-assisted design</strong> (Galileo AI, Uizard, Figma Make)</li>
              <li><i class="fas fa-comments"></i> Ask me about <strong>Figma, prototyping, or which game to grind next</strong></li>
            </ul>
          </td>
        </tr>
      </table>
    </div>
  </section>

  <div class="divider container"></div>

  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <!-- TECH STACK                                                                 -->
  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <section class="section" id="tech">
    <div class="container">
      <div class="section-header">
        <div class="section-eyebrow">Toolbox</div>
        <h2 class="section-title">Design & Dev <span class="accent">Stack</span></h2>
      </div>

      <div class="tech-sub-label">🎨 Design & Prototyping</div>
      <div class="tech-grid">
        <img src="https://skillicons.dev/icons?i=figma,xd,ps,ai,canva,framer&theme=dark" alt="Design Tools" />
      </div>

      <div class="tech-sub-label">💻 Frontend & Code</div>
      <div class="tech-grid">
        <img src="https://skillicons.dev/icons?i=html,css,tailwind,js,github,git&theme=dark" alt="Frontend Tools" />
      </div>

      <div class="tech-sub-label">🤖 AI & Innovation</div>
      <div class="tech-grid" style="gap: 8px; flex-wrap: wrap;">
        <img src="https://img.shields.io/badge/Galileo_AI-8b5cf6?style=for-the-badge&logo=openai&logoColor=white" alt="Galileo AI" />
        <img src="https://img.shields.io/badge/Uizard-22d3ee?style=for-the-badge&logo=uizard&logoColor=black" alt="Uizard" />
        <img src="https://img.shields.io/badge/Figma_Make-f24e1e?style=for-the-badge&logo=figma&logoColor=white" alt="Figma Make" />
        <img src="https://img.shields.io/badge/Google_Stitch-4285F4?style=for-the-badge&logo=google&logoColor=white" alt="Google Stitch" />
        <img src="https://img.shields.io/badge/UX_Pilot-fbbf24?style=for-the-badge&logo=rocket&logoColor=black" alt="UX Pilot" />
      </div>
    </div>
  </section>

  <div class="divider container"></div>

  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <!-- GITHUB STATS                                                               -->
  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <section class="section" id="stats">
    <div class="container">
      <div class="section-header">
        <div class="section-eyebrow">GitHub Stats</div>
        <h2 class="section-title">My <span class="accent">open-source</span> journey</h2>
      </div>

      <div class="stats-row">
        <img src="https://github-readme-stats.vercel.app/api?username=Aneeskumarghosh&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=22d3ee&icon_color=8b5cf6&text_color=c9d1d9&count_private=true" alt="GitHub Stats" height="180" />
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Aneeskumarghosh&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=22d3ee&text_color=c9d1d9" alt="Top Languages" height="180" />
      </div>

      <div class="stats-row">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=Aneeskumarghosh&theme=tokyonight&hide_border=true&background=0D1117&stroke=22d3ee&ring=8b5cf6&fire=fbbf24&currStreakLabel=22d3ee" alt="Streak Stats" />
      </div>

      <div class="stats-row">
        <img src="https://github-profile-trophy.vercel.app/?username=Aneeskumarghosh&theme=tokyonight&no-frame=true&no-bg=true&column=7&margin-w=10" alt="Trophies" />
      </div>

      <div class="stats-row">
        <img src="https://github-readme-activity-graph.vercel.app/graph?username=Aneeskumarghosh&bg_color=0d1117&color=22d3ee&line=8b5cf6&point=fbbf24&area=true&hide_border=true" alt="Activity Graph" width="100%" />
      </div>
    </div>
  </section>

  <div class="divider container"></div>

  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <!-- PROJECTS                                                                   -->
  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <section class="section" id="projects">
    <div class="container">
      <div class="section-header">
        <div class="section-eyebrow">Featured Work</div>
        <h2 class="section-title">Projects I've <span class="accent">designed</span></h2>
      </div>

      <div class="project-grid">
        <!-- BloodLink -->
        <div class="project-card">
          <div class="icon"><i class="fas fa-droplet"></i></div>
          <h3>🩸 BloodLink</h3>
          <div class="tagline">Emergency Blood Donation App</div>
          <p>A unified real-time platform connecting patients and donors to reduce emergency response time from <strong>hours to minutes</strong>.</p>
          <div class="project-tags">
            <span>Figma</span><span>UX Research</span><span>Prototyping</span>
          </div>
          <a href="https://www.figma.com/proto/9yJOAEfb3sSm39veCK2wVu/PRATICE-FILE-ANEES" target="_blank" class="project-link">
            View Prototype <i class="fas fa-arrow-right"></i>
          </a>
        </div>

        <!-- AneesPay -->
        <div class="project-card">
          <div class="icon"><i class="fas fa-wallet"></i></div>
          <h3>💰 AneesPay</h3>
          <div class="tagline">Ultimate Financial Command Center</div>
          <p>Your money, moving with you. Send, receive, and analyze your wealth swiftly.</p>
          <div class="project-tags">
            <span>Figma</span><span>Fintech</span><span>Interaction Design</span>
          </div>
          <a href="https://www.figma.com/proto/9yJOAEfb3sSm39veCK2wVu/PRATICE-FILE-ANEES" target="_blank" class="project-link">
            View Prototype <i class="fas fa-arrow-right"></i>
          </a>
        </div>

        <!-- FreshPlate -->
        <div class="project-card">
          <div class="icon"><i class="fas fa-utensils"></i></div>
          <h3>🍳 FreshPlate</h3>
          <div class="tagline">Smart Waste-Free Kitchen Assistant</div>
          <p>Cook smart, waste less. Track your fridge inventory and unlock AI-driven meal recommendations.</p>
          <div class="project-tags">
            <span>Figma</span><span>AI</span><span>Design System</span>
          </div>
          <span class="project-link" style="opacity: 0.6;">Coming Soon</span>
        </div>

        <!-- BookFlow -->
        <div class="project-card">
          <div class="icon"><i class="fas fa-book-open"></i></div>
          <h3>📚 BookFlow</h3>
          <div class="tagline">Premium Reading Habit Builder</div>
          <p>Cultivating health through knowledge. Set achievable goals and build a consistent reading streak.</p>
          <div class="project-tags">
            <span>Figma</span><span>Habit Design</span><span>UX</span>
          </div>
          <span class="project-link" style="opacity: 0.6;">Coming Soon</span>
        </div>

        <!-- Find Everything -->
        <div class="project-card">
          <div class="icon"><i class="fas fa-magnifying-glass"></i></div>
          <h3>🔍 Find Everything</h3>
          <div class="tagline">On-Demand Service Hub</div>
          <p>From local repairs to personal care, book trusted professionals instantly — all in one place.</p>
          <div class="project-tags">
            <span>Figma</span><span>On-Demand</span><span>Mobile</span>
          </div>
          <span class="project-link" style="opacity: 0.6;">Coming Soon</span>
        </div>

        <!-- EduVerse -->
        <div class="project-card">
          <div class="icon"><i class="fas fa-graduation-cap"></i></div>
          <h3>🎓 EduVerse</h3>
          <div class="tagline">Next-Gen Digital Learning</div>
          <p>Discover expert courses, attend live classes, and track your path to certified success.</p>
          <div class="project-tags">
            <span>Figma</span><span>EdTech</span><span>Web App</span>
          </div>
          <span class="project-link" style="opacity: 0.6;">Coming Soon</span>
        </div>
      </div>

      <!-- Live sites -->
      <div class="glass-card mt-3">
        <h3 style="font-size: 1rem; margin-bottom: 4px;">🌐 Live Websites I've Designed & Built</h3>
        <table class="sites-table">
          <thead>
            <tr>
              <th>Project</th>
              <th>Description</th>
              <th>Live</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><strong>Chitrangi Creation</strong></td>
              <td>Handmade clay jewellery — where art meets adornment</td>
              <td><a href="https://chitrangicreation.netlify.app/" target="_blank">Visit <i class="fas fa-arrow-up-right-from-square" style="font-size: 10px;"></i></a></td>
            </tr>
            <tr>
              <td><strong>The Escape</strong></td>
              <td>Travel agent — your gateway to unforgettable journeys</td>
              <td><a href="https://thexcape.netlify.app/" target="_blank">Visit <i class="fas fa-arrow-up-right-from-square" style="font-size: 10px;"></i></a></td>
            </tr>
            <tr>
              <td><strong>VOIVO</strong></td>
              <td>Premium car engine fluids for peak performance</td>
              <td><span style="color: var(--amber); font-weight: 500;">🚧 Launching Soon</span></td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </section>

  <div class="divider container"></div>

  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <!-- GAMER ZONE                                                                 -->
  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <section class="section" id="gamer">
    <div class="container">
      <div class="section-header">
        <div class="section-eyebrow">Gamer Zone</div>
        <h2 class="section-title">PC Gamer <span class="accent">Profile</span></h2>
      </div>

      <!-- Gamer profile box -->
      <div class="gamer-box">
<span class="cy">╔══════════════════════════════════════════════════════════════╗</span>
<span class="cy">║</span>                    <span class="hl">🎯  GAMER  PROFILE  🎯</span>                    <span class="cy">║</span>
<span class="cy">╠══════════════════════════════════════════════════════════════╣</span>
<span class="cy">║</span>  Handle     : <span class="hl">Anees</span>  ⚡                                      <span class="cy">║</span>
<span class="cy">║</span>  Platform   : <span class="hl">PC Master Race</span>  🖥️                             <span class="cy">║</span>
<span class="cy">║</span>  Playstyle  : <span class="hl">Tactical • Aggressive • Strategy</span>               <span class="cy">║</span>
<span class="cy">║</span>  Status     : 🟢 <span class="hl">Online</span> — down for a match anytime           <span class="cy">║</span>
<span class="cy">║</span>  Motto      : "<span class="vi">Design by day, dominate by night.</span>"            <span class="cy">║</span>
<span class="cy">╚══════════════════════════════════════════════════════════════╝</span>
      </div>

      <!-- Games I've Played -->
      <h3 class="mt-3" style="font-size: 1.1rem; font-weight: 600; margin-bottom: 12px;">🕹️ Games I've Played & Grinded</h3>

      <!-- FPS / Shooter -->
      <div class="game-category">
        <div class="cat-label">🔫 FPS / Shooter</div>
        <div class="game-badge-row">
          <img src="https://img.shields.io/badge/Counter--Strike_2-fbbf24?style=for-the-badge&logo=counter-strike&logoColor=black" alt="CS2" />
          <img src="https://img.shields.io/badge/Valorant-FF4655?style=for-the-badge&logo=valorant&logoColor=white" alt="Valorant" />
          <img src="https://img.shields.io/badge/Call_of_Duty-000000?style=for-the-badge&logo=callofduty&logoColor=white" alt="Call of Duty" />
          <img src="https://img.shields.io/badge/Battlefield-0066CC?style=for-the-badge&logo=battlefield&logoColor=white" alt="Battlefield" />
          <img src="https://img.shields.io/badge/Apex_Legends-DA2924?style=for-the-badge&logo=apex&logoColor=white" alt="Apex Legends" />
          <img src="https://img.shields.io/badge/PUBG-F2A900?style=for-the-badge&logo=pubg&logoColor=black" alt="PUBG" />
        </div>
      </div>

      <!-- Racing -->
      <div class="game-category">
        <div class="cat-label">🏁 Racing</div>
        <div class="game-badge-row">
          <img src="https://img.shields.io/badge/Forza_Horizon-0078D4?style=for-the-badge&logo=xbox&logoColor=white" alt="Forza Horizon" />
          <img src="https://img.shields.io/badge/Need_for_Speed-000000?style=for-the-badge&logo=ea&logoColor=white" alt="Need for Speed" />
          <img src="https://img.shields.io/badge/Asphalt-FF6B00?style=for-the-badge&logo=gameloft&logoColor=white" alt="Asphalt" />
        </div>
      </div>

      <!-- Action / Adventure / RPG -->
      <div class="game-category">
        <div class="cat-label">⚔️ Action / Adventure / RPG</div>
        <div class="game-badge-row">
          <img src="https://img.shields.io/badge/GTA_V-8b5cf6?style=for-the-badge&logo=rockstargames&logoColor=white" alt="GTA V" />
          <img src="https://img.shields.io/badge/Assassin's_Creed-000000?style=for-the-badge&logo=ubisoft&logoColor=white" alt="Assassin's Creed" />
          <img src="https://img.shields.io/badge/God_of_War-D32F2F?style=for-the-badge&logo=playstation&logoColor=white" alt="God of War" />
          <img src="https://img.shields.io/badge/Red_Dead_Redemption_2-B22222?style=for-the-badge&logo=rockstargames&logoColor=white" alt="Red Dead Redemption 2" />
        </div>
      </div>

      <!-- Strategy / MOBA -->
      <div class="game-category">
        <div class="cat-label">🧠 Strategy / MOBA</div>
        <div class="game-badge-row">
          <img src="https://img.shields.io/badge/League_of_Legends-1E90FF?style=for-the-badge&logo=leagueoflegends&logoColor=white" alt="League of Legends" />
          <img src="https://img.shields.io/badge/Dota_2-CC0000?style=for-the-badge&logo=dota2&logoColor=white" alt="Dota 2" />
          <img src="https://img.shields.io/badge/Age_of_Empires-8B4513?style=for-the-badge&logo=xbox&logoColor=white" alt="Age of Empires" />
        </div>
      </div>

      <!-- Sandbox / Survival / Co-op -->
      <div class="game-category">
        <div class="cat-label">🏗️ Sandbox / Survival / Co-op</div>
        <div class="game-badge-row">
          <img src="https://img.shields.io/badge/Minecraft-62B47A?style=for-the-badge&logo=minecraft&logoColor=white" alt="Minecraft" />
          <img src="https://img.shields.io/badge/Among_Us-D71F1F?style=for-the-badge&logo=amongus&logoColor=white" alt="Among Us" />
          <img src="https://img.shields.io/badge/Fortnite-8b5cf6?style=for-the-badge&logo=fortnite&logoColor=white" alt="Fortnite" />
          <img src="https://img.shields.io/badge/Free_Fire-FB8C00?style=for-the-badge&logo=garena&logoColor=white" alt="Free Fire" />
        </div>
      </div>

      <!-- Sports -->
      <div class="game-category">
        <div class="cat-label">🏆 Sports</div>
        <div class="game-badge-row">
          <img src="https://img.shields.io/badge/FIFA_FC-2ECC71?style=for-the-badge&logo=ea&logoColor=white" alt="FIFA FC" />
          <img src="https://img.shields.io/badge/eFootball-0078D4?style=for-the-badge&logo=konami&logoColor=white" alt="eFootball" />
        </div>
      </div>

      <p style="font-size: 13px; color: var(--text-mute); font-style: italic; margin-top: 16px;">
        💡 <em>I treat every game like a UX problem — understand the system, find the pattern, optimize the flow, dominate the outcome.</em>
      </p>

      <!-- Snake animation -->
      <div class="text-center mt-3">
        <img src="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake-dark.svg" alt="Snake Game" style="max-width: 100%; border-radius: 12px;" />
      </div>
    </div>
  </section>

  <div class="divider container"></div>

  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <!-- EXPERIENCE                                                                 -->
  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <section class="section" id="experience">
    <div class="container">
      <div class="section-header">
        <div class="section-eyebrow">Experience</div>
        <h2 class="section-title">Where I've <span class="accent">worked</span></h2>
      </div>

      <div class="exp-card">
        <div class="exp-icon"><i class="fas fa-pen-nib"></i></div>
        <div class="exp-content">
          <h3>UI/UX Intern</h3>
          <div class="company">Desun Technology</div>
          <p>
            Designed responsive web & mobile interfaces in <strong>Figma</strong> — wireframes, interactive prototypes, and user flows based on user research and usability testing. Collaborated with senior designers and developers to deliver high-fidelity screens on tight deadlines.
          </p>
          <div class="exp-tags">
            <span>Figma</span><span>Wireframing</span><span>Prototyping</span><span>User Research</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <div class="divider container"></div>

  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <!-- EDUCATION                                                                  -->
  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <section class="section" id="education">
    <div class="container">
      <div class="section-header">
        <div class="section-eyebrow">Education</div>
        <h2 class="section-title">Academic <span class="accent">background</span></h2>
      </div>

      <div class="glass-card">
        <table class="edu-table">
          <thead>
            <tr>
              <th>🎓 Degree</th>
              <th>🏫 Institution</th>
              <th>📅 Year</th>
              <th>📊 Score</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><strong>B.Sc.</strong></td>
              <td>Sainthia Abhedananda Mahavidyalaya</td>
              <td>Dec 2020</td>
              <td>62%</td>
            </tr>
            <tr>
              <td><strong>12th Grade</strong></td>
              <td>Sainthia High School</td>
              <td>Mar 2017</td>
              <td>79.4%</td>
            </tr>
            <tr>
              <td><strong>10th Grade</strong></td>
              <td>Sainthia Town High School</td>
              <td>Mar 2015</td>
              <td>78.14%</td>
            </tr>
          </tbody>
        </table>
        <p class="mt-2" style="font-size: 13px; color: var(--text-dim);">
          🏅 <strong>Certifications:</strong> Graphic Design & UI/UX Design with AI — Desun Academy
        </p>
      </div>
    </div>
  </section>

  <div class="divider container"></div>

  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <!-- SKILLS                                                                     -->
  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <section class="section" id="skills">
    <div class="container">
      <div class="section-header">
        <div class="section-eyebrow">Skills</div>
        <h2 class="section-title">Core <span class="accent">competencies</span></h2>
      </div>

      <div class="glass-card">
        <!-- UI Design -->
        <div class="skill-item">
          <div class="skill-head"><span>UI Design</span><span class="pct">95%</span></div>
          <div class="skill-bar"><div class="skill-bar-fill" data-width="95"></div></div>
        </div>
        <!-- UX Research -->
        <div class="skill-item">
          <div class="skill-head"><span>UX Research</span><span class="pct">88%</span></div>
          <div class="skill-bar"><div class="skill-bar-fill" data-width="88"></div></div>
        </div>
        <!-- Prototyping -->
        <div class="skill-item">
          <div class="skill-head"><span>Prototyping</span><span class="pct">92%</span></div>
          <div class="skill-bar"><div class="skill-bar-fill" data-width="92"></div></div>
        </div>
        <!-- Design Systems -->
        <div class="skill-item">
          <div class="skill-head"><span>Design Systems</span><span class="pct">85%</span></div>
          <div class="skill-bar"><div class="skill-bar-fill" data-width="85"></div></div>
        </div>
        <!-- Motion Design -->
        <div class="skill-item">
          <div class="skill-head"><span>Motion Design</span><span class="pct">78%</span></div>
          <div class="skill-bar"><div class="skill-bar-fill" data-width="78"></div></div>
        </div>
      </div>

      <h3 class="mt-3" style="font-size: 1rem; font-weight: 600; margin-bottom: 8px;">🧩 Soft Skills</h3>
      <div class="soft-badge-row">
        <img src="https://img.shields.io/badge/Cross--functional_Collaboration-22d3ee?style=for-the-badge" alt="Cross-functional Collaboration" />
        <img src="https://img.shields.io/badge/Problem--Solving-8b5cf6?style=for-the-badge" alt="Problem-Solving" />
        <img src="https://img.shields.io/badge/Design_Thinking-fbbf24?style=for-the-badge" alt="Design Thinking" />
        <img src="https://img.shields.io/badge/Analytical_Skills-34d399?style=for-the-badge" alt="Analytical Skills" />
        <img src="https://img.shields.io/badge/Time_Management-f472b6?style=for-the-badge" alt="Time Management" />
        <img src="https://img.shields.io/badge/Stakeholder_Communication-a855f7?style=for-the-badge" alt="Stakeholder Communication" />
      </div>

      <h3 class="mt-3" style="font-size: 1rem; font-weight: 600; margin-bottom: 8px;">🌐 Languages</h3>
      <div class="soft-badge-row">
        <img src="https://img.shields.io/badge/Bengali-Native-22d3ee?style=for-the-badge" alt="Bengali" />
        <img src="https://img.shields.io/badge/Hindi-Fluent-8b5cf6?style=for-the-badge" alt="Hindi" />
        <img src="https://img.shields.io/badge/English-Professional-fbbf24?style=for-the-badge" alt="English" />
      </div>
    </div>
  </section>

  <div class="divider container"></div>

  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <!-- TESTIMONIALS                                                               -->
  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <section class="section" id="testimonials">
    <div class="container">
      <div class="section-header">
        <div class="section-eyebrow">Kind Words</div>
        <h2 class="section-title">What clients <span class="accent">are saying</span></h2>
      </div>

      <div class="testi-grid">
        <!-- Testimonial 1 -->
        <div class="testi-card">
          <div class="testi-quote">"</div>
          <div class="testi-stars">
            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
          </div>
          <p class="testi-text">
            "Anees has an incredible eye for detail. He transformed our clunky interface into something users actually enjoy. Highly recommend!"
          </p>
          <div class="testi-author">
            <div class="testi-avatar">O</div>
            <div class="testi-info">
              <div class="name">Ourabi Das</div>
              <div class="role">Founder of Chitrangi Creation</div>
            </div>
          </div>
        </div>

        <!-- Testimonial 2 -->
        <div class="testi-card">
          <div class="testi-quote">"</div>
          <div class="testi-stars">
            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
          </div>
          <p class="testi-text">
            "Working with Anees was seamless. He listens, iterates fast, and delivers designs that are both beautiful and usable."
          </p>
          <div class="testi-author">
            <div class="testi-avatar" style="background: linear-gradient(135deg, var(--violet), var(--amber));">K</div>
            <div class="testi-info">
              <div class="name">Koushik Mondal</div>
              <div class="role">Founder of VOIVO Engine Fluids</div>
            </div>
          </div>
        </div>

        <!-- Testimonial 3 -->
        <div class="testi-card">
          <div class="testi-quote">"</div>
          <div class="testi-stars">
            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
          </div>
          <p class="testi-text">
            "Our conversion rate jumped 40% after Anees redesigned our onboarding flow. He truly understands user psychology."
          </p>
          <div class="testi-author">
            <div class="testi-avatar" style="background: linear-gradient(135deg, var(--amber), var(--emerald));">S</div>
            <div class="testi-info">
              <div class="name">Saswata Mondal</div>
              <div class="role">Founder of The Escape</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <div class="divider container"></div>

  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <!-- CONTACT                                                                    -->
  <!-- ═══════════════════════════════════════════════════════════════════════════ -->
  <section class="section" id="contact">
    <div class="container">
      <div class="contact-card">
        <h2>Let's build something <span class="accent">remarkable</span></h2>
        <p>Have a project in mind? Drop a message — I'll reply within 24 hours.</p>

        <div class="contact-links">
          <a href="mailto:aneesghosh98.ag@gmail.com">
            <i class="fas fa-envelope"></i> aneesghosh98.ag@gmail.com
          </a>
          <a href="https://wa.me/918906454507" target="_blank">
            <i class="fab fa-whatsapp"></i> WhatsApp
          </a>
          <a href="https://linkedin.com/in/anees-kumar-ghosh-183034258" target="_blank">
            <i class="fab fa-linkedin-in"></i> LinkedIn
          </a>
          <a href="https://aneeskumarghosh.github.io/anees-portfolio" target="_blank">
            <i class="fas fa-globe"></i> Portfolio
          </a>
          <a href="https://github.com/Aneeskumarghosh" target="_blank" rel="noopener noreferrer">
            <i class="fab fa-github"></i> GitHub
          </a>
        </div>
      </div>
    </div>
  </section>

  <footer class="footer">
    <div class="container">
      <div class="random-widgets">
        <a href="#about">About</a>
        <a href="#tech">Toolbox</a>
        <a href="#projects">Projects</a>
        <a href="#experience">Experience</a>
        <a href="#contact">Contact</a>
      </div>
      <p>Designed & built with <span>♥</span> by Anees Kumar Ghosh</p>
      <p class="mt-1">© <span id="year"></span> Anees Kumar Ghosh. All rights reserved.</p>
    </div>
  </footer>

  <button class="back-to-top" id="backToTop" type="button" aria-label="Back to top">
    <i class="fas fa-arrow-up"></i>
  </button>

  <style>
    /* Completion and responsive refinements */
    .footer .random-widgets a {
      color: var(--text-dim);
      font-size: 12px;
      padding: 6px 10px;
      border: 1px solid var(--border);
      border-radius: 30px;
      transition: color .25s ease, border-color .25s ease;
    }
    .footer .random-widgets a:hover { color: var(--cyan); border-color: var(--cyan); }
    .back-to-top {
      position: fixed;
      right: 22px;
      bottom: 22px;
      z-index: 10;
      width: 44px;
      height: 44px;
      border: 1px solid rgba(34,211,238,.35);
      border-radius: 50%;
      color: var(--bg);
      background: var(--cyan);
      box-shadow: 0 8px 24px rgba(34,211,238,.2);
      cursor: pointer;
      opacity: 0;
      visibility: hidden;
      transform: translateY(10px);
      transition: .3s ease;
    }
    .back-to-top.visible { opacity: 1; visibility: visible; transform: translateY(0); }
    .back-to-top:hover { background: #a5f3fc; transform: translateY(-3px); }
    a:focus-visible, button:focus-visible {
      outline: 2px solid var(--cyan);
      outline-offset: 4px;
    }
    img { max-width: 100%; }
    .stats-row { align-items: center; }
    .stats-row img { object-fit: contain; }
    .about-table { table-layout: fixed; }
    .about-table td { overflow-wrap: anywhere; }
    .sites-table, .edu-table { min-width: 560px; }
    .glass-card:has(.sites-table), .glass-card:has(.edu-table) { overflow-x: auto; }
    @media (max-width: 768px) {
      .about-table, .about-table tbody, .about-table tr, .about-table td { display: block; width: 100%; }
      .about-table td { padding: 0 !important; }
      .about-table td + td { padding-top: 18px !important; }
      .hero-title { overflow-wrap: anywhere; }
      .stat-row { gap: 10px; }
      .stat-item { flex: 1 1 40%; }
      .stats-row { flex-direction: column; }
      .stats-row img { width: 100%; }
      .gamer-box { font-size: 10px; padding: 14px; }
      .contact-card { padding: 28px 18px; }
    }
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        scroll-behavior: auto !important;
        animation-duration: .01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: .01ms !important;
      }
    }
  </style>

  <script>
    // Current year in the footer.
    document.getElementById('year').textContent = new Date().getFullYear();

    // Animate skill bars when the skills section enters the viewport.
    const skillFills = document.querySelectorAll('.skill-bar-fill');
    if ('IntersectionObserver' in window) {
      const skillObserver = new IntersectionObserver((entries, observer) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            const fill = entry.target;
            const width = Math.min(100, Math.max(0, Number(fill.dataset.width) || 0));
            fill.style.width = width + '%';
            observer.unobserve(fill);
          }
        });
      }, { threshold: 0.25 });
      skillFills.forEach(fill => skillObserver.observe(fill));
    } else {
      skillFills.forEach(fill => {
        fill.style.width = Math.min(100, Number(fill.dataset.width) || 0) + '%';
      });
    }

    // Back-to-top control.
    const backToTop = document.getElementById('backToTop');
    const toggleBackToTop = () => {
      backToTop.classList.toggle('visible', window.scrollY > 500);
    };
    window.addEventListener('scroll', toggleBackToTop, { passive: true });
    toggleBackToTop();
    backToTop.addEventListener('click', () => {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    // Add safe defaults to external links opened in a new tab.
    document.querySelectorAll('a[target="_blank"]').forEach(link => {
      link.setAttribute('rel', 'noopener noreferrer');
    });
  </script>
</body>
</html>
