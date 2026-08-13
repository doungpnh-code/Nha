<!DOCTYPE html>
<html lang="km">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Le Gourmet Express | European Restaurant</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Kantumruy+Pro:wght@300;400;500;600;700&display=swap" rel="stylesheet">

<style>
:root{
    --red:#f43f5e;
    --red-dark:#be123c;
    --gold:#fbbf24;
    --dark-bg:#0a0f1d;
    --dark-card:#161f36;
    --white:#ffffff;
    --muted:#94a3b8;
    --card:rgba(22, 31, 54, 0.95);
    --line:rgba(255,255,255,0.1);
    --shadow:0 15px 40px rgba(0,0,0,0.4);
    --radius:22px;
    --transition:.25s ease;
}

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:"Kantumruy Pro",sans-serif;
}

html{scroll-behavior:smooth}

body{
    min-height:100vh;
    color:#f8fafc;
    background-color:var(--dark-bg);
}

button,input,textarea{
    font-family:inherit;
}

button{
    cursor:pointer;
}

header{
    position:sticky;
    top:0;
    z-index:1000;
    background:rgba(10, 15, 29, 0.92);
    backdrop-filter:blur(18px);
    border-bottom:1px solid rgba(255,255,255,.08);
}

.navbar{
    max-width:1320px;
    margin:auto;
    min-height:76px;
    padding:12px 22px;
    display:flex;
    align-items:center;
    gap:22px;
}

.logo{
    display:flex;
    align-items:center;
    gap:12px;
    cursor:pointer;
    min-width:210px;
}

.logo-icon{
    width:48px;
    height:48px;
    border-radius:15px;
    display:grid;
    place-items:center;
    font-size:24px;
    background:linear-gradient(135deg,var(--gold),var(--red));
    box-shadow:0 8px 25px rgba(244,63,94,.35);
}

.logo h1{
    font-size:19px;
    line-height:1.1;
    color: var(--white);
}

.logo small{
    color:var(--gold);
    font-size:10px;
    font-weight:700;
    letter-spacing:.8px;
}

.search{
    flex:1;
    position:relative;
    max-width:520px;
}

.search input{
    width:100%;
    height:46px;
    padding:0 18px 0 45px;
    border-radius:30px;
    border:1px solid rgba(255,255,255,.16);
    outline:none;
    color:white;
    background:rgba(255,255,255,.07);
    transition:var(--transition);
}

.search input:focus{
    border-color:var(--red);
    background:rgba(255,255,255,.12);
    box-shadow:0 0 0 4px rgba(244,63,94,.15);
}

.search span{
    position:absolute;
    left:17px;
    top:11px;
    font-size:18px;
    opacity:.7;
}

.cart-button{
    border:0;
    color:#fff;
    background:linear-gradient(135deg,var(--red),var(--red-dark));
    padding:11px 18px;
    border-radius:30px;
    font-weight:700;
    box-shadow:0 8px 22px rgba(244,63,94,.3);
    white-space:nowrap;
}

.badge{
    display:inline-grid;
    place-items:center;
    min-width:22px;
    height:22px;
    padding:0 5px;
    margin-left:6px;
    border-radius:50px;
    background:white;
    color:var(--red);
    font-size:12px;
}

.container{
    width:min(1320px,calc(100% - 36px));
    margin:28px auto;
}

.hero{
    min-height:380px;
    padding:50px;
    border-radius:28px;
    overflow:hidden;
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:30px;
    background: 
        linear-gradient(to right, rgba(10, 15, 29, 0.95) 35%, rgba(10, 15, 29, 0.45)),
        url("https://images.unsplash.com/photo-1555396273-367ea4eb4db5?auto=format&fit=crop&w=1600&q=85") center/cover no-repeat;
    box-shadow:0 20px 50px rgba(0,0,0,.5);
    border:1px solid rgba(255,255,255,.08);
}

.hero-content{
    max-width:690px;
}

.tag{
    display:inline-block;
    padding:7px 15px;
    border-radius:30px;
    background:rgba(255,255,255,.12);
    border:1px solid rgba(255,255,255,.2);
    font-size:13px;
    margin-bottom:16px;
}

.hero h2{
    font-size:clamp(28px,4vw,46px);
    line-height:1.2;
    margin-bottom:15px;
}

.hero p{
    color:#e2e8f0;
    line-height:1.8;
    margin-bottom:25px;
}

.hero-btn{
    display:inline-block;
    padding:13px 25px;
    border-radius:30px;
    color:var(--red);
    background:white;
    text-decoration:none;
    font-weight:700;
}

.hero-img{
    width:220px;
    height:220px;
    flex:none;
    border-radius:50%;
    object-fit:cover;
    border:5px solid rgba(255,255,255,.15);
}

.section-title{
    margin:34px 0 15px;
    font-size:21px;
}

.categories{
    display:flex;
    gap:10px;
    overflow-x:auto;
    scrollbar-width:none;
    padding-bottom:5px;
}

.categories::-webkit-scrollbar{display:none}

