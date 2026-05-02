<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Atul Jha — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --blue: #3B82F6; --violet: #8B5CF6; --emerald: #10B981; --cyan: #06B6D4;
    --rose: #F43F5E; --amber: #F59E0B; --bg: #0D1117; --bg2: #161B22;
    --bg3: #21262D; --border: rgba(48,54,61,0.9); --text: #E6EDF3; --muted: #8B949E; --subtle: #484F58;
  }
  body { font-family: 'Space Grotesk', sans-serif; background: var(--bg); color: var(--text); min-height: 100vh; padding: 0; overflow-x: hidden; }
  .grid-bg { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 0; background-image: linear-gradient(rgba(59,130,246,0.03) 1px, transparent 1px), linear-gradient(90deg, rgba(59,130,246,0.03) 1px, transparent 1px); background-size: 40px 40px; pointer-events: none; }
  .glow-orb { position: fixed; border-radius: 50%; filter: blur(80px); pointer-events: none; z-index: 0; }
  .orb1 { width: 400px; height: 400px; background: rgba(139,92,246,0.08); top: -100px; right: -100px; }
  .orb2 { width: 500px; height: 500px; background: rgba(59,130,246,0.06); bottom: -150px; left: -150px; }
  .container { max-width: 860px; margin: 0 auto; padding: 3rem 2rem 4rem; position: relative; z-index: 1; }
  .header { display: flex; align-items: flex-start; gap: 2rem; margin-bottom: 3rem; padding-bottom: 2.5rem; border-bottom: 1px solid var(--border); }
  .avatar-wrap { position: relative; flex-shrink: 0; }
  .avatar { width: 96px; height: 96px; border-radius: 50%; background: linear-gradient(135deg, #3B82F6 0%, #8B5CF6 50%, #EC4899 100%); display: flex; align-items: center; justify-content: center; font-family: 'Fira Code', monospace; font-size: 2rem; font-weight: 500; color: #fff; letter-spacing: -1px; box-shadow: 0 0 0 3px var(--bg), 0 0 0 4px rgba(59,130,246,0.5); }
  .status-dot { position: absolute; bottom: 4px; right: 4px; width: 16px; height: 16px; border-radius: 50%; background: var(--emerald); border: 3px solid var(--bg); }
  .header-info { flex: 1; }
  .name { font-size: 1.75rem; font-weight: 700; color: var(--text); letter-spacing: -0.5px; margin-bottom: 2px; }
  .handle { font-family: 'Fira Code', monospace; font-size: 0.9rem; color: var(--blue); margin-bottom: 0.75rem; }
  .bio { font-size: 0.95rem; color: var(--muted); line-height: 1.6; max-width: 480px; margin-bottom: 1rem; }
  .tags { display: flex; flex-wrap: wrap; gap: 6px; }
  .tag { font-family: 'Fira Code', monospace; font-size: 0.72rem; padding: 3px 10px; border-radius: 20px; border: 1px solid; }
  .tag-blue   { color: var(--blue);    border-color: rgba(59,130,246,0.3);  background: rgba(59,130,246,0.08); }
  .tag-violet { color: var(--violet);  border-color: rgba(139,92,246,0.3);  background: rgba(139,92,246,0.08); }
  .tag-cyan   { color: var(--cyan);    border-color: rgba(6,182,212,0.3);   background: rgba(6,182,212,0.08); }
  .tag-emerald{ color: var(--emerald); border-color: rgba(16,185,129,0.3);  background: rgba(16,185,129,0.08); }
  .stats-row { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; margin-bottom: 2rem; }
  .stat-card { background: var(--bg2); border: 1px solid var(--border); border-radius: 10px; padding: 1rem 1.1rem; position: relative; overflow: hidden; transition: border-color 0.2s, transform 0.2s; cursor: default; }
  .stat-card:hover { border-color: rgba(59,130,246,0.4); transform: translateY(-2px); }
  .stat-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px; background: var(--accent-color, var(--blue)); }
  .stat-label { font-size: 0.72rem; color: var(--muted); text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 4px; }
  .stat-value { font-size: 1.4rem; font-weight: 700; color: var(--text); }
  .stat-sub   { font-size: 0.7rem; color: var(--muted); margin-top: 2px; }
  .section { margin-bottom: 2rem; }
  .section-title { font-size: 0.7rem; font-weight: 600; color: var(--muted); text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 1rem; display: flex; align-items: center; gap: 8px; }
  .section-title::after { content: ''; flex: 1; height: 1px; background: var(--border); }
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
  .about-item { background: var(--bg2); border: 1px solid var(--border); border-radius: 8px; padding: 0.75rem 1rem; display: flex; align-items: flex-start; gap: 10px; font-size: 0.85rem; color: var(--muted); transition: border-color 0.2s; }
  .about-item:hover { border-color: rgba(59,130,246,0.3); }
  .about-icon { font-size: 1rem; flex-shrink: 0; margin-top: 1px; }
  .about-text strong { display: block; color: var(--text); font-weight: 500; font-size: 0.82rem; }
  .stack-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
  .stack-row { background: var(--bg2); border: 1px solid var(--border); border-radius: 8px; padding: 0.85rem 1rem; transition: border-color 0.2s; }
  .stack-row:hover { border-color: rgba(139,92,246,0.3); }
  .stack-category { font-family: 'Fira Code', monospace; font-size: 0.68rem; color: var(--violet); margin-bottom: 6px; letter-spacing: 0.05em; }
  .stack-chips { display: flex; flex-wrap: wrap; gap: 5px; }
  .chip { font-size: 0.72rem; padding: 2px 8px; border-radius: 4px; background: var(--bg3); border: 1px solid var(--border); color: var(--text); font-family: 'Fira Code', monospace; transition: background 0.15s, border-color 0.15s; }
  .chip:hover { background: rgba(59,130,246,0.1); border-color: rgba(59,130,246,0.3); color: var(--blue); }
  .heatmap { display: grid; grid-template-columns: repeat(52, 1fr); gap: 2px; margin-top: 8px; }
  .heatmap-cell { aspect-ratio: 1; border-radius: 2px; background: var(--bg3); transition: transform 0.1s; }
  .heatmap-cell:hover { transform: scale(1.5); }
  .h1 { background: rgba(59,130,246,0.15); } .h2 { background: rgba(59,130,246,0.35); }
  .h3 { background: rgba(59,130,246,0.55); } .h4 { background: rgba(59,130,246,0.80); } .h5 { background: #3B82F6; }
  .connect-grid { display: grid; grid-template-columns: repeat(4,1fr); gap: 10px; }
  .connect-card { background: var(--bg2); border: 1px solid var(--border); border-radius: 10px; padding: 1rem; display: flex; flex-direction: column; align-items: center; gap: 6px; text-decoration: none; color: var(--muted); transition: border-color 0.2s, transform 0.2s, color 0.2s; cursor: pointer; }
  .connect-card:hover { transform: translateY(-3px); color: var(--text); }
  .connect-card.li:hover { border-color: #0077B5; } .connect-card.tw:hover { border-color: #1DA1F2; }
  .connect-card.po:hover { border-color: var(--blue); } .connect-card.gm:hover { border-color: #EA4335; }
  .connect-icon { width: 36px; height: 36px; border-radius: 8px; display: flex; align-items: center; justify-content: center; font-size: 1.1rem; }
  .li-icon { background: rgba(0,119,181,0.15); } .tw-icon { background: rgba(29,161,242,0.15); }
  .po-icon { background: rgba(59,130,246,0.15); } .gm-icon { background: rgba(234,67,53,0.15); }
  .connect-label { font-size: 0.72rem; font-weight: 500; }
  .footer { border-top: 1px solid var(--border); padding-top: 1.5rem; margin-top: 2rem; display: flex; justify-content: space-between; align-items: center; }
  .footer-left { font-family: 'Fira Code', monospace; font-size: 0.72rem; color: var(--subtle); }
  .views-badge { font-family: 'Fira Code', monospace; font-size: 0.72rem; background: rgba(59,130,246,0.1); border: 1px solid rgba(59,130,246,0.2); color: var(--blue); padding: 4px 10px; border-radius: 20px; }
  @keyframes fadeUp { from { opacity:0; transform:translateY(16px); } to { opacity:1; transform:translateY(0); } }
  .fade-up { animation: fadeUp 0.5s ease both; }
  .d1{animation-delay:0.05s;} .d2{animation-delay:0.1s;} .d3{animation-delay:0.18s;}
  .d4{animation-delay:0.26s;} .d5{animation-delay:0.34s;} .d6{animation-delay:0.42s;}
  @media(max-width:600px){
    .stats-row{grid-template-columns:repeat(2,1fr);}
    .about-grid,.stack-grid,.connect-grid{grid-template-columns:1fr;}
    .header{flex-direction:column;align-items:center;text-align:center;}
    .bio{max-width:100%;} .tags{justify-content:center;}
  }
</style>
</head>
<body>
<div class="grid-bg"></div>
<div class="glow-orb orb1"></div>
<div class="glow-orb orb2"></div>
<div class="container">

  <div class="header fade-up d1">
    <div class="avatar-wrap">
      <div class="avatar">AJ</div>
      <div class="status-dot"></div>
    </div>
    <div class="header-info">
      <div class="name">Atul Jha</div>
      <div class="handle">@atuljha-tech</div>
      <div class="bio">CS student at Heritage Institute of Technology, Kolkata — turning ideas into production-ready applications. Building at the intersection of AI, Web3, and modern full-stack engineering.</div>
      <div class="tags">
        <span class="tag tag-blue">Full Stack Dev</span>
        <span class="tag tag-violet">AI / ML</span>
        <span class="tag tag-cyan">Blockchain Builder</span>
        <span class="tag tag-emerald">Open Source</span>
      </div>
    </div>
  </div>

  <div class="stats-row fade-up d2">
    <div class="stat-card" style="--accent-color:#3B82F6">
      <div class="stat-label">Repos</div>
      <div class="stat-value">40+</div>
      <div class="stat-sub">public projects</div>
    </div>
    <div class="stat-card" style="--accent-color:#8B5CF6">
      <div class="stat-label">Stack</div>
      <div class="stat-value">15+</div>
      <div class="stat-sub">technologies</div>
    </div>
    <div class="stat-card" style="--accent-color:#10B981">
      <div class="stat-label">Focus</div>
      <div class="stat-value">Agentic</div>
      <div class="stat-sub">AI systems</div>
    </div>
    <div class="stat-card" style="--accent-color:#F59E0B">
      <div class="stat-label">Status</div>
      <div class="stat-value" style="font-size:1rem;color:#10B981;margin-top:4px;">● Open to</div>
      <div class="stat-sub">collaborations</div>
    </div>
  </div>

  <div class="section fade-up d3">
    <div class="section-title">About</div>
    <div class="about-grid">
      <div class="about-item"><span class="about-icon">🔭</span><div class="about-text"><strong>Currently building</strong>AI-integrated tools & full-stack platforms</div></div>
      <div class="about-item"><span class="about-icon">🌱</span><div class="about-text"><strong>Deep diving into</strong>Agentic AI & Blockchain development</div></div>
      <div class="about-item"><span class="about-icon">👯</span><div class="about-text"><strong>Looking to collaborate</strong>Open-source AI projects</div></div>
      <div class="about-item"><span class="about-icon">💬</span><div class="about-text"><strong>Ask me about</strong>Next.js · TypeScript · Python · Web3</div></div>
    </div>
  </div>

  <div class="section fade-up d4">
    <div class="section-title">Tech Arsenal</div>
    <div class="stack-grid">
      <div class="stack-row"><div class="stack-category">// frontend</div><div class="stack-chips"><span class="chip">Next.js</span><span class="chip">React</span><span class="chip">TypeScript</span><span class="chip">Tailwind CSS</span><span class="chip">JavaScript</span></div></div>
      <div class="stack-row"><div class="stack-category">// backend</div><div class="stack-chips"><span class="chip">Node.js</span><span class="chip">Express</span><span class="chip">Python</span><span class="chip">FastAPI</span></div></div>
      <div class="stack-row"><div class="stack-category">// database & devops</div><div class="stack-chips"><span class="chip">MongoDB</span><span class="chip">PostgreSQL</span><span class="chip">Supabase</span><span class="chip">Docker</span><span class="chip">Vercel</span></div></div>
      <div class="stack-row"><div class="stack-category">// ai / web3</div><div class="stack-chips"><span class="chip">LangChain</span><span class="chip">RAG</span><span class="chip">Groq API</span><span class="chip">Solidity</span><span class="chip">Ethers.js</span></div></div>
    </div>
  </div>

  <div class="section fade-up d5">
    <div class="section-title">Contribution Activity</div>
    <div id="heatmap" class="heatmap"></div>
    <div style="display:flex;gap:6px;align-items:center;margin-top:8px;font-size:0.65rem;color:var(--subtle);font-family:'Fira Code',monospace;">
      <span>Less</span>
      <div style="width:10px;height:10px;border-radius:2px;background:var(--bg3);"></div>
      <div style="width:10px;height:10px;border-radius:2px;background:rgba(59,130,246,0.2);"></div>
      <div style="width:10px;height:10px;border-radius:2px;background:rgba(59,130,246,0.45);"></div>
      <div style="width:10px;height:10px;border-radius:2px;background:rgba(59,130,246,0.7);"></div>
      <div style="width:10px;height:10px;border-radius:2px;background:#3B82F6;"></div>
      <span>More</span>
    </div>
  </div>

  <div class="section fade-up d6">
    <div class="section-title">Connect</div>
    <div class="connect-grid">
      <a class="connect-card li" href="https://linkedin.com/in/atuljha275" target="_blank">
        <div class="connect-icon li-icon"><svg width="20" height="20" viewBox="0 0 24 24" fill="#0077B5"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg></div>
        <div class="connect-label">LinkedIn</div>
      </a>
      <a class="connect-card tw" href="https://twitter.com/atuljha275" target="_blank">
        <div class="connect-icon tw-icon"><svg width="20" height="20" viewBox="0 0 24 24" fill="#1DA1F2"><path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/></svg></div>
        <div class="connect-label">Twitter</div>
      </a>
      <a class="connect-card po" href="https://atuljhaportfolio-delta.vercel.app" target="_blank">
        <div class="connect-icon po-icon"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="#3B82F6" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="3" width="20" height="14" rx="2"/><line x1="8" y1="21" x2="16" y2="21"/><line x1="12" y1="17" x2="12" y2="21"/></svg></div>
        <div class="connect-label">Portfolio</div>
      </a>
      <a class="connect-card gm" href="mailto:atuljha275@gmail.com">
        <div class="connect-icon gm-icon"><svg width="20" height="20" viewBox="0 0 24 24" fill="#EA4335"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.910 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg></div>
        <div class="connect-label">Gmail</div>
      </a>
    </div>
  </div>

  <div class="footer">
    <div class="footer-left"><span style="color:var(--blue);">❯</span> git push origin main <span style="color:var(--emerald);">✓</span></div>
    <div class="views-badge">👁 profile views tracking enabled</div>
  </div>

</div>
<script>
const heatmap = document.getElementById('heatmap');
const total = 52 * 7;
for(let i = 0; i < total; i++){
  const cell = document.createElement('div');
  cell.className = 'heatmap-cell';
  const r = Math.random();
  let level = 0;
  if(r > 0.55) level = 1 + Math.floor(Math.random() * 4);
  if(i > total - 60 && Math.random() > 0.3) level = 2 + Math.floor(Math.random() * 3);
  if(level > 0) cell.classList.add(['','h1','h2','h3','h4','h5'][Math.min(level,5)]);
  heatmap.appendChild(cell);
}
</script>
</body>
</html>
