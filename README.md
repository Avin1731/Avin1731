<!-- ===================== HEADER — Anime Neon Sakura ===================== -->

<style>
  .anime-row {
    position: relative;
    width: 100%;
    max-width: 500px;
    height: 180px; /* Tinggi ditambah untuk 3 baris */
    margin: 40px auto;
  }

  .anime-item {
    position: absolute;
    width: 80px;
    height: 80px;
    border: 2px solid #0ff;
    border-radius: 50%;
    overflow: hidden;
    cursor: pointer;
    transition: transform 0.3s ease;
    background-color: black;
  }

  .anime-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 50%;
    display: block;
  }

  .anime-name {
    position: absolute;
    bottom: -30px;
    left: 50%;
    transform: translateX(-50%);
    background-color: rgba(0,0,0,0.7);
    color: white;
    padding: 3px 8px;
    border-radius: 5px;
    font-size: 0.75rem;
    white-space: nowrap;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.3s ease, bottom 0.3s ease;
  }

  .anime-item:hover {
    transform: scale(1.2);
    z-index: 10;
  }

  .anime-item:hover .anime-name {
    opacity: 1;
    bottom: 90px;
  }

  /* Posisi dengan 6 item (34, 25, 16) */
  /* Baris atas: item 3 dan 4 */
  .anime-item:nth-child(3) {
    top: 20px;   /* baris atas */
    left: calc(50% - 90px); /* kiri dari tengah */
  }
  .anime-item:nth-child(4) {
    top: 20px;   /* baris atas */
    left: calc(50% + 10px); /* kanan dari tengah */
  }

  /* Baris tengah: item 2 dan 5 */
  .anime-item:nth-child(2) {
    top: 40px;   /* baris tengah */
    left: calc(50% - 170px); /* lebih kiri */
  }
  .anime-item:nth-child(5) {
    top: 40px;   /* baris tengah */
    left: calc(50% + 90px); /* lebih kanan */
  }

  /* Baris bawah: item 1 dan 6 */
  .anime-item:nth-child(1) {
    top: 60px;  /* baris bawah */
    left: calc(50% - 250px); /* paling kiri */
  }
  .anime-item:nth-child(6) {
    top: 60px;  /* baris bawah */
    left: calc(50% + 170px); /* paling kanan */
  }

/* CSS untuk tabel projects - GITHUB THEME DARK WITH NEON */
.projects-table {
  width: 95%;
  max-width: 1000px;
  margin: 30px auto;
  border-collapse: collapse;
  background-color: transparent;
  border: 2px solid #0ff; /* Neon cyan border */
  border-radius: 6px;
  overflow: hidden;
  box-shadow: 0 0 15px rgba(0, 255, 255, 0.1);
}

.projects-table th {
  background-color: rgba(13, 17, 23, 0.9); /* Semi-transparent GitHub bg */
  color: #58a6ff; /* GitHub blue text */
  padding: 16px;
  text-align: center;
  font-size: 1em;
  font-weight: 600;
  border-bottom: 2px solid #0ff; /* Neon border */
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.projects-table td {
  padding: 0;
  vertical-align: middle; /* Center content vertically */
  text-align: center; /* Center content horizontally */
  border-bottom: 1px solid #30363d;
  background-color: transparent;
}

.projects-table tr:last-child td {
  border-bottom: none;
}

.projects-table tr:hover {
  background-color: rgba(0, 255, 255, 0.05); /* Neon hover effect */
}

/* MODIFIKASI: Cover column - KONSISTEN */
.projects-table td:first-child {
  width: 180px; /* Lebar tetap yang cukup */
  padding: 0;
  border-right: 1px solid #30363d;
}

/* MODIFIKASI: Project cover container */
.project-cover {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 15px; /* Padding untuk memberi ruang */
  width: 100%;
  height: 180px; /* Tinggi tetap untuk konsistensi */
  overflow: hidden;
  transition: all 0.3s ease;
  background-color: transparent;
}

.project-cover:hover {
  transform: scale(1.05);
  opacity: 0.9;
}

/* MODIFIKASI: Cover image - pertahankan rasio aspek dengan batasan */
.project-cover img {
  width: auto; /* Lebar menyesuaikan gambar */
  height: auto; /* Tinggi menyesuaikan gambar */
  max-width: 100%; /* Maksimum lebar container */
  max-height: 150px; /* Maksimum tinggi */
  object-fit: contain; /* Pertahankan proporsi */
  border-radius: 6px;
  border: 1px solid #30363d;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
  display: block;
}

/* Project details column */
.project-details {
  padding: 20px;
  text-align: center; /* Center all text */
}

/* Project name - blue by default, changes based on status */
.project-name {
  font-size: 1.3em;
  font-weight: 600;
  margin-bottom: 8px;
  line-height: 1.4;
}

/* Project description - blue by default, changes based on status */
.project-desc {
  font-size: 0.95em;
  line-height: 1.5;
  margin-bottom: 12px;
}

/* Status row classes untuk warna teks dinamis */
.status-completed-row .project-name {
  color: #3fb950 !important;
}

.status-completed-row .project-desc {
  color: rgba(63, 185, 80, 0.8) !important;
}

.status-progress-row .project-name {
  color: #d29922 !important;
}

.status-progress-row .project-desc {
  color: rgba(210, 153, 34, 0.8) !important;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 15px;
  justify-content: center; /* Center tech tags */
}

.tech-tag {
  padding: 4px 10px;
  background-color: rgba(19, 35, 58, 0.7); /* Semi-transparent */
  color: #58a6ff;
  border-radius: 2em;
  font-size: 0.85em;
  font-weight: 500;
  border: 1px solid rgba(88, 166, 255, 0.3);
}

/* Status column */
.status-cell {
  width: 150px;
  padding: 20px;
  text-align: center;
  border-left: 1px solid #30363d;
}

.status {
  display: inline-block;
  padding: 6px 16px;
  border-radius: 2em;
  font-weight: 600;
  font-size: 0.85em;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  border: 1px solid;
  text-align: center;
}

.status-completed {
  color: #3fb950;
  border-color: #3fb950;
  background-color: rgba(63, 185, 80, 0.1);
}

.status-progress {
  color: #d29922;
  border-color: #d29922;
  background-color: rgba(210, 153, 34, 0.1);
}

/* GitHub-like Tags */
.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 15px;
  justify-content: center;
}

