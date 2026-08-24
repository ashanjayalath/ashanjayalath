<style>
  /* ---------- Global Reset & Dark Theme ---------- */
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    background: #0b0b1a;
    font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
    color: #f0f0f0;
    overflow-x: hidden;
  }

  /* ---------- Animated Background ---------- */
  .app-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
    background: radial-gradient(ellipse at 20% 50%, rgba(255, 59, 48, 0.08) 0%, transparent 60%),
                radial-gradient(ellipse at 80% 50%, rgba(255, 107, 107, 0.06) 0%, transparent 60%),
                #0b0b1a;
    border-radius: 32px;
    box-shadow: 0 0 80px rgba(255, 59, 48, 0.05);
  }

  /* ---------- Typing Animation (CSS only) ---------- */
  .typing-wrapper {
    display: inline-block;
    font-size: 1.8rem;
    font-weight: 600;
    letter-spacing: 1px;
    background: linear-gradient(135deg, #FF3B30, #FF6B6B);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .typing-text {
    overflow: hidden;
    white-space: nowrap;
    border-right: 3px solid #FF3B30;
    width: 0;
    animation: typing 3.5s steps(40, end) forwards, blink-caret 0.75s step-end infinite;
    display: inline-block;
    -webkit-text-fill-color: transparent;
  }

  @keyframes typing {
    from { width: 0; }
    to { width: 100%; }
  }

  @keyframes blink-caret {
    from, to { border-color: transparent; }
    50% { border-color: #FF3B30; }
  }

  /* ---------- Floating Glow Effect ---------- */
  .glow-float {
    animation: float 6s ease-in-out infinite;
  }

  @keyframes float {
    0% { transform: translateY(0px); }
    50% { transform: translateY(-12px); }
    100% { transform: translateY(0px); }
  }

  /* ---------- Navigation Bar ---------- */
  .nav-bar {
    display: flex;
    justify-content: center;
    gap: 40px;
    padding: 18px 30px;
    margin: 20px 0 30px;
    background: rgba(255, 255, 255, 0.03);
    backdrop-filter: blur(12px);
    border-radius: 60px;
    border: 1px solid rgba(255, 59, 48, 0.2);
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
    flex-wrap: wrap;
  }

  .nav-item {
    color: #b0b0c0;
    text-decoration: none;
    font-weight: 500;
    font-size: 1.05rem;
    padding: 8px 6px;
    position: relative;
    transition: color 0.3s ease;
    letter-spacing: 0.5px;
  }

  .nav-item::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 2.5px;
    background: linear-gradient(90deg, #FF3B30, #FF6B6B);
    transition: width 0.35s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    border-radius: 4px;
  }

  .nav-item:hover {
    color: #ffffff;
  }

  .nav-item:hover::after {
    width: 100%;
  }

  /* ---------- Glassmorphism Cards ---------- */
  .glass-card {
    background: rgba(255, 255, 255, 0.03);
    backdrop-filter: blur(8px);
    border-radius: 28px;
    border: 1px solid rgba(255, 255, 255, 0.06);
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
    transition: transform 0.4s cubic-bezier(0.23, 1, 0.32, 1), box-shadow 0.4s ease;
    padding: 30px;
  }

  .glass-card:hover {
    transform: translateY(-6px) scale(1.005);
    box-shadow: 0 30px 80px rgba(255, 59, 48, 0.15);
    border-color: rgba(255, 59, 48, 0.25);
  }

  /* ---------- Glowing Border Card (About) ---------- */
  .glow-border-card {
    position: relative;
    background: rgba(255, 255, 255, 0.02);
    border-radius: 28px;
    padding: 30px;
    margin: 20px 0;
    border: 1px solid transparent;
    background-clip: padding-box;
    transition: all 0.4s ease;
  }

  .glow-border-card::before {
    content: '';
    position: absolute;
    inset: -2px;
    border-radius: 30px;
    padding: 2px;
    background: conic-gradient(from 0deg, #FF3B30, #FF6B6B, #FF3B30, #FF6B6B, #FF3B30);
    background-size: 300% 300%;
    -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
    mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
    -webkit-mask-composite: xor;
    mask-composite: exclude;
    animation: rotate-glow 6s linear infinite;
    opacity: 0.6;
    transition: opacity 0.4s;
  }

  .glow-border-card:hover::before {
    opacity: 1;
  }

  @keyframes rotate-glow {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  /* ---------- Skill Icons Row ---------- */
  .skill-row {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    justify-content: center;
    margin-top: 8px;
  }

  .skill-icon {
    transition: transform 0.3s cubic-bezier(0.23, 1, 0.32, 1), filter 0.3s ease;
    filter: grayscale(0.2) brightness(0.9);
    display: inline-block;
  }

  .skill-icon:hover {
    transform: scale(1.18) rotate(2deg);
    filter: grayscale(0) brightness(1.2) drop-shadow(0 0 12px rgba(255, 59, 48, 0.3));
  }

  /* ---------- Project Cards (3D Tilt on Hover) ---------- */
  .project-card {
    background: rgba(255, 255, 255, 0.02);
    backdrop-filter: blur(6px);
    border-radius: 24px;
    padding: 24px 18px;
    border: 1px solid rgba(255, 255, 255, 0.04);
    transition: transform 0.5s cubic-bezier(0.23, 1, 0.32, 1), box-shadow 0.5s ease;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
    height: 100%;
    display: flex;
    flex-direction: column;
  }

  .project-card:hover {
    transform: perspective(800px) rotateY(4deg) rotateX(2deg) translateY(-10px);
    box-shadow: 0 30px 60px rgba(255, 59, 48, 0.18);
    border-color: rgba(255, 59, 48, 0.2);
  }

  .project-card h3 {
    font-size: 1.5rem;
    margin-bottom: 6px;
    background: linear-gradient(135deg, #FF3B30, #FF6B6B);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  /* ---------- Stats Images Glow ---------- */
  .stats-img {
    border-radius: 16px;
    transition: transform 0.4s ease, box-shadow 0.4s ease;
    box-shadow: 0 0 20px rgba(255, 59, 48, 0.05);
  }

  .stats-img:hover {
    transform: scale(1.03);
    box-shadow: 0 0 50px rgba(255, 59, 48, 0.15);
  }

  /* ---------- Social Icons Animation ---------- */
  .social-link {
    display: inline-block;
    transition: transform 0.3s cubic-bezier(0.23, 1, 0.32, 1), filter 0.3s ease;
  }

  .social-link:hover {
    transform: translateY(-8px) scale(1.08);
    filter: drop-shadow(0 12px 24px rgba(255, 59, 48, 0.25));
  }

  /* ---------- Responsive Fine-tune ---------- */
  @media (max-width: 768px) {
    .nav-bar { gap: 20px; padding: 14px 18px; }
    .typing-wrapper { font-size: 1.2rem; }
    .glass-card { padding: 20px; }
  }
</style>

<!-- ============================================ -->
<!--  APP CONTAINER                               -->
<!-- ============================================ -->
<div class="app-container">

  <!-- ========== HEADER (Capsule + Typing) ========== -->
  <div align="center">
    <a href="https://ashanjayalath.vercel.app/" target="_blank">
      <img src="https://capsule-render.vercel.app/api?type=waving&color=0:FF3B30,100:FF6B6B&height=220&section=header&text=ASHAN%20JAYALATH&fontSize=70&animation=fadeIn&fontAlignY=35&desc=Full-Stack%20Engineer%20%7C%20Educator%20%7C%20Tech%20Enthusiast&descSize=20&descAlignY=55" width="100%" />
    </a>

    <!-- Animated Typing Subtitle -->
    <div style="margin-top: -10px; margin-bottom: 15px;">
      <span class="typing-wrapper">
        <span class="typing-text">✦ Code · Create · Inspire ✦</span>
      </span>
    </div>

    <!-- Badge Row -->
    <p style="display: flex; flex-wrap: wrap; justify-content: center; gap: 10px; margin-top: 5px;">
      <img src="https://img.shields.io/badge/BIT(Reading)-University%20of%20Moratuwa-FF3B30?style=for-the-badge&logo=graduation-cap&logoColor=white" />
      <img src="https://img.shields.io/badge/Role-Assistant%20Programme%20Coordinator-FF6B6B?style=for-the-badge&logo=esoft&logoColor=white" />
    </p>
    <p style="display: flex; flex-wrap: wrap; justify-content: center; gap: 10px;">
      <a href="https://linkedin.com/in/nashan-jayalath"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
      <a href="mailto:gpashanjayalath@gmail.com"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
      <a href="https://ashanjayalath.vercel.app/"><img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white" /></a>
      <img src="https://img.shields.io/badge/Location-Sri%20Lanka-00c6ff?style=for-the-badge&logo=googlemaps&logoColor=white" />
    </p>
  </div>

  <!-- ========== NAVIGATION BAR ========== -->
  <div class="nav-bar">
    <a href="#" class="nav-item">🏠 Home</a>
    <a href="#" class="nav-item">👨‍💻 About</a>
    <a href="#" class="nav-item">🛠 Skills</a>
    <a href="#" class="nav-item">🚀 Projects</a>
    <a href="#" class="nav-item">📫 Contact</a>
  </div>

  <!-- ========== ABOUT SECTION (Glow Border Card) ========== -->
  <div class="glow-border-card">
    <table width="100%" style="border-collapse: collapse;">
      <tr>
        <td width="60%" valign="top" style="padding-right: 20px;">
          <h2 style="font-size: 2rem; font-weight: 700; background: linear-gradient(135deg, #FF3B30, #FF6B6B); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; margin-bottom: 12px;">
            ✨ About Me
          </h2>
          <div style="text-align: justify; color: #d0d0e0; line-height: 1.7; font-size: 1.05rem;">
            <p>I am an experienced <b style="color: #FF6B6B;">Software Engineering Tutor</b> and <b style="color: #FF6B6B;">Full‑Stack Developer</b> with a strong foundation in software design and application development. I thrive on breaking down complex concepts into practical lessons that empower students and professionals alike.</p>
            <ul style="list-style: none; padding-left: 0; margin-top: 16px;">
              <li style="padding: 6px 0;">🔭 <b>Current Focus:</b> Developing <b style="color: #FF6B6B;">farmo</b>, a GPS‑free agricultural supply chain platform.</li>
              <li style="padding: 6px 0;">🎓 <b>Education:</b> Pursuing BIT at <b style="color: #FF6B6B;">University of Moratuwa</b> and holder of an <b style="color: #FF6B6B;">HNDIT</b>.</li>
              <li style="padding: 6px 0;">🏢 <b>Experience:</b> Assistant Programme Coordinator at <b style="color: #FF6B6B;">ESOFT Metro College</b>.</li>
              <li style="padding: 6px 0;">📚 <b>Teaching:</b> Specializing in <b style="color: #FF6B6B;">DIIT</b> and <b style="color: #FF6B6B;">DISE</b> subjects including Software Engineering and Network Technology.</li>
            </ul>
          </div>
        </td>
        <td width="40%" valign="top" align="center">
          <br>
          <img src="https://github-readme-stats.vercel.app/api?username=ashanjayalath&show_icons=true&theme=transparent&hide_border=true&title_color=FF3B30&icon_color=FF6B6B&text_color=ccccdd" width="100%" class="stats-img" />
          <br><br>
          <img src="https://komarev.com/ghpvc/?username=ashanjayalath&style=flat-square&color=FF3B30" alt="Profile views" style="border-radius: 12px;" />
        </td>
      </tr>
    </table>
  </div>

  <!-- ========== SKILLS SECTION ========== -->
  <div class="glass-card" style="margin: 30px 0;">
    <h2 style="font-size: 2rem; font-weight: 700; background: linear-gradient(135deg, #FF3B30, #FF6B6B); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; text-align: center; margin-bottom: 20px;">
      🛠 Technical Arsenal
    </h2>

    <div style="margin-bottom: 24px;">
      <h4 style="color: #FF6B6B; font-weight: 500; letter-spacing: 1px; margin-bottom: 10px;">🎨 Frontend</h4>
      <div class="skill-row">
        <img src="https://skillicons.dev/icons?i=nextjs,react,ts,js,tailwind,bootstrap,html,css,figma,redux" class="skill-icon" />
      </div>
    </div>

    <div style="margin-bottom: 24px;">
      <h4 style="color: #FF6B6B; font-weight: 500; letter-spacing: 1px; margin-bottom: 10px;">⚙️ Backend & Database</h4>
      <div class="skill-row">
        <img src="https://skillicons.dev/icons?i=nodejs,express,mongodb,mysql,postgres,firebase,php,py,flask,java,cpp,cs" class="skill-icon" />
      </div>
    </div>

    <div style="margin-bottom: 24px;">
      <h4 style="color: #FF6B6B; font-weight: 500; letter-spacing: 1px; margin-bottom: 10px;">🔧 DevOps & Tools</h4>
      <div class="skill-row">
        <img src="https://skillicons.dev/icons?i=gcp,vercel,git,github,npm,yarn,postman,anaconda,cloudflare" class="skill-icon" />
      </div>
    </div>

    <div style="margin-bottom: 24px;">
      <h4 style="color: #FF6B6B; font-weight: 500; letter-spacing: 1px; margin-bottom: 10px;">🖥️ Other Tools & Frameworks</h4>
      <div class="skill-row">
        <img src="https://skillicons.dev/icons?i=selenium,mysql,stackoverflow,sublime,atom,androidstudio,vscode,idea,webstorm,visualstudio,eclipse" class="skill-icon" />
      </div>
      <div class="skill-row" style="margin-top: 8px;">
        <img src="https://skillicons.dev/icons?i=materialui,electron,c,godot" class="skill-icon" />
      </div>
    </div>

    <div style="margin-bottom: 24px;">
      <h4 style="color: #FF6B6B; font-weight: 500; letter-spacing: 1px; margin-bottom: 10px;">🐧 Operating Systems</h4>
      <div class="skill-row">
        <img src="https://skillicons.dev/icons?i=bash,linux,debian,kali,ubuntu,mint,arch,powershell,windows" class="skill-icon" />
      </div>
    </div>

    <div>
      <h4 style="color: #FF6B6B; font-weight: 500; letter-spacing: 1px; margin-bottom: 10px;">🌐 Social Platforms</h4>
      <div class="skill-row">
        <img src="https://skillicons.dev/icons?i=discord,linkedin,gmail,twitter,instagram" class="skill-icon" />
      </div>
    </div>
  </div>

  <!-- ========== PROJECTS SECTION (3D Cards) ========== -->
  <div style="margin: 30px 0;">
    <h2 style="font-size: 2rem; font-weight: 700; background: linear-gradient(135deg, #FF3B30, #FF6B6B); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; text-align: center; margin-bottom: 24px;">
      🚀 Featured Projects
    </h2>

    <table width="100%" style="border-collapse: collapse; gap: 20px; display: flex; flex-wrap: wrap; justify-content: center;">
      <tr>
        <td width="33%" valign="top" style="padding: 10px; display: inline-block; vertical-align: top; width: 30%;">
          <div class="project-card">
            <h3 align="center">🌾 farmo</h3>
            <p align="center" style="font-weight: 500; color: #b0b0c0; margin-bottom: 8px;">Agricultural Supply Chain</p>
            <p align="justify" style="color: #c0c0d0; flex: 1;">AI‑driven complaint classification and transparent tracking for farmers and distributors.</p>
            <p align="center" style="margin-top: 12px;">
              <img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=next.js&logoColor=white" />
              <img src="https://img.shields.io/badge/Chakra%20UI-319795?style=flat-square&logo=chakraui&logoColor=white" />
              <img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white" />
              <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
            </p>
          </div>
        </td>
        <td width="33%" valign="top" style="padding: 10px; display: inline-block; vertical-align: top; width: 30%;">
          <div class="project-card">
            <h3 align="center">🏙️ BkCiTy</h3>
            <p align="center" style="font-weight: 500; color: #b0b0c0; margin-bottom: 8px;">Real‑Time Web App</p>
            <p align="justify" style="color: #c0c0d0; flex: 1;">Scalable solution with Firebase authentication and real‑time data sync, built with TypeScript.</p>
            <p align="center" style="margin-top: 12px;">
              <img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=next.js&logoColor=white" />
              <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" />
              <img src="https://img.shields.io/badge/Redux-764ABC?style=flat-square&logo=redux&logoColor=white" />
              <img src="https://img.shields.io/badge/GCP-4285F4?style=flat-square&logo=googlecloud&logoColor=white" />
            </p>
          </div>
        </td>
        <td width="33%" valign="top" style="padding: 10px; display: inline-block; vertical-align: top; width: 30%;">
          <div class="project-card">
            <h3 align="center">🌴 Serendip Tour</h3>
            <p align="center" style="font-weight: 500; color: #b0b0c0; margin-bottom: 8px;">Dynamic Travel Solution</p>
            <p align="justify" style="color: #c0c0d0; flex: 1;">Full‑stack web platform for tour planning and local experiences using PHP and SQL.</p>
            <p align="center" style="margin-top: 12px;">
              <img src="https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white" />
              <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" />
              <img src="https://img.shields.io/badge/Bootstrap-7952B3?style=flat-square&logo=bootstrap&logoColor=white" />
            </p>
          </div>
        </td>
      </tr>
    </table>
  </div>

  <!-- ========== STATS SECTION ========== -->
  <div class="glass-card" style="margin: 30px 0; text-align: center;">
    <h2 style="font-size: 2rem; font-weight: 700; background: linear-gradient(135deg, #FF3B30, #FF6B6B); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; margin-bottom: 20px;">
      📊 Engineering Metrics
    </h2>
    <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 20px;">
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=ashanjayalath&theme=transparent&hide_border=true&stroke=FF6B6B&ring=FF3B30&fire=FF3B30&currStreakLabel=FF3B30" width="48%" class="stats-img" />
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=ashanjayalath&layout=compact&theme=transparent&hide_border=true&title_color=FF3B30&text_color=ccccdd" width="40%" class="stats-img" />
    </div>
  </div>

  <!-- ========== FOOTER / CONNECT ========== -->
  <div align="center" style="margin: 40px 0 10px;">
    <h2 style="font-size: 2rem; font-weight: 700; background: linear-gradient(135deg, #FF3B30, #FF6B6B); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; margin-bottom: 6px;">
      💡 Let's Build Something Amazing
    </h2>
    <p style="color: #b0b0c0; font-size: 1.1rem; margin-bottom: 20px;">
      I'm always open to new projects, creative ideas, or teaching opportunities.
    </p>
    <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 16px;">
      <a href="mailto:gpashanjayalath@gmail.com" class="social-link">
        <img src="https://img.shields.io/badge/Hire%20Me-FF3B30?style=for-the-badge&logo=gmail&logoColor=white" />
      </a>
      <a href="https://linkedin.com/in/nashan-jayalath" class="social-link">
        <img src="https://img.shields.io/badge/Let's%20Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
      </a>
      <a href="https://github.com/ashanjayalath" class="social-link">
        <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" />
      </a>
      <a href="https://twitter.com/ashanjayalath" class="social-link">
        <img src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white" />
      </a>
    </div>
    <br>
    <!-- Animated Footer Wave -->
    <img src="https://capsule-render.vercel.app/api?type=waving&color=0:FF3B30,100:FF6B6B&height=120&section=footer" width="100%" style="margin-top: 20px;" />
  </div>

</div>
<!-- ========== END APP CONTAINER ========== -->
