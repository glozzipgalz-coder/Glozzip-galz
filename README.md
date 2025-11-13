<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Glozzip-galz | Luxury Lip Gloss</title>
    <!-- Maroon & Gold Luxury -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Playfair+Display:wght@700&family=Montserrat:wght@600&display=swap" rel="stylesheet">
    <style>
        :root {
            --maroon: #68151d;
            --gold: #FFD700;
            --gold-metallic: #dab04b;
            --deep-maroon: #2d0a13;
            --soft-white: #FFF8F1;
            --light-gold: #F4E4A6;
            --serif: 'Playfair Display', serif;
            --cursive: 'Dancing Script', cursive;
            --sans: 'Montserrat', sans-serif;
            --card-radius: 20px;
        }
        body {
            font-family: var(--sans);
            background: var(--maroon);
            color: var(--soft-white);
            min-height: 100vh;
            margin: 0;
        }
        header {
            width: 100%;
            background: var(--maroon);
            padding: 2rem 0 1.3rem 0;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
        }
        .logo-img {
            width: 110px;
            height: 110px;
            border-radius: 50%;
            background: var(--gold-metallic);
            display: block;
            margin: 0 auto 0.5rem auto;
            box-shadow: 0 4px 36px var(--deep-maroon);
            object-fit: contain;
        }
        .logo-title {
            font-family: var(--cursive);
            font-size: 2.75rem;
            color: var(--gold);
            text-align: center;
            margin-bottom: 0.4rem;
            font-weight: 700;
            text-shadow: 0 2px 22px var(--gold);
            letter-spacing: 1.5px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.4em;
        }
        .crown {
            color: var(--gold);
            font-size: 1.5em;
        }
        nav {
            margin-top: 0.8rem;
            text-align: center;
        }
        nav ul {
            list-style: none;
            display: flex;
            gap: 2em;
            justify-content: center;
            padding: 0;
        }
        nav ul li a {
            color: var(--soft-white);
            font-size: 1.13rem;
            text-decoration: none;
            padding: 0.2em 1em 0.1em 1em;
            border-radius: 20px;
            font-family: var(--serif);
            font-weight: bold;
            transition: background 0.27s, color 0.27s;
        }
        nav ul li a:hover {
            background: var(--gold-metallic);
            color: var(--deep-maroon);
        }
        /* Cart floating top right */
        .cart-container {
            position: fixed;
            top: 24px;
            right: 34px;
            z-index: 1050;
        }
        .cart-btn {
            background: var(--gold);
            color: var(--deep-maroon);
            border: none;
            border-radius: 50%;
            width: 60px;
            height: 60px;
            font-size: 2rem;
            box-shadow: 0 6px 32px var(--deep-maroon);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            cursor: pointer;
            transition: box-shadow 0.25s, background 0.25s;
        }
        .cart-btn:hover {
            background: var(--gold-metallic);
            box-shadow: 0 10px 40px var(--gold);
        }
        .cart-count {
            position: absolute;
            top: 8px;
            right: 13px;
            background: var(--deep-maroon);
            color: var(--gold);
            border-radius: 50%;
            width: 24px;
            height: 24px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1.03rem;
            border: 2px solid var(--gold);
            box-shadow: 0 2px 10px var(--maroon);
        }
        /* Cart Modal Panel */
        .cart-modal-bg {
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(104, 21, 29, 0.9);
            z-index: 1100;
            display: none;
            align-items: flex-end;
            justify-content: flex-end;
        }
        .cart-modal-bg.open {
            display: flex;
        }
        .cart-modal {
            background: var(--soft-white);
            color: var(--deep-maroon);
            border-top-left-radius: var(--card-radius);
            border-bottom-left-radius: var(--card-radius);
            box-shadow: -6px 0 40px var(--deep-maroon);
            width: 350px;
            max-width: 95vw;
            padding: 2.2rem 2rem 1.1rem 2rem;
            position: relative;
            height: auto;
            max-height: 90vh;
            overflow-y: auto;
            animation: cartSlideIn 0.35s cubic-bezier(.72,.01,.29,.99);
        }
        @keyframes cartSlideIn {
            from { transform: translateX(100%); opacity: 0;}
            to { transform: translateX(0); opacity: 1;}
        }
        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.2rem;
        }
        .cart-title {
            font-family: var(--serif);
            font-size: 1.45rem;
            color: var(--gold-metallic);
        }
        .cart-close {
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--deep-maroon);
            cursor: pointer;
            transition: color 0.2s;
        }
        .cart-close:hover { color: var(--gold-metallic); }
        .cart-items {
            margin-bottom: 1rem;
        }
        .cart-item {
            border-bottom: 1px solid var(--maroon);
            padding: 0.7rem 0;
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
        }
        .item-details {
            flex: 1;
        }
        .item-name {
            font-weight: bold;
            color: var(--maroon);
            font-family: var(--serif);
            font-size: 1.07rem;
        }
        .item-price {
            color: var(--gold-metallic);
            font-size: 1.02rem;
            font-weight: bold;
        }
        .quantity-controls {
            display: flex;
            align-items: center;
            margin-top: 4px;
        }
        .quantity-btn {
            background: var(--light-gold);
            border: none;
            color: var(--deep-maroon);
            width: 25px;
            height: 25px;
            border-radius: 50%;
            font-weight: bold;
            font-size: 1.07rem;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            margin-right: 2px;
            margin-left: 2px;
            transition: background 0.22s;
        }
        .quantity-btn:hover {
            background: var(--gold-metallic);
        }
        .remove-item {
            background: none;
            border: none;
            color: var(--maroon);
            cursor: pointer;
            margin-left: 10px;
            font-size: 1.13rem;
        }
        .remove-item:hover { color: var(--gold-metallic);}
        .item-total {
            padding-top: 8px;
            color: var(--gold);
            font-weight: bold;
            font-size: 1.07rem;
        }
        .cart-summary {
            margin-top: 1.2rem;
            border-top: 1px solid var(--maroon);
            padding-top: 1rem;
        }
        .cart-total {
            font-size: 1.25rem;
            font-weight: bold;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: var(--gold-metallic);
        }
        .cart-saved {
            color: var(--deep-maroon);
            font-weight: bold;
            font-size: 1.09rem;
            margin-top: 9px;
            padding-bottom: 8px;
        }
        .cart-checkout {
            display: block;
            width: 100%;
            background: linear-gradient(100deg, var(--gold) 0%, var(--gold-metallic) 100%);
            color: var(--deep-maroon);
            font-family: var(--serif);
            font-size: 1.17rem;
            font-weight: bold;
            padding: 15px 0;
            border-radius: 30px;
            border: none;
            margin-top: 1rem;
            cursor: pointer;
            box-shadow: 0 4px 20px var(--gold-metallic);
            transition: background 0.2s, box-shadow 0.2s;
        }
        .cart-checkout:hover {
            background: var(--gold-metallic);
            box-shadow: 0 6px 26px var(--gold);
        }
        .cart-empty {
            text-align: center;
            color: var(--maroon);
            margin: 2.3rem 0;
            font-size: 1.17rem;
        }
        .cart-clear {
            background: none;
            border: none;
            color: var(--maroon);
            margin-top: 0.8rem;
            cursor: pointer;
            font-size: 1rem;
            float: right;
            transition: color 0.2s;
        }
        .cart-clear:hover { color: var(--gold-metallic);}
        /* Checkout notification overlay */
        .order-notif-bg {
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            width: 100vw; height: 100vh;
            background: rgba(104, 21, 29, 0.93);
            z-index: 1600;
            display: none;
            align-items: center;
            justify-content: center;
        }
        .order-notif-bg.show { display: flex; }
        .order-notif-modal {
            background: var(--soft-white);
            color: var(--maroon);
            border-radius: var(--card-radius);
            padding: 3.7rem 2rem 2.3rem 2rem;
            box-shadow: 0 8px 40px var(--deep-maroon);
            text-align: center;
            min-width: 310px;
            max-width: 97vw;
            border: 2px solid var(--gold-metallic);
            position: relative;
        }
        .order-notif-modal .noti-icon {
            font-size: 2.7rem;
            color: var(--gold);
            margin-bottom: 1.3rem;
        }
        .order-notif-modal .noti-header {
            font-family: var(--cursive);
            font-size: 2.18rem;
            font-weight: bold;
            color: var(--gold);
            margin-bottom: 0.7rem;
        }
        .order-notif-modal .noti-desc {
            font-size: 1.18rem;
            color: var(--maroon);
            font-family: var(--serif);
            margin-bottom: 1.4rem;
        }
        .order-notif-modal .notif-dismiss {
            margin-top: 1.2rem;
            background: var(--gold);
            color: var(--maroon);
            border-radius: 25px;
            border: none;
            padding: 12px 25px;
            font-weight: bold;
            font-family: var(--serif);
            font-size: 1.03rem;
            cursor: pointer;
            box-shadow: 0 2px 10px var(--gold);
            transition: background 0.2s;
        }
        .order-notif-modal .notif-dismiss:hover {
            background: var(--gold-metallic);
        }
        /* Product section (Showcase) */
        main {
            width: 94%;
            max-width: 1200px;
            margin: 0 auto 3rem auto;
        }
        .products-title {
            color: var(--gold);
            font-family: var(--cursive);
            font-size: 2.3rem;
            text-align: center;
            margin-top: 2.7rem;
            margin-bottom: 1.3rem;
            letter-spacing: 1px;
        }
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2.2rem;
            margin-bottom: 3rem;
        }
        .product-card {
            background: var(--deep-maroon);
            border-radius: var(--card-radius);
            padding: 2rem 1.2rem 1.6rem 1.2rem;
            text-align: center;
            box-shadow: 0 2px 28px var(--maroon);
            color: var(--gold);
            border: 2px solid var(--gold-metallic);
            position: relative;
            transition: transform 0.2s, box-shadow 0.2s;
        }
        .product-card.best-seller {
            box-shadow: 0 6px 36px var(--gold);
            border: 2.5px solid var(--gold);
        }
        .product-img {
            width: 130px;
            height: 130px;
            object-fit: cover;
            border-radius: 16px;
            margin-bottom: 1.1rem;
            box-shadow: 0 2px 18px var(--gold-metallic);
        }
        .product-title {
            font-family: var(--serif);
            font-size: 1.17rem;
            color: var(--light-gold);
            margin-bottom: 0.7rem;
        }
        .product-price {
            color: var(--gold);
            font-weight: bold;
            font-size: 1.1rem;
            margin-bottom: 0.4rem;
        }
        .product-save {
            color: var(--gold-metallic);
            font-size: 1rem;
            margin-bottom: 0.45rem;
        }
        .add-to-cart-btn {
            background: linear-gradient(100deg, var(--gold) 0%, var(--gold-metallic) 100%);
            color: var(--deep-maroon);
            font-weight: bold;
            font-family: var(--serif);
            border: none;
            border-radius: 24px;
            padding: 11px 26px;
            font-size: 1.08rem;
            margin-top: 10px;
            cursor: pointer;
            box-shadow: 0 2px 8px var(--gold-metallic);
            transition: background 0.2s;
        }
        .add-to-cart-btn:hover {
            background: var(--gold-metallic);
            color: var(--maroon);
        }
        /* Sparkle animation */
        @keyframes sparkle {
            0% { opacity: 0; transform: scale(0) rotate(0deg);}
            51% { opacity: 1; transform: scale(1.2) rotate(180deg);}
            100% { opacity: 0; transform: scale(0) rotate(360deg);}
        }
        .sparkle {
            position: fixed;
            pointer-events: none;
            z-index: 2200;
            border-radius: 50%;
            animation: sparkle 1.6s linear;
        }
        /* Responsive */
        @media (max-width: 860px) {
            .products-grid {grid-template-columns: 1fr;}
            .cart-modal {width: 96vw;}
            .cart-container { top: 16px; right: 10px;}
        }
    </style>