.chip{
    flex:none;
    border:1px solid rgba(255,255,255,.16);
    background:rgba(255,255,255,.06);
    color:#e2e8f0;
    padding:10px 17px;
    border-radius:30px;
    font-weight:600;
    transition:var(--transition);
}

.chip:hover,
.chip.active{
    color:#fff;
    background:var(--red);
    border-color:var(--red);
    transform:translateY(-2px);
}

.list-header{
    display:flex;
    align-items:center;
    justify-content:space-between;
    margin:30px 0 16px;
}

.list-header h2{
    font-size:22px;
}

.count{
    color:#cbd5e1;
    font-size:13px;
}

.grid{
    display:grid;
    grid-template-columns:repeat(auto-fill,minmax(235px,1fr));
    gap:20px;
}

.card{
    background:var(--dark-card);
    color:#f8fafc;
    border-radius:var(--radius);
    padding:12px;
    box-shadow:var(--shadow);
    transition:var(--transition);
    border:1px solid var(--line);
}

.card:hover{
    transform:translateY(-7px);
    border-color:var(--red);
}

.food-img{
    height:175px;
    position:relative;
    overflow:hidden;
    border-radius:16px;
    background:#1e293b;
}

.food-img img{
    width:100%;
    height:100%;
    object-fit:cover;
    transition:.4s ease;
}

.card:hover .food-img img{
    transform:scale(1.07);
}

.favorite{
    position:absolute;
    top:10px;
    right:10px;
    width:35px;
    height:35px;
    border:0;
    border-radius:50%;
    background:rgba(10,15,29,.8);
    color:#94a3b8;
    font-size:17px;
}

.favorite.active{
    color:var(--red);
}

.food-body{
    padding:13px 3px 3px;
}

.food-name{
    font-weight:700;
    font-size:15px;
    min-height:44px;
}

.meta{
    color:var(--muted);
    font-size:12px;
    margin:5px 0 13px;
}

.rating{
    color:var(--gold);
    font-weight:700;
}

.food-bottom{
    display:flex;
    justify-content:space-between;
    align-items:center;
}

.price{
    color:var(--gold);
    font-size:19px;
    font-weight:800;
}

.add{
    width:40px;
    height:40px;
    border:0;
    border-radius:50%;
    color:white;
    background:var(--red);
    font-size:22px;
    font-weight:700;
}

.add:hover{
    background:var(--red-dark);
}

.detail-page{
    display:none;
}

.detail-page.active{
    display:block;
}

.home-page.hidden{
    display:none;
}

.back{
    border:1px solid rgba(255,255,255,.15);
    background:rgba(255,255,255,.1);
    color:white;
    padding:10px 18px;
    border-radius:30px;
    margin-bottom:18px;
}

.detail{
    background:var(--dark-card);
    color:#f8fafc;
    border-radius:28px;
    padding:25px;
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:30px;
    box-shadow:var(--shadow);
    border:1px solid var(--line);
}

.detail-image{
    width:100%;
    height:470px;
    object-fit:cover;
    border-radius:20px;
}

.detail-info{
    display:flex;
    flex-direction:column;
    justify-content:center;
}

.detail-info h1{
    font-size:32px;
    margin-bottom:8px;
}

.detail-description{
    color:var(--muted);
    line-height:1.8;
    margin:20px 0;
}

.detail-price{
    font-size:32px;
    color:var(--gold);
    font-weight:800;
    margin-bottom:20px;
}

.quantity{
    display:flex;
    align-items:center;
    gap:15px;
    margin-bottom:25px;
}

.qty-btn{
    width:40px;
    height:40px;
    border-radius:50%;
    border:1px solid var(--line);
    background:rgba(255,255,255,0.1);
    color:white;
    font-size:20px;
}

.qty-number{
    min-width:30px;
    text-align:center;
    font-weight:700;
}

.actions{
    display:flex;
    gap:12px;
}

.btn{
    flex:1;
    border:0;
    padding:14px;
    border-radius:30px;
    font-weight:700;
}

.btn.secondary{
    background:rgba(255,255,255,0.1);
    color:#f8fafc;
}

.btn.primary{
    color:white;
    background:var(--red);
}

.floating-cart{
    position:fixed;
    z-index:900;
    right:22px;
    bottom:22px;
    border:0;
    border-radius:40px;
    color:white;
    background:linear-gradient(135deg,var(--red),var(--red-dark));
    padding:14px 21px;
    font-weight:700;
    box-shadow:0 15px 35px rgba(244,63,94,.4);
}

.modal{
    position:fixed;
    inset:0;
    z-index:2000;
    display:none;
    align-items:center;
    justify-content:center;
    padding:18px;
    background:rgba(2,6,23,.85);
    backdrop-filter:blur(8px);
}

.modal.active{
    display:flex;
}

.modal-box{
    width:min(520px,100%);
    max-height:90vh;
    overflow:auto;
    background:var(--dark-card);
    color:#f8fafc;
    border-radius:25px;
    padding:25px;
    box-shadow:0 30px 80px rgba(0,0,0,.6);
    position:relative;
    border:1px solid var(--line);
}

.close{
    position:absolute;
    right:18px;
    top:15px;
    border:0;
    background:rgba(255,255,255,0.1);
    color:white;
    width:35px;
    height:35px;
    border-radius:50%;
}

