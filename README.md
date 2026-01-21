<style>
  :root {
    color-scheme: dark;
  }
  
  .header {
    text-align: center;
    padding: 20px 0;
    background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
    border: 2px solid #667eea;
    border-radius: 10px;
    color: #e0e0e0;
    margin-bottom: 30px;
  }
  .header h1 {
    margin: 0 0 10px 0;
    font-size: 2.5em;
    color: #667eea;
  }
  .header p {
    margin: 10px 0;
    font-size: 1.1em;
    font-weight: 300;
    color: #b0b0b0;
  }
  .quick-links {
    display: flex;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
    margin: 20px 0;
  }
  .quick-links a {
    padding: 8px 16px;
    background: #2a2a4e;
    color: #667eea;
    text-decoration: none;
    border: 1px solid #667eea;
    border-radius: 5px;
    transition: all 0.3s ease;
    font-weight: 600;
  }
  .quick-links a:hover {
    background: #667eea;
    color: white;
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(102, 126, 234, 0.4);
  }
  .section {
    margin: 30px 0;
    padding: 20px;
    border-left: 4px solid #667eea;
    background: #1a1a2e;
    border-radius: 5px;
    border: 1px solid #2a2a4e;
  }
  .section h2 {
    margin-top: 0;
    color: #667eea;
  }
  .section p {
    color: #b0b0b0;
  }
  .section ul li {
    color: #b0b0b0;
  }
  .tech-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 15px;
  }
  .tech-badge {
    background: #2a2a4e;
    color: #667eea;
    padding: 5px 12px;
    border: 1px solid #667eea;
    border-radius: 20px;
    font-size: 0.9em;
    font-weight: 600;
  }
  .contact-grid {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }
  .contact-item {
    padding: 10px;
    background: #2a2a4e;
    border: 1px solid #3a3a5e;
    border-radius: 5px;
    display: flex;
    align-items: center;
    gap: 10px;
    color: #b0b0b0;
  }
  .contact-item strong {
    color: #667eea;
  }
  .contact-item a {
    color: #667eea;
    text-decoration: none;
    transition: color 0.3s ease;
  }
  .contact-item a:hover {
    color: #764ba2;
  }
  .work-card {
    margin: 10px 0;
    padding: 12px;
    background: #2a2a4e;
    border: 1px solid #3a3a5e;
    border-radius: 5px;
    color: #b0b0b0;
    transition: all 0.3s ease;
  }
  .work-card:hover {
    border-color: #667eea;
    box-shadow: 0 4px 12px rgba(102, 126, 234, 0.2);
  }
  .work-card strong {
    color: #667eea;
  }
  .work-card a {
    color: #667eea;
    text-decoration: none;
  }
  .work-card a:hover {
    color: #764ba2;
    text-decoration: underline;
  }
</style>

<div class="header">
  <h1>👋 Hi, I'm BENZOOgataga!</h1>
  <p>Network Engineering Student | Infrastructure Specialist</p>
  <p>Designing production-ready servers, game clusters & self-hosted platforms</p>
</div>

<div class="quick-links">
  <a href="https://benzoogataga.com">🌐 Portfolio</a>
  <a href="https://louismorice.fr/">⚙️ Infra Projects</a>
  <a href="https://industrium.net">💼 Industrium</a>
  <a href="https://altitude-interactive.com">🎮 Altitude Interactive</a>
</div>

<div style="text-align: center; margin: 20px 0;">
  
