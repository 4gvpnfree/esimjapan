chung
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>eSIM Nhật Bản – Internet du lịch</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
*,
*::before,
*::after{box-sizing:border-box}

html,body{
  margin:0;
  padding:0;
  width:100%;
  overflow-x:hidden;
  font-family:Arial,sans-serif;
  background:linear-gradient(180deg,#f0f6ff,#f9f9f9);
}

/* ẨN HEADER BLOGGER */
header,.Header,#header,#Header1,.header,.header-wrapper{
  display:none!important;
}

/* ===== BANNER ===== */
.banner{
  width:100%;
  height:240px;
  position:relative;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  text-align:center;
  color:#fff;
  border-radius:0 0 25px 25px;
  overflow:hidden;

  background-image:url('https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&w=1920&q=80');

  background-size:cover;
  background-position:center;
  transition:background-image .5s ease-in-out;
}

/* lớp phủ tối */
.banner::after{
  content:"";
  position:absolute;
  inset:0;
  background:rgba(0,0,0,.45);
}

.banner h1,
.banner p{
  position:relative;
  z-index:2;
}

.banner h1{
  font-size:30px;
  font-weight:800;
  margin:0;
  text-shadow:0 4px 20px rgba(0,0,0,.6);
}

.banner p{
  margin-top:8px;
  font-size:16px;
}
.banner h1,
.banner p{
  position:relative;
  z-index:2;
}

.banner h1{
  font-size:30px;
  font-weight:800;
  margin:0;
  text-shadow:0 4px 20px rgba(0,0,0,.6);
}

.banner p{
  margin-top:8px;
  font-size:16px;
  opacity:.95;
}

/* ===== CONTAINER ===== */
.container{
  width:100%;
  max-width:600px;
  margin:0 auto 28px;
  background:#fff;
  padding:16px;
  border-radius:16px;
  box-shadow:0 10px 25px rgba(0,0,0,.12);
}

/* ===== FORM ===== */
select,input{
  width:100%;
  padding:14px;
  margin-top:12px;
  font-size:16px;
  border-radius:12px;
  border:2px solid #ff7043;   /* Viền cam nổi bật */
  outline:none;
  transition:all .25s ease;
  background:#fff;
  box-shadow:0 4px 12px rgba(255,112,67,.15); /* Bóng nhẹ */
}