.modal-title{
    font-size:23px;
    font-weight:800;
    margin-bottom:18px;
}

.cart-item{
    display:flex;
    gap:12px;
    align-items:center;
    padding:12px 0;
    border-bottom:1px solid var(--line);
}

.cart-item img{
    width:65px;
    height:65px;
    object-fit:cover;
    border-radius:12px;
}

.cart-item-info{
    flex:1;
}

.cart-item-name{
    font-size:13px;
    font-weight:700;
}

.cart-controls{
    display:flex;
    align-items:center;
    gap:7px;
    margin-top:5px;
}

.small-btn{
    width:26px;
    height:26px;
    border:0;
    border-radius:50%;
    background:rgba(255,255,255,0.1);
    color:white;
}

.remove{
    border:0;
    background:none;
    color:#ef4444;
}

.total-box{
    margin-top:18px;
    padding:17px;
    border-radius:15px;
    background:rgba(0,0,0,0.2);
}

.total-row{
    display:flex;
    justify-content:space-between;
    margin:6px 0;
}

.grand-total{
    font-size:21px;
    font-weight:800;
    color:var(--gold);
}

.checkout{
    width:100%;
    margin-top:15px;
    padding:14px;
    border:0;
    border-radius:30px;
    color:white;
    background:var(--red);
    font-weight:800;
}

.form{
    display:grid;
    gap:10px;
    margin-top:15px;
}

.form input,
.form textarea{
    width:100%;
    padding:12px 14px;
    border:1px solid var(--line);
    background:rgba(0,0,0,0.2);
    color:white;
    border-radius:12px;
    outline:none;
}

.form textarea{
    min-height:80px;
    resize:vertical;
}

.qr{
    text-align:center;
    padding:20px;
    margin-top:15px;
    border:2px dashed var(--line);
    border-radius:18px;
    background:white;
    color:#0f172a;
}

.qr img{
    width:210px;
    height:210px;
    max-width:100%;
}

.empty{
    grid-column:1/-1;
    padding:60px 20px;
    text-align:center;
    color:#cbd5e1;
}

.toast{
    position:fixed;
    z-index:3000;
    left:50%;
    bottom:28px;
    transform:translate(-50%,120px);
    padding:12px 20px;
    border-radius:30px;
    color:white;
    background:#1e293b;
    border:1px solid var(--line);
    box-shadow:0 10px 30px rgba(0,0,0,.5);
    transition:.3s ease;
}

.toast.show{
    transform:translate(-50%,0);
}

@media(max-width:800px){
    .navbar{ flex-wrap:wrap; gap:10px; }
    .logo{ min-width:auto; flex:1; }
    .search{ order:3; flex-basis:100%; max-width:none; }
    .hero{ padding:32px 24px; text-align:center; justify-content:center; }
    .hero-img{ display:none; }
    .detail{ grid-template-columns:1fr; }
    .detail-image{ height:320px; }
    .grid{ grid-template-columns:repeat(2,minmax(0,1fr)); gap:12px; }
    .food-img{ height:145px; }
    .floating-cart{ right:12px; bottom:12px; }
}

@media(max-width:500px){
    .container{ width:min(100% - 20px,1320px); margin:18px auto; }
    .logo h1{ font-size:16px; }
    .logo small{ display:none; }
    .cart-button{ padding:9px 12px; font-size:12px; }
    .hero{ min-height:350px; border-radius:22px; }
    .hero h2{ font-size:28px; }
    .grid{ grid-template-columns:1fr 1fr; }
    .food-name{ font-size:13px; }
    .food-img{ height:125px; }
    .price{ font-size:16px; }
    .add{ width:35px; height:35px; }
    .detail{ padding:15px; }
    .detail-info h1{ font-size:25px; }
}
</style>
</head>

<body>

<header>
    <div class="navbar">

        <div class="logo" onclick="goHome()">
            <div class="logo-icon">🍷</div>
            <div>
                <h1>Le Gourmet</h1>
                <small>FINE EUROPEAN CUISINE</small>
            </div>
        </div>

        <div class="search">
            <span>🔍</span>
            <input
                id="searchInput"
                type="text"
                placeholder="ស្វែងរក Steak, Pasta, Pizza..."
                oninput="filterFoods()"
            >
        </div>

        <button class="cart-button" onclick="openCart()">
            🛒 កន្ត្រក
            <span class="badge" id="cartCount">0</span>
        </button>

    </div>
</header>