[![IndustriumMC](https://img.shields.io/badge/org-IndustriumMC-blue?logo=github)](https://github.com/IndustriumMC)
[![Altitude Interactive](https://img.shields.io/badge/org-AltitudeInteractive-purple?logo=github)](https://github.com/Altitude-Interactive)
[![Website](https://img.shields.io/badge/website-benzoogataga.com-0a0a0a?style=flat-square&logo=about-dot-me&logoColor=white)](https://benzoogataga.com)
[![Discord](https://img.shields.io/badge/Discord-benzoogataga-7289da?style=flat-square&logo=discord&logoColor=white)](https://guns.lol/benzoogataga)
[![Mail](https://img.shields.io/badge/email-contact@benzoogataga.com-red?style=flat-square&logo=gmail&logoColor=white)](mailto:contact@benzoogataga.com)

</div>

<div class="section">
  <h2>🛠️ Currently Working On</h2>
  <ul style="list-style: none; padding: 0;">
    <li class="work-card">
      <strong><a href="https://industrium.net">Industrium</a></strong> - Modded Minecraft with infrastructure & company systems
    </li>
    <li class="work-card">
      <strong>Server upgrades</strong> - Monitoring stacks, DNS, automation pipelines
    </li>
    <li class="work-card">
      <strong>Internal tools</strong> - CLI & web utilities for player/company management
    </li>
  </ul>
</div>

<div class="section">
  <h2>💼 What I Do</h2>
  <p>I specialize in <strong>Linux infrastructure design</strong> and automation. From containerization with Docker to monitoring stacks with Prometheus & Grafana, I build systems that scale.</p>
  
  <ul style="list-style: none; padding: 0;">
    <li style="margin: 8px 0;">🖥️ Infrastructure as Code (Bash, Ansible)</li>
    <li style="margin: 8px 0;">🕹️ Game server optimization & management</li>
    <li style="margin: 8px 0;">🤖 Discord bots & automation tools</li>
    <li style="margin: 8px 0;">🔐 Real-world system security & AD integration</li>
  </ul>

  <p><strong>Tech Stack:</strong></p>
  <div class="tech-stack">
    <span class="tech-badge">Debian</span>
    <span class="tech-badge">Proxmox</span>
    <span class="tech-badge">Docker</span>
    <span class="tech-badge">Nginx</span>
    <span class="tech-badge">GitHub Actions</span>
    <span class="tech-badge">Pterodactyl</span>
    <span class="tech-badge">Prometheus</span>
    <span class="tech-badge">Grafana</span>
  </div>
</div>

<div class="section">
  <h2>📫 Contact & Links</h2>
  <div class="contact-grid">
    <div class="contact-item">
      <span style="font-size: 1.2em;">💬</span>
      <div>
        <strong>Discord</strong>: <code>benzoogataga</code><br>
        <a href="https://guns.lol/benzoogataga">View my profile</a>
      </div>
    </div>
    <div class="contact-item">
      <span style="font-size: 1.2em;">📧</span>
      <div>
        <strong>Email</strong>: <a href="mailto:contact@benzoogataga.com">contact@benzoogataga.com</a>
      </div>
    </div>
    <div class="contact-item">
      <span style="font-size: 1.2em;">📊</span>
      <div>
        <strong>Status Page</strong>: <a href="https://status.benzoogataga.com">status.benzoogataga.com</a>
      </div>
    </div>
  </div>
</div>

<p align="center">
  <img src="https://profile-counter.glitch.me/BENZOOgataga/count.svg"><br>
  people visited my GitHub profile 😎
</p>

---

<p align="center">
  <img height=150 src="https://github-readme-stats.vercel.app/api?username=BENZOOgataga&show_icons=true&theme=react&border_color=61dafb&hide_border=true">
  <img height=150 src="https://github-readme-stats.vercel.app/api/top-langs/?username=BENZOOgataga&hide=c%23,powershell,Mathematica,Ruby,Objective-C,Objective-C%2b%2b,Cuda&title_color=61dafb&text_color=ffffff&icon_color=61dafb&bg_color=20232a&langs_count=8&layout=compact&border_color=61dafb&hide_border=true&size_weight=0.5&count_weight=0.5"><br>
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=BENZOOgataga&theme=react-dark&bg_color=20232a&hide_border=true" width=688><br>
  <i>⚠️ GitHub stats don’t reflect my real expertise, I focus on infrastructure, systems, and bots, not commits or stars.</i>
</p>