button{
  display:block;
  width:85%;
  margin:20px auto 0;
  padding:16px;
  font-size:18px;
  font-weight:bold;
  border:none;
  border-radius:14px;
  cursor:pointer;
  background:linear-gradient(135deg,#e53935,#ff7043);
  color:#fff;
  box-shadow:0 8px 20px rgba(229,57,53,.35);
  transition:all .25s ease;
}

button:hover{
  transform:translateY(-3px);
  box-shadow:0 12px 25px rgba(229,57,53,.45);
}

button:active{
  transform:scale(.97);
}

.price{
  text-align:center;
  font-size:19px;
  font-weight:bold;
  color:#e53935;
  margin-top:10px;
}

/* ===== THANH TOÁN ===== */
.note{
  background:#fff7d6;
  padding:16px;
  border-radius:16px;
  margin-top:18px;
  font-size:13px;
}
  /* ===== FIX PAYMENT DARK MODE ===== */
body.dark-mode .note{
  background:#1e1e1e !important;
  color:#ffffff !important;
  border:1px solid rgba(255,255,255,0.1);
}

body.dark-mode .note h3,
body.dark-mode .note p,
body.dark-mode .note span,
body.dark-mode .note b{
  color:#ffffff !important;
}

body.dark-mode .transfer-box{
  background:#2a2a2a !important;
  border:1px dashed #ff7043 !important;
}

body.dark-mode .transfer-label{
  color:#ff7043 !important;
}

body.dark-mode .transfer-content{
  color:#ffffff !important;
}

.note h3{
  margin:0 0 14px;
  font-size:16px;
  text-align:center;
}
  /* ===== TRUST BOX ===== */
.trust-box{
  margin-top:20px;
  padding:16px;
  border-radius:16px;
  background:#f9fafc;
  box-shadow:0 5px 15px rgba(0,0,0,.05);
}

.trust-box h3{
  text-align:center;
  margin-bottom:15px;
  font-size:16px;
  color:#333;
}

.trust-item{
  display:flex;
  gap:12px;
  margin-bottom:14px;
  align-items:flex-start;
}

.trust-item i{
  font-size:22px;
  color:#e53935;
  margin-top:3px;
}

.trust-item b{
  font-size:14px;
  color:#222;
}

.trust-item p{
  margin:4px 0 0;
  font-size:12px;
  color:#666;
}

.pay-block{margin-bottom:14px}
.pay-row{font-size:14px;margin-bottom:6px}

.copy-btn{
  width:100%;
  background:#ff7043;
  color:#fff;
  border:none;
  padding:11px;
  border-radius:10px;
  font-size:14px;
  font-weight:bold;
  cursor:pointer;
}
.copy-btn:active{transform:scale(0.97)}

.qr-box{
  margin:16px auto 12px;
  background:#fff;
  padding:14px;
  border-radius:16px;
  width:100%;
  display:flex;
  flex-direction:column;
  align-items:center;
}

.qr-box img{
  width:100%;
  max-width:220px;
  display:block;
}

.transfer-box{
  width:100%;
  margin-top:12px;
  padding:14px;
  border-radius:14px;
  background:#fff8e1;
  border:2px dashed #ff9800;
  text-align:center;
}

.transfer-label{
  font-size:13px;
  font-weight:bold;
  color:#e65100;
  margin-bottom:6px;
}

.transfer-content{
  font-size:14px;
  font-weight:bold;
  letter-spacing:0.5px;
  color:#d84315;
  word-break:break-word;
}


/* ===== CHECKBOX ===== */
.confirm-box{margin-top:16px}
.confirm-box input{display:none}

.confirm-box label{
  display:flex;
  align-items:center;
  gap:10px;
  padding:12px;
  border:2px dashed #ccc;
  border-radius:12px;
  cursor:pointer;
  font-weight:bold;
  color:#555;
}

.confirm-box input:checked+label{
  border-color:#4caf50;
  background:#e8f5e9;
  color:#2e7d32;
}

.confirm-box i{font-size:22px}

/* ===== NÚT HỖ TRỢ ===== */
.support-buttons{
  position:fixed;
  right:16px;
  bottom:16px;
  z-index:9999;
  display:flex;
  flex-direction:column;
  gap:10px;
}

.support-btn{
  width:48px;
  height:48px;
  border-radius:50%;
  display:flex;
  align-items:center;
  justify-content:center;
  color:#fff;
  font-size:22px;
  text-decoration:none;
  box-shadow:0 6px 15px rgba(0,0,0,.35);
}

.support-zalo{background:#0068ff}
.support-messenger{
  background:linear-gradient(135deg,#00c6ff,#0072ff);
}

/* ===== THÊM CHỌN QUỐC GIA ===== */
.country-select{
  display:flex;
  gap:10px;
  margin-bottom:15px;
}

.country-btn{
  flex:1;
  padding:14px;
  border-radius:14px;
  border:2px solid #ddd;
  cursor:pointer;
  font-weight:bold;
  font-size:16px;
  background:#f5f5f5;
  color:#555;
  transition:all .25s ease;
}

.country-btn:hover{
  transform:translateY(-2px);
  box-shadow:0 6px 15px rgba(0,0,0,.08);
}


.country-btn.active{
  background:linear-gradient(135deg,#e53935,#ff7043);
  color:#fff;
}
/* ===== SOCIAL PROOF ===== */
.social-proof{
  margin:20px auto;
  padding:16px;
  border-radius:16px;
  background:#ffffff;
  box-shadow:0 6px 18px rgba(0,0,0,.06);
  text-align:center;
  max-width:600px;
}

.stars{
  color:#ff9800;
  font-size:20px;
  margin-bottom:8px;
}

.review-text{
  font-size:14px;
  color:#444;
  margin-bottom:10px;
}

.counter-box{
  font-size:14px;
  color:#2e7d32;
  font-weight:bold;
  margin-top:6px;
}

.big-sale{
  margin-top:10px;
  font-size:15px;
  font-weight:bold;
  color:#e53935;
}
  /* ===== GUIDE BUTTONS ===== */
.guide-btn{
  flex:1;
  padding:14px;
  border-radius:14px;
  border:2px solid #ff7043;
  background:#f2f2f2;   /* nền xám nhạt */
  color:#333;           /* chữ đậm */
  font-weight:bold;
  font-size:16px;
  cursor:pointer;
  transition:all .3s ease;
}

.guide-btn:hover{
  transform:translateY(-2px);
  box-shadow:0 6px 15px rgba(0,0,0,.08);
}

.guide-btn.active{
  background:linear-gradient(135deg,#e53935,#ff7043);
  color:#fff;
  box-shadow:0 8px 20px rgba(229,57,53,.35);
}

.guide-content{
  display:none;
  margin-top:10px;
}

.guide-content.active{
  display:block;
}
/* ===== FOOTER ===== */
.footer-info{
  background:#111;
  color:#ddd;
  padding:30px 16px;
  margin-top:40px;
}

.footer-container{
  max-width:600px;
  margin:auto;
  font-size:14px;
  line-height:1.8;
}

.footer-info h3{
  color:#fff;
  margin-bottom:12px;
}

.footer-info b{
  color:#ff7043;
}

.footer-info p{
  margin:6px 0;
}

.bo-cong-thuong{
  margin-top:12px;
}

.bo-cong-thuong img{
  width:150px;
  background:#fff;
  padding:6px;
  border-radius:8px;
}

.copyright{
  margin-top:20px;
  font-size:12px;
  color:#888;
  text-align:center;
}
  /* ===== POPUP THÔNG BÁO ĐẦU TRANG ===== */
.welcome-popup{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.65);
  display:none;
  align-items:center;
  justify-content:center;
  z-index:9999999;
}

.welcome-box{
  width:92%;
  max-width:400px;
  background:#fff;
  border-radius:18px;
  padding:22px;
  animation:fadeIn .3s ease;
  position:relative;
}

.welcome-box h3{
  margin:0 0 12px;
  font-size:18px;
}

.welcome-box p{
  font-size:14px;
  margin:6px 0;
  line-height:1.6;
}

.close-welcome{
  position:absolute;
  top:10px;
  right:14px;
  font-size:18px;
  cursor:pointer;
  color:#999;
}

.welcome-actions{
  display:flex;
  justify-content:space-between;
  margin-top:18px;
}

.btn-later{
  background:none;
  border:none;
  color:#6c2bd9;
  font-weight:bold;
  cursor:pointer;
}

.btn-ok{
  background:linear-gradient(135deg,#e53935,#ff7043);
  color:#fff;
  border:none;
  padding:10px 18px;
  border-radius:10px;
  font-weight:bold;
  cursor:pointer;
}
  /* ===== POPUP THÀNH CÔNG ===== */
/* ===== POPUP ===== */
.custom-popup{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.6);
  display:none;
  align-items:center;
  justify-content:center;
  z-index:999999;
}

.popup-box{
  width:90%;
  max-width:380px;
  background:#fff;
  border-radius:18px;
  padding:25px 20px;
  text-align:center;
  animation:fadeIn .3s ease;
}

.popup-icon{
  font-size:50px;
  color:#2ecc71;
  margin-bottom:10px;
}

.popup-box button{
  margin-top:18px;
  padding:14px;
  width:100%;
  border:none;
  border-radius:12px;
  font-weight:bold;
  font-size:16px;
  background:linear-gradient(135deg,#e53935,#ff7043);
  color:#fff;
  cursor:pointer;
}
 
@keyframes fadeIn{
  from{transform:scale(.9);opacity:0}
  to{transform:scale(1);opacity:1}
}
  /* ===== HOA RƠI ===== */
.falling-flowers{
  position:fixed;
  inset:0;
  pointer-events:none;
  overflow:hidden;
  z-index:9999;
}

.flower{
  position:absolute;
  top:-20px;
  font-size:20px;
  animation:fall linear forwards;
}

@keyframes fall{
  to{
    transform:translateY(110vh) rotate(360deg);
    opacity:0.7;
  }
}
  /* ===== COUNTRY DROPDOWN ===== */
.country-dropdown{
  position:relative;
  margin-bottom:15px;
}

.country-selected{
  padding:14px;
  border-radius:14px;
  border:2px solid #ff7043;
  font-weight:bold;
  background:#fff;
  cursor:pointer;
  display:flex;
  justify-content:space-between;
  align-items:center;
  box-shadow:0 6px 15px rgba(0,0,0,.08);
}

.country-list{
  position:absolute;
  width:100%;
  background:#fff;
  border-radius:14px;
  box-shadow:0 10px 25px rgba(0,0,0,.15);
  margin-top:8px;
  display:none;
  z-index:999;
  overflow:hidden;
}

.country-list div{
  padding:12px;
  cursor:pointer;
  transition:.2s;
}

.country-list div:hover{
  background:#fff3e0;
}
  .pay-btn{
  width:100%;
  padding:15px;
  border:none;
  border-radius:14px;
  background:linear-gradient(45deg,#ff512f,#dd2476);
  color:#fff;
  font-size:16px;
  font-weight:bold;
  margin-top:15px;
  cursor:pointer;
  box-shadow:0 5px 15px rgba(0,0,0,0.2);
  transition:0.3s;
}

.pay-btn:hover{
  transform:translateY(-2px);
}
  /* ===== DARK MODE ===== */
.theme-btn{
  position:fixed;
  top:15px;
  right:15px;
  width:42px;
  height:42px;
  border-radius:50%;
  border:none;
  background:#ffffff;
  font-size:18px;
  cursor:pointer;
  display:flex;
  align-items:center;
  justify-content:center;
  box-shadow:0 4px 12px rgba(0,0,0,0.25);
  z-index:9999;
  transition:0.3s;
}

.theme-btn:hover{
  transform:scale(1.1);
}

.theme-btn:hover{
  transform:scale(1.1);
}

/* Khi bật dark */
body.dark-mode{
  background:#121212 !important;
  color:#f1f1f1 !important;
}

body.dark-mode .card,
body.dark-mode .payment-box,
body.dark-mode .container{
  background:#1e1e1e !important;
  color:#fff !important;
}

body.dark-mode input,
body.dark-mode select{
  background:#2a2a2a !important;
  color:#fff !important;
  border:1px solid #444 !important;
}
  /* ===== FIX POPUP KHI DARK MODE ===== */
body.dark-mode .welcome-box,
body.dark-mode .popup-box{
  background:#1f1f1f !important;
  color:#ffffff !important;
}

body.dark-mode .welcome-box p,
body.dark-mode .welcome-box h3,
body.dark-mode .popup-box p,
body.dark-mode .popup-box h3{
  color:#ffffff !important;
}

body.dark-mode .close-welcome{
  color:#ccc !important;
}
  body.dark-mode .country-selected{
  background:#2a2a2a !important;
  color:#fff !important;
  border:1px solid #444 !important;
}

body.dark-mode .country-list{
  background:#2a2a2a !important;
  color:#fff !important;
}

body.dark-mode .country-list div{
  color:#fff !important;
}
</style>
</head>

<body>

<!-- NÚT BẬT TỐI SÁNG -->
<button id="themeToggle" class="theme-btn">
  🌙
</button>

<div class="banner" id="mainBanner">
  <h1>🌍 eSIM Du Lịch</h1>
  <p>Chọn quốc gia và gói phù hợp</p>
</div>

<div class="container">
<form id="orderForm">
 

<!-- CHỌN QUỐC GIA DROPDOWN -->
<div class="country-dropdown">
  <div class="country-selected" onclick="toggleCountryList()">
    🌍 <span id="selectedCountryText">Chọn quốc gia bạn muốn đến</span>
    <i class="fa-solid fa-chevron-down"></i>
  </div>

  <div class="country-list" id="countryList">
    <div onclick="selectCountry('japan','🇯🇵 Nhật Bản - SoftBank')">
      🇯🇵 Nhật Bản - SoftBank
    </div>
    <div onclick="selectCountry('vietnam','🇻🇳 Việt Nam')">
      🇻🇳 Việt Nam
    </div>
  </div>
</div>
<select id="package" name="Goi_eSIM" onchange="updateQR()" disabled>
  <option value="">Chọn thời gian sử dụng eSIM</option>
</select>

<div class="price" id="priceText">Giá: 150.000đ</div>

<input type="email" id="email" name="Email_khach"
 placeholder="Nhập email nhận eSIM"
 required oninput="updateQR()">
 <button type="button" onclick="showPayment()" style="margin-top:15px;">
  💳 Thanh toán ngay
</button>

<div id="paymentSection" style="display:none;">
  <div class="note">
    <h3>💳 Thanh toán QR MB Bank</h3>

    <div class="pay-block">
      <div class="pay-row">
        <b>Số TK:</b> <span id="stkText">1807200320033</span>
      </div>
      <button type="button" class="copy-btn" onclick="copyText('stkText')">
        Sao chép số TK
      </button>
    </div>

    <div class="pay-block">
      <div class="pay-row">
        <b>Chủ TK:</b> <span id="ctkText">DO THANH CHUNG</span>
      </div>
      <button type="button" class="copy-btn" onclick="copyText('ctkText')">
        Sao chép chủ TK
      </button>
    </div>

  </div>

  <div class="qr-box">
    <img id="qrImage" alt="QR Thanh toán">
    <div class="transfer-box">
  <div class="transfer-label">📌 Nội dung chuyển khoản</div>
  <div class="transfer-content" id="transferText"></div>
</div>
  </div>

  <button type="button" class="copy-btn" onclick="copyText('transferText')">
    Sao chép nội dung chuyển khoản
  </button>

  <p style="margin-top:8px;font-size:12px;color:#c0392b;text-align:center">
  ⚠️ Vui lòng điền đúng nội dung chuyển khoản để được xử lý nhanh
</p>
</div>

<div class="confirm-box">
  <input type="checkbox" id="paidCheck">
  <label for="paidCheck">
    <i class="fa-solid fa-circle-check"></i>
    Thanh toán và đồng ý điều khoản!
  </label>
</div>



<button type="button" onclick="submitOrder()">Đặt mua eSIM</button>
</form>
</div>
<!-- NÚT HỖ TRỢ -->
<div class="support-buttons">
  <a href="https://zalo.me/0858712745" 
     class="support-btn support-zalo" 
     target="_blank">
    <i class="fa-solid fa-comment-dots"></i>
  </a>

  <a href="https://www.facebook.com/profile.php?id=100083581842218"
     class="support-btn support-messenger"
     target="_blank">
    <i class="fa-brands fa-facebook-messenger"></i>
  </a>
</div>

<script>
const ACCOUNT="1807200320033";
const emailInput=document.getElementById("email");
let currentCountry="";

const vietnamPackages=[
  {name:"7 ngày – 4GB/ngày",price:90000},
  {name:"15 ngày – 6GB/ngày",price:150000},
  {name:"30 ngày – 8GB/ngày",price:250000}
];

const japanPackages=[
  {name:"3 ngày – 1GB/ngày",price:150000},
  {name:"5 ngày – 2GB/ngày",price:230000},
  {name:"7 ngày – 5GB",price:320000},
  {name:"10 ngày – Không giới hạn",price:450000}
];

function changeCountry(country,btn){
  currentCountry=country;
  const banner=document.getElementById("mainBanner");

if(country==="japan"){
  banner.style.backgroundImage=
  "url('https://i.imgur.com/yA0uNyA.jpeg')";
}else{
  banner.style.backgroundImage=
  "url('https://images.unsplash.com/photo-1528127269322-539801943592')";
}
  document.querySelectorAll(".country-btn").forEach(b=>b.classList.remove("active"));
  btn.classList.add("active");

  const pkgSelect=document.getElementById("package");
  pkgSelect.innerHTML="";

  const list=country==="japan"?japanPackages:vietnamPackages;

  list.forEach(p=>{
    const option=document.createElement("option");
    option.textContent=p.name;
    option.dataset.price=p.price;
    pkgSelect.appendChild(option);
  });

  updateQR();
}
function updateQR(){

  if(!currentCountry){
    document.getElementById("priceText").innerText = "Vui lòng chọn quốc gia trước";
    document.getElementById("transferText").innerText = "";
    document.getElementById("qrImage").src = "";
    return;
  }

  const pkg=document.getElementById("package");

  if(!pkg.value){
    document.getElementById("priceText").innerText = "Chọn thời gian sử dụng eSIM";
    return;
  }

  const price=pkg.options[pkg.selectedIndex].dataset.price;
  const email=emailInput.value||"CHUA_CO_EMAIL";

  const content=`ESIM ${currentCountry.toUpperCase()} | ${price} | ${email}`;

  document.getElementById("priceText").innerText=
  "Giá: "+Number(price).toLocaleString("vi-VN")+"đ";

  document.getElementById("transferText").innerText=content;

  document.getElementById("qrImage").src=
  `https://img.vietqr.io/image/MB-${ACCOUNT}-qr_only.png?amount=${price}&addInfo=${encodeURIComponent(content)}`;
  const payBtn = document.querySelector(".pay-btn");
if(currentCountry && pkg.value){
  payBtn.style.display="block";
}else{
  payBtn.style.display="none";
}
}

function copyText(id){
  navigator.clipboard.writeText(document.getElementById(id).innerText);
}

function submitOrder(){
  const paidCheck = document.getElementById("paidCheck");

  if(!paidCheck.checked){
    alert("⚠️ Vui lòng xác nhận đã thanh toán");
    return;
  }

  document.getElementById("successPopup").style.display="flex";
}

function closeSuccessPopup(){
  document.getElementById("successPopup").style.display="none";
}
  
updateQR();

function randomViewer(){
  const el=document.getElementById("viewerCount");
  setInterval(()=>{
    const random=120+Math.floor(Math.random()*20);
    el.innerText=random;
  },3000);
}

randomViewer();

function showGuide(type, btn){
  document.querySelectorAll(".guide-btn").forEach(b=>b.classList.remove("active"));
  btn.classList.add("active");

  document.querySelectorAll(".guide-content").forEach(c=>c.classList.remove("active"));
  document.getElementById(type).classList.add("active");
}
  // ===== POPUP CHÀO MỪNG =====
function closeWelcome(){
  const popup = document.getElementById("welcomePopup");
  if(popup){
    popup.style.display = "none";
  }
}

function hide15Minutes(){
  localStorage.setItem("hideWelcome", Date.now());
  closeWelcome();
}

window.addEventListener("DOMContentLoaded", function(){
  const popup = document.getElementById("welcomePopup");
  const hideTime = localStorage.getItem("hideWelcome");

  if(!hideTime){
    popup.style.display = "flex";
  } else {
    const diff = Date.now() - hideTime;
    if(diff > 15 * 60 * 1000){
      popup.style.display = "flex";
    }
  }
});

function hide15Minutes(){
  localStorage.setItem("hideWelcome", Date.now());
  closeWelcome();
}

window.addEventListener("load",function(){
  const hideTime = localStorage.getItem("hideWelcome");
  if(hideTime){
    const diff = Date.now() - hideTime;
    if(diff < 15 * 60 * 1000){
      document.getElementById("welcomePopup").style.display="none";
    }
  }
});
// ===== HIỆU ỨNG HOA RƠI =====
function createFlower(){
  const container = document.getElementById("flowerContainer");
  const flower = document.createElement("div");

  flower.classList.add("flower");
  flower.innerHTML = "🌸";

  flower.style.left = Math.random() * 100 + "vw";
  flower.style.animationDuration = (4 + Math.random() * 5) + "s";
  flower.style.fontSize = (16 + Math.random() * 20) + "px";

  container.appendChild(flower);

  setTimeout(() => {
    flower.remove();
  }, 9000);
}

setInterval(createFlower, 500);
  
function toggleCountryList(){
  const list=document.getElementById("countryList");
  list.style.display=list.style.display==="block"?"none":"block";
}

function selectCountry(code,text){
  currentCountry = code;
  const banner = document.getElementById("mainBanner");

if(code === "japan"){
  banner.style.backgroundImage =
  "url('https://images.unsplash.com/photo-1493976040374-85c8e12f0c0e?auto=format&fit=crop&w=1920&q=80')";
}else if(code === "vietnam"){
  banner.style.backgroundImage =
  "url('https://images.unsplash.com/photo-1528127269322-539801943592?auto=format&fit=crop&w=1920&q=80')";
}

  document.getElementById("selectedCountryText").innerText = text;
  document.getElementById("countryList").style.display = "none";

  const pkgSelect = document.getElementById("package");
  pkgSelect.innerHTML = "";
  pkgSelect.disabled = false;

  const list = code === "japan" ? japanPackages : vietnamPackages;

  const defaultOption = document.createElement("option");
  defaultOption.textContent = "Chọn thời gian sử dụng eSIM";
  defaultOption.value = "";
  pkgSelect.appendChild(defaultOption);

  list.forEach(p => {
    const option = document.createElement("option");
    option.textContent = p.name;
    option.dataset.price = p.price;
    pkgSelect.appendChild(option);
  });

  updateQR();
}
  function showPayment(){
  document.getElementById("paymentSection").style.display="block";
  document.getElementById("paymentSection").scrollIntoView({behavior:"smooth"});
}
const toggleBtn = document.getElementById("themeToggle");

// Load trạng thái cũ
if(localStorage.getItem("theme") === "dark"){
  document.body.classList.add("dark-mode");
  toggleBtn.innerText = "☀️";
}

toggleBtn.onclick = function(){
  document.body.classList.toggle("dark-mode");

  if(document.body.classList.contains("dark-mode")){
    toggleBtn.innerText = "☀️";
    localStorage.setItem("theme","dark");
  }else{
    toggleBtn.innerText = "🌙";
    localStorage.setItem("theme","light");
  }
};
</script>
<div class="guide-box">
  <h3>📲 Hướng dẫn cài đặt eSIM</h3>

  <div class="guide-buttons">
    <button type="button" class="guide-btn active" onclick="showGuide('iphone', this)">
      🍎 iPhone
    </button>
    <button type="button" class="guide-btn" onclick="showGuide('android', this)">
      🤖 Android
    </button>
  </div>

  <!-- iPhone -->
  <div id="iphone" class="guide-content active">
    <div class="guide-step">
      <i class="fa-solid fa-envelope"></i>
      <div>
        <b>Bước 1:</b>
        <p>Mở email và nhận mã QR eSIM.</p>
      </div>
    </div>

    <div class="guide-step">
      <i class="fa-solid fa-qrcode"></i>
      <div>
        <b>Bước 2:</b>
        <p>Cài đặt → Di động → Thêm eSIM → Quét mã QR.</p>
      </div>
    </div>

    <div class="guide-step">
      <i class="fa-solid fa-wifi"></i>
      <div>
        <b>Bước 3:</b>
        <p>Bật chuyển vùng dữ liệu và bắt đầu sử dụng.</p>
      </div>
    </div>
  </div>

  <!-- Android -->
  <div id="android" class="guide-content">
    <div class="guide-step">
      <i class="fa-solid fa-envelope"></i>
      <div>
        <b>Bước 1:</b>
        <p>Mở email nhận mã QR eSIM.</p>
      </div>
    </div>

    <div class="guide-step">
      <i class="fa-solid fa-qrcode"></i>
      <div>
        <b>Bước 2:</b>
        <p>Cài đặt → Kết nối → SIM → Thêm eSIM → Quét mã QR.</p>
      </div>
    </div>

    <div class="guide-step">
      <i class="fa-solid fa-wifi"></i>
      <div>
        <b>Bước 3:</b>
        <p>Bật dữ liệu di động và sử dụng internet.</p>
      </div>
    </div>
  </div>
</div>
<div class="trust-box">
  <h3>🔒 Cam kết - Nhận Esim ngay sau khi thanh toán</h3>

  <div class="trust-item">
    <i class="fa-solid fa-shield-halved"></i>
    <div>
      <b>Kích hoạt nhanh chỉ trong 30 giây</b>
      <p>QR eSIM được gửi tự động qua email sau khi xác nhận thanh toán.</p>
    </div>
  </div>

  <div class="trust-item">
    <i class="fa-solid fa-bolt"></i>
    <div>
      <b>Tốc độ cao – Không giới hạn data</b>
      <p>Sử dụng ổn định tại sân bay, tàu điện, khách sạn.</p>
    </div>
  </div>

  <div class="trust-item">
    <i class="fa-solid fa-headset"></i>
    <div>
      <b>Hỗ trợ 24/7</b>
      <p>Liên hệ Zalo hoặc Messenger bên dưới để được hỗ trợ nhanh 24/24.</p>
    </div>
  </div>
</div>
<div class="social-proof">

  <div class="stars">
    ⭐⭐⭐⭐⭐
  </div>

  <div class="review-text">
    Hơn 19.200+ khách hàng hài lòng khi sử dụng eSIM tại shop
  </div>

  <div class="counter-box">
    👥 Khách đang xem: <span id="viewerCount">126</span>
  </div>

  <div class="big-sale">
    🏆 Đã bán <span id="saleCount">1298</span> đơn tháng này
  </div>

</div>
<footer class="footer-info">
  <div class="footer-container">
    
    <h3>🏢 Thông tin công ty</h3>

    <p><b>Tên giao dịch:</b> Chung Thành</p>
    <p><b>Địa chỉ:</b> T11 Time City, Hai Bà Trưng, Hà Nội</p>
    <p><b>Email:</b> dothanhchung@gmail.com</p>
    <p><b>Hotline / Zalo:</b> 0858.7127.45</p>

  <p style="font-size:13px;color:#666;margin-top:8px">
  Cam kết hoàn tiền 100% nếu Esim bị lỗi!
</p>

    <p class="copyright">
      © 2026 eSIM Travel. All rights reserved.
    </p>

  </div>
</footer>
<!-- POPUP THÔNG BÁO KHI VÀO WEB -->
<div class="welcome-popup" id="welcomePopup">
  <div class="welcome-box">
    <div class="close-welcome" onclick="closeWelcome()">✕</div>

    <h3>🔔 Thông báo từ hệ thống</h3>

    <p>Xin chào quý anh/chị,</p>
    <p>Nếu cần hỗ trợ hoặc tư vấn eSIM vui lòng liên hệ:</p>

    <p><b>Zalo:</b> 0858.7127.45</p>
    <p><b>Nhóm Zalo:</b> 
      <a href="https://zalo.me/0858712745" target="_blank">
        Tham gia tại đây
      </a>
    </p>

    <div class="welcome-actions">
      <button class="btn-later" onclick="hide15Minutes()">Tắt 15 phút</button>
      <button class="btn-ok" onclick="closeWelcome()">Đã hiểu</button>
    </div>
  </div>
</div>

<!-- POPUP THÔNG BÁO -->
<div class="custom-popup" id="successPopup">
  <div class="popup-box">
    <div class="popup-icon">
      <i class="fa-solid fa-circle-check"></i>
    </div>
    <h3>Đặt hàng thành công!</h3>
    <p>QR eSIM sẽ được gửi qua email của bạn trong ít phút.</p>
    <button onclick="closeSuccessPopup()">OK</button>
  </div>
</div>
<div class="falling-flowers" id="flowerContainer"></div>
</body>
</html>