<main id="homePage">

    <div class="container">

        <section class="hero">

            <div class="hero-content">
                <span class="tag">✨ Authentic European Taste</span>

                <h2>
                    រសជាតិអឺរ៉ុបប្រណិត
                    🥩🍝🍷
                </h2>

                <p>
                    ស្វែងរកមុខម្ហូបអឺរ៉ុប ៥០ មុខដែលបានជ្រើសរើសយ៉ាងសម្រិតសម្រាំង
                    ចាប់ពី Steak, Pasta, Pizza, Salad, Dessert រhodដល់ភេសជ្ជៈប្រណិត។
                </p>

                <a href="#menu" class="hero-btn">
                    🍽️ មើលមុខម្ហូប
                </a>
            </div>

            <img
                class="hero-img"
                src="https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=600&q=85"
                alt="Steak"
            >

        </section>

        <h3 class="section-title">ប្រភេទមុខម្ហូប</h3>

        <div class="categories">

            <button class="chip active" onclick="setCategory('all',this)">
                🍽️ ទាំងអស់
            </button>

            <button class="chip" onclick="setCategory('steak',this)">
                🥩 Steak & Grill
            </button>

            <button class="chip" onclick="setCategory('pasta',this)">
                🍝 Pasta & Pizza
            </button>

            <button class="chip" onclick="setCategory('appetizer',this)">
                🥗 Appetizer
            </button>

            <button class="chip" onclick="setCategory('drink',this)">
                🍷 Drinks
            </button>

            <button class="chip" onclick="setCategory('dessert',this)">
                🍰 Dessert
            </button>

        </div>

        <div class="list-header" id="menu">
            <h2>បញ្ជីមុខម្ហូប</h2>
            <span class="count">
                <span id="itemCount">50</span> មុខ
            </span>
        </div>

        <div class="grid" id="foodGrid"></div>

    </div>

</main>

<section class="detail-page" id="detailPage">

    <div class="container">

        <button class="back" onclick="goHome()">
            ← ត្រឡប់ទៅមុខម្ហូប
        </button>

        <div class="detail">

            <img id="detailImage" class="detail-image" alt="Food">

            <div class="detail-info">

                <h1 id="detailName"></h1>

                <div class="meta">
                    <span class="rating" id="detailRating"></span>
                    · ⭐ Popular
                </div>

                <p class="detail-description" id="detailDescription"></p>

                <div class="detail-price" id="detailPrice"></div>

                <div class="quantity">
                    <strong>ចំនួន:</strong>

                    <button class="qty-btn" onclick="changeDetailQty(-1)">
                        −
                    </button>

                    <span class="qty-number" id="detailQty">
                        1
                    </span>

                    <button class="qty-btn" onclick="changeDetailQty(1)">
                        +
                    </button>
                </div>

                <div class="actions">

                    <button
                        class="btn secondary"
                        onclick="addDetailToCart()"
                    >
                        🛒 បន្ថែមកន្ត្រក
                    </button>

                    <button
                        class="btn primary"
                        onclick="buyDetailNow()"
                    >
                        ⚡ ទិញភ្លាម
                    </button>

                </div>

            </div>

        </div>

    </div>

</section>

<button class="floating-cart" onclick="openCart()">
    🛒 កន្ត្រក
    <span id="floatingCount">0</span>
</button>

<!-- CART MODAL -->
<div class="modal" id="cartModal">

    <div class="modal-box">

        <button class="close" onclick="closeModal('cartModal')">
            ✕
        </button>

        <div class="modal-title">
            🛒 កន្ត្រកទំនិញ
        </div>

        <div id="cartItems"></div>

        <div class="total-box">

            <div class="total-row">
                <span>Subtotal</span>
                <strong id="subtotal">$0.00</strong>
            </div>

            <div class="total-row">
                <span>Delivery</span>
                <strong id="delivery">$2.00</strong>
            </div>

            <hr style="margin:10px 0;border:0;border-top:1px solid var(--line)">

            <div class="total-row grand-total">
                <span>Total</span>
                <strong id="cartTotal">$0.00</strong>
            </div>

        </div>

        <button class="checkout" onclick="openCheckout()">
            💳 បន្តទៅការទូទាត់
        </button>

    </div>

</div>

<!-- CHECKOUT MODAL -->
<div class="modal" id="checkoutModal">

    <div class="modal-box">

        <button class="close" onclick="closeModal('checkoutModal')">
            ✕
        </button>

        <div class="modal-title">
            🧾 ព័ត៌មានការកុម្ម៉ង់
        </div>

        <div class="form">

            <input
                id="customerName"
                placeholder="ឈ្មោះអតិថិជន"
            >

            <input
                id="customerPhone"
                placeholder="លេខទូរស័ព្ទ"
            >

            <textarea
                id="customerAddress"
                placeholder="អាសយដ្ឋានដឹកជញ្ជូន"
            ></textarea>

        </div>

        <button class="checkout" onclick="showPayment()">
            បន្តទៅ KHQR →
        </button>

    </div>

</div>

<!-- PAYMENT MODAL -->
<div class="modal" id="paymentModal">

    <div class="modal-box">

        <button class="close" onclick="closeModal('paymentModal')">
            ✕
        </button>

        <div class="modal-title">
            💳 ទូទាត់តាម KHQR
        </div>

        <p
            style="text-align:center;color:var(--muted);font-size:13px"
        >
            ស្កែន QR Code ខាងក្រោមដើម្បីទូទាត់
        </p>

        <div class="qr">

            <img
                src="https://api.qrserver.com/v1/create-qr-code/?size=300x300&data=KHQR_LE_GOURMET_DEMO"
                alt="KHQR"
            >

            <p style="margin-top:12px;font-weight:700">
                Le Gourmet Express
            </p>

            <div
                id="paymentTotal"
                style="
                    font-size:28px;
                    color:#e11d48;
                    font-weight:800;
                    margin-top:5px;
                "
            >
                $0.00
            </div>

        </div>

        <button class="checkout" onclick="completeOrder()">
            ✅ ខ្ញុំបានទូទាត់រួច
        </button>

    </div>

