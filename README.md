# RN-Varsha
<!doctype html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Fashion & Fragrance Store</title>
  <style>
    :root{
      --bg:#0b0b0f;
      --card:#141422;
      --card2:#10101a;
      --text:#f5f5f7;
      --muted:#b8b8c7;
      --brand:#ffb703;   /* warm gold */
      --brand2:#fb8500;  /* orange */
      --accent:#8ecae6;  /* soft blue */
      --danger:#ff4d6d;
      --ok:#00d4a6;
      --line:rgba(255,255,255,0.08);
      --shadow: 0 18px 50px rgba(0,0,0,0.45);
      --radius:22px;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial;
      background: radial-gradient(1200px 700px at 20% -10%, rgba(255,183,3,0.22), transparent 50%),
                  radial-gradient(900px 500px at 95% 20%, rgba(142,202,230,0.18), transparent 52%),
                  linear-gradient(180deg, #07070b, #0b0b10);
      color:var(--text);
    }
    a{color:inherit;text-decoration:none}
    .container{max-width:1180px;margin:0 auto;padding:18px}

    /* Header */
    header{
      position:sticky; top:0; z-index:99;
      backdrop-filter: blur(12px);
      background: rgba(11,11,15,0.72);
      border-bottom:1px solid var(--line);
    }
    .topbar{
      display:flex; align-items:center; justify-content:space-between;
      gap:12px; padding:12px 18px;
    }
    .logo{
      display:flex; align-items:center; gap:10px; font-weight:900; letter-spacing:0.2px;
    }
    .mark{
      width:38px;height:38px;border-radius:12px;
      background: linear-gradient(135deg, var(--brand), var(--brand2));
      box-shadow: 0 10px 30px rgba(251,133,0,0.35);
    }
    .search{
      flex:1; max-width:520px;
      display:flex; align-items:center; gap:10px;
      background: rgba(255,255,255,0.05);
      border:1px solid var(--line);
      padding:10px 14px; border-radius:16px;
    }
    .search input{
      width:100%; background:transparent; border:none; outline:none;
      color:var(--text); font-size:14px;
    }
    .actions{display:flex; align-items:center; gap:10px}
    .btn{
      border:none; cursor:pointer; font-weight:800;
      padding:10px 14px; border-radius:16px;
      background: rgba(255,255,255,0.06);
      color:var(--text);
      border:1px solid var(--line);
      transition:.2s;
    }
    .btn:hover{transform:translateY(-1px); background:rgba(255,255,255,0.09)}
    .btn.primary{
      background: linear-gradient(135deg, var(--brand), var(--brand2));
      border: none;
      color:#1b1300;
      box-shadow: 0 16px 40px rgba(255,183,3,0.22);
    }
    .badge{
      padding:6px 10px; border-radius:999px;
      border:1px solid rgba(255,183,3,0.35);
      color: var(--brand);
      font-weight:900;
      font-size:12px;
      background: rgba(255,183,3,0.06);
    }

    /* Hero */
    .hero{
      margin-top:18px;
      display:grid; grid-template-columns: 1.2fr 0.8fr;
      gap:16px;
    }
    .heroCard{
      border:1px solid var(--line);
      border-radius: var(--radius);
      padding:22px;
      background: linear-gradient(135deg, rgba(255,183,3,0.12), rgba(255,255,255,0.03));
      box-shadow: var(--shadow);
      overflow:hidden;
      position:relative;
      min-height:240px;
    }
    .heroCard::after{
      content:"";
      position:absolute; inset:-60px -120px auto auto;
      width:340px;height:340px;border-radius:50%;
      background: radial-gradient(circle, rgba(255,183,3,0.35), transparent 60%);
      filter: blur(2px);
      transform: rotate(10deg);
    }
    .hero h1{margin:0;font-size:38px;line-height:1.1}
    .hero p{color:var(--muted); margin:12px 0 0; max-width:520px}
    .hero .ctaRow{display:flex; gap:10px; margin-top:18px; flex-wrap:wrap}
    .miniCard{
      border:1px solid var(--line);
      border-radius: var(--radius);
      padding:18px;
      background: rgba(255,255,255,0.04);
      box-shadow: var(--shadow);
    }
    .miniCard h3{margin:0 0 8px}
    .miniCard .stat{
      display:flex; justify-content:space-between; align-items:center;
      padding:12px 12px; border-radius:16px;
      border:1px solid rgba(255,255,255,0.08);
      background: rgba(0,0,0,0.15);
      margin-top:10px;
    }
    .miniCard .stat span{color:var(--muted); font-weight:700}
    .miniCard .stat b{color:var(--brand)}

    /* Categories */
    .sectionTitle{
      display:flex; align-items:end; justify-content:space-between;
      margin:26px 0 12px;
    }
    .sectionTitle h2{margin:0;font-size:20px}
    .chips{display:flex; gap:10px; flex-wrap:wrap}
    .chip{
      padding:10px 14px;
      border-radius:999px;
      border:1px solid var(--line);
      background: rgba(255,255,255,0.04);
      color:var(--muted);
      font-weight:900;
      cursor:pointer;
      transition:.2s;
      user-select:none;
    }
    .chip.active{
      background: rgba(255,183,3,0.12);
      border-color: rgba(255,183,3,0.30);
      color: var(--brand);
    }

    /* Products */
    .grid{
      display:grid;
      grid-template-columns: repeat(4, 1fr);
      gap:14px;
      margin-bottom:40px;
    }
    .card{
      border:1px solid var(--line);
      border-radius: 22px;
      background: linear-gradient(180deg, rgba(255,255,255,0.05), rgba(255,255,255,0.02));
      box-shadow: 0 10px 28px rgba(0,0,0,0.35);
      overflow:hidden;
      transition:.2s;
      display:flex; flex-direction:column;
    }
    .card:hover{transform: translateY(-4px); border-color: rgba(255,183,3,0.18)}
    .img{
      height:160px;
      background: radial-gradient(circle at 30% 20%, rgba(255,183,3,0.18), transparent 55%),
                  radial-gradient(circle at 70% 40%, rgba(142,202,230,0.14), transparent 50%),
                  linear-gradient(135deg, rgba(255,255,255,0.06), rgba(0,0,0,0.22));
      border-bottom:1px solid var(--line);
      display:flex; align-items:center; justify-content:center;
      font-size:56px;
    }
    .pbody{padding:14px}
    .ptag{
      display:inline-flex; gap:8px; align-items:center;
      color:var(--muted); font-weight:900; font-size:12px;
      margin-bottom:8px;
    }
    .ptag i{
      width:10px;height:10px;border-radius:50%;
      background: var(--accent);
      display:inline-block;
    }
    .pname{margin:0;font-size:16px;font-weight:900}
    .pdesc{margin:8px 0 0;color:var(--muted);font-size:13px;line-height:1.4}
    .row{display:flex; align-items:center; justify-content:space-between; gap:10px; margin-top:12px}
    .price{font-size:18px;font-weight:1000; color: var(--brand)}
    .small{font-size:12px; color:var(--muted); font-weight:800}
    .btnAdd{
      width:100%;
      margin-top:12px;
      padding:11px 14px;
      border-radius:16px;
      border:none;
      cursor:pointer;
      font-weight:1000;
      background: rgba(255,183,3,0.13);
      color: var(--brand);
      border:1px solid rgba(255,183,3,0.18);
      transition:.2s;
    }
    .btnAdd:hover{background: rgba(255,183,3,0.18); transform: translateY(-1px)}

    /* Cart Drawer */
    .drawer{
      position:fixed; inset:0; pointer-events:none;
      z-index:200;
    }
    .drawer.active{pointer-events:auto}
    .overlay{
      position:absolute; inset:0;
      background: rgba(0,0,0,0.55);
      opacity:0; transition:.25s;
    }
    .drawer.active .overlay{opacity:1}
    .panel{
      position:absolute; top:0; right:0;
      height:100%;
      width: 380px;
      max-width: 92vw;
      background: rgba(12,12,18,0.96);
      border-left:1px solid var(--line);
      transform: translateX(110%);
      transition:.25s;
      padding:16px;
      display:flex; flex-direction:column;
      gap:12px;
    }
    .drawer.active .panel{transform:translateX(0)}
    .panelHeader{display:flex; align-items:center; justify-content:space-between}
    .panelHeader h3{margin:0;font-size:18px}
    .cartList{flex:1; overflow:auto; padding-right:6px}
    .cartItem{
      border:1px solid var(--line);
      border-radius:18px;
      padding:12px;
      background: rgba(255,255,255,0.04);
      margin-bottom:10px;
    }
    .cartItemTop{display:flex; align-items:start; justify-content:space-between; gap:10px}
    .cartItem b{display:block}
    .qtyRow{display:flex; gap:8px; margin-top:10px; align-items:center}
    .iconBtn{
      width:34px; height:34px; border-radius:12px;
      border:1px solid var(--line);
      background: rgba(255,255,255,0.05);
      color:var(--text);
      cursor:pointer; font-weight:1000;
    }
    .iconBtn.danger{border-color: rgba(255,77,109,0.30); color: #ffd0d9}
    .total{
      border:1px solid rgba(255,183,3,0.18);
      background: rgba(255,183,3,0.08);
      border-radius:18px;
      padding:14px;
    }
    .totalRow{display:flex; justify-content:space-between; font-weight:1000}
    .form{
      display:grid; gap:10px;
      border:1px solid var(--line);
      border-radius:18px;
      padding:12px;
      background: rgba(255,255,255,0.03);
    }
    .form input, .form textarea{
      width:100%;
      border:1px solid var(--line);
      background: rgba(0,0,0,0.25);
      color:var(--text);
      padding:11px 12px;
      border-radius:14px;
      outline:none;
      font-weight:700;
      font-size:14px;
    }
    .form textarea{min-height:80px; resize:vertical}

    /* Footer */
    footer{
      border-top:1px solid var(--line);
      padding:18px;
      color:var(--muted);
      text-align:center;
    }

    /* Responsive */
    @media (max-width: 980px){
      .grid{grid-template-columns: repeat(2, 1fr);}
      .hero{grid-template-columns:1fr;}
    }
    @media (max-width: 520px){
      .grid{grid-template-columns: 1fr;}
      .hero h1{font-size:30px}
    }
  </style>
</head>
<body>

<header>
  <div class="topbar">
    <div class="logo">
      <div class="mark"></div>
      <div>
        <div style="font-size:14px; opacity:.9;">Fashion • Fragrance • Lifestyle</div>
        <div style="font-size:18px;">AuraWear</div>
      </div>
    </div>

    <div class="search">
      <span style="opacity:.85;">🔎</span>
      <input id="searchInput" placeholder="Search clothing, perfume, shoes..." />
    </div>

    <div class="actions">
      <span class="badge" id="liveCount">0 Products</span>
      <button class="btn primary" id="openCartBtn">🛒 Cart (<span id="cartCount">0</span>)</button>
    </div>
  </div>
</header>

<main class="container">
  <section class="hero">
    <div class="heroCard">
      <div class="badge">New Collection 2026</div>
      <h1>Bold. Warm. Classic.<br/>Your Style Store.</h1>
      <p>
        Clothing, perfumes, accessories, shoes & garments — all in one premium store experience.
        Add products to cart & place order on WhatsApp in seconds.
      </p>
      <div class="ctaRow">
        <button class="btn primary" onclick="scrollToProducts()">Shop Now</button>
        <button class="btn" onclick="filterCategory('All')">Explore All</button>
        <a class="btn" href="#contact">Business Enquiry</a>
      </div>
    </div>

    <div class="miniCard">
      <h3>✨ Quick Highlights</h3>
      <div class="stat">
        <span>Fast Checkout</span>
        <b>WhatsApp Order</b>
      </div>
      <div class="stat">
        <span>Categories</span>
        <b>5+</b>
      </div>
      <div class="stat">
        <span>Secure</span>
        <b>Client Ready</b>
      </div>
      <p style="margin:12px 0 0; color:var(--muted); font-weight:700;">
        Tip: Replace products & prices easily inside code.
      </p>
    </div>
  </section>

  <div class="sectionTitle" id="products">
    <h2>🔥 Featured Products</h2>
    <div class="chips" id="chips"></div>
  </div>

  <section class="grid" id="productGrid"></section>
</main>

<footer id="contact">
  <div style="font-weight:900; color:#fff; margin-bottom:6px;">AuraWear — Fashion & Lifestyle</div>
  <div>Made for client orders • Customizable website • 100% responsive</div>
</footer>

<!-- CART DRAWER -->
<div class="drawer" id="drawer">
  <div class="overlay" id="overlay"></div>
  <div class="panel">
    <div class="panelHeader">
      <h3>🛒 Your Cart</h3>
      <button class="btn" id="closeCartBtn">Close</button>
    </div>

    <div class="cartList" id="cartList"></div>

    <div class="total">
      <div class="totalRow">
        <span>Total</span>
        <span>₹ <span id="cartTotal">0</span></span>
      </div>
      <div class="small" style="margin-top:6px;">Delivery charges as per location.</div>
    </div>

    <div class="form">
      <input id="custName" placeholder="Customer Name" />
      <input id="custPhone" placeholder="Phone Number" />
      <textarea id="custAddr" placeholder="Full Address"></textarea>
      <button class="btn primary" onclick="placeWhatsAppOrder()">✅ Place Order on WhatsApp</button>
      <div class="small">You can change WhatsApp number in code.</div>
    </div>
  </div>
</div>

<script>
  // ====== SETTINGS ======
  const WHATSAPP_NUMBER = "919999999999"; // <-- change to client whatsapp number (with country code)

  // ====== PRODUCTS DATA ======
  const products = [
    {id:1,  name:"Classic Women's Kurti Set", category:"Clothing", price:1299, icon:"👗", desc:"Premium fabric • Elegant fit • Best for daily & party."},
    {id:2,  name:"Men's Cotton Shirt", category:"Clothing", price:899, icon:"👔", desc:"Soft cotton • Slim fit • Trendy classic."},
    {id:3,  name:"Luxury Attar (Long Lasting)", category:"Perfume", price:699, icon:"🧴", desc:"Strong fragrance • Pocket friendly • Best seller."},
    {id:4,  name:"French Perfume Spray 100ml", category:"Perfume", price:999, icon:"🌸", desc:"Fresh notes • Long-lasting • Premium feel."},
    {id:5,  name:"Women Handbag (Classic)", category:"Accessories", price:1099, icon:"👜", desc:"Stylish • Spacious • Perfect daily carry."},
    {id:6,  name:"Stylish Sunglasses", category:"Accessories", price:499, icon:"🕶️", desc:"UV protection • Trendy look • Unisex."},
    {id:7,  name:"White Sneakers (Unisex)", category:"Shoes", price:1499, icon:"👟", desc:"Comfort sole • Premium finish • Daily wear."},
    {id:8,  name:"Women Sandals (Party)", category:"Shoes", price:899, icon:"👡", desc:"Comfort + style • Best for functions."},
    {id:9,  name:"Garment Fabric (Suit Material)", category:"Garments", price:799, icon:"🧵", desc:"Quality cloth • Smooth finish • Perfect stitching."},
    {id:10, name:"Winter Hoodie (Unisex)", category:"Clothing", price:1199, icon:"🧥", desc:"Warm • Stylish • Best for winter season."},
    {id:11, name:"Jewellery Set (Golden)", category:"Accessories", price:599, icon:"💎", desc:"Elegant • Wedding ready • Budget friendly."},
    {id:12, name:"Leather Formal Shoes", category:"Shoes", price:1799, icon:"👞", desc:"Classic formal • Office wear • Premium look."},
  ];

  const categories = ["All", "Clothing", "Perfume", "Accessories", "Shoes", "Garments"];
  let activeCategory = "All";
  let cart = []; // {id, qty}

  // ====== UI RENDER ======
  const grid = document.getElementById("productGrid");
  const chipsWrap = document.getElementById("chips");
  const searchInput = document.getElementById("searchInput");
  const liveCount = document.getElementById("liveCount");

  function money(x){ return Number(x).toLocaleString("en-IN"); }

  function renderChips(){
    chipsWrap.innerHTML = "";
    categories.forEach(cat=>{
      const chip = document.createElement("div");
      chip.className = "chip" + (cat===activeCategory ? " active" : "");
      chip.textContent = cat;
      chip.onclick = ()=> filterCategory(cat);
      chipsWrap.appendChild(chip);
    });
  }

  function renderProducts(){
    const q = (searchInput.value || "").toLowerCase().trim();
    const filtered = products.filter(p=>{
      const matchCat = activeCategory==="All" ? true : p.category===activeCategory;
      const matchSearch = !q ? true : (p.name.toLowerCase().includes(q) || p.category.toLowerCase().includes(q));
      return matchCat && matchSearch;
    });

    liveCount.textContent = `${filtered.length} Products`;
    grid.innerHTML = "";

    filtered.forEach(p=>{
      const card = document.createElement("div");
      card.className = "card";
      card.innerHTML = `
        <div class="img">${p.icon}</div>
        <div class="pbody">
          <div class="ptag"><i></i>${p.category}</div>
          <h3 class="pname">${p.name}</h3>
          <p class="pdesc">${p.desc}</p>
          <div class="row">
            <div>
              <div class="price">₹ ${money(p.price)}</div>
              <div class="small">Ready Stock</div>
            </div>
          </div>
          <button class="btnAdd" onclick="addToCart(${p.id})">➕ Add to Cart</button>
        </div>
      `;
      grid.appendChild(card);
    });
  }

  function filterCategory(cat){
    activeCategory = cat;
    renderChips();
    renderProducts();
  }

  function scrollToProducts(){
    document.getElementById("products").scrollIntoView({behavior:"smooth"});
  }

  // ====== CART ======
  const drawer = document.getElementById("drawer");
  const cartList = document.getElementById("cartList");
  const cartTotal = document.getElementById("cartTotal");
  const cartCount = document.getElementById("cartCount");

  document.getElementById("openCartBtn").onclick = ()=> openCart();
  document.getElementById("closeCartBtn").onclick = ()=> closeCart();
  document.getElementById("overlay").onclick = ()=> closeCart();

  function openCart(){ drawer.classList.add("active"); renderCart(); }
  function closeCart(){ drawer.classList.remove("active"); }

  function addToCart(id){
    const item = cart.find(x=>x.id===id);
    if(item) item.qty += 1;
    else cart.push({id, qty:1});
    renderCart();
    drawer.classList.add("active");
  }

  function updateQty(id, delta){
    const item = cart.find(x=>x.id===id);
    if(!item) return;
    item.qty += delta;
    if(item.qty<=0) cart = cart.filter(x=>x.id!==id);
    renderCart();
  }

  function removeItem(id){
    cart = cart.filter(x=>x.id!==id);
    renderCart();
  }

  function getTotal(){
    let total = 0;
    cart.forEach(ci=>{
      const p = products.find(p=>p.id===ci.id);
      if(p) total += p.price * ci.qty;
    });
    return total;
  }

  function renderCart(){
    cartCount.textContent = cart.reduce((a,b)=>a+b.qty,0);
    cartList.innerHTML = "";

    if(cart.length===0){
      cartList.innerHTML = `<div class="miniCard" style="background:rgba(255,255,255,0.03)">
        <h3 style="margin:0 0 8px">Cart is empty</h3>
        <div class="small">Add products to place order.</div>
      </div>`;
    }

    cart.forEach(ci=>{
      const p = products.find(x=>x.id===ci.id);
      const div = document.createElement("div");
      div.className = "cartItem";
      div.innerHTML = `
        <div class="cartItemTop">
          <div>
            <b>${p.name}</b>
            <div class="small">${p.category} • ₹ ${money(p.price)}</div>
          </div>
          <button class="iconBtn danger" onclick="removeItem(${p.id})">✕</button>
        </div>

        <div class="qtyRow">
          <button class="iconBtn" onclick="updateQty(${p.id}, -1)">−</button>
          <b style="min-width:28px; text-align:center">${ci.qty}</b>
          <button class="iconBtn" onclick="updateQty(${p.id}, 1)">+</button>
          <div style="margin-left:auto; font-weight:1000; color:var(--brand)">₹ ${money(p.price*ci.qty)}</div>
        </div>
      `;
      cartList.appendChild(div);
    });

    cartTotal.textContent = money(getTotal());
  }

  // ====== WHATSAPP ORDER ======
  function placeWhatsAppOrder(){
    if(cart.length===0){
      alert("Cart is empty! Please add products first.");
      return;
    }
    const name = document.getElementById("custName").value.trim();
    const phone = document.getElementById("custPhone").value.trim();
    const addr = document.getElementById("custAddr").value.trim();

    if(!name || !phone || !addr){
      alert("Please fill Name, Phone and Address.");
      return;
    }

    let msg = `*New Order Request*%0A%0A`;
    msg += `👤 Name: ${encodeURIComponent(name)}%0A`;
    msg += `📞 Phone: ${encodeURIComponent(phone)}%0A`;
    msg += `📍 Address: ${encodeURIComponent(addr)}%0A%0A`;
    msg += `*Order Items:*%0A`;

    cart.forEach(ci=>{
      const p = products.find(x=>x.id===ci.id);
      msg += `• ${encodeURIComponent(p.name)}  x${ci.qty}  (₹${p.price})%0A`;
    });

    msg += `%0A*Total:* ₹${getTotal()}%0A`;
    msg += `%0A✅ Please confirm availability & delivery.`;

    const url = `https://wa.me/${WHATSAPP_NUMBER}?text=${msg}`;
    window.open(url, "_blank");
  }

  // init
  renderChips();
  renderProducts();
  searchInput.addEventListener("input", renderProducts);
</script>

</body>
</html>

