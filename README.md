<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>The Village Diner — Menu & Info</title>
  <style>
    /* --- Base & layout --- */
    :root{
      --red:#b33a3a;
      --cream:#fffaf0;
      --muted:#666;
      --card:#fff;
      --glass: rgba(255,255,255,0.6);
    }
    *{box-sizing:border-box}
    html{scroll-behavior:smooth}
    body{margin:0;font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, Arial;color:#222;background:var(--cream);-webkit-font-smoothing:antialiased}
    a{color:inherit}
    .container{max-width:1100px;margin:0 auto;padding:16px}

    /* --- Header --- */
    header.site-header{background:linear-gradient(180deg,var(--red),#9b2b2b);color:#fff;padding:18px 0;position:sticky;top:0;z-index:50;box-shadow:0 4px 14px rgba(0,0,0,0.08)}
    .header-inner{display:flex;gap:12px;align-items:center;justify-content:space-between;max-width:1100px;margin:0 auto;padding:0 16px}
    .brand{font-weight:700;font-size:1.25rem}
    .tag{font-size:.95rem;opacity:.95}
    .cta-group{display:flex;gap:8px;align-items:center}
    .btn{background:var(--glass);backdrop-filter: blur(4px);border-radius:10px;padding:8px 12px;color:#111;text-decoration:none;font-weight:600;border:1px solid rgba(0,0,0,0.06)}
    .btn.accent{background:var(--red);color:#fff;border:none}
    .nav-links{display:flex;gap:10px}
    .nav-links a{color:rgba(255,255,255,0.95);text-decoration:none;font-weight:600;padding:6px 8px;border-radius:8px}
    .nav-links a:hover{background:rgba(255,255,255,0.06)}

    /* --- Hero --- */
    .hero{background:linear-gradient(180deg, rgba(0,0,0,0.05), rgba(0,0,0,0.02));padding:28px 0;text-align:center}
    .hero h1{margin:0;font-size:clamp(1.6rem,3.2vw,2.6rem);color:#111}
    .hero p{margin:.6rem 0 0;color:var(--muted)}

    /* --- Main grid --- */
    main{padding:20px 16px}
    .grid{display:grid;grid-template-columns:1fr 360px;gap:20px;max-width:1100px;margin:0 auto}
    @media (max-width:980px){ .grid{grid-template-columns:1fr} }

    .card{background:var(--card);border-radius:12px;padding:16px;box-shadow:0 10px 30px rgba(10,10,10,0.06)}
    .section-title{margin:0 0 10px;color:var(--red);font-size:1.05rem;border-bottom:3px solid #f6dede;padding-bottom:8px}

    /* --- Menu styles --- */
    .menu-category{margin-bottom:18px;opacity:0;transform:translateY(8px);transition:all .45s ease}
    .menu-category.visible{opacity:1;transform:none}
    .menu-category h3{margin:0 0 8px;font-size:1.02rem}
    .menu-item{display:flex;justify-content:space-between;padding:8px 0;border-bottom:1px dashed #eee}
    .menu-item .meta{display:block;color:var(--muted);font-size:.92rem;margin-top:4px}
    @media (max-width:600px){
      .menu-item{flex-direction:column;align-items:flex-start;gap:6px}
      .cta-group{display:none} /* keep header compact on small screens */
    }

    /* --- Hours / map right column --- */
    .hours-table td{padding:6px 0}
    .map-wrap{height:260px;border-radius:8px;overflow:hidden;background:#eee}
    .map-fallback{text-align:center;margin-top:8px}

    /* --- Footer --- */
    footer{padding:14px 0;background:var(--red);color:#fff;text-align:center;margin-top:28px}

    /* small helpers */
    .muted{color:var(--muted)}
    .note{font-size:.93rem;color:var(--muted);margin-top:10px}
  </style>
</head>
<body>
  <header class="site-header" role="banner">
    <div class="header-inner">
      <div>
        <div class="brand">The Village Diner</div>
        <div class="tag muted">Homey diner — cinnamon-bun pancakes & classic comfort</div>
      </div>

      <div style="display:flex;align-items:center;gap:12px">
        <nav class="nav-links" aria-label="Primary navigation">
          <a href="#menu">Menu</a>
          <a href="#hours">Hours</a>
          <a href="#contact">Contact</a>
        </nav>

        <div class="cta-group">
          <a class="btn" href="tel:+12158869656" aria-label="Call The Village Diner">Call</a>
          <a class="btn" href="https://www.google.com/maps/search/?api=1&query=299+Keswick+Ave+Glenside+PA+19038" target="_blank" rel="noopener" aria-label="Get directions">Get directions</a>
          <a class="btn accent" href="#menu">View menu</a>
        </div>
      </div>
    </div>
  </header>

  <section class="hero" aria-hidden="false">
    <div class="container">
      <h1>The Village Diner</h1>
      <p>299 Keswick Ave, Glenside, PA 19038 • (215) 886-9656 • Open daily 8 AM–2 PM</p>
    </div>
  </section>

  <main>
    <div class="grid container">
      <!-- LEFT: menu -->
      <div>
        <section class="card" id="about">
          <h2 class="section-title">About</h2>
          <p class="muted">Family-friendly diner serving breakfast & lunch classics with generous portions and friendly service.</p>
        </section>

        <section class="card" id="menu" style="margin-top:16px">
          <h2 class="section-title">Menu</h2>

          <!-- ALL CATEGORIES (transcribed from images) -->
          <!-- Each .menu-category will fade in when scrolled into view -->
          <div class="menu-category" id="breakfast-mains">
            <h3>BREAKFAST MAINS</h3>
            <div class="menu-item"><div><strong>Two Eggs (any style)</strong><div class="meta">Served with homefries, grits or sliced tomatoes and your choice of toast.</div></div><div>$8.50</div></div>
            <div class="menu-item"><div><strong>Shortstack Buttermilk Pancakes</strong><div class="meta">Two buttermilk pancakes served with butter.</div></div><div>$7.25</div></div>
            <div class="menu-item"><div><strong>Texas French Toast</strong><div class="meta">Two thick slices of Texas French toast served with butter and powdered sugar.</div></div><div>$7.50</div></div>
            <div class="menu-item"><div><strong>Belgian Waffle</strong><div class="meta">Served with butter, powdered sugar and whipped cream upon request.</div></div><div>$7.25</div></div>
          </div>

          <div class="menu-category" id="breakfast-specials">
            <h3>BREAKFAST SPECIALS</h3>
            <div class="menu-item"><div><strong>The Village Sampler</strong><div class="meta">Selection of pancakes, eggs & breakfast meats.</div></div><div>$12.50</div></div>
            <div class="menu-item"><div><strong>Biscuits & Gravy</strong></div><div>$9.25</div></div>
            <div class="menu-item"><div><strong>Village Breakfast Scramble</strong></div><div>$10.50</div></div>
            <div class="menu-item"><div><strong>Specialty Pancakes</strong><div class="meta">Daily varieties — ask your server.</div></div><div>Varies</div></div>
          </div>

          <div class="menu-category" id="omelettes">
            <h3>OMELETTES</h3>
            <div class="menu-item"><div><strong>Tomatoes Omelette</strong><div class="meta">Tomatoes, mushrooms, peppers, onions, spinach & cheese.</div></div><div>$11.25</div></div>
            <div class="menu-item"><div><strong>Denver Omelette</strong><div class="meta">Ham, peppers & onions.</div></div><div>$11.25</div></div>
            <div class="menu-item"><div><strong>Chicken Fajita Omelette</strong><div class="meta">Shredded chicken, peppers, onions & cheddar. Served with sour cream & salsa.</div></div><div>$11.25</div></div>
          </div>

          <div class="menu-category" id="egg-platters">
            <h3>EGG PLATTERS</h3>
            <div class="menu-item"><div><strong>Jumbo Breakfast Sandwich</strong></div><div>$7.25</div></div>
            <div class="menu-item"><div><strong>Breakfast Wrap</strong></div><div>$7.50</div></div>
          </div>

          <div class="menu-category" id="pancakes-waffles">
            <h3>PANCAKES & WAFFLES</h3>
            <div class="menu-item"><div><strong>Cinnamon-bun Pancakes</strong><div class="meta">House specialty — cinnamon bun flavor folded into pancakes.</div></div><div>$8.99</div></div>
            <div class="menu-item"><div><strong>Shortstack / Full Stack</strong><div class="meta">Ask your server for portions.</div></div><div>See server</div></div>
          </div>

          <div class="menu-category" id="sides">
            <h3>SIDES</h3>
            <div class="menu-item"><div><strong>Homefries</strong></div><div>$3.25</div></div>
            <div class="menu-item"><div><strong>Bacon (3 pcs)</strong></div><div>$3.25</div></div>
            <div class="menu-item"><div><strong>Sausage (links or patty)</strong></div><div>$3.25</div></div>
          </div>

          <div class="menu-category" id="kids">
            <h3>KID'S BREAKFAST</h3>
            <div class="menu-item"><div><strong>Pancake & Bacon</strong></div><div>$5.50</div></div>
            <div class="menu-item"><div><strong>Scrambled Eggs & Toast</strong></div><div>$5.25</div></div>
          </div>

          <div class="menu-category" id="burgers-lunch">
            <h3>BURGERS</h3>
            <div class="menu-item"><div><strong>Burger</strong></div><div>$8.25</div></div>
            <div class="menu-item"><div><strong>Cheeseburger</strong></div><div>$9.25</div></div>
            <div class="menu-item"><div><strong>Bacon Cheeseburger</strong></div><div>$10.75</div></div>

            <h3 style="margin-top:12px">WRAPS</h3>
            <div class="menu-item"><div><strong>Chicken Finger Wrap</strong></div><div>$10.25</div></div>
            <div class="menu-item"><div><strong>Chicken Parmesan Wrap</strong></div><div>$10.75</div></div>

            <h3 style="margin-top:12px">STEAK SANDWICHES</h3>
            <div class="menu-item"><div><strong>Plain Steak</strong></div><div>$8.25</div></div>
            <div class="menu-item"><div><strong>Cheesesteak</strong></div><div>$9.00</div></div>
            <div class="menu-item"><div><strong>Chicken Cheesesteak</strong></div><div>$10.25</div></div>
          </div>

          <div class="menu-category" id="apps-soup">
            <h3>APPETIZERS & SOUP</h3>
            <div class="menu-item"><div><strong>Soup of the Day (Cup)</strong></div><div>$4.00</div></div>
            <div class="menu-item"><div><strong>Soup of the Day (Bowl)</strong></div><div>$5.00</div></div>
            <div class="note">Consuming raw or undercooked meats, poultry, seafood, shellfish or eggs may increase your risk of food-borne illness.</div>
          </div>

          <div class="menu-category" id="desserts">
            <h3>DESSERTS & FOUNTAIN</h3>
            <div class="menu-item"><div><strong>Ice Cream Sundae</strong></div><div>$4.25</div></div>
            <div class="menu-item"><div><strong>Chocolate Fountain Drinks</strong><div class="meta">Shakes & floats — ask server.</div></div><div>Varies</div></div>
          </div>

          <div class="menu-category" id="drinks">
            <h3>BEVERAGES</h3>
            <div class="menu-item"><div><strong>Coffee</strong></div><div>$3.25</div></div>
            <div class="menu-item"><div><strong>Tea</strong></div><div>$3.00</div></div>
            <div class="menu-item"><div><strong>Hot Chocolate</strong></div><div>$3.00</div></div>
            <div class="menu-item"><div><strong>Juice</strong></div><div>$3.25</div></div>
            <div class="menu-item"><div><strong>Milk</strong></div><div>$3.75</div></div>
            <div class="menu-item"><div><strong>Lemonade</strong></div><div>$3.75</div></div>
            <div class="menu-item"><div><strong>Fountain Soda</strong></div><div>$2.00</div></div>
          </div>

          <div class="note" style="margin-top:12px">NOTE: Menu transcribed from photos. If you spot any typos or missing items, tell me which line and I’ll update the site immediately.</div>
        </section>
      </div>

      <!-- RIGHT: hours & map -->
      <aside>
        <div class="card" id="hours">
          <h2 class="section-title">Hours</h2>
          <table class="hours-table" aria-label="Hours">
            <tr><td>Saturday</td><td style="text-align:right">8 AM – 2 PM</td></tr>
            <tr><td>Sunday</td><td style="text-align:right">8 AM – 2 PM</td></tr>
            <tr><td>Monday</td><td style="text-align:right">8 AM – 2 PM</td></tr>
            <tr><td>Tuesday</td><td style="text-align:right">8 AM – 2 PM</td></tr>
            <tr><td>Wednesday</td><td style="text-align:right">8 AM – 2 PM</td></tr>
            <tr><td>Thursday</td><td style="text-align:right">8 AM – 2 PM</td></tr>
            <tr><td>Friday</td><td style="text-align:right">8 AM – 2 PM</td></tr>
          </table>
        </div>

        <div class="card" style="margin-top:16px" id="contact">
          <h2 class="section-title">Location</h2>
          <p style="margin:6px 0"><strong>299 Keswick Ave</strong><br>Glenside, PA 19038</p>
          <div class="map-wrap" aria-hidden="false">
            <iframe title="The Village Diner map" src="https://www.google.com/maps?q=299+Keswick+Ave,+Glenside,+PA+19038&output=embed" width="100%" height="100%" style="border:0" loading="lazy" referrerpolicy="no-referrer-when-downgrade" allowfullscreen></iframe>
          </div>
          <div class="map-fallback" style="margin-top:8px;text-align:center">
            <a href="https://www.google.com/maps/search/?api=1&query=299+Keswick+Ave+Glenside+PA+19038" target="_blank" rel="noopener">Open in Google Maps</a>
          </div>
        </div>
      </aside>
    </div>
  </main>

  <footer>
    © <span id="year"></span> The Village Diner • (215) 886-9656
  </footer>

  <script>
    // Set year
    document.getElementById('year').textContent = new Date().getFullYear();

    // Small intersection observer to fade-in menu categories
    const obs = new IntersectionObserver((entries) => {
      entries.forEach(e => {
        if (e.isIntersecting) e.target.classList.add('visible');
      });
    }, {threshold: 0.08});

    document.querySelectorAll('.menu-category').forEach(el => obs.observe(el));

    // Smooth scroll offset fix for sticky header when linking (optional)
    // If user clicks an anchor, offset a bit so section title isn't hidden under header
    const headerHeight = document.querySelector('.site-header').offsetHeight;
    document.querySelectorAll('a[href^="#"]').forEach(a => {
      a.addEventListener('click', (ev) => {
        const href = a.getAttribute('href');
        if (!href || href === '#') return;
        const target = document.querySelector(href);
        if (target) {
          ev.preventDefault();
          const top = target.getBoundingClientRect().top + window.pageYOffset - headerHeight - 12;
          window.scrollTo({top, behavior:'smooth'});
        }
      });
    });
  </script>
</body>
</html>