</div>

<div class="toast" id="toast"></div>

<script>

const menu = {
    steak: [
        ["Ribeye Steak", "ស្ទេកសាច់គោ Ribeye", 24, "https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=700&q=85"],
        ["Beef Tenderloin", "សាច់គោ Tenderloin", 27, "https://images.unsplash.com/photo-1546833999-b9f581a1996d?auto=format&fit=crop&w=700&q=85"],
        ["T-Bone Steak", "ស្ទេក T-Bone", 29, "https://images.unsplash.com/photo-1558030006-450675393462?auto=format&fit=crop&w=700&q=85"],
        ["Sirloin Steak", "ស្ទេក Sirloin", 19, "https://images.unsplash.com/photo-1600891964092-4316c288032e?auto=format&fit=crop&w=700&q=85"],
        ["Wagyu Beef Steak", "ស្ទេកសាច់គោ Wagyu", 45, "https://images.unsplash.com/photo-1504973960431-1c467e159aa4?auto=format&fit=crop&w=700&q=85"],
        ["Filet Mignon", "Filet Mignon ប្រណិត", 35, "https://images.unsplash.com/photo-1588168333986-5078d3ae3976?auto=format&fit=crop&w=700&q=85"],
        ["Grilled Lamb Chops", "ឆ្អឹងជំនីចៀមអាំង", 22, "https://images.unsplash.com/photo-1603048588665-791ca8aea617?auto=format&fit=crop&w=700&q=85"],
        ["BBQ Pork Ribs", "ឆ្អឹងជំនីជ្រូក BBQ", 15, "https://images.unsplash.com/photo-1529193591184-b1d58069ecdd?auto=format&fit=crop&w=700&q=85"],
        ["Grilled Duck Breast", "សុដន់ទាអាំង", 18, "https://images.unsplash.com/photo-1514944288352-fffac99f0bdf?auto=format&fit=crop&w=700&q=85"],
        ["Grilled Salmon Steak", "ស្ទេកត្រី Salmon", 21, "https://images.unsplash.com/photo-1519708227418-c8fd9a32b7a2?auto=format&fit=crop&w=700&q=85"]
    ],
    pasta: [
        ["Spaghetti Carbonara", "ផាស្តា Carbonara", 11, "https://images.unsplash.com/photo-1612874742237-6526221588e3?auto=format&fit=crop&w=700&q=85"],
        ["Spaghetti Bolognese", "ផាស្តា Bolognese", 11, "https://images.unsplash.com/photo-1621996346565-e3def6164286?auto=format&fit=crop&w=700&q=85"],
        ["Penne Arrabbiata", "Penne Arrabbiata", 9, "https://images.unsplash.com/photo-1563379091339-03b21ab4a4f8?auto=format&fit=crop&w=700&q=85"],
        ["Fettuccine Alfredo", "Fettuccine Alfredo", 12, "https://images.unsplash.com/photo-1645112411341-6c4fd023714a?auto=format&fit=crop&w=700&q=85"],
        ["Seafood Fettuccine", "Fettuccine គ្រឿងសមុទ្រ", 16, "https://images.unsplash.com/photo-1551183053-bf91a1d81141?auto=format&fit=crop&w=700&q=85"],
        ["Truffle Pasta", "ផាស្តា Truffle", 18, "https://images.unsplash.com/photo-1546549032-9571cd6b27df?auto=format&fit=crop&w=700&q=85"],
        ["Lasagna Bolognese", "Lasagna Bolognese", 14, "https://images.unsplash.com/photo-1574894709920-11b28e7367e3?auto=format&fit=crop&w=700&q=85"],
        ["Margherita Pizza", "ភីហ្សា Margherita", 10, "https://images.unsplash.com/photo-1604382355076-af4b0eb60143?auto=format&fit=crop&w=700&q=85"],
        ["Pepperoni Pizza", "ភីហ្សា Pepperoni", 12, "https://images.unsplash.com/photo-1628840042765-356cda07504e?auto=format&fit=crop&w=700&q=85"],
        ["Four Cheese Pizza", "ភីហ្សាឈីស 4 ប្រភេទ", 13, "https://images.unsplash.com/photo-1513104890138-7c749659a591?auto=format&fit=crop&w=700&q=85"]
    ],
    appetizer: [
        ["Caesar Salad", "សាឡាត់ Caesar", 7, "https://images.unsplash.com/photo-1550304943-4f24f54ddde9?auto=format&fit=crop&w=700&q=85"],
        ["Greek Salad", "សាឡាត់ក្រិក", 7, "https://images.unsplash.com/photo-1540420773420-3366772f4999?auto=format&fit=crop&w=700&q=85"],
        ["Caprese Salad", "សាឡាត់ Caprese", 8, "https://images.unsplash.com/photo-1592417817098-8f3d6ef23a28?auto=format&fit=crop&w=700&q=85"],
        ["Shrimp Cocktail", "Cocktail បង្គា", 10, "https://images.unsplash.com/photo-1565557623262-b51c2513a641?auto=format&fit=crop&w=700&q=85"],
        ["Crispy Calamari", "មឹកបំពងស្រួយ", 11, "https://images.unsplash.com/photo-1599488615731-7e5c2823ff28?auto=format&fit=crop&w=700&q=85"],
        ["Bruschetta", "Bruschetta ប៉េងប៉ោះ", 6, "https://images.unsplash.com/photo-1572695157366-5e585ab2b69f?auto=format&fit=crop&w=700&q=85"],
        ["Garlic Bread", "នំប៉័ងខ្ទឹមស", 4, "https://images.unsplash.com/photo-1619535860434-ba1d8fa12536?auto=format&fit=crop&w=700&q=85"],
        ["French Fries", "ដំឡូងបារាំងបំពង", 4, "https://images.unsplash.com/photo-1576107232684-1279f3908594?auto=format&fit=crop&w=700&q=85"],
        ["Mushroom Soup", "ស៊ុបផ្សិត", 6, "https://images.unsplash.com/photo-1547592166-23ac45744acd?auto=format&fit=crop&w=700&q=85"],
        ["French Onion Soup", "ស៊ុបខ្ទឹមបារាំងបារាំង", 7, "https://images.unsplash.com/photo-1583394293214-28ded15ee548?auto=format&fit=crop&w=700&q=85"]
    ],
    drink: [
        ["Cabernet Sauvignon", "ស្រាក្រហម Cabernet", 28, "https://images.unsplash.com/photo-1510812431401-41d2bd2722f3?auto=format&fit=crop&w=700&q=85"],
        ["Chardonnay", "ស្រាស Chardonnay", 27, "https://images.unsplash.com/photo-1584917865442-de89df76afd3?auto=format&fit=crop&w=700&q=85"],
        ["Rosé Wine", "ស្រា Rosé", 24, "https://images.unsplash.com/photo-1558001373-7b93ee48ffa0?auto=format&fit=crop&w=700&q=85"],
        ["Champagne", "Champagne", 55, "https://images.unsplash.com/photo-1594488311333-e99fec6f3cb3?auto=format&fit=crop&w=700&q=85"],
        ["Espresso", "កាហ្វេ Espresso", 3, "https://images.unsplash.com/photo-1510591509098-f4fdc6d0ff04?auto=format&fit=crop&w=700&q=85"],
        ["Cappuccino", "Cappuccino", 4, "https://images.unsplash.com/photo-1534778101976-62847782c213?auto=format&fit=crop&w=700&q=85"],
        ["Café Latte", "Café Latte", 4, "https://images.unsplash.com/photo-1570968915860-54d5c301fa9f?auto=format&fit=crop&w=700&q=85"],
        ["Iced Latte", "Iced Latte", 5, "https://images.unsplash.com/photo-1517701604599-bb29b565090c?auto=format&fit=crop&w=700&q=85"],
        ["Fresh Orange Juice", "ទឹកក្រូចស្រស់", 4, "https://images.unsplash.com/photo-1613478223719-2ab802602423?auto=format&fit=crop&w=700&q=85"],
        ["Classic Mojito", "Mojito", 7, "https://images.unsplash.com/photo-1551024709-8f23befc6f87?auto=format&fit=crop&w=700&q=85"]
    ],
    dessert: [
        ["Classic Tiramisu", "នំ Tiramisu", 7, "https://images.unsplash.com/photo-1571877227200-a0d98ea607e9?auto=format&fit=crop&w=700&q=85"],
        ["Crème Brûlée", "Crème Brûlée", 7, "https://images.unsplash.com/photo-1470124182917-cc6e71b22ecc?auto=format&fit=crop&w=700&q=85"],
        ["Chocolate Lava Cake", "នំសូកូឡា Lava", 8, "https://images.unsplash.com/photo-1606313564200-e75d5e30476c?auto=format&fit=crop&w=700&q=85"],
        ["New York Cheesecake", "Cheesecake New York", 7, "https://images.unsplash.com/photo-1533134242443-d4fd215305ad?auto=format&fit=crop&w=700&q=85"],
        ["Chocolate Mousse", "Chocolate Mousse", 6, "https://images.unsplash.com/photo-1541781774459-bb2af2f05b55?auto=format&fit=crop&w=700&q=85"],
        ["Panna Cotta", "Panna Cotta", 7, "https://images.unsplash.com/photo-1488477181946-6428a0291777?auto=format&fit=crop&w=700&q=85"],
        ["French Macarons", "Macarons បារាំង", 8, "https://images.unsplash.com/photo-1569864358642-9d1684040f43?auto=format&fit=crop&w=700&q=85"],
        ["Apple Pie", "នំ Apple Pie", 6, "https://images.unsplash.com/photo-1568571780765-9276ac8b75a2?auto=format&fit=crop&w=700&q=85"],
        ["Vanilla Gelato", "Gelato Vanilla", 5, "https://images.unsplash.com/photo-1570197788417-0e82375c9371?auto=format&fit=crop&w=700&q=85"],
        ["French Crêpe", "Crêpe បារាំង", 7, "https://images.unsplash.com/photo-1519676867240-f03562e64548?auto=format&fit=crop&w=700&q=85"]
    ]
};

