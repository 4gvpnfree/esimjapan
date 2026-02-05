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
header,.Header,#header,#Header1{display:none!important}

/* ===== BANNER ===== */
.banner{
  background:linear-gradient(135deg,#d32f2f,#ff7043);
  color:#fff;
  padding:26px 16px 36px;
  text-align:center;
}
.banner h1{margin:0;font-size:26px}
.banner p{margin-top:6px;font-size:15px}

/* ===== CONTAINER ===== */
.container{
  max-width:600px;
  margin:-24px auto 28px;
  background:#fff;
  padding:16px;
  border-radius:18px;
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

/* ===== THANH TOÁN ===== */
.note{
  background:#fff7d6;
  padding:16px;
  border-radius:16px;
  margin-top:18px;
  font-size:13px;
}

.note h3{
  margin:0 0 10px;
  font-size:16px;
}

/* ===== COPY BLOCK ===== */
.pay-block{margin-bottom:14px}
.pay-row{font-size:14px;margin-bottom:6px}

.copy-btn{
  width:100%;
  background:#ff7043;
  color:#fff;
  padding:12px;
  border:none;
  border-radius:12px;
  font-size:15px;
  font-weight:bold;
  margin-top:6px;
}

/* ===== QR ===== */
.qr-box{
  margin:16px 0 12px;
  background:#fff;
  padding:14px;
  border-radius:14px;
  display:flex;
  flex-direction:column;
  align-items:center;
}

.qr-box img{
  width:100%;
  max-width:240px;
}

.transfer-content{
  margin-top:10px;
  width:100%;
  background:#f1f1f1;
  padding:8px;
  border-radius:8px;
  font-size:12px;
  text-align:center;
}

/* ===== CHECKBOX ===== */
.confirm-box{margin-top:16px}
.confirm-box input{display:none}

.confirm-box label{
  display:flex;
  align-items:center;
  gap:10px;
  padding:14px;
  border:2px dashed #ccc;
  border-radius:14px;
  cursor:pointer;
  font-weight:bold;
}

.confirm-box input:checked+label{
  border-color:#4caf50;
  background:#e8f5e9;
  color:#2e7d32;
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
 method="POST"
 target="hidden_iframe"
 onsubmit="return false">

<select id="package" onchange="updateQR()">
  <option data-price="150000">3 ngày – 1GB/ngày</option>
  <option data-price="230000">5 ngày – 2GB/ngày</option>
  <option data-price="320000">7 ngày – 5GB</option>
</select>

<div class="price" id="priceText">Giá: 150.000đ</div>

<input type="email" id="email" placeholder="Nhập email nhận eSIM" oninput="updateQR()" required>

<div class="note">
  <h3>💳 Thanh toán QR MB Bank</h3>

  <div class="pay-block">
    <div class="pay-row"><b>Số TK:</b> 1807200320033</div>
    <button type="button" class="copy-btn" onclick="copyText('1807200320033')">Sao chép số TK</button>
  </div>

  <div class="pay-block">
    <div class="pay-row"><b>Chủ TK:</b> DO THANH CHUNG</div>
    <button type="button" class="copy-btn" onclick="copyText('DO THANH CHUNG')">Sao chép chủ TK</button>
  </div>

  <div class="qr-box">
    <img id="qrImage">
    <div class="transfer-content" id="transferText"></div>
  </div>

  <button type="button" class="copy-btn" onclick="copyText(document.getElementById('transferText').innerText)">
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

<input type="hidden" name="_captcha" value="false">

<button type="button" onclick="submitOrder()">Đặt mua eSIM</button>
</form>

<iframe name="hidden_iframe" style="display:none"></iframe>
</div>

<script>
const ACCOUNT="1807200320033";

function updateQR(){
  const pkg=document.getElementById("package");
  const price=pkg.options[pkg.selectedIndex].dataset.price;
  const email=document.getElementById("email").value||"CHUA_CO_EMAIL";
  const content=`ESIM JAPAN | ${price} | ${email}`;

  document.getElementById("priceText").innerText=
    "Giá: "+Number(price).toLocaleString("vi-VN")+"đ";

  document.getElementById("transferText").innerText=content;

  document.getElementById("qrImage").src=
    `https://img.vietqr.io/image/MB-${ACCOUNT}-qr_only.png?amount=${price}&addInfo=${encodeURIComponent(content)}`;
}

function copyText(text){
  navigator.clipboard.writeText(text);
}

function submitOrder(){
  if(!paidCheck.checked){
    alert("⚠️ Vui lòng xác nhận đã thanh toán");
    return;
  }
  alert("✅ Đã ghi nhận đơn hàng!");
  orderForm.submit();
}

updateQR();
</script>

</body>
</html>