/* GitHub Tag Style */
.tech-tag {
  display: inline-flex;
  align-items: center;
  padding: 4px 12px;
  font-size: 0.75em;
  font-weight: 500;
  border-radius: 2em;
  line-height: 1;
  white-space: nowrap;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans', Helvetica, Arial, sans-serif;
}

/* GitHub Tag Colors */
.tech-tag.html {
  background-color: rgba(227, 76, 38, 0.15);
  color: #e34c26;
  border: 1px solid rgba(227, 76, 38, 0.3);
}

.tech-tag.css {
  background-color: rgba(21, 114, 182, 0.15);
  color: #1572b6;
  border: 1px solid rgba(21, 114, 182, 0.3);
}

.tech-tag.js {
  background-color: rgba(247, 223, 30, 0.15);
  color: #f7df1e;
  border: 1px solid rgba(247, 223, 30, 0.3);
}

.tech-tag.react {
  background-color: rgba(97, 218, 251, 0.15);
  color: #61dafb;
  border: 1px solid rgba(97, 218, 251, 0.3);
}

.tech-tag.node {
  background-color: rgba(104, 160, 99, 0.15);
  color: #68a063;
  border: 1px solid rgba(104, 160, 99, 0.3);
}

.tech-tag.python {
  background-color: rgba(53, 114, 165, 0.15);
  color: #3572a5;
  border: 1px solid rgba(53, 114, 165, 0.3);
}

.tech-tag.php {
  background-color: rgba(79, 91, 147, 0.15);
  color: #4f5b93;
  border: 1px solid rgba(79, 91, 147, 0.3);
}

.tech-tag.mysql {
  background-color: rgba(0, 117, 143, 0.15);
  color: #00758f;
  border: 1px solid rgba(0, 117, 143, 0.3);
}

.tech-tag.mongodb {
  background-color: rgba(71, 153, 76, 0.15);
  color: #47994c;
  border: 1px solid rgba(71, 153, 76, 0.3);
}

.tech-tag.vue {
  background-color: rgba(65, 184, 131, 0.15);
  color: #41b883;
  border: 1px solid rgba(65, 184, 131, 0.3);
}

.tech-tag.default {
  background-color: rgba(88, 166, 255, 0.15);
  color: #58a6ff;
  border: 1px solid rgba(88, 166, 255, 0.3);
}

/* Responsive */
@media (max-width: 768px) {
  .projects-table {
    width: 100%;
    margin: 15px auto;
  }
  
  .projects-table th,
  .projects-table td {
    padding: 10px 5px;
    font-size: 0.85em;
  }
  
  /* Responsive cover */
  .projects-table td:first-child {
    width: 120px; /* Lebar lebih kecil di mobile */
  }
  
  .project-cover {
    height: 140px; /* Tinggi lebih kecil di mobile */
    padding: 10px;
  }
  
  .project-cover img {
    max-height: 120px;
  }
  
  .status-cell {
    width: 100px;
    padding: 10px 5px;
  }
  
  .project-tech {
    gap: 4px;
  }
  
  .tech-tag {
    padding: 3px 8px;
    font-size: 0.7em;
  }
}
</style>