const categoryNames={
    steak:"🥩 Steak & Grill",
    pasta:"🍝 Pasta & Pizza",
    appetizer:"🥗 Appetizer",
    drink:"🍷 Drinks",
    dessert:"🍰 Dessert"
};

const foods=[];
let id=1;

Object.entries(menu).forEach(([cat,items])=>{
    items.forEach((item,index)=>{
        foods.push({
            id:id++,
            name:item[0],
            khmer:item[1],
            price:item[2],
            cat,
            rating:(4.7+(index%3)*.1).toFixed(1),
            image:item[3],
            description: `${item[1]} ត្រូវបានរៀបចំដោយគ្រឿងផ្សំស្រស់ៗ និងចម្អិនតាមរចនាប័ទ្មអឺរ៉ុប។ សាកសមសម្រាប់អាហារថ្ងៃត្រង់ អាហារពេលល្ងាច និងឱកាសពិសេស។`
        });
    });
});

let cart=JSON.parse(localStorage.getItem("leGourmetCart")||"[]");
let favorites=JSON.parse(localStorage.getItem("leGourmetFavorites")||"[]");

let activeCategory="all";
let currentFood=null;
let detailQty=1;

function money(value){
    return "$"+Number(value).toFixed(2);
}

function save(){
    localStorage.setItem("leGourmetCart",JSON.stringify(cart));
    localStorage.setItem("leGourmetFavorites",JSON.stringify(favorites));
}

