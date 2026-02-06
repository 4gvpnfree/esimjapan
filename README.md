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
  background:linear-gradient(135deg,#d32f2f,#ff7043);
  color:#fff;
  padding:26px 16px 40px;
  text-align:center;
}
.banner h1{margin:0;font-size:26px}
.banner p{margin-top:6px;font-size:15px;opacity:.95}

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
  background:linear-gradient(135deg,#e53935,#ff7043);
  color:#fff;
  border:none;
  border-radius:10px;
  font-weight:bold;
  cursor:pointer;
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
</style>
</head>

<body>

<div class="banner">
  <h1>🌍 eSIM Du Lịch</h1>
  <p>Chọn quốc gia và gói phù hợp</p>
</div>

<div class="container">
<form id="orderForm">
 

<!-- THÊM CHỌN QUỐC GIA -->
<div class="country-select">
  <button type="button" class="country-btn active" onclick="changeCountry('japan', this)">🇯🇵 Nhật</button>
  <button type="button" class="country-btn" onclick="changeCountry('vietnam', this)">🇻🇳 Việt Nam</button>
</div>

<select id="package" name="Goi_eSIM" onchange="updateQR()">
  <option data-price="150000">3 ngày – 1GB/ngày</option>
  <option data-price="230000">5 ngày – 2GB/ngày</option>
  <option data-price="320000">7 ngày – 5GB</option>
  <option data-price="450000">10 ngày – Không giới hạn</option>
</select>

<div class="price" id="priceText">Giá: 150.000đ</div>

<input type="email" id="email" name="Email_khach"
 placeholder="Nhập email nhận eSIM"
 required oninput="updateQR()">

<div class="note">
  <h3>💳 Thanh toán QR MB Bank</h3>

  <div class="pay-block">
    <div class="pay-row"><b>Số TK:</b> <span id="stkText">1807200320033</span></div>
    <button type="button" class="copy-btn" onclick="copyText('stkText')">Sao chép số TK</button>
  </div>

  <div class="pay-block">
    <div class="pay-row"><b>Chủ TK:</b> <span id="ctkText">DO THANH CHUNG</span></div>
    <button type="button" class="copy-btn" onclick="copyText('ctkText')">Sao chép chủ TK</button>
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
    Tôi đã thanh toán và đồng ý điều khoản
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
let currentCountry="japan";

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
  const pkg=document.getElementById("package");
  const price=pkg.options[pkg.selectedIndex].dataset.price;
  const email=emailInput.value||"CHUA_CO_EMAIL";

  const content=`ESIM ${currentCountry.toUpperCase()} | ${price} | ${email}`;

  document.getElementById("priceText").innerText=
  "Giá: "+Number(price).toLocaleString("vi-VN")+"đ";

  document.getElementById("transferText").innerText=content;

  document.getElementById("qrImage").src=
  `https://img.vietqr.io/image/MB-${ACCOUNT}-qr_only.png?amount=${price}&addInfo=${encodeURIComponent(content)}`;
}

function copyText(id){
  navigator.clipboard.writeText(document.getElementById(id).innerText);
}

function submitOrder(){
  if(!paidCheck.checked){
    alert("⚠️ Vui lòng xác nhận đã thanh toán");
    return;
  }
  alert("✅ Đã ghi nhận đơn hàng! QR eSIM sẽ được gửi qua email.");
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
</script>
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
    Hơn 1.200+ khách hàng hài lòng khi sử dụng eSIM tại shop
  </div>

  <div class="counter-box">
    👥 Khách đang xem: <span id="viewerCount">128</span>
  </div>

  <div class="big-sale">
    🏆 Đã bán <span id="saleCount">1258</span> đơn tháng này
  </div>

</div>

</body>
</html>
