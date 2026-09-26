<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Omerullah Ansari · Software Developer</title>
  <!-- Google Fonts for modern typography -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
  <!-- Font Awesome 6 (free) for icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #f6f9fc 0%, #eef2f6 100%);
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      padding: 2rem 1rem;
      color: #1e293b;
    }

    .profile-card {
      max-width: 1000px;
      width: 100%;
      background: #ffffff;
      border-radius: 2.5rem;
      box-shadow: 0 30px 50px -20px rgba(0, 20, 40, 0.25), 0 10px 20px -8px rgba(0,0,0,0.1);
      overflow: hidden;
      transition: all 0.2s ease;
      border: 1px solid rgba(255,255,255,0.6);
      backdrop-filter: blur(2px);
    }

    /* Hero banner */
    .hero-banner {
      position: relative;
      height: 160px;
      background: #0e75b6; /* fallback */
    }

    .hero-banner img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
      filter: brightness(0.95) saturate(1.1);
    }

    /* Profile content container */
    .content {
      padding: 2rem 2.5rem 2.5rem 2.5rem;
      position: relative;
    }

    /* Avatar + title block */
    .title-section {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 1.5rem;
      gap: 1rem;
    }

    .name-title h1 {
      font-size: 2.4rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      line-height: 1.2;
      color: #0a1e2f;
    }

    .name-title h1 b {
      font-weight: 800;
      background: linear-gradient(135deg, #0e75b6, #1e4a6d);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .name-title h3 {
      font-size: 1.2rem;
      font-weight: 500;
      color: #2c5f7e;
      margin-top: 0.3rem;
      display: flex;
      align-items: center;
      gap: 0.45rem;
      flex-wrap: wrap;
    }

    .name-title h3 i {
      color: #0e75b6;
      font-size: 1rem;
    }

    .name-title h3 em {
      font-style: normal;
      background: #e9f0f6;
      padding: 0.2rem 0.8rem;
      border-radius: 40px;
      font-size: 0.9rem;
      font-weight: 500;
      color: #1a4b6d;
      display: inline-block;
    }

    /* animated dev gif */
    .dev-gif {
      width: 130px;
      flex-shrink: 0;
      filter: drop-shadow(0 8px 12px rgba(0,0,0,0.08));
    }

    .dev-gif img {
      width: 100%;
      height: auto;
      display: block;
      border-radius: 20px;
    }

    /* profile views counter */
    .views-badge {
      display: inline-flex;
      align-items: center;
      background: #f1f6fa;
      border-radius: 40px;
      padding: 0.3rem 0.9rem 0.3rem 0.7rem;
      font-size: 0.8rem;
      font-weight: 500;
      color: #1a4b6d;
      border: 1px solid #d0e2f0;
      margin-bottom: 1.6rem;
      transition: 0.2s;
    }

    .views-badge i {
      margin-right: 0.4rem;
      color: #0e75b6;
      font-size: 0.9rem;
    }

    .views-badge img {
      height: 18px;
      vertical-align: middle;
      margin-left: 8px;
    }

    /* info lines */
    .info-line {
      display: flex;
      align-items: center;
      gap: 0.75rem;
      font-size: 1rem;
      padding: 0.6rem 0;
      color: #1e3a5f;
    }

    .info-line i {
      width: 24px;
      color: #0e75b6;
      font-size: 1.2rem;
      text-align: center;
    }

    .info-line a {
      color: #1e3a5f;
      text-decoration: none;
      font-weight: 500;
      border-bottom: 2px solid transparent;
      transition: 0.2s;
    }

    .info-line a:hover {
      color: #0e75b6;
      border-bottom-color: #0e75b6;
    }

    .info-line strong {
      font-weight: 600;
      color: #0e2f47;
    }

    /* Section headers */
    .section-title {
      font-size: 1.1rem;
      font-weight: 700;
      letter-spacing: 0.3px;
      text-transform: uppercase;
      color: #1a4b6d;
      margin: 2rem 0 1rem 0;
      display: flex;
      align-items: center;
      gap: 0.6rem;
      border-bottom: 2px solid #e2edf6;
      padding-bottom: 0.6rem;
    }

    .section-title i {
      color: #0e75b6;
      font-size: 1.1rem;
    }

    /* social icons */
    .social-links {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      align-items: center;
      margin-bottom: 0.5rem;
    }

    .social-links a {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      background: #f0f6fc;
      border-radius: 50%;
      width: 48px;
      height: 48px;
      transition: all 0.2s ease;
      border: 1px solid #d4e4f0;
      color: #1a4b6d;
      font-size: 1.3rem;
      text-decoration: none;
      box-shadow: 0 2px 6px rgba(0,0,0,0.02);
    }

    .social-links a:hover {
      background: #0e75b6;
      color: white;
      transform: translateY(-3px);
      border-color: #0e75b6;
      box-shadow: 0 12px 18px -8px rgba(14, 117, 182, 0.4);
    }

    /* tech stack grid */
    .tech-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem 1.2rem;
      align-items: center;
      padding: 0.5rem 0 0.5rem 0;
    }

    .tech-grid a {
      display: inline-block;
      transition: transform 0.15s ease, filter 0.15s;
      filter: grayscale(0.2) brightness(1);
    }

    .tech-grid a:hover {
      transform: scale(1.15) translateY(-3px);
      filter: grayscale(0) brightness(1.05);
    }

    .tech-grid img {
      width: 40px;
      height: 40px;
      object-fit: contain;
      display: block;
    }

    /* github stats cards */
    .stats-container {
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
      margin-top: 1rem;
      justify-content: space-between;
    }

    .stat-card {
      background: #f9fcff;
      border-radius: 1.8rem;
      padding: 0.8rem 1.2rem;
      border: 1px solid #ddebf5;
      box-shadow: 0 8px 18px -10px rgba(0, 35, 70, 0.08);
      transition: 0.2s;
      flex: 1 1 180px;
      display: flex;
      justify-content: center;
      align-items: center;
      min-width: 0;
    }

    .stat-card:hover {
      border-color: #b6d2e9;
      background: #ffffff;
      box-shadow: 0 18px 25px -12px rgba(14, 117, 182, 0.2);
    }

    .stat-card img {
      max-width: 100%;
      height: auto;
      display: block;
      border-radius: 12px;
    }

    /* small adjustments for images inside stats (they are dynamic) */
    .stats-container .stat-card img[src*="github-readme-stats"] {
      width: 100%;
    }

    /* tweaks for layout on mobile */
    @media (max-width: 700px) {
      .content {
        padding: 1.8rem 1.5rem;
      }
      .name-title h1 {
        font-size: 1.9rem;
      }
      .title-section {
        flex-direction: column;
        align-items: flex-start;
      }
      .dev-gif {
        width: 100px;
        align-self: flex-end;
        margin-top: -20px;
      }
      .social-links a {
        width: 44px;
        height: 44px;
        font-size: 1.2rem;
      }
      .tech-grid img {
        width: 34px;
        height: 34px;
      }
      .stats-container {
        gap: 1rem;
      }
    }

    @media (max-width: 480px) {
      .hero-banner {
        height: 120px;
      }
      .name-title h1 {
        font-size: 1.6rem;
      }
      .info-line {
        font-size: 0.9rem;
      }
      .section-title {
        font-size: 1rem;
      }
    }

    /* the original "komarev" counter gets styled as part of the badge */
    .views-badge img {
      height: 20px;
      border-radius: 20px;
    }

    /* fix any potential overflow from long emails */
    .info-line a, .info-line span {
      word-break: break-word;
    }
  </style>