function toast(message){
    const el=document.getElementById("toast");
    el.textContent=message;
    el.classList.add("show");

    clearTimeout(window.toastTimer);

    window.toastTimer=setTimeout(()=>{
        el.classList.remove("show");
    },2200);
}

function renderFoods(list=foods){

    const grid=document.getElementById("foodGrid");

    document.getElementById("itemCount").textContent=list.length;

    if(!list.length){
        grid.innerHTML=`
            <div class="empty">
                <div style="font-size:45px">🔍</div>
                <h3 style="margin:10px 0">រកមិនឃើញមុខម្ហូប</h3>
                <p>សូមសាកល្បងពាក្យស្វែងរកផ្សេងទៀត។</p>
            </div>
        `;
        return;
    }

    grid.innerHTML=list.map(food=>{

        const fav=favorites.includes(food.id);

        return `
        <article class="card">

            <div
                class="food-img"
                onclick="openDetail(${food.id})"
            >

                <img
                    src="${food.image}"
                    alt="${food.name}"
                    loading="lazy"
                    onerror="this.src='https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=700&q=80'"
                >

                <button
                    class="favorite ${fav?"active":""}"
                    onclick="event.stopPropagation();toggleFavorite(${food.id})"
                >
                    ${fav?"♥":"♡"}
                </button>

            </div>

            <div class="food-body">

                <div
                    class="food-name"
                    onclick="openDetail(${food.id})"
                    style="cursor:pointer"
                >
                    ${food.name}
                    <br>
                    <span style="font-size:12px;color:var(--muted)">
                        ${food.khmer}
                    </span>
                </div>

                <div class="meta">
                    <span class="rating">
                        ★ ${food.rating}
                    </span>
                    · 🚚 ដឹកជញ្ជូនរហ័ស
                </div>

                <div class="food-bottom">

                    <div class="price">
                        ${money(food.price)}
                    </div>

                    <button
                        class="add"
                        onclick="addToCart(${food.id})"
                    >
                        +
                    </button>

                </div>

            </div>

        </article>
        `;
    }).join("");
}

function filterFoods(){

    const q=document
        .getElementById("searchInput")
        .value
        .toLowerCase()
        .trim();

    const result=foods.filter(food=>{

        const categoryOK=
            activeCategory==="all" ||
            food.cat===activeCategory;

        const text=
            `${food.name} ${food.khmer} ${categoryNames[food.cat]||""}`
            .toLowerCase();

        return categoryOK && text.includes(q);
    });

    renderFoods(result);
}

function setCategory(cat,button){

    activeCategory=cat;

    document
        .querySelectorAll(".chip")
        .forEach(x=>x.classList.remove("active"));

    button.classList.add("active");
    filterFoods();
}

function toggleFavorite(id){
    const index=favorites.indexOf(id);
    if(index>-1){
        favorites.splice(index,1);
        toast("បានលុបចេញពីបញ្ជីសំណព្វចិត្ត");
    } else {
        favorites.push(id);
        toast("បានបន្ថែមទៅបញ្ជីសំណព្វចិត្ត");
    }
    save();
    filterFoods();
}

function openDetail(id){
    currentFood=foods.find(x=>x.id===id);
    if(!currentFood) return;

    detailQty=1;
    document.getElementById("detailQty").textContent=detailQty;
    document.getElementById("detailImage").src=currentFood.image;
    document.getElementById("detailName").textContent=`${currentFood.name} (${currentFood.khmer})`;
    document.getElementById("detailRating").textContent=`★ ${currentFood.rating}`;
    document.getElementById("detailDescription").textContent=currentFood.description;
    document.getElementById("detailPrice").textContent=money(currentFood.price);

    document.getElementById("homePage").classList.add("hidden");
    document.getElementById("detailPage").classList.add("active");
    window.scrollTo({top:0,behavior:"smooth"});
}

function goHome(){
    document.getElementById("detailPage").classList.remove("active");
    document.getElementById("homePage").classList.remove("hidden");
    window.scrollTo({top:0,behavior:"smooth"});
}

function changeDetailQty(val){
    detailQty=Math.max(1,detailQty+val);
    document.getElementById("detailQty").textContent=detailQty;
}

function addDetailToCart(){
    if(!currentFood) return;
    addToCart(currentFood.id, detailQty);
    toast("បានបន្ថែមទៅក្នុងកន្ត្រក");
}

function buyDetailNow(){
    if(!currentFood) return;
    addToCart(currentFood.id, detailQty);
    openCart();
}

function addToCart(id, qty=1){
    const food=foods.find(x=>x.id===id);
    if(!food) return;

    const found=cart.find(x=>x.id===id);
    if(found){
        found.qty+=qty;
    }else{
        cart.push({...food, qty});
    }

    save();
    updateCartUI();
    toast(`បានបន្ថែម ${food.name} ទៅកន្ត្រក`);
}

function updateCartQty(id, val){
    const item=cart.find(x=>x.id===id);
    if(!item) return;

    item.qty+=val;
    if(item.qty<=0){
        cart=cart.filter(x=>x.id!==id);
    }

    save();
    updateCartUI();
}

function removeFromCart(id){
    cart=cart.filter(x=>x.id!==id);
    save();
    updateCartUI();
    toast("បានលុបទំនិញចេញពីកន្ត្រក");
}

function updateCartUI(){
    const totalCount=cart.reduce((sum,item)=>sum+item.qty,0);
    document.getElementById("cartCount").textContent=totalCount;
    document.getElementById("floatingCount").textContent=totalCount;

    const container=document.getElementById("cartItems");

    if(!cart.length){
        container.innerHTML=`
            <div style="text-align:center;padding:40px 0;color:var(--muted)">
                <div style="font-size:40px">🛒</div>
                <p style="margin-top:10px">កន្ត្រករបស់អ្នកទទេ</p>
            </div>
        `;
        document.getElementById("subtotal").textContent=money(0);
        document.getElementById("cartTotal").textContent=money(2);
        return;
    }

    container.innerHTML=cart.map(item=>`
        <div class="cart-item">
            <img src="${item.image}" alt="${item.name}">
            <div class="cart-item-info">
                <div class="cart-item-name">${item.name}</div>
                <div style="font-size:12px;color:var(--gold);font-weight:700">${money(item.price)}</div>
                <div class="cart-controls">
                    <button class="small-btn" onclick="updateCartQty(${item.id},-1)">−</button>
                    <span style="font-weight:700;font-size:13px">${item.qty}</span>
                    <button class="small-btn" onclick="updateCartQty(${item.id},1)">+</button>
                    <button class="remove" onclick="removeFromCart(${item.id})" style="margin-left:auto;font-size:12px">លុប</button>
                </div>
            </div>
        </div>
    `).join("");

    const sub=cart.reduce((sum,item)=>sum+(item.price*item.qty),0);
    const delivery=sub>0?2:0;
    const grand=sub+delivery;

    document.getElementById("subtotal").textContent=money(sub);
    document.getElementById("delivery").textContent=money(delivery);
    document.getElementById("cartTotal").textContent=money(grand);
}

function openCart(){
    updateCartUI();
    document.getElementById("cartModal").classList.add("active");
}

function closeModal(id){
    document.getElementById(id).classList.remove("active");
}

function openCheckout(){
    if(!cart.length){
        toast("កន្ត្រករបស់អ្នកទទេ");
        return;
    }
    closeModal('cartModal');
    document.getElementById("checkoutModal").classList.add("active");
}

function showPayment(){
    const name=document.getElementById("customerName").value.trim();
    const phone=document.getElementById("customerPhone").value.trim();
    const address=document.getElementById("customerAddress").value.trim();

    if(!name || !phone || !address){
        toast("សូមបំពេញព័ត៌មានឱ្យបានគ្រប់គ្រាន់");
        return;
    }

    const sub=cart.reduce((sum,item)=>sum+(item.price*item.qty),0);
    const grand=sub+2;

    document.getElementById("paymentTotal").textContent=money(grand);

    closeModal('checkoutModal');
    document.getElementById("paymentModal").classList.add("active");
}

function completeOrder(){
    closeModal('paymentModal');
    cart=[];
    save();
    updateCartUI();
    toast("ការកុម្ម៉ង់បានជោគជ័យ! អរគុណច្រើន។");
}

// Initial Render
renderFoods();
updateCartUI();

</script>
</body>
</html>
