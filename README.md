<!DOCTYPE html>
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

/* ===== CONTAINER (FIX LỆCH DỌC) ===== */
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
  width:100%;
  background:#fff7d6;
  padding:12px;
  border-radius:12px;
  margin-top:14px;
  font-size:13px;
}

.note h3{
  margin:0 0 6px;
  font-size:15px;
}

.note p{
  margin:4px 0;
  font-size:13px;
}

/* ===== QR FIX TUYỆT ĐỐI ===== */
.qr-box{
  width:100%;
  margin-top:10px;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
}

.qr-box img{
  width:100%;
  max-width:240px;
  height:auto;
  display:block;
  margin:0 auto;
  border-radius:12px;
  background:#fff;
  padding:8px;
}

.transfer-content{
  width:100%;
  background:#eee;
  padding:6px;
  border-radius:6px;
  font-size:11px;
  word-break:break-word;
  text-align:center;
  margin-top:6px;
}

/* ===== CHECKBOX ===== */
.confirm-box{margin-top:14px}
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

/* ===== SUPPORT ===== */
.support-buttons{
  position:fixed;
  bottom:14px;
  right:14px;
  z-index:9999;
}

.support-btn{
  width:48px;
  height:48px;
  border-radius:50%;
  margin-top:10px;
  display:flex;
  align-items:center;
  justify-content:center;
  color:#fff;
  font-size:20px;
  text-decoration:none;
  box-shadow:0 6px 15px rgba(0,0,0,.35);
}

.support-zalo{background:#0068ff}
.support-messenger{background:linear-gradient(135deg,#00c6ff,#0072ff)}

/* ===== MOBILE PORTRAIT ===== */
@media (max-width:480px){
  .banner h1{font-size:22px}
  .banner p{font-size:14px}
  .container{
    margin-left:auto;
    margin-right:auto;
  }
}
</style>
</head>

<body>

<div class="banner">
  <h1>🇯🇵 eSIM Nhật Bản</h1>
  <p>Internet tốc độ cao • Nhận QR qua email • Không cần SIM vật lý</p>
</div>

<div class="container">
<form id="orderForm"
 action="https://formsubmit.co/chungthanh18072003@gmail.com"
 method="POST">

<select id="package" name="Goi_eSIM" onchange="updateQR()">
  <option data-price="150000">3 ngày – 1GB/ngày</option>
  <option data-price="230000">5 ngày – 2GB/ngày</option>
  <option data-price="320000">7 ngày – 5GB</option>
  <option data-price="450000">10 ngày – Không giới hạn</option>
</select>

<div class="price" id="priceText">Giá: 150.000đ</div>

<input type="email" id="email" name="Email_khach" placeholder="Nhập email nhận eSIM" required>

<div class="note">
  <h3>💳 Thanh toán QR MB Bank</h3>
  <p><b>Số TK:</b> 1807200320033</p>
  <p><b>Chủ TK:</b> DO THANH CHUNG</p>

  <div class="qr-box">
    <img id="qrImage" alt="QR Thanh toán">
    <div class="transfer-content" id="transferText"></div>
  </div>
</div>

<div class="confirm-box">
  <input type="checkbox" id="paidCheck">
  <label for="paidCheck">
    <i class="fa-solid fa-circle-check"></i>
    Tôi đã thanh toán và đồng ý điều khoản
  </label>
</div>

<input type="hidden" name="_subject" value="🔔 Đơn hàng eSIM Nhật">
<input type="hidden" name="_captcha" value="false">

<button type="button" onclick="submitOrder()">Đặt mua eSIM</button>
</form>
</div>

<div class="support-buttons">
  <a href="https://zalo.me/0858712745" class="support-btn support-zalo" target="_blank">
    <i class="fa-solid fa-comment-dots"></i>
  </a>
  <a href="https://m.me/100083581842218" class="support-btn support-messenger" target="_blank">
    <i class="fa-brands fa-facebook-messenger"></i>
  </a>
</div>

<script>
const ACCOUNT="1807200320033";
const emailInput=document.getElementById("email");

function updateQR(){
  const pkg=document.getElementById("package");
  const price=pkg.options[pkg.selectedIndex].dataset.price;
  const email=emailInput.value||"EMAIL";
  const content=`ESIM JAPAN - ${price} - ${email}`;

  document.getElementById("priceText").innerText =
    "Giá: "+Number(price).toLocaleString("vi-VN")+"đ";

  document.getElementById("transferText").innerText = content;

  /* QR TRẦN – KHÔNG LOGO */
  document.getElementById("qrImage").src =
    `https://img.vietqr.io/image/MB-${ACCOUNT}-qr_only.png?amount=${price}&addInfo=${encodeURIComponent(content)}`;
}
updateQR();

function submitOrder(){
  if(!paidCheck.checked){
    alert("⚠️ Vui lòng xác nhận đã thanh toán");
    return;
  }
  alert("✅ Đã ghi nhận đơn hàng! QR eSIM sẽ được gửi qua email.");
  orderForm.submit();
}
</script>

</body>
</html>
