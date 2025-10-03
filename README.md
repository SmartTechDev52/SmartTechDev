<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SmartTech Guides</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
<style>
/* ================== RESET ================== */
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family:'Poppins', sans-serif; background:#f4f7f9; color:#333; scroll-behavior:smooth; }

/* ================== HEADER ================== */
header {
  background: linear-gradient(135deg,#0a3d62,#3c6382);
  color:white; text-align:center; padding:80px 20px;
}
header h1 { font-size:2.5em; margin-bottom:10px; }
header p { font-size:1.2em; margin-bottom:20px; }
header .btn {
  display:inline-block; padding:12px 25px; background:#e67e22; color:white; border-radius:5px;
  font-weight:600; transition:0.3s; text-decoration:none;
}
header .btn:hover { background:#d35400; transform:scale(1.05); }

/* ================== NAV ================== */
nav { position:sticky; top:0; background:white; display:flex; justify-content:center; padding:10px 0; box-shadow:0 2px 6px rgba(0,0,0,0.1); }
nav a { margin:0 15px; color:#0a3d62; font-weight:600; text-decoration:none; transition:0.3s; }
nav a:hover { color:#e67e22; }

/* ================== SECTIONS ================== */
section { max-width:1000px; margin:40px auto; padding:20px; background:white; border-radius:10px; box-shadow:0 4px 6px rgba(0,0,0,0.1); opacity:0; transform:translateY(20px); transition:opacity 0.8s ease-out, transform 0.8s ease-out; }
section.visible { opacity:1; transform:translateY(0); }
h2 { color:#0a3d62; margin-bottom:20px; text-align:center; }

/* ================== SERVICES ================== */
.services { display:grid; grid-template-columns:repeat(auto-fit,minmax(250px,1fr)); gap:20px; }
.service-card { background:#f1f1f1; padding:20px; border-radius:10px; text-align:center; transition:0.3s; cursor:pointer; }
.service-card:hover { transform:translateY(-5px); box-shadow:0 10px 20px rgba(0,0,0,0.2); }
.service-card i { font-size:2.5em; color:#e67e22; margin-bottom:10px; }
.service-card button { margin-top:10px; padding:8px 15px; border:none; border-radius:5px; background:#e67e22; color:white; font-weight:600; cursor:pointer; transition:0.3s; }
.service-card button:hover { background:#d35400; transform:scale(1.05); }

/* ================== MODAL ================== */
.modal {
  display: none; position: fixed; z-index:1000; left:0; top:0; width:100%; height:100%;
  background: rgba(0,0,0,0.7); display:flex; justify-content:center; align-items:center;
}
.modal-content {
  background:#fff; padding:30px; border-radius:12px; max-width:600px; width:90%; position:relative; box-shadow:0 10px 25px rgba(0,0,0,0.3);
}
.modal-content h2 { margin-bottom:15px; color:#0a3d62; text-align:center; }
.modal-content ul { margin-left:20px; margin-bottom:20px; }
.modal-content ul li { margin-bottom:10px; }
.modal-content .btn { display:block; text-align:center; margin-top:10px; }
.close {
  position:absolute; top:15px; right:20px; font-size:28px; font-weight:bold; cursor:pointer; color:#333; transition:0.3s;
}
.close:hover { color:#e67e22; }

/* ================== BLOG ================== */
.blog { display:grid; grid-template-columns:repeat(auto-fit,minmax(250px,1fr)); gap:20px; }
.blog-card { background:#f1f1f1; border-radius:10px; padding:15px; transition:0.3s; }
.blog-card:hover { transform:scale(1.03); box-shadow:0 10px 20px rgba(0,0,0,0.2); }
.blog-card h3 { margin-bottom:10px; color:#0a3d62; }

/* ================== CONTACT ================== */
.contact form { display:flex; flex-direction:column; gap:15px; max-width:500px; margin:0 auto; }
.contact input, .contact textarea { padding:10px; border-radius:5px; border:1px solid #ccc; width:100%; }
.contact button { padding:12px; background:#e67e22; color:white; border:none; border-radius:5px; font-weight:600; cursor:pointer; transition:0.3s; }
.contact button:hover { background:#d35400; transform:scale(1.05); }

/* ================== FOOTER ================== */
footer { text-align:center; padding:15px; background:#eee; margin-top:30px; font-size:0.9em; }

/* ================== MEDIA ================== */
@media(max-width:768px){ nav { flex-wrap:wrap; } section { margin:20px 10px; padding:15px; } }
</style>
</head>
<body>

<header>
  <h1>SmartTech Guides</h1>
  <p>Votre source de conseils, projets et technologies modernes</p>
  <a href="#services" class="btn">Découvrir nos services</a>
</header>

<nav>
  <a href="#services">Services</a>
  <a href="#blog">Blog</a>
  <a href="#contact">Contact</a>
</nav>

<section id="services">
  <h2>Nos Services</h2>
  <div class="services">
    <!-- Développement Web -->
    <div class="service-card">
      <i class="fas fa-laptop-code"></i>
      <h3>Développement Web</h3>
      <p>Création de sites modernes, responsive et interactifs.</p>
      <button class="service-btn" data-modal="webModal">En savoir plus</button>
    </div>
    <!-- Intelligence Artificielle -->
    <div class="service-card">
      <i class="fas fa-robot"></i>
      <h3>Intelligence Artificielle</h3>
      <p>Conseils et projets IA adaptés à vos besoins professionnels.</p>
      <button class="service-btn" data-modal="aiModal">En savoir plus</button>
    </div>
    <!-- Consulting Tech -->
    <div class="service-card">
      <i class="fas fa-lightbulb"></i>
      <h3>Consulting Tech</h3>
      <p>Solutions pratiques pour améliorer vos processus numériques.</p>
      <button class="service-btn" data-modal="consultingModal">En savoir plus</button>
    </div>
  </div>
</section>

<!-- MODALS -->
<!-- Développement Web Modal -->
<div id="webModal" class="modal">
  <div class="modal-content">
    <span class="close">&times;</span>
    <h2>Développement Web Professionnel</h2>
    <ul>
      <li>Sites vitrines modernes et responsive</li>
      <li>Applications web interactives (HTML, CSS, JavaScript, PHP, Laravel, Django…)</li>
      <li>Optimisation SEO & performance</li>
      <li>Maintenance et mises à jour régulières</li>
      <li>Intégration d’outils et API externes</li>
    </ul>
    <a href="#contact" class="btn">Contactez-nous</a>
  </div>
</div>

<!-- Intelligence Artificielle Modal -->
<div id="aiModal" class="modal">
  <div class="modal-content">
    <span class="close">&times;</span>
    <h2>Intelligence Artificielle</h2>
    <ul>
      <li>Automatisation des processus métier</li>
      <li>Applications IA et machine learning</li>
      <li>Analyse de données et prédictions</li>
      <li>Chatbots intelligents pour support client</li>
      <li>Intégration IA dans vos applications existantes</li>
    </ul>
    <a href="#contact" class="btn">Contactez-nous</a>
  </div>
</div>

<!-- Consulting Tech Modal -->
<div id="consultingModal" class="modal">
  <div class="modal-content">
    <span class="close">&times;</span>
    <h2>Consulting Tech</h2>
    <ul>
      <li>Audit des systèmes et processus numériques</li>
      <li>Optimisation des workflows et productivité</li>
      <li>Conseils en infrastructure et sécurité</li>
      <li>Formation et accompagnement technique</li>
      <li>Stratégie digitale adaptée à vos objectifs</li>
    </ul>
    <a href="#contact" class="btn">Contactez-nous</a>
  </div>
</div>

<section id="blog">
  <h2>Articles Récents</h2>
  <div class="blog">
    <div class="blog-card">
      <h3>Découvrir l’IA en 2025</h3>
      <p>Les technologies d’intelligence artificielle à connaître cette année.</p>
    </div>
    <div class="blog-card">
      <h3>Top 10 des Frameworks Web</h3>
      <p>Choisir le meilleur framework pour vos projets web modernes.</p>
    </div>
    <div class="blog-card">
      <h3>Conseils pour débuter en programmation</h3>
      <p>Les bonnes pratiques pour devenir un développeur compétent rapidement.</p>
    </div>
  </div>
</section>

<section id="contact">
  <h2>Contactez-nous</h2>
  <form id="contactForm">
    <input type="text" placeholder="Votre nom" required>
    <input type="email" placeholder="Votre email" required>
    <textarea placeholder="Votre message" rows="5" required></textarea>
    <button type="submit">Envoyer</button>
  </form>
  <p style="text-align:center;margin-top:10px;">
    <a href="https://www.linkedin.com/in/issouf-ouedraogo-6b721a338/" target="_blank" style="margin-right:10px;"><i class="fab fa-linkedin"></i> LinkedIn</a>
    <a href="https://github.com/SmartTechDev52" target="_blank"><i class="fab fa-github"></i> GitHub</a>
  </p>
</section>

<footer>
  <p>&copy; 2025 SmartTech Guides | Tous droits réservés</p>
</footer>

<script>
// Animation fade-in des sections au scroll
document.addEventListener("DOMContentLoaded", () => {
    const sections = document.querySelectorAll("section");
    const observer = new IntersectionObserver(entries => {
        entries.forEach(entry => {
            if(entry.isIntersecting) entry.target.classList.add("visible");
        });
    }, { threshold: 0.2 });
    sections.forEach(section => observer.observe(section));

    // Modal Logic
    const serviceButtons = document.querySelectorAll(".service-btn");
    serviceButtons.forEach(btn => {
        btn.addEventListener("click", () => {
            const modalId = btn.getAttribute("data-modal");
            const modal = document.getElementById(modalId);
            if(modal) modal.style.display = "flex";
        });
    });

    const closeButtons = document.querySelectorAll(".close");
    closeButtons.forEach(btn => {
        btn.addEventListener("click", () => {
            btn.parentElement.parentElement.style.display = "none";
        });
    });

    window.addEventListener("click", (e) => {
        if(e.target.classList.contains("modal")) e.target.style.display = "none";
    });

    // Formulaire simple
    document.getElementById("contactForm").addEventListener("submit", function(e){
        e.preventDefault();
        alert("Merci pour votre message ! Vous pouvez l'envoyer vers votre email via backend plus tard.");
    });
});
</script>

</body>
</html>