</head>
<body>
    <header>
        <img src="logo.png" alt="Glozzip-galz Logo" class="logo-img">
        <div class="logo-title">
            <span class="crown"><i class="fas fa-crown"></i></span>
            Glozzip-galz
        </div>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#best">Best Seller</a></li>
                <li><a href="#shades">Shades</a></li>
                <li><a href="#bundles">Bundles</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>
    <!-- Floating Cart Icon -->
    <div class="cart-container">
        <button class="cart-btn" id="open-cart"><i class="fas fa-shopping-bag"></i>
            <div class="cart-count" id="cart-count">0</div>
        </button>
    </div>

    <!-- Products Showcase -->
    <main>
        <div class="products-title" id="best">👑 Best Seller Shade</div>
        <div class="products-grid">
            <!-- #04 Rebel Glow BEST SELLER -->
            <div class="product-card best-seller">
                <img src="https://images.unsplash.com/photo-1513364776144-60967b0f800f?auto=format&fit=crop&w=400&q=80" alt="Rebel Glow" class="product-img">
                <div class="product-title">#04 Rebel Glow</div>
                <div class="product-price">₱99</div>
                <div class="product-save">Most loved. Signature warm shimmer.</div>
                <button class="add-to-cart-btn"
                    data-id="4" data-name="#04 Rebel Glow"
                    data-price="99"
                    data-save="0"
                    >Add to Cart</button>
            </div>
        </div>
        <div class="products-title" id="shades">Shades</div>
        <div class="products-grid">
            <!-- #01 Satin Spark -->
            <div class="product-card">
                <img src="https://images.unsplash.com/photo-1517486808906-6ca8b3f04846?auto=format&fit=crop&w=400&q=80" alt="Satin Spark" class="product-img">
                <div class="product-title">#01 Satin Spark</div>
                <div class="product-price">₱99</div>
                <div class="product-save">Soft champagne gold.</div>
                <button class="add-to-cart-btn"
                    data-id="1" data-name="#01 Satin Spark"
                    data-price="99"
                    data-save="0"
                    >Add to Cart</button>
            </div>
            <!-- #02 Golden Aura -->
            <div class="product-card">
                <img src="https://images.unsplash.com/photo-1517841905240-472988babdf9?auto=format&fit=crop&w=400&q=80" alt="Golden Aura" class="product-img">
                <div class="product-title">#02 Golden Aura</div>
                <div class="product-price">₱99</div>
                <div class="product-save">Radiant golden bronze.</div>
                <button class="add-to-cart-btn"
                    data-id="2" data-name="#02 Golden Aura"
                    data-price="99"
                    data-save="0"
                    >Add to Cart</button>
            </div>
            <!-- #03 Midnight Muse -->
            <div class="product-card">
                <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=400&q=80" alt="Midnight Muse" class="product-img">
                <div class="product-title">#03 Midnight Muse</div>
                <div class="product-price">₱99</div>
                <div class="product-save">Deep plum shimmer.</div>
                <button class="add-to-cart-btn"
                    data-id="3" data-name="#03 Midnight Muse"
                    data-price="99"
                    data-save="0"
                    >Add to Cart</button>
            </div>
            <!-- #05 Strawberry Drip -->
            <div class="product-card">
                <img src="https://images.unsplash.com/photo-1465101162946-4377e57745c3?auto=format&fit=crop&w=400&q=80" alt="Strawberry Drip" class="product-img">
                <div class="product-title">#05 Strawberry Drip</div>
                <div class="product-price">₱99</div>
                <div class="product-save">Playful pink with sparkle.</div>
                <button class="add-to-cart-btn"
                    data-id="5" data-name="#05 Strawberry Drip"
                    data-price="99"
                    data-save="0"
                    >Add to Cart</button>
            </div>
        </div>
        <div class="products-title" id="bundles">Bundles & Deals</div>
        <div class="products-grid">
            <!-- Buy 2 Bundle -->
            <div class="product-card">
                <img src="https://images.unsplash.com/photo-1517486808906-6ca8b3f04846?auto=format&fit=crop&w=400&q=80" class="product-img" alt="Buy 2 Bundle">
                <div class="product-title">Buy 2 Bundle</div>
                <div class="product-price">
                    <span style="text-decoration:line-through;color:#dab04b;">₱198</span> ₱188
                </div>
                <div class="product-save">Save ₱10! Include any 2 shades</div>
                <button class="add-to-cart-btn"
                    data-id="b2" data-name="Buy 2 Bundle"
                    data-price="188"
                    data-save="10"
                    >Add to Cart</button>
            </div>
            <!-- Buy 3 Bundle -->
            <div class="product-card">
                <img src="https://images.unsplash.com/photo-1513364776144-60967b0f800f?auto=format&fit=crop&w=400&q=80" class="product-img" alt="Buy 3 Bundle">
                <div class="product-title">Buy 3 Bundle</div>
                <div class="product-price">
                    <span style="text-decoration:line-through;color:#dab04b;">₱297</span> ₱277
                </div>
                <div class="product-save">Save ₱20! Include any 3 shades</div>
                <button class="add-to-cart-btn"
                    data-id="b3" data-name="Buy 3 Bundle"
                    data-price="277"
                    data-save="20"
                    >Add to Cart</button>
            </div>
        </div>
    </main>

    <!-- Cart Modal Background & Panel -->
    <div class="cart-modal-bg" id="cart-modal-bg">
        <div class="cart-modal" id="cart-modal">
            <div class="cart-header">
                <div class="cart-title">Your Cart</div>
                <button class="cart-close" id="close-cart">&times;</button>
            </div>
            <div class="cart-items" id="cart-items"></div>
            <div class="cart-summary" id="cart-summary"></div>
            <button class="cart-checkout" id="cart-checkout">Checkout</button>
            <button class="cart-clear" id="cart-clear">Clear Cart</button>
        </div>
    </div>
    <!-- Order Notification Modal -->
    <div class="order-notif-bg" id="order-notif-bg">
        <div class="order-notif-modal">
            <div class="noti-icon"><i class="fas fa-gift"></i></div>
            <div class="noti-header">Thank You for your Order!</div>
            <div class="noti-desc">
                Your luxury lip gloss order is on its way.<br>
                You'll shine like royalty! 👑
            </div>
            <button class="notif-dismiss" id="notif-dismiss">Close</button>
        </div>
    </div>
    <!-- Sparkle effect -->
    <script>
        function makeSparkle() {
            const sparkle = document.createElement('div');
            sparkle.className = 'sparkle';
            const size = Math.random() * 10 + 5;
            sparkle.style.width = ${size}px;
            sparkle.style.height = ${size}px;
            sparkle.style.background = ['#FFD700','#dab04b','#F4E4A6'][Math.floor(Math.random()*3)];
            sparkle.style.left = ${Math.random()*100}vw;
            sparkle.style.top = ${Math.random()*100}vh;
            document.body.appendChild(sparkle);
            setTimeout(() => sparkle.remove(), 1750);
        }
        setInterval(makeSparkle, 310);
        for(let i=0;i<17;i++) setTimeout(makeSparkle, i*130);

        // Shopping Cart Logic
        let cart = [];
        let cartTotal = 0;
        let cartSaved = 0;
        const cartCount = document.getElementById('cart-count');
        const cartModalBg = document.getElementById('cart-modal-bg');
        const cartModal = document.getElementById('cart-modal');
        const cartItemsDiv = document.getElementById('cart-items');
        const cartSummaryDiv = document.getElementById('cart-summary');
        // Open Cart
        document.getElementById('open-cart').onclick = () => {
            cartModalBg.classList.add('open');
            renderCart();
        };
        // Close Cart by button
        document.getElementById('close-cart').onclick = () => {
            cartModalBg.classList.remove('open');
        };
        // Cart Close by clicking BG
        cartModalBg.onclick = function(e) {
            if(e.target === cartModalBg) cartModalBg.classList.remove('open');
        }
        // Add to Cart buttons
        document.querySelectorAll('.add-to-cart-btn').forEach(btn => {
            btn.onclick = () => {
                const id = btn.getAttribute('data-id');
                const name = btn.getAttribute('data-name');
                const price = parseInt(btn.getAttribute('data-price'));
                const save = parseInt(btn.getAttribute('data-save'));
                let found = cart.find(it=>it.id===id);
                if(found) {
                    found.qty += 1;
                } else {
                    cart.push({id, name, price, qty:1, save});
                }
                flashCartIcon();
                renderCart();
            };
        });
        function flashCartIcon() {
            cartCount.style.background = "#FFD700";
            cartCount.style.color = "#2d0a13";
            setTimeout(()=>{cartCount.style.background = "#2d0a13";cartCount.style.color="#FFD700";},280);
        }
        function renderCart() {
            if(cart.length==0) {
                cartItemsDiv.innerHTML = <div class="cart-empty">Cart is empty.</div>;
                cartSummaryDiv.innerHTML = '';
                cartCount.innerText = '0';
                return;
            }
            cartItemsDiv.innerHTML = '';
            cartTotal = 0; cartSaved = 0;
            cartCount.innerText = cart.reduce((acc,it)=>acc+it.qty,0);
            cart.forEach((item,idx) => {
                const itemTotal = item.price * item.qty;
                cartTotal += itemTotal;
                cartSaved += item.save * item.qty;
                const el = document.createElement('div');
                el.className = 'cart-item';
                el.innerHTML = `
                    <div class="item-details">
                        <div class="item-name">${item.name}</div>
                        <div class="item-price">₱${item.price}</div>
                        <div class="quantity-controls">
                            <button class="quantity-btn minus" data-idx="${idx}">-</button>
                            <span class="quantity">${item.qty}</span>
                            <button class="quantity-btn plus" data-idx="${idx}">+</button>
                            <button class="remove-item" data-idx="${idx}"><i class="fas fa-trash"></i></button>
                        </div>
                    </div>
                    <div class="item-total">₱${itemTotal}</div>
                `;
                cartItemsDiv.appendChild(el);
            });
            // Quantity minus/plus
            cartModal.querySelectorAll('.quantity-btn.minus').forEach(btn=>{
                btn.onclick = ()=> {
                    const idx = parseInt(btn.getAttribute('data-idx'));
                    if(cart[idx].qty>1) { cart[idx].qty--; renderCart();}
                };
            });
            cartModal.querySelectorAll('.quantity-btn.plus').forEach(btn=>{
                btn.onclick = ()=> {
                    const idx = parseInt(btn.getAttribute('data-idx'));
                    cart[idx].qty++; renderCart();
                };
            });
            cartModal.querySelectorAll('.remove-item').forEach(btn=>{
                btn.onclick = ()=> {
                    const idx = parseInt(btn.getAttribute('data-idx'));
                    cart.splice(idx,1); renderCart();
                }
            });
            let summary = '';
            summary += <div class="cart-total"><span>Total:</span><span>₱${cartTotal}</span></div>;
            if(cartSaved>0) summary += <div class="cart-saved">You saved ₱${cartSaved}!</div>;
            cartSummaryDiv.innerHTML = summary;
        }
        // Checkout
        document.getElementById('cart-checkout').onclick = () => {
            if(cart.length===0) return;
            cartModalBg.classList.remove('open');
            document.getElementById('order-notif-bg').classList.add('show');
        }
        // Dismiss Notification (button and background)
        document.getElementById('notif-dismiss').onclick = () => {
            document.getElementById('order-notif-bg').classList.remove('show');
            cart = [];
            renderCart();
        }
        document.getElementById('order-notif-bg').onclick = function(e) {
            if(e.target === this) {
                this.classList.remove('show');
                cart = [];
                renderCart();
            }
        }
        // Clear cart
        document.getElementById('cart-clear').onclick = () => {
            cart = [];
            renderCart();
        };
    </script>
</body>
</html>
