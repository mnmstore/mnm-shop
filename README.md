<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>MNM | Midnight Muse</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Georgia', serif; background-color: #0a0a1a; color: #e0e0e0; scroll-behavior: smooth; }
        nav { display: flex; justify-content: space-between; align-items: center; padding: 1rem 5%; background: #0a0a1a; border-bottom: 1px solid #2a2a3a; flex-wrap: wrap; }
        .logo-text { font-size: 1.5rem; font-weight: bold; color: #c9a03d; }
        .nav-links { display: flex; gap: 1.2rem; align-items: center; }
        .nav-links a { color: #e0e0e0; text-decoration: none; }
        .cart-icon { position: relative; }
        .cart-count { background: #c9a03d; color: #0a0a1a; border-radius: 50%; padding: 2px 6px; font-size: 11px; position: absolute; top: -10px; right: -15px; }
        section { padding: 3rem 5%; }
        .hero { min-height: 50vh; background: linear-gradient(rgba(10,10,26,0.7), rgba(10,10,26,0.9)); display: flex; align-items: center; justify-content: center; text-align: center; }
        .hero-content h1 { font-size: 2.5rem; letter-spacing: 4px; }
        .section-title { text-align: center; font-size: 2rem; margin-bottom: 2rem; color: #c9a03d; }
        .product-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 2rem; max-width: 1400px; margin: 0 auto; }
        .product-card { background: #111122; border-radius: 12px; padding: 1.5rem; text-align: center; border: 1px solid #2a2a3a; }
        .main-image { width: 100%; height: 280px; object-fit: cover; border-radius: 12px; background: #1a1a2e; }
        .product-title { font-size: 1.3rem; font-weight: bold; margin: 1rem 0 0.5rem; }
        .product-price { color: #c9a03d; font-size: 1.3rem; margin-bottom: 1rem; }
        .design-swatches { display: flex; gap: 15px; justify-content: center; margin: 1rem 0; flex-wrap: wrap; }
        .design-swatch { text-align: center; cursor: pointer; }
        .design-swatch img { width: 60px; height: 60px; object-fit: cover; border-radius: 12px; border: 2px solid #2a2a3a; transition: 0.2s; }
        .design-swatch.active img { border-color: #c9a03d; box-shadow: 0 0 8px #c9a03d; }
        .design-swatch span { display: block; font-size: 0.7rem; margin-top: 5px; color: #888; }
        .size-select { width: 100%; padding: 0.8rem; background: #1a1a2e; border: 1px solid #2a2a3a; color: #e0e0e0; border-radius: 8px; margin: 0.5rem 0; }
        .add-to-cart { width: 100%; padding: 0.8rem; background: #c9a03d; color: #0a0a1a; border: none; font-weight: bold; cursor: pointer; border-radius: 8px; }
        .add-to-cart:hover { background: #b88a2c; }
        .about, .newsletter { background: #111122; text-align: center; max-width: 800px; margin: 2rem auto; padding: 2rem; border-radius: 12px; }
        .newsletter input { padding: 0.8rem; width: 70%; background: #1a1a2e; border: 1px solid #2a2a3a; color: #e0e0e0; border-radius: 8px; }
        .newsletter button { padding: 0.8rem 1.5rem; background: #c9a03d; border: none; cursor: pointer; border-radius: 8px; }
        footer { text-align: center; padding: 2rem; border-top: 1px solid #2a2a3a; color: #666; }
        
        /* Back to Top Button */
        .back-to-top {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #c9a03d;
            color: #0a0a1a;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 1.5rem;
            border: none;
            opacity: 0;
            visibility: hidden;
            transition: 0.3s;
            z-index: 1000;
        }
        .back-to-top.show { opacity: 1; visibility: visible; }
        .back-to-top:hover { background: #b88a2c; }
        
        @media (max-width: 768px) { .hero-content h1 { font-size: 1.8rem; } .design-swatch img { width: 50px; height: 50px; } }
    </style>
</head>
<body>

<nav>
    <div class="logo">
        <img src="https://i.imgur.com/us79u6t.png" alt="MNM Logo" style="height: 50px; width: auto; border-radius: 8px;">
    </div>
    <div class="nav-links">
        <a href="#home">Home</a>
        <a href="#shop">Shop</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
		  <a href="dashboard.html">Dashboard</a>
        <a href="cart.html" class="cart-icon">🛒 <span id="cart-counter" class="cart-count">0</span></a>
    </div>
</nav>

<section id="home" class="hero">
    <div class="hero-content">
        <h1>MIDNIGHT MUSE</h1>
        <p>Inspirations from the Night</p>
        <a href="#shop" style="display:inline-block; background:#c9a03d; color:#0a0a1a; padding:0.8rem 2rem; border-radius:8px; margin-top:1rem; text-decoration:none;">Shop Now</a>
    </div>
</section>

<section id="shop">
    <h2 class="section-title">The Collection</h2>
    <div class="product-grid" id="product-grid"></div>
</section>

<section id="about" class="about">
    <h2 class="section-title">About MNM</h2>
    <p>Midnight Muse was born from the belief that true style is inspired — not dictated. It's for anyone who finds confidence in quiet hours, draws creativity from the night, and wears their personality as effortlessly as their favorite piece.</p>
    <p style="margin-top:1rem"><em>— Inspirations from the Night —</em></p>
</section>

<section id="contact" class="newsletter">
    <h3>Join the Night</h3>
    <p>Be the first to know about new drops.</p>
    <input type="email" id="newsletter-email" placeholder="Your email address">
    <br><br>
    <button onclick="subscribeNewsletter()">Subscribe</button>
</section>

<footer>
    <p>© 2026 Midnight Muse — Inspirations from the Night</p>
    <p>📍 Accra, Ghana | ✉️ hello@midnightmuse.com</p>
</footer>

<!-- Back to Top Button -->
<button class="back-to-top" id="backToTopBtn" onclick="scrollToTop()">↑</button>

<script>
    // ==================== PRODUCT DATA ====================
    const products = [
        { id: 1, name: "Midnight Jersey", basePrice: 300, sizes: ["S","M","L","XL","XXL"],
          designs: [
            { name: "Black", image: "https://i.imgur.com/yea89Hm.jpeg", swatch: "https://i.imgur.com/yea89Hm.jpeg" },
            { name: "White Hockey", image: "https://i.imgur.com/iigAx2V.png", swatch: "https://i.imgur.com/iigAx2V.png" },
            { name: "Black Hockey", image: "https://i.imgur.com/Wqswtwz.png", swatch: "https://i.imgur.com/Wqswtwz.png" }
          ]},
        { id: 2, name: "Muse Tee", basePrice: 150, sizes: ["S","M","L","XL","XXL"],
          designs: [
            { name: "Black", image: "https://i.imgur.com/BOo1eTG.jpeg", swatch: "https://i.imgur.com/BOo1eTG.jpeg" },
				{ name: "Cream", image:"https://i.imgur.com/Pf7Idqa.jpeg", swatch: "https://i.imgur.com/Pf7Idqa.jpeg" },
            { name: "Red-Wine", image: "https://i.imgur.com/a9dzW8H.jpeg", swatch: "https://i.imgur.com/a9dzW8H.jpeg" },
            { name: "Green", image: "https://i.imgur.com/zNLr0wO.jpeg", swatch: "https://i.imgur.com/zNLr0wO.jpeg" }
          ]},
        { id: 3, name: "Midnight Cap", basePrice: 150, sizes: ["One Size"],
          designs: [
            { name: "White", image: "https://i.imgur.com/OaXnqgU.png", swatch: "https://i.imgur.com/OaXnqgU.png" },
            { name: "Navy", image: "https://i.imgur.com/tKAHqZd.png", swatch: "https://i.imgur.com/tKAHqZd.png" },  
            { name: "Black", image: "https://i.imgur.com/YtGxhhW.png", swatch: "https://i.imgur.com/YtGxhhW.png" }
          ]},
        { id: 4, name: "Midnight Hoodie", basePrice: 350, sizes: ["S","M","L","XL","XXL"],
          designs: [
            { name: "White", image: "https://i.imgur.com/c1F2F0a.png", swatch: "https://i.imgur.com/c1F2F0a.png" },
            { name: "Red-Wine", image: "https://i.imgur.com/RJJ0dqg.png", swatch: "https://i.imgur.com/RJJ0dqg.png" }
          ]}
    ];

    // ==================== CART ====================
    let cart = JSON.parse(localStorage.getItem('cart')) || [];
    let selectedDesigns = {};

    function saveCart() { localStorage.setItem('cart', JSON.stringify(cart)); updateCartDisplay(); }
    function updateCartDisplay() { const total = cart.reduce((s,i)=>s+i.quantity,0); document.getElementById('cart-counter').innerText = total; }

    function addToCart(product, designName, size) {
        const itemName = `${product.name} - ${designName}`;
        const existing = cart.find(i => i.id === product.id && i.design === designName && i.size === size);
        if(existing) existing.quantity++;
        else cart.push({ id: product.id, name: itemName, price: product.basePrice, design: designName, size: size, quantity: 1, image: product.designs.find(d=>d.name===designName)?.image });
        saveCart();
        alert(`✓ ${itemName} (${size}) added to cart`);
    }

    function subscribeNewsletter() { let e=document.getElementById('newsletter-email').value; alert(e&&e.includes('@')?'Thanks for subscribing!':'Valid email please'); }

    // ==================== SCROLL TO TOP ====================
    window.onscroll = function() {
        const btn = document.getElementById('backToTopBtn');
        if (document.body.scrollTop > 200 || document.documentElement.scrollTop > 200) {
            btn.classList.add('show');
        } else {
            btn.classList.remove('show');
        }
    };
    function scrollToTop() { window.scrollTo({ top: 0, behavior: 'smooth' }); }

    // ==================== RENDER ====================
    function renderProducts() {
        const grid = document.getElementById('product-grid');
        grid.innerHTML = '';
        products.forEach(p => {
            const defaultDesign = p.designs[0];
            let swatchesHtml = '';
            p.designs.forEach(d => { swatchesHtml += `<div class="design-swatch" onclick="selectDesign(${p.id},'${d.name}','${d.image}')"><img src="${d.swatch}" onerror="this.src='https://placehold.co/60x60/1a1a2e/c9a03d?text=${d.name.charAt(0)}'"><span>${d.name}</span></div>`; });
            let sizesHtml = p.sizes.map(s => `<option value="${s}">${s}</option>`).join('');
            grid.innerHTML += `
                <div class="product-card" data-product-id="${p.id}">
                    <img src="${defaultDesign.image}" class="main-image" id="main-img-${p.id}">
                    <div class="product-title">${p.name}</div>
                    <div class="product-price">₵${p.basePrice}</div>
                    <div class="design-swatches" id="swatches-${p.id}">${swatchesHtml}</div>
                    <select class="size-select" id="size-${p.id}">${sizesHtml}</select>
                    <button class="add-to-cart" onclick="addToCart(products.find(pr=>pr.id===${p.id}), getSelectedDesign(${p.id}), document.getElementById('size-${p.id}').value)">Add to Cart</button>
                </div>
            `;
        });
    }

    function selectDesign(productId, designName, imageUrl) {
        selectedDesigns[productId] = designName;
        document.getElementById(`main-img-${productId}`).src = imageUrl;
        const swatches = document.querySelectorAll(`.product-card[data-product-id="${productId}"] .design-swatch`);
        swatches.forEach(s => { if(s.innerText.includes(designName)) s.classList.add('active'); else s.classList.remove('active'); });
    }
    function getSelectedDesign(productId) { return selectedDesigns[productId] || products.find(p=>p.id===productId)?.designs[0]?.name; }

    renderProducts();
    updateCartDisplay();
</script>
</body>
</html>