<div align="center">
  ╔══════════════════ ✦ ✦ ✦ ══════════════════╗  
  <h1>🌸✨ Xte • Avin1731 ✨🌸</h1>  
  ╚══════════════════ ✦ ✦ ✦ ══════════════════╝  

  <h4>⚡🌸 Welcome to My GitHub 🌸⚡</h4>

  <img src="images/rikka.gif" width="600" alt="Anime banner" />
  <div align="center">╔══════════════════ ✦ ✦ ✦ ══════════════════╗</div>
  <section>
    <h3 style="font-weight: bold; margin: 4px 0;">~ Electronics Engineering</h3>
    <h3 style="font-weight: bold; margin: 4px 0;">&</h3>
    <h3 style="font-weight: bold; margin: 4px 0;">Software Engineering ~</h3>
  </section>

  <h4 style="font-weight: normal;">Web Developer &rArr; Frontend Developer</h4>
  <h5 style="font-weight: normal;">~ Anime Enthusiast • Hololive Fans • Gaming Enjoyer ~</h5>
  <br>
  <div align="center">╚══════════════════ ✦ ✦ ✦ ══════════════════╝
  </div>
  <div align="center">╔══════════════════ ✦ ✦ ✦ ══════════════════╗</div> 
</div>

<!-- ===================== WHO AM I ===================== -->
<section>
  <div align="center">
    <h2>🌸✨ Who Am I? ✨🌸</h2>
    <i>"Maybe you know me, but you don't understand me.." ~ 1412</i>
  </div>

  <ul>
    <li>💻 Frontend Web Developer</li>
    <li>🌸 Loves tidy workflows, tidy code, and of course… anime</li>
    <li>⚡ Tech interests: Laravel, Next.js, Typescript, APIs, Python</li>
    <li>🎧 Often codes with anisong and VTuber streams in the background</li>
    <li>⭐ Codes and works best when the world is asleep</li>
    <li>🌌 Sometimes I feel like a side character… until I write code</li>
  </ul>

  <div align="center">╚══════════════════ ✦ ✦ ✦ ══════════════════╝</div>
  <div align="center">╔══════════════════ ✦ ✦ ✦ ══════════════════╗</div>
</section>

<!-- ===================== TECH STACK ===================== -->
<section>
  <div align="center">
    <h2>⚡ Tech Stack ⚡</h2>
    <img src="https://skillicons.dev/icons?i=html,css,js,ts,react,nextjs,php,laravel,python,mysql,github,vscode,figma&theme=dark" alt="Tech stack icons"/>
  </div>
  <div align="center">╚══════════════════ ✦ ✦ ✦ ══════════════════╝</div>
  <div align="center">╔══════════════════ ✦ ✦ ✦ ══════════════════╗</div>
</section>

<!-- ===================== PROJECTS ===================== -->
<section>
  <div align="center">
    <h2>🌸 Featured Projects 🌸</h2>
  <div>
    <table class="projects-table">
      <thead>
        <tr>
          <th width="150">Cover</th>
          <th width="400">Project Details</th>
          <th width="150">Status</th>
        </tr>
      </thead>
      <tbody>
        <!-- Baris 1: Completed -->
        <tr class="status-completed-row">
          <td>
            <a href="#" class="project-cover">
              <img src="images/e.png" alt="Project 1 Cover">
            </a>
          </td>
          <td class="project-details">
            <div class="project-name">Coming Soon..</div>
            <div class="project-desc">Coming Soon..</div>
            <div class="project-tech">
              <span class="tech-tag react">React</span>
              <span class="tech-tag node">Node.js</span>
              <span class="tech-tag mongodb">MongoDB</span>
              <span class="tech-tag default">Stripe</span>
            </div>
          </td>
          <td class="status-cell">
            <span class="status status-completed">Completed</span>
          </td>
        </tr>
        <!-- Baris 2: In Progress -->
        <tr class="status-progress-row">
          <td>
            <a href="#" class="project-cover">
              <img src="images/e.png" alt="Project 2 Cover">
            </a>
          </td>
          <td class="project-details">
            <div class="project-name">Coming Soon..</div>
            <div class="project-desc">Coming Soon..</div>
            <div class="project-tech">
              <span class="tech-tag react">React</span>
              <span class="tech-tag node">Node.js</span>
              <span class="tech-tag mongodb">MongoDB</span>
              <span class="tech-tag default">Stripe</span>
            </div>
          </td>
          <td class="status-cell">
            <span class="status status-progress">On Progress</span>
          </td>
        </tr>
        <!-- Baris 3: In Progress -->
        <tr class="status-progress-row">
          <td>
            <a href="#" class="project-cover">
              <img src="images/e.png" alt="Project 3 Cover">
            </a>
          </td>
          <td class="project-details">
            <div class="project-name">Coming Soon..</div>
            <div class="project-desc">Coming Soon..</div>
            <div class="project-tech">
              <span class="tech-tag react">React</span>
              <span class="tech-tag node">Node.js</span>
              <span class="tech-tag mongodb">MongoDB</span>
              <span class="tech-tag default">Stripe</span>
            </div>
          </td>
          <td class="status-cell">
            <span class="status status-progress">On Progress</span>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
  </div>

  <div align="center">╚══════════════════ ✦ ✦ ✦ ══════════════════╝</div>
  <div align="center">╔══════════════════ ✦ ✦ ✦ ══════════════════╗</div>
