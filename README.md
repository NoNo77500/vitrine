<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>L'Atelier Pixel</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
:root{
  --accent:#E4405F;
  --nav-bg:#000;
  --nav-sep:#444;
  --max-w:1100px;
}
*{box-sizing:border-box;}
body{
  margin:0;
  font-family:"Poppins",sans-serif;
  color:#222;
  background:#fff;
}
nav{
  background:var(--nav-bg);
  display:flex;
  justify-content:center;
  align-items:center;
  position:relative;
  padding:10px 20px;
  box-shadow:0 2px 6px rgba(0,0,0,0.06);
}
.logo-left{
  position:absolute;
  left:20px;
  color:#fff;
  font-weight:700;
  font-size:18px;
  text-decoration:none;
}
.nav-links{
  display:flex;
  gap:16px;
  align-items:center;
}
.nav-links a{
  color:#fff;
  text-decoration:none;
  padding:10px 14px;
  font-weight:600;
  position:relative;
  border-radius:6px;
}
.nav-links a:not(:last-child)::after{
  content:"";
  position:absolute;
  right:-8px;
  top:50%;
  transform:translateY(-50%);
  width:1px;
  height:22px;
  background:var(--nav-sep);
}
.nav-links a:hover{color:var(--accent); background:rgba(255,255,255,0.02);}
.nav-links a.active-link{color:var(--accent);}
.section{
  display:none;
  padding:60px 20px;
  max-width:var(--max-w);
  margin:auto;
  opacity:0;
  transform:translateY(8px);
  transition:opacity .35s, transform .35s;
}
.section.active{display:block; opacity:1; transform:none;}
h1,h2{color:var(--accent);}
p{line-height:1.6; margin-bottom:14px;}
.btn{
  display:inline-block;
  background:var(--nav-bg);
  color:#fff;
  border:none;
  padding:10px 18px;
  border-radius:24px;
  cursor:pointer;
  font-weight:700;
  text-decoration:none;
  transition:background .25s, transform .12s;
}
.btn:hover{background:var(--accent); transform:translateY(-2px);}
.grid{
  display:grid;
  gap:18px;
  grid-template-columns:repeat(auto-fill,minmax(230px,1fr));
  margin-top:18px;
}
.card{
  background:#fff;
  border-radius:10px;
  border:1px solid #eee;
  padding:12px;
  box-shadow:0 6px 18px rgba(0,0,0,0.04);
  display:flex;
  flex-direction:column;
  gap:12px;
}
.card img{width:100%; height:150px; object-fit:cover; border-radius:8px; transition:transform .25s;}
.card img:hover{transform:scale(1.04);}
.card h3{margin:0; font-size:18px;}
.card .price{font-weight:700;}
.card .actions{margin-top:auto; display:flex; justify-content:flex-end;}
.gallery{
  display:grid;
  grid-template-columns:repeat(auto-fill,minmax(160px,1fr));
  gap:12px;
}
.gallery img{width:100%; height:110px; object-fit:cover; border-radius:8px; transition:transform .2s;}
.gallery img:hover{transform:scale(1.05);}
.contact-info{ display:flex; flex-direction:column; gap:10px; align-items:center; font-size:16px; }
.contact-info a{text-decoration:none; color:var(--accent); font-weight:700;}
.contact-icons{display:flex; gap:12px; margin-top:8px;}
.contact-icons a{font-size:20px; text-decoration:none; color:inherit;}
a.insta{color:#E4405F;} a.fb{color:#1877F2;} a.tk{color:#000;}
footer{background:#000; color:#fff; text-align:center; padding:18px 12px; margin-top:30px;}
/* overlay produit */
#overlay{
  position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.8); display:none;
  justify-content:center; align-items:center; z-index:9999;
}
#overlay .overlay-content{
  background:#fff; border-radius:10px; padding:24px; max-width:600px; width:90%; text-align:center; position:relative;
}
#overlay .overlay-content img{width:100%; max-width:400px; border-radius:8px; margin-bottom:12px;}
#overlay .close-overlay{position:absolute; top:12px; right:12px; cursor:pointer; font-size:22px; font-weight:bold;}
/* ACCUEIL centré */
#accueil .hero{
  display:flex; flex-direction:column; justify-content:center; align-items:center; min-height:60vh; text-align:center; gap:16px;
}
</style>
</head>
<body>

<nav>
  <a class="logo-left">L'Atelier Pixel</a>
  <div class="nav-links">
    <a data-section="accueil" onclick="showSection('accueil')">Accueil</a>
    <a data-section="apropos" onclick="showSection('apropos')">À propos</a>
    <a data-section="produits" onclick="showSection('produits')">Produits</a>
    <a data-section="galerie" onclick="showSection('galerie')">Galerie</a>
    <a data-section="contact" onclick="showSection('contact')">Contact</a>
  </div>
</nav>

<section id="accueil" class="section active">
  <div class="hero">
    <img src="https://via.placeholder.com/200x200?text=Logo" alt="Logo boutique" style="border-radius:12px;">
    <h1>Bienvenue à L'Atelier Pixel</h1>
    <p>Votre boutique geek préférée, remplie de gadgets et objets de collection uniques !</p>
    <button class="btn" onclick="showSection('produits')">Découvrir nos produits</button>
  </div>
</section>

<section id="apropos" class="section">
  <h2>À propos</h2>
  <p>L’Atelier Pixel est une boutique passionnée, née en 2020 pour rassembler les amoureux de la culture geek, du rétro-gaming et des univers créatifs.</p>
</section>

<section id="produits" class="section">
  <h2>Produits</h2>
  <div class="grid">
    <div class="card">
      <img src="https://via.placeholder.com/300x200?text=Figurine+Pixel">
      <h3>Figurine Pixel</h3>
      <div class="price">19,99€</div>
      <div class="actions"><button class="btn" onclick="showOverlay(1)">Voir plus</button></div>
    </div>
    <div class="card">
      <img src="https://via.placeholder.com/300x200?text=Tasse+Geek">
      <h3>Tasse Geek</h3>
      <div class="price">12,50€</div>
      <div class="actions"><button class="btn" onclick="showOverlay(2)">Voir plus</button></div>
    </div>
    <div class="card">
      <img src="https://via.placeholder.com/300x200?text=Lampe+LED+Pixel">
      <h3>Lampe LED Pixel</h3>
      <div class="price">34,99€</div>
      <div class="actions"><button class="btn" onclick="showOverlay(3)">Voir plus</button></div>
    </div>
  </div>
</section>

<section id="galerie" class="section">
  <h2>Galerie</h2>
  <div class="gallery">
    <img src="https://via.placeholder.com/200x150?text=Boutique">
    <img src="https://via.placeholder.com/200x150?text=Equipe">
    <img src="https://via.placeholder.com/200x150?text=Clients">
    <img src="https://via.placeholder.com/200x150?text=Evenement">
  </div>
</section>

<section id="contact" class="section">
  <h2>Contact</h2>
  <div class="contact-info">
    <p>Téléphone : <a href="tel:+33123456789">+33 1 23 45 67 89</a></p>
    <p>Email : <a href="mailto:contact@atelierpixel.fr">contact@atelierpixel.fr</a></p>
    <div class="contact-icons">
      <a class="insta" href="#"><i class="fab fa-instagram"></i></a>
      <a class="fb" href="#"><i class="fab fa-facebook"></i></a>
      <a class="tk" href="#"><i class="fab fa-tiktok"></i></a>
    </div>
  </div>
  <iframe 
    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2624.999231513216!2d2.2922926156747756!3d48.85837307928781!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47e66fdf02a2f1b3%3A0x4216b604ddf2b30!2sTour%20Eiffel!5e0!3m2!1sfr!2sfr!4v1680100000000!5m2!1sfr!2sfr" 
    width="100%" height="300" style="border:0;border-radius:8px;margin-top:10px;" allowfullscreen="" loading="lazy">
  </iframe>
</section>

<footer>
  © 2025 L'Atelier Pixel — Tous droits réservés
</footer>

<div id="overlay">
  <div class="overlay-content">
    <span class="close-overlay" onclick="closeOverlay()">×</span>
    <img id="ov-img" src="">
    <h2 id="ov-name"></h2>
    <div class="price" id="ov-price"></div>
    <p id="ov-desc"></p>
    <button class="btn" onclick="closeOverlay()">Retour aux produits</button>
  </div>
</div>

<script>
const products = {
  1:{name:"Figurine Pixel", price:"19,99€", img:"https://via.placeholder.com/400x300?text=Figurine+Pixel", desc:"Une superbe figurine inspirée du style pixel art, parfaite pour les fans de jeux rétro."},
  2:{name:"Tasse Geek", price:"12,50€", img:"https://via.placeholder.com/400x300?text=Tasse+Geek", desc:"Tasse céramique geek 330ml, va au micro-ondes et lave-vaisselle."},
  3:{name:"Lampe LED Pixel", price:"34,99€", img:"https://via.placeholder.com/400x300?text=Lampe+LED+Pixel", desc:"Lampe LED modulable, contrôle tactile, ambiance gaming ou cosy."}
};

function showSection(id){
  document.querySelectorAll('.section').forEach(s=>s.classList.toggle('active', s.id===id));
  document.querySelectorAll('.nav-links a').forEach(a=>a.classList.toggle('active-link', a.dataset.section===id));
  window.scrollTo({top:0, behavior:'smooth'});
}

function showOverlay(id){
  const p = products[id];
  document.getElementById('ov-img').src=p.img;
  document.getElementById('ov-name').textContent=p.name;
  document.getElementById('ov-price').textContent=p.price;
  document.getElementById('ov-desc').textContent=p.desc;
  document.getElementById('overlay').style.display='flex';
}

function closeOverlay(){document.getElementById('overlay').style.display='none';}

document.addEventListener('DOMContentLoaded', ()=>{
  const hash = location.hash.replace('#','');
  if(hash && document.getElementById(hash)) showSection(hash);
  else showSection('accueil');
});
</script>
</body>
</html>
