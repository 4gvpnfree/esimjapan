<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>eSIM Nhật Bản – Internet du lịch</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
*{box-sizing:border-box}

body{
  margin:0;
  font-family:Arial,sans-serif;
  background:linear-gradient(180deg,#f0f6ff,#f9f9f9);
}

/* ẨN HEADER BLOGGER */
header,.Header,#header,#Header1,.header,.header-wrapper{
  display:none!important;
}

/* ===== BANNER ===== */
.banner{
  background:linear-gradient(135deg,#d32f2f,#ff7043);
  color:#fff;
  padding:28px 16px 42px;
  text-align:center;
}
.banner h1{margin:0;font-size:26px}
.banner p{margin-top:6px;font-size:15px;opacity:.95}

/* ===== CONTAINER (KHÓA GIỮA) ===== */
.container{
  max-width:600px;
  margin:0 auto 40px;
  padding:16px;
  background:#fff;
  border-radius:18px;
  box-shadow:0 12px 30px rgba(0,0,0,.12);
}

/* ===== FORM ===== */
select,input,button{
  width:100%;
  padding:12px;
  margin-top:12px;
  font-size:16px;
}

button{
  background:linear-gradient(135deg,#e53935,#ff7043);
  color:#fff;
  border:none;
  border-radius:12px;
  font-weight:bold;
  cursor:pointer;
}

.price{
  text-align:center;
  font-size:20px;
  font-weight:bold;
  color:#e53935;
  margin-top:12px;
}

/* ===== KHỐI THANH TOÁN (FIX LỆCH) ===== */
.note{
  background:#fff7d6;
  padding:16px;
  border-radius:16px;
  margin:20px auto 0;
  width:100%;
}

.note h3{
  text-align:center;
  margin:0 0 16px;
  font-size:16px;
}

.pay-block{margin-bottom:14px}
.pay-row{font-size:14px;margin-bottom:6px}

/* ===== NÚT COPY ===== */
.copy-btn{
  width:100%;
  background:#ff7043;
  padding:11px;
  border-radius:10px;
  color:#fff;
  font-weight:bold;
  border:none;
}
.copy-btn:active{transform:scale(.97)}

/* ===== QR KHÓA CỨNG GIỮA ===== */
.qr-wrap{
  width:100%;
  display:flex;
  justify-content:center;
}

.qr-box{
  background:#fff;
  padding:14px;
  border-radius:16px;
  width:240px;
  text-align:center;
  box-shadow:0 6px 16px rgba(0,0,0,.15);
}

.qr-box img{
  width:200px;
  display:block;
  margin:0 auto;
}

.transfer-content{
  margin-top:10px;
  background:#f1f1f1;
  padding:8px;
  border-radius:8px;
  font-size:12px;
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
}

.confirm-box input:checked+label{
  border-color:#4caf50;
  background:#e8f5e9;
  color:#2e7d32;
}

/* ===== NÚT HỖ TRỢ ===== */
.support-buttons{
  position:fixed;
  right:16px;
  bottom:16px;
  display:flex;
  flex-direction:column;
  gap:10px;
  z-index:999;
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
  box-shadow:0 6px 14px rgba(0,0,0,.35);
}
.support-zalo{background:#0068ff}
.support-messenger{background:#0078ff}
</style>
</head>

<body>

<div class="banner">
  <h1>🇯🇵 eSIM Nhật Bản</h1>
  <p>Internet tốc độ cao • Nhận QR qua email • Không cần SIM vật lý</p>
</div>

<div class="container">
<form id="orderForm" action="https://formsubmit.co/chungthanh18072003@gmail.com" method="POST">

<select id="package" onchange="updateQR()">
  <option data-price="150000">3 ngày – 1GB/ngày</option>
  <option data-price="230000">5 ngày – 2GB/ngày</option>
  <option data-price="320000">7 ngày – 5GB</option>
  <option data-price="450000">10 ngày – Không giới hạn</option>
</select>

<div class="price" id="priceText">Giá: 150.000đ</div>

<input id="email" type="email" placeholder="Nhập email nhận eSIM" required oninput="updateQR()">

<div class="note">
  <h3>💳 Thanh toán QR MB Bank</h3>

  <div class="pay-block">
    <div class="pay-row"><b>Số TK:</b> <span id="stkText">1807200320033</span></div>
    <button type="button" class="copy-btn" onclick="copyText('stkText')">Sao chép số TK</button>
  </div>

  <div class="pay-block">
    <div class="pay-row"><b>Chủ TK:</b> DO THANH CHUNG</div>
  </div>

  <div class="qr-wrap">
    <div class="qr-box">
      <img id="qrImage">
      <div class="transfer-content" id="transferText"></div>
    </div>
  </div>

  <button type="button" class="copy-btn" onclick="copyText('transferText')">
    Sao chép nội dung chuyển khoản
  </button>

  <p style="text-align:center;font-size:12px;color:#c0392b;margin-top:8px">
    ⚠️ Vui lòng điền đúng nội dung chuyển khoản để được xử lý nhanh
  </p>
</div>

<div class="confirm-box">
  <input type="checkbox" id="paidCheck">
  <label for="paidCheck">
    <i class="fa-solid fa-circle-check"></i> Tôi đã thanh toán
  </label>
</div>

<button type="button" onclick="submitOrder()">Đặt mua eSIM</button>
</form>
</div>

<div class="support-buttons">
  <a href="https://zalo.me/0858712745" class="support-btn support-zalo" target="_blank">
    <i class="fa-solid fa-comment"></i>
  </a>
  <a href="https://www.facebook.com/profile.php?id=100083581842218"
     class="support-btn support-messenger" target="_blank">
    <i class="fa-brands fa-facebook-messenger"></i>
  </a>
</div>

<script>
const ACCOUNT="1807200320033";

function updateQR(){
  const pkg=document.getElementById("package");
  const price=pkg.options[pkg.selectedIndex].dataset.price;
  const email=document.getElementById("email").value || "CHUA_CO_EMAIL";
  const content=`ESIM JAPAN | ${price} | ${email}`;

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
    alert("Vui lòng xác nhận đã thanh toán");
    return;
  }
  alert("Đã ghi nhận đơn hàng!");
}

updateQR();
</script>

</body>
</html>