</section>

<section>
  <div align="center">
    <h2>🌸 My favorite Anime 🌸</h2>
  </div>
    <div class="anime-row">
      <a href="https://myanimelist.net/anime/11757/Sword_Art_Online" target="_blank" class="anime-item" title="Anime 1">
        <img src="images/4sao.jpg" alt="Anime 1" />
        <div class="anime-name">Sword Art Online</div>
      </a>
      <a href="https://myanimelist.net/anime/4654/Toaru_Majutsu_no_Index" target="_blank" class="anime-item" title="Anime 2">
        <img src="images/3tm.jpg" alt="Anime 2" />
        <div class="anime-name">Toaru Series</div>
      </a>
      <a href="https://myanimelist.net/anime/235/Detective_Conan" target="_blank" class="anime-item" title="Anime 3">
        <img src="images/1dc.jpg" alt="Anime 3" />
        <div class="anime-name">Detective Conan</div>
      </a>
      <a href="https://myanimelist.net/anime/14741/Chuunibyou_demo_Koi_ga_Shitai" target="_blank" class="anime-item" title="Anime 4">
        <img src="images/2cd.jpg" alt="Anime 4" />
        <div class="anime-name">Chuunibyou</div>
      </a>
      <a href="https://myanimelist.net/anime/32615/Youjo_Senki" target="_blank" class="anime-item" title="Anime 5">
        <img src="images/5ys.jpg" alt="Anime 5" />
        <div class="anime-name">Youjo Senki</div>
      </a>
      <a href="https://myanimelist.net/anime/50739/Otonari_no_Tenshi-sama_ni_Itsunomanika_Dame_Ningen_ni_Sareteita_Ken?q=otonari&cat=anime" target="_blank" class="anime-item" title="Anime 6">
        <img src="images/OT.jpg" alt="Anime 6" />
        <div class="anime-name">Otonari Tenshi</div>
      </a>
    </div>
</section>

<!-- ===================== SOCIAL ===================== -->
<section>
  <div align="center">╚══════════════════ ✦ ✦ ✦ ══════════════════╝</div>
  <div align="center">╔══════════════════ ✦ ✦ ✦ ══════════════════╗</div>
  
  <div align="center">
    <h2>🔗 Connect With Me 🔗</h2>
    <a href="https://www.instagram.com/vinx177/">
      <img src="https://skillicons.dev/icons?i=instagram" width="45" alt="Instagram"/>
    </a>
    &nbsp;
    <a href="https://discordapp.com/users/819799820549095464">
      <img src="https://skillicons.dev/icons?i=discord" width="45" alt="Discord"/>
    </a>
    &nbsp;
    <a href="mailto:hnostenostogei@gmail.com">
      <img src="https://skillicons.dev/icons?i=gmail" width="45" alt="Email"/>
    </a>
  </div>

  <div align="center">╚══════════════════ ✦ ✦ ✦ ══════════════════╝</div>
</section>

<!-- ===================== QUOTE ===================== -->
<section>
  <div align="center">╔══════════════════ ✦ ✦ ✦ ══════════════════╗</div>
  <div align="center">
    <h2>🌙⚡ Night Owl Dev Manifest ⚡🌙</h2>
    <i>"May your silent progress outshine the noise,<br>
    and may every late-night commit sharpen you sharper than yesterday."</i>
  </div>
    <div align="center">╚══════════════════ ✦ ✦ ✦ ══════════════════╝</div>
</section>