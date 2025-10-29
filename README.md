# totiecouille.github.io
<h1>Mes projets web</h1>

<ul>
  <li><a href="https://eliotoffredo.github.io/poisson/" target="_blank">Site de vente de poisson</a></li>
  <li><a href="https://eliotoffredo.github.io/voiture/" target="_blank">Site d’import de voitures US</a></li>
  <li><a href="https://monsite.wordpress.com/" target="_blank">Site WordPress Démo</a></li>
</ul>
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>US Auto Import — Showroom 🇺🇸</title>
  <meta name="description" content="One‑page showroom : annonces détaillées, services, process, avis, contact. Images libres de droits intégrées.">
  <link href="https://fonts.googleapis.com/css2?family=Oswald:wght@400;600;700&family=Inter:wght@400;600&display=swap" rel="stylesheet">
  <style>
    :root{
      --blue:#0c1f3c;
      --red:#e11d2e;
      --bg:#0a0f18;         /* Ambiance showroom sombre */
      --bg-soft:#0f1624;    /* Cartes */
      --bg-elev:#121a2a;    /* Surfaces élevées */
      --ink:#e5eaf1;        /* Texte principal */
      --muted:#9aa6b2;      /* Texte second. */
      --accent:#ffd166;     /* Doré lumineux */
      --glow:0 0 0 rgba(0,0,0,0);
      --radius:16px;
      --shadow:0 16px 40px rgba(0,0,0,.35);
      --line:1px solid rgba(255,255,255,.08);
    }
    *{box-sizing:border-box}
    html,body{margin:0;padding:0;background:var(--bg);color:var(--ink);font-family:Inter,system-ui,Arial,sans-serif}
    a{color:inherit;text-decoration:none}
    img{max-width:100%;display:block}
    .container{width:min(1200px,92%);margin:0 auto}

    /* Header / Nav */
    header{position:sticky;top:0;z-index:20;background:linear-gradient(90deg,#0b1426,#12254a);border-bottom:var(--line);backdrop-filter:saturate(1.2) blur(6px)}
    .nav{display:flex;justify-content:space-between;align-items:center;padding:14px 0}
    .brand{display:flex;gap:12px;align-items:center}
    .flag{width:42px;height:28px;border-radius:6px;background:linear-gradient(90deg,#b22234 0 20%,#fff 20% 30%,#b22234 30% 40%,#fff 40% 50%,#b22234 50% 60%,#fff 60% 70%,#b22234 70% 80%,#fff 80% 90%,#b22234 90% 100%);position:relative;box-shadow:var(--shadow)}
    .flag:before{content:"";position:absolute;left:0;top:0;width:42%;height:60%;background:#3c3b6e;border-top-left-radius:6px}
    .brand b{font-family:Oswald,Impact,Inter,sans-serif;letter-spacing:.5px;font-size:20px}
    nav.actions{display:flex;gap:14px;flex-wrap:wrap}
    .btn{padding:10px 16px;border-radius:999px;border:1px solid rgba(255,255,255,.18);color:#fff;transition:.2s ease;font-weight:600;background:transparent}
    .btn:hover{transform:translateY(-2px);box-shadow:0 8px 20px rgba(0,0,0,.35)}
    .btn-cta{background:var(--red);border-color:var(--red)}

    /* Hero */
    .hero{position:relative;overflow:hidden}
    .hero::before{content:"";position:absolute;inset:0;background:radial-gradient(1200px 500px at 50% 10%,rgba(255,255,255,.15),transparent 60%),linear-gradient(180deg,rgba(6,10,18,.1),rgba(6,10,18,.85));z-index:1}
    .hero-bg{height:60vh;min-height:420px;background:url('https://images.unsplash.com/photo-1525609004556-c46c7d6cf023?q=80&w=1920&auto=format&fit=crop') center/cover no-repeat;filter:saturate(1.05) contrast(1.05)}
    .hero-inner{position:absolute;inset:0;z-index:2;display:grid;place-items:center}
    .hero-content{text-align:center;color:#fff;padding:20px}
    .hero h1{font-family:Oswald,Impact,sans-serif;font-size:clamp(36px,6vw,64px);margin:0 0 8px;text-transform:uppercase;letter-spacing:1px;text-shadow:0 6px 30px rgba(0,0,0,.6)}
    .hero p{max-width:900px;margin:0 auto 16px;color:#d7deea}
    .ribbons{display:flex;gap:10px;flex-wrap:wrap;justify-content:center}
    .rib{background:rgba(10,15,24,.6);padding:8px 12px;border:var(--line);border-radius:999px;color:#d7deea}

    /* Sections */
    .section{padding:72px 0}
    .section h2{font-family:Oswald,Impact,sans-serif;color:#dfe7f4;font-size:clamp(24px,3.5vw,36px);margin:0 0 8px;text-transform:uppercase;letter-spacing:.5px}
    .sub{color:var(--muted);margin-bottom:28px}

    /* Modèles phares */
    .grid{display:grid;grid-template-columns:repeat(4,1fr);gap:18px}
    .card{background:linear-gradient(180deg,var(--bg-soft),var(--bg-elev));border:var(--line);border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow);transition:.25s ease}
    .card:hover{transform:translateY(-6px);box-shadow:0 24px 60px rgba(0,0,0,.5)}
    .p-body{padding:14px}
    .p-head{display:flex;justify-content:space-between;align-items:center;gap:12px}
    .p-title{font-weight:700}
    .badge{display:inline-flex;align-items:center;gap:6px;font-size:12px;padding:6px 8px;border-radius:999px;border:var(--line);color:#c6cfda;background:rgba(255,255,255,.03)}
    .price{font-weight:800;color:var(--accent)}

    /* Annonces détaillées */
    #annonces .grid{grid-template-columns:repeat(2,1fr)}
    .listing{background:linear-gradient(180deg,var(--bg-soft),var(--bg-elev));border:var(--line);border-radius:18px;overflow:hidden;box-shadow:var(--shadow)}
    .listing .media{position:relative}
    .listing .media img{height:320px;width:100%;object-fit:cover}
    .thumbs{display:flex;gap:8px;padding:10px;background:rgba(255,255,255,.03);border-top:var(--line);flex-wrap:wrap}
    .thumbs img{width:96px;height:64px;object-fit:cover;border-radius:8px;border:var(--line);opacity:.9;cursor:pointer}
    .thumbs img:hover{opacity:1;outline:2px solid var(--red)}
    .l-body{padding:16px}
    .specs{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin:10px 0 14px}
    .spec{background:rgba(255,255,255,.03);border:var(--line);border-radius:10px;padding:10px;font-size:13px;color:#cfd6e3}
    .features{display:flex;flex-wrap:wrap;gap:8px;margin:8px 0}
    .chip{font-size:12px;padding:6px 8px;border-radius:999px;border:var(--line);background:rgba(255,255,255,.03);color:#cfd6e3}
    .cta-row{display:flex;gap:10px;margin-top:10px}
    .btn-red{background:var(--red);color:#fff;border:none}
    .btn-outline{background:transparent;color:#e5eaf1;border:2px solid #2b3f68}

    /* Services & Process */
    .features-3{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
    .feat{background:linear-gradient(180deg,var(--bg-soft),var(--bg-elev));border:var(--line);border-radius:16px;padding:18px}
    .steps{display:grid;grid-template-columns:repeat(4,1fr);gap:14px}
    .step{background:#0b1426;color:#e5eaf1;border-radius:14px;padding:18px;border:1px solid #1f2f54}
    .step h4{margin:0 0 6px}

    /* Avis */
    .reviews{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
    .review{background:linear-gradient(180deg,var(--bg-soft),var(--bg-elev));border:var(--line);border-radius:16px;padding:18px;color:#dfe7f4}
    .stars{color:#ffcc00}

    /* Contact */
    form.contact{max-width:640px;margin:0 auto;background:linear-gradient(180deg,var(--bg-soft),var(--bg-elev));padding:20px;border-radius:16px;box-shadow:var(--shadow);border:var(--line)}
    input,textarea{width:100%;padding:12px;border-radius:10px;border:1px solid #24324f;background:#0b1426;color:#dfe7f4}
    textarea{min-height:110px}

    /* Footer */
    footer{border-top:var(--line);background:#090f19;color:#c8d0da;padding:30px 0}

    /* Responsive */
    @media (max-width: 1100px){.grid{grid-template-columns:repeat(3,1fr)}#annonces .grid{grid-template-columns:1fr}}
    @media (max-width: 680px){.grid{grid-template-columns:1fr}.features-3,.reviews,.steps{grid-template-columns:1fr}.specs{grid-template-columns:repeat(2,1fr)}}
  </style>
</head>
<body>

  <!-- NAV -->
  <header>
    <div class="container nav">
      <div class="brand">
        <div class="flag" aria-hidden="true"></div>
        <div>
          <b>US Auto Import</b><br>
          <small style="opacity:.8">Showroom & Import de véhicules 🇺🇸</small>
        </div>
      </div>
      <nav class="actions">
        <a class="btn" href="#modeles">Modèles</a>
        <a class="btn" href="#annonces">Annonces</a>
        <a class="btn" href="#services">Services</a>
        <a class="btn" href="#process">Process</a>
        <a class="btn btn-cta" href="#contact">Devis</a>
      </nav>
    </div>
  </header>

  <!-- HERO (showroom) -->
  <section class="hero">
    <div class="hero-bg"></div>
    <div class="hero-inner">
      <div class="hero-content">
        <h1>Showroom américain — prêt à rouler</h1>
        <p>Import clé en main : sourcing, expertise, transport maritime, douanes, homologation et livraison en France. Ambiance <em>muscle cars</em> & routes US.</p>
        <div class="ribbons">
          <span class="rib">🔍 Sélection sur mesure</span>
          <span class="rib">🚢 Transport & assurance</span>
          <span class="rib">📄 DREAL / UTAC</span>
          <span class="rib">🧰 Garantie & entretien</span>
        </div>
      </div>
    </div>
  </section>

  <!-- MODELES PHARES -->
  <section id="modeles" class="section">
    <div class="container">
      <h2>Modèles phares</h2>
      <p class="sub">Visuels libres de droits (Unsplash) — parfaits pour une démo</p>
      <div class="grid">
        <article class="card">
          <img src="https://images.unsplash.com/photo-1502877338535-766e1452684a?q=80&w=1600&auto=format&fit=crop" alt="Ford Mustang" onerror="this.onerror=null;this.src=window.CAR_PLACEHOLDER;">
          <div class="p-body">
            <div class="p-head"><div class="p-title">Ford Mustang GT</div><div class="price">45 900 €</div></div>
            <div class="features"><span class="badge">V8 5.0L</span><span class="badge">450 ch</span><span class="badge">RWD</span></div>
          </div>
        </article>
        <article class="card">
          <img src="https://images.unsplash.com/photo-1590362891991-f776e747a588?q=80&w=1600&auto=format&fit=crop" alt="Dodge Challenger" onerror="this.onerror=null;this.src=window.CAR_PLACEHOLDER;">
          <div class="p-body">
            <div class="p-head"><div class="p-title">Dodge Challenger R/T</div><div class="price">52 300 €</div></div>
            <div class="features"><span class="badge">V8 HEMI 5.7</span><span class="badge">Auto</span><span class="badge">Échapp. Sport</span></div>
          </div>
        </article>
        <article class="card">
          <img src="https://images.unsplash.com/photo-1619767886558-efdc259cde1b?q=80&w=1600&auto=format&fit=crop" alt="Chevrolet Corvette C8" onerror="this.onerror=null;this.src=window.CAR_PLACEHOLDER;">
          <div class="p-body">
            <div class="p-head"><div class="p-title">Chevrolet Corvette C8</div><div class="price">94 800 €</div></div>
            <div class="features"><span class="badge">V8 6.2</span><span class="badge">495 ch</span><span class="badge">MC MR</span></div>
          </div>
        </article>
        <article class="card">
          <img src="https://images.unsplash.com/photo-1619840698470-5bbd9a19a3a5?q=80&w=1600&auto=format&fit=crop" alt="RAM 1500" onerror="this.onerror=null;this.src=window.CAR_PLACEHOLDER;">
          <div class="p-body">
            <div class="p-head"><div class="p-title">RAM 1500 Laramie</div><div class="price">62 900 €</div></div>
            <div class="features"><span class="badge">V8 5.7</span><span class="badge">4x4</span><span class="badge">Crew Cab</span></div>
          </div>
        </article>
      </div>
    </div>
  </section>

  <!-- ANNONCES DETAILLEES (8) -->
  <section id="annonces" class="section">
    <div class="container">
      <h2>Annonces détaillées</h2>
      <p class="sub">Fiches avec 1 visuel principal + 2 vignettes (cliquables)</p>
      <div class="grid">
        <!-- Listing 1: Mustang -->
        <article class="listing">
          <div class="media">
            <img id="main-1" src="https://images.unsplash.com/photo-1519624070599-49ac05dd2b0d?q=80&w=1600&auto=format&fit=crop" alt="Mustang 2019">
            <div class="thumbs" data-target="main-1">
              <img src="https://images.unsplash.com/photo-1541447271390-1613b0f57118?q=80&w=600&auto=format&fit=crop" alt="Mustang latéral">
              <img src="https://images.unsplash.com/photo-1555215695-3004980ad54e?q=80&w=600&auto=format&fit=crop" alt="Mustang intérieur">
            </div>
          </div>
          <div class="l-body">
            <h3 style="margin:0">Ford Mustang GT Fastback — 2019</h3>
            <div class="specs">
              <div class="spec">⛽ V8 5.0L — 450 ch</div>
              <div class="spec">⚙️ Boîte manuelle 6</div>
              <div class="spec">📍 Californie (Carfax)</div>
              <div class="spec">🛣️ 38 500 km</div>
              <div class="spec">VIN 1FA6P8CF…</div>
              <div class="spec">🇫🇷 Homologation incluse</div>
            </div>
            <div class="features"><span class="chip">Pack Performance</span><span class="chip">Échappement actif</span><span class="chip">Apple CarPlay</span><span class="chip">Camera recul</span></div>
            <div class="p-head"><div class="price">49 900 €</div></div>
            <div class="cta-row"><a class="btn btn-red" href="#contact">Demander ce véhicule</a><a class="btn btn-outline" href="#services">Voir le process</a></div>
          </div>
        </article>
        <!-- Listing 2: Challenger -->
        <article class="listing">
          <div class="media">
            <img id="main-2" src="https://images.unsplash.com/photo-1619767886558-efdc259cde1b?q=80&w=1600&auto=format&fit=crop" alt="Challenger 2020">
            <div class="thumbs" data-target="main-2">
              <img src="https://images.unsplash.com/photo-1606666828828-0180529151ea?q=80&w=600&auto=format&fit=crop" alt="Challenger arrière">
              <img src="https://images.unsplash.com/photo-1603732551658-5f4b1b9a5f10?q=80&w=600&auto=format&fit=crop" alt="Challenger intérieur">
            </div>
          </div>
          <div class="l-body">
            <h3 style="margin:0">Dodge Challenger R/T — 2020</h3>
            <div class="specs">
              <div class="spec">⛽ V8 HEMI 5.7L</div>
              <div class="spec">⚙️ BVA 8</div>
              <div class="spec">📍 Texas</div>
              <div class="spec">🛣️ 24 100 km</div>
              <div class="spec">VIN 2C3CDZBT…</div>
              <div class="spec">🇫🇷 Homologation incluse</div>
            </div>
            <div class="features"><span class="chip">U-Connect</span><span class="chip">Sièges chauffants</span><span class="chip">Ligne inox</span><span class="chip">Jantes 20"</span></div>
            <div class="p-head"><div class="price">54 500 €</div></div>
            <div class="cta-row"><a class="btn btn-red" href="#contact">Demander ce véhicule</a><a class="btn btn-outline" href="#services">Voir le process</a></div>
          </div>
        </article>
        <!-- Listing 3: Corvette C8 -->
        <article class="listing">
          <div class="media">
            <img id="main-3" src="https://images.unsplash.com/photo-1621135802920-133df287f89f?q=80&w=1600&auto=format&fit=crop" alt="Corvette C8 2021">
            <div class="thumbs" data-target="main-3">
              <img src="https://images.unsplash.com/photo-1617493584236-10f30bd65ccb?q=80&w=600&auto=format&fit=crop" alt="Corvette avant">
              <img src="https://images.unsplash.com/photo-1619779513741-d9a73c1e4212?q=80&w=600&auto=format&fit=crop" alt="Corvette cockpit">
            </div>
          </div>
          <div class="l-body">
            <h3 style="margin:0">Chevrolet Corvette C8 — 2021</h3>
            <div class="specs">
              <div class="spec">⛽ V8 6.2L — 495 ch</div>
              <div class="spec">⚙️ DCT 8</div>
              <div class="spec">📍 Floride</div>
              <div class="spec">🛣️ 15 800 km</div>
              <div class="spec">VIN 1G1YB2D…</div>
              <div class="spec">🇫🇷 Homologation incluse</div>
            </div>
            <div class="features"><span class="chip">Z51 Pack</span><span class="chip">MagRide</span><span class="chip">BOSE</span><span class="chip">HUD</span></div>
            <div class="p-head"><div class="price">99 900 €</div></div>
            <div class="cta-row"><a class="btn btn-red" href="#contact">Demander ce véhicule</a><a class="btn btn-outline" href="#services">Voir le process</a></div>
          </div>
        </article>
        <!-- Listing 4: RAM 1500 -->
        <article class="listing">
          <div class="media">
            <img id="main-4" src="https://images.unsplash.com/photo-1623191251167-2e175ccae9b4?q=80&w=1600&auto=format&fit=crop" alt="RAM 1500 2018">
            <div class="thumbs" data-target="main-4">
              <img src="https://images.unsplash.com/photo-1618401479427-c8ef9467fd2a?q=80&w=600&auto=format&fit=crop" alt="RAM intérieur">
              <img src="https://images.unsplash.com/photo-1623191250596-c957b3b26671?q=80&w=600&auto=format&fit=crop" alt="RAM benne">
            </div>
          </div>
          <div class="l-body">
            <h3 style="margin:0">RAM 1500 Laramie — 2018</h3>
            <div class="specs">
              <div class="spec">⛽ V8 5.7L</div>
              <div class="spec">⚙️ 4x4 BVA</div>
              <div class="spec">📍 Arizona</div>
              <div class="spec">🛣️ 62 000 km</div>
              <div class="spec">VIN 1C6SRFJT…</div>
              <div class="spec">🇫🇷 Homologation incluse</div>
            </div>
            <div class="features"><span class="chip">Crew Cab</span><span class="chip">Écran 12"</span><span class="chip">Cuir ventilé</span><span class="chip">Attelage</span></div>
            <div class="p-head"><div class="price">64 900 €</div></div>
            <div class="cta-row"><a class="btn btn-red" href="#contact">Demander ce véhicule</a><a class="btn btn-outline" href="#services">Voir le process</a></div>
          </div>
        </article>
        <!-- Listing 5: Camaro SS -->
        <article class="listing">
          <div class="media">
            <img id="main-5" src="https://images.unsplash.com/photo-1549921296-3a6b3c5a8b99?q=80&w=1600&auto=format&fit=crop" alt="Camaro SS 2017">
            <div class="thumbs" data-target="main-5">
              <img src="https://images.unsplash.com/photo-1606666828156-7f7dedf86431?q=80&w=600&auto=format&fit=crop" alt="Camaro arrière">
              <img src="https://images.unsplash.com/photo-1533473359331-0135ef1b58bf?q=80&w=600&auto=format&fit=crop" alt="Camaro intérieur">
            </div>
          </div>
          <div class="l-body">
            <h3 style="margin:0">Chevrolet Camaro SS — 2017</h3>
            <div class="specs">
              <div class="spec">⛽ V8 6.2L</div>
              <div class="spec">⚙️ BVM 6</div>
              <div class="spec">📍 Nevada</div>
              <div class="spec">🛣️ 48 300 km</div>
              <div class="spec">VIN 1G1FH1R…</div>
              <div class="spec">🇫🇷 Homologation incluse</div>
            </div>
            <div class="features"><span class="chip">Recaro</span><span class="chip">Brembo</span><span class="chip">HUD</span><span class="chip">Mode Track</span></div>
            <div class="p-head"><div class="price">44 700 €</div></div>
            <div class="cta-row"><a class="btn btn-red" href="#contact">Demander ce véhicule</a><a class="btn btn-outline" href="#services">Voir le process</a></div>
          </div>
        </article>
        <!-- Listing 6: Bronco -->
        <article class="listing">
          <div class="media">
            <img id="main-6" src="https://images.unsplash.com/photo-1605558114235-13c2356eb1f3?q=80&w=1600&auto=format&fit=crop" alt="Bronco 2022">
            <div class="thumbs" data-target="main-6">
              <img src="https://images.unsplash.com/photo-1617296532108-450ab2f81b4d?q=80&w=600&auto=format&fit=crop" alt="Bronco offroad">
              <img src="https://images.unsplash.com/photo-1617814079462-2d87aea7e665?q=80&w=600&auto=format&fit=crop" alt="Bronco intérieur">
            </div>
          </div>
          <div class="l-body">
            <h3 style="margin:0">Ford Bronco Badlands — 2022</h3>
            <div class="specs">
              <div class="spec">⛽ V6 2.7L EcoBoost</div>
              <div class="spec">⚙️ 4x4 — BVA</div>
              <div class="spec">📍 Colorado</div>
              <div class="spec">🛣️ 12 600 km</div>
              <div class="spec">VIN 1FMEE5BP…</div>
              <div class="spec">🇫🇷 Homologation incluse</div>
            </div>
            <div class="features"><span class="chip">Toit amovible</span><span class="chip">Blocage diff.</span><span class="chip">Trail Assist</span><span class="chip">Écran 12"</span></div>
            <div class="p-head"><div class="price">68 900 €</div></div>
            <div class="cta-row"><a class="btn btn-red" href="#contact">Demander ce véhicule</a><a class="btn btn-outline" href="#services">Voir le process</a></div>
          </div>
        </article>
        <!-- Listing 7: Tesla Model Y -->
        <article class="listing">
          <div class="media">
            <img id="main-7" src="https://images.unsplash.com/photo-1619767886558-efdc259cde1b?q=80&w=1600&auto=format&fit=crop" alt="Tesla Model Y 2021">
            <div class="thumbs" data-target="main-7">
              <img src="https://images.unsplash.com/photo-1619767886555-efdc259cde1a?q=80&w=600&auto=format&fit=crop" alt="Model Y latéral">
              <img src="https://images.unsplash.com/photo-1549923746-c502d488b3ea?q=80&w=600&auto=format&fit=crop" alt="Model Y intérieur">
            </div>
          </div>
          <div class="l-body">
            <h3 style="margin:0">Tesla Model Y Long Range — 2021</h3>
            <div class="specs">
              <div class="spec">🔋 Dual Motor AWD</div>
              <div class="spec">⚡ Autonomie 505 km WLTP*</div>
              <div class="spec">📍 New York</div>
              <div class="spec">🛣️ 21 400 km</div>
              <div class="spec">VIN 5YJYGDE…</div>
              <div class="spec">🇫🇷 Homologation incluse</div>
            </div>
            <div class="features"><span class="chip">Autopilot</span><span class="chip">Pompe à chaleur</span><span class="chip">Toit panoramique</span><span class="chip">Sièges chauffants</span></div>
            <div class="p-head"><div class="price">48 900 €</div></div>
            <div class="cta-row"><a class="btn btn-red" href="#contact">Demander ce véhicule</a><a class="btn btn-outline" href="#services">Voir le process</a></div>
          </div>
        </article>
        <!-- Listing 8: GMC Yukon -->
        <article class="listing">
          <div class="media">
            <img id="main-8" src="https://images.unsplash.com/photo-1582015752627-3b9b1a17f3ce?q=80&w=1600&auto=format&fit=crop" alt="GMC Yukon 2019">
            <div class="thumbs" data-target="main-8">
              <img src="https://images.unsplash.com/photo-1617137968427-85924a94c820?q=80&w=600&auto=format&fit=crop" alt="Yukon 3/4 arrière">
              <img src="https://images.unsplash.com/photo-1494976388531-d1058494cdd8?q=80&w=600&auto=format&fit=crop" alt="Yukon intérieur">
            </div>
          </div>
          <div class="l-body">
            <h3 style="margin:0">GMC Yukon Denali — 2019</h3>
            <div class="specs">
              <div class="spec">⛽ V8 6.2L</div>
              <div class="spec">⚙️ BVA 10</div>
              <div class="spec">📍 Michigan</div>
              <div class="spec">🛣️ 58 200 km</div>
              <div class="spec">VIN 1GKS2DK…</div>
              <div class="spec">🇫🇷 Homologation incluse</div>
            </div>
            <div class="features"><span class="chip">7 places</span><span class="chip">Magnetic Ride</span><span class="chip">BOSE</span><span class="chip">HUD</span></div>
            <div class="p-head"><div class="price">72 400 €</div></div>
            <div class="cta-row"><a class="btn btn-red" href="#contact">Demander ce véhicule</a><a class="btn btn-outline" href="#services">Voir le process</a></div>
          </div>
        </article>
      </div>
    </div>
  </section>

  <!-- SERVICES -->
  <section id="services" class="section">
    <div class="container">
      <h2>Services</h2>
      <p class="sub">Accompagnement de A à Z — concentrez‑vous sur la conduite, on gère le reste.</p>
      <div class="features-3">
        <div class="feat"><h3>🔎 Sourcing & expertise</h3><p>Analyse historique (Carfax / Autocheck), inspection indépendante, négociation vendeur.</p></div>
        <div class="feat"><h3>🚢 Logistique & douanes</h3><p>Transport routier US, maritime, assurance, dédouanement, TVA, malus si applicable.</p></div>
        <div class="feat"><h3>📄 Homologation & immatriculation</h3><p>Mises en conformité France (feux, radio, OBD), UTAC/DREAL, carte grise définitive.</p></div>
      </div>
    </div>
  </section>

  <!-- PROCESS -->
  <section id="process" class="section" style="background:linear-gradient(180deg,#0b1426,#090f19);color:#e5eaf1">
    <div class="container">
      <h2 style="color:#fff">Process d’importation</h2>
      <p class="sub" style="color:#c9d2e3">Les 4 grandes étapes de la commande à la livraison en France.</p>
      <div class="steps">
        <div class="step"><h4>1. Sélection</h4><p>Brief, recherche annonces, vérifs historiques & inspections, offre d’achat.</p></div>
        <div class="step"><h4>2. Transport</h4><p>Enlèvement vendeur, terminal portuaire US, container / roulier, assurance.</p></div>
        <div class="step"><h4>3. Douanes</h4><p>Débarquement FR, dédouanement, TVA & droits, livraison au centre technique.</p></div>
        <div class="step"><h4>4. Homologation</h4><p>Mise en conformité, UTAC/DREAL, plaques provisoires puis carte grise.</p></div>
      </div>
    </div>
  </section>

  <!-- AVIS -->
  <section class="section" id="avis">
    <div class="container">
      <h2>Avis clients</h2>
      <p class="sub">Ce qu’ils disent de nous.</p>
      <div class="reviews">
        <div class="review"><div class="stars">★★★★★</div> « Challenger reçue conforme et homologuée — suivi au top. » — <b>Mehdi</b></div>
        <div class="review"><div class="stars">★★★★☆</div> « Transport et douanes gérés sans surprise, je recommande. » — <b>Anne</b></div>
        <div class="review"><div class="stars">★★★★★</div> « Mustang V8 introuvable en France, super sourcing. » — <b>Louis</b></div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact" class="section">
    <div class="container">
      <h2>Contact</h2>
      <p class="sub">Demandez une estimation pour votre import — réponse sous 24h ouvrées.</p>
      <form class="contact" onsubmit="event.preventDefault(); alert('Formulaire de démonstration.');">
        <label>Nom<br><input required></label><br><br>
        <label>Email<br><input type="email" required></label><br><br>
        <label>Votre projet (modèle, budget, délai)<br><textarea></textarea></label><br>
        <div class="cta-row"><button class="btn btn-red" type="submit">Envoyer</button><a class="btn btn-outline" href="#annonces">Voir les annonces</a></div>
      </form>
    </div>
  </section>

  <footer>
    <div class="container" style="display:flex;justify-content:space-between;gap:16px;flex-wrap:wrap">
      <div>© <span id="y"></span> US Auto Import — Démonstration</div>
      <div>Mentions · Conditions · RGPD</div>
    </div>
  </footer>

  <script>
    // Fallback si une image échoue
    window.CAR_PLACEHOLDER = 'data:image/svg+xml;charset=UTF-8,' + encodeURIComponent(`
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 480">
        <defs><linearGradient id="g" x1="0" x2="1"><stop offset="0" stop-color="#0b1426"/><stop offset="1" stop-color="#e11d2e"/></linearGradient></defs>
        <rect width="800" height="480" fill="url(#g)"/>
        <text x="50%" y="50%" dominant-baseline="middle" text-anchor="middle" font-size="34" font-family="Arial" fill="#ffffff">Image véhicule</text>
      </svg>`);

    // Swap d'image au clic sur les vignettes
    document.querySelectorAll('.thumbs').forEach(g => {
      const targetId = g.getAttribute('data-target');
      const main = document.getElementById(targetId);
      if(!main) return;
      g.querySelectorAll('img').forEach(thumb => {
        thumb.addEventListener('click', () => {
          const tmp = main.src;
          main.src = thumb.src;
          thumb.src = tmp;
        });
      });
    });

    document.getElementById('y').textContent = new Date().getFullYear();
  </script>
</body>
</html>