</head>
<body>
  <div class="profile-card">
    <!-- HEADER BANNER -->
    <div class="hero-banner">
      <img src="https://media.licdn.com/dms/image/D5616AQERO_HZtWE2GA/profile-displaybackgroundimage-shrink_350_1400/0/1711002426710?e=1720051200&v=beta&t=fgCwmyUDX0cbArvpJeN0JXI8oiuNtSYdVvcTtQNVhZo" alt="Profile banner">
    </div>

    <!-- MAIN CONTENT -->
    <div class="content">
      <!-- TITLE + DEV GIF -->
      <div class="title-section">
        <div class="name-title">
          <h1>Hello, I'm <b>Omerullah Ansari</b></h1>
          <h3>
            <i class="fas fa-code"></i>
            <em>A passionate Software Developer from Pakistan</em>
          </h3>
        </div>
        <div class="dev-gif">
          <img src="https://cdn.dribbble.com/users/1162077/screenshots/3848914/programmer.gif" alt="Programmer illustration">
        </div>
      </div>

      <!-- PROFILE VIEWS BADGE (original komarev counter now integrated) -->
      <div class="views-badge">
        <i class="fas fa-eye"></i> Profile views
        <img src="https://komarev.com/ghpvc/?username=omerullahansari&label=&color=0e75b6&style=flat" alt="profile views counter">
      </div>

      <!-- QUICK INFO LINES (learning + email) with modern icons -->
      <div class="info-line">
        <i class="fas fa-seedling"></i>
        <span>Currently learning <strong>Data Structures and Algorithms</strong></span>
      </div>
      <div class="info-line">
        <i class="fas fa-envelope"></i>
        <span>📫 How to reach me: <a href="mailto:omerullah.ansari@gmail.com">omerullah.ansari@gmail.com</a></span>
      </div>

      <!-- CONNECT SECTION (social icons) -->
      <div class="section-title">
        <i class="fas fa-link"></i> Connect with me
      </div>
      <div class="social-links">
        <a href="https://linkedin.com/in/omerullah-ansari" target="_blank" rel="noopener" title="LinkedIn">
          <i class="fab fa-linkedin-in"></i>
        </a>
        <a href="https://instagram.com/itsmeomer_" target="_blank" rel="noopener" title="Instagram">
          <i class="fab fa-instagram"></i>
        </a>
        <a href="https://www.hackerrank.com/omerullah_ansari" target="_blank" rel="noopener" title="HackerRank">
          <i class="fab fa-hackerrank"></i>
        </a>
      </div>

      <!-- LANGUAGES AND TOOLS -->
      <div class="section-title">
        <i class="fas fa-tools"></i> Languages & Tools
      </div>
      <div class="tech-grid">
        <!-- Using Font Awesome for some icons? No, we keep original SVGs for recognizability but we improve hover & style -->
        <a href="https://www.arduino.cc/" target="_blank" rel="noreferrer" title="Arduino"><img src="https://cdn.worldvectorlogo.com/logos/arduino-1.svg" alt="arduino"></a>
        <a href="https://getbootstrap.com" target="_blank" rel="noreferrer" title="Bootstrap"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/bootstrap/bootstrap-plain-wordmark.svg" alt="bootstrap"></a>
        <a href="https://www.w3schools.com/cs/" target="_blank" rel="noreferrer" title="C#"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/csharp/csharp-original.svg" alt="csharp"></a>
        <a href="https://www.w3schools.com/css/" target="_blank" rel="noreferrer" title="CSS3"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="css3"></a>
        <a href="https://dotnet.microsoft.com/" target="_blank" rel="noreferrer" title=".NET"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/dot-net/dot-net-original-wordmark.svg" alt="dotnet"></a>
        <a href="https://www.figma.com/" target="_blank" rel="noreferrer" title="Figma"><img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt="figma"></a>
        <a href="https://firebase.google.com/" target="_blank" rel="noreferrer" title="Firebase"><img src="https://www.vectorlogo.zone/logos/firebase/firebase-icon.svg" alt="firebase"></a>
        <a href="https://www.w3.org/html/" target="_blank" rel="noreferrer" title="HTML5"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5"></a>
        <a href="https://ifttt.com/" target="_blank" rel="noreferrer" title="IFTTT"><img src="https://www.vectorlogo.zone/logos/ifttt/ifttt-ar21.svg" alt="ifttt"></a>
        <a href="https://www.adobe.com/in/products/illustrator.html" target="_blank" rel="noreferrer" title="Illustrator"><img src="https://www.vectorlogo.zone/logos/adobe_illustrator/adobe_illustrator-icon.svg" alt="illustrator"></a>
        <a href="https://www.java.com" target="_blank" rel="noreferrer" title="Java"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="java"></a>
        <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" rel="noreferrer" title="JavaScript"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="javascript"></a>
        <a href="https://kotlinlang.org" target="_blank" rel="noreferrer" title="Kotlin"><img src="https://www.vectorlogo.zone/logos/kotlinlang/kotlinlang-icon.svg" alt="kotlin"></a>
        <a href="https://www.mongodb.com/" target="_blank" rel="noreferrer" title="MongoDB"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="mongodb"></a>
        <a href="https://www.mysql.com/" target="_blank" rel="noreferrer" title="MySQL"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="mysql"></a>
        <a href="https://nodejs.org" target="_blank" rel="noreferrer" title="Node.js"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="nodejs"></a>
        <a href="https://www.photoshop.com/en" target="_blank" rel="noreferrer" title="Photoshop"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/photoshop/photoshop-line.svg" alt="photoshop"></a>
        <a href="https://www.python.org" target="_blank" rel="noreferrer" title="Python"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python"></a>
      </div>

      <!-- GITHUB STATS SECTION (modernized) -->
      <div class="section-title">
        <i class="fas fa-chart-bar"></i> GitHub Stats
      </div>
      <div class="stats-container">
        <!-- top languages card -->
        <div class="stat-card">
          <img src="https://github-readme-stats.vercel.app/api/top-langs?username=omerullahansari&show_icons=true&locale=en&layout=compact&theme=default&hide_border=true&bg_color=ffffff&title_color=0e75b6&text_color=1e293b" alt="Top languages">
        </div>
        <!-- github stats card -->
        <div class="stat-card">
          <img src="https://github-readme-stats.vercel.app/api?username=omerullahansari&show_icons=true&locale=en&theme=default&hide_border=true&bg_color=ffffff&title_color=0e75b6&text_color=1e293b&icon_color=0e75b6" alt="GitHub stats">
        </div>
        <!-- streak stats card -->
        <div class="stat-card">
          <img src="https://github-readme-streak-stats.herokuapp.com/?user=omerullahansari&theme=default&hide_border=true&background=ffffff&stroke=0e75b6&ring=0e75b6&fire=0e75b6&currStreakLabel=0e75b6" alt="GitHub streak">
        </div>
      </div>
      <!-- subtle footer note (optional) -->
      <div style="text-align: center; margin-top: 2.5rem; font-size: 0.75rem; color: #9ab3c9; letter-spacing: 0.4px;">
        <i class="fas fa-code-branch"></i> built with passion · omerullah ansari
      </div>
    </div>
  </div>
</body>
</html>
