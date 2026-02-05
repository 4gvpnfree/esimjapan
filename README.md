<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>eSIM Nhật Bản – Internet du lịch</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
*{box-sizing:border-box}
html,body{
  margin:0;padding:0;width:100%;
  font-family:Arial,sans-serif;
  background:linear-gradient(180deg,#eef4ff,#f9f9f9);
}
header{display:none!important}

/* ===== BANNER ===== */
.banner{
  background:linear-gradient(135deg,#c62828,#ff7043);
  color:#fff;
  padding:30px 16px 48px;
  text-align:center;
  border-bottom-left-radius:24px;
  border-bottom-right-radius:24px;
}
.banner h1{margin:0;font-size:28px}
.banner p{margin-top:8px;font-size:15px;opacity:.95}

/* ===== USP ===== */
.usp{
  margin:-26px auto 18px;
  max-width:600px;
  background:#fff;
  border-radius:16px;
  box-shadow:0 8px 20px rgba(0,0,0,.12);
  padding:14px;
}
.usp li{
  list-style:none;
  font-size:14px;
  margin:8px 0;
}
.usp i{color:#4caf50;margin-right:6px}

/* ===== CONTAINER ===== */
.container{
  max-width:600px;
  margin:0 auto 32px;
  background:#fff;
  padding:18px;
  border-radius:18px;
  box-shadow:0 10px 28px rgba(0,0,0,.15);
}

/* FORM */
select,input,button{
  width:100%;padding:12px;margin-top:12px;font-size:16px
}
button{
  background:linear-gradient(135deg,#e53935,#ff7043);
  color:#fff;border:none;border-radius:12px;
  font-weight:bold;cursor:pointer;
  transition:.2s;
}
button:active{transform:scale(.97)}

.price{text-align:center;font-size:20px;font-weight:bold;color:#e53935}

/* PAYMENT */
.note{
  background:#fff7d6;
  padding:18px;border-radius:18px;margin-top:20px
}
.note h3{text-align:center;margin-bottom:14px}

.pay-block{margin-bottom:14px}
.pay-row{font-size:14px;margin-bottom:6px}

.copy-btn{
  background:#ff7043;border:none;color:#fff;
  padding:11px;border-radius:12px;
  font-size:14px;font-weight:bold;
}

.qr-box{
  background:#fff;
  padding:16px;
  border-radius:18px;
  max-width:260px;
  margin:18px auto;
  box-shadow:0 6px 18px rgba(0,0,0,.15);
  display:flex;
  flex-direction:column;
  align-items:center;
}
.qr-box img{width:100%;max-width:220px}
.transfer-content{
  margin-top:10px;
  background:#f1f1f1;
  padding:8px;
  border-radius:8px;
  font-size:12px;
  text-align:center;
}

/* CHECKBOX */
.confirm-box{margin-top:18px}
.confirm-box input{display:none}
.confirm-box label{
  display:flex;gap:10px;
  padding:12px;border:2px dashed #ccc;
  border-radius:14px;cursor:pointer;font-weight:bold
}
.confirm-box input:checked+label{
  border-color:#4caf50;background:#e8f5e9;color:#2e7d32
}

/* SUPPORT */
.support-buttons{
  position:fixed;right:16px;bottom:16px;
  display:flex;flex-direction:column;gap:10px;z-index:999
}
.support-btn{
  width:50px;height:50px;border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  color:#fff;font-size:22px;
  box-shadow:0 6px 15px rgba(0,0,0,.35)
}
.support-zalo{background:#0068ff}
.support-messenger{background:linear-gradient(135deg,#00c6ff,#0072ff)}
</style>
</head>

<body>

<div class="banner">
  <h1>🇯🇵 eSIM Nhật Bản</h1>
  <p>Internet tốc độ cao • Nhận QR qua email • Không cần SIM vật lý</p>
</div>

<ul class="usp">
  <li><i class="fa-solid fa-check"></i> Nhận eSIM trong 5–10 phút</li>
  <li><i class="fa-solid fa-check"></i> Hỗ trợ Zalo & Messenger 24/7</li>
  <li><i class="fa-solid fa-check"></i> Không cần SIM vật lý</li>
  <li><i class="fa-solid fa-check"></i> Hoàn tiền nếu không dùng được</li>
</ul>

<div class="container">
<form id="orderForm">

<select id="package" onchange="updateQR()">
  <option data-price="150000">3 ngày – 1GB/ngày</option>
  <option data-price="230000">5 ngày – 2GB/ngày</option>
  <option data-price="320000">7 ngày – 5GB</option>
  <option data-price="450000">10 ngày – Không giới hạn</option>
</select>

<div class="price" id="priceText"></div>

<input type="email" id="email" placeholder="Nhập email nhận eSIM" required oninput="updateQR()">

<div class="note">
<h3>💳 Thanh toán QR MB Bank</h3>

<div class="pay-block">
<b>Số TK:</b> <span id="stkText">1807200320033</span>
<button type="button" class="copy-btn" onclick="copyText('stkText')">Sao chép số TK</button>
</div>

<div class="pay-block">
<b>Chủ TK:</b> <span id="ctkText">DO THANH CHUNG</span>
<button type="button" class="copy-btn" onclick="copyText('ctkText')">Sao chép chủ TK</button>
</div>

<div class="qr-box">
<img id="qrImage">
<div class="transfer-content" id="transferText"></div>
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
<label for="paidCheck"><i class="fa-solid fa-circle-check"></i> Tôi đã thanh toán</label>
</div>

<button type="button" onclick="submitOrder()">Đặt mua eSIM</button>
</form>
</div>

<div class="support-buttons">
<a href="https://zalo.me/0858712745" class="support-btn support-zalo" target="_blank">
<i class="fa-solid fa-comment-dots"></i></a>
<a href="https://www.facebook.com/profile.php?id=100083581842218"
 class="support-btn support-messenger" target="_blank">
<i class="fa-brands fa-facebook-messenger"></i></a>
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
function copyText(id){navigator.clipboard.writeText(document.getElementById(id).innerText)}
function submitOrder(){
 if(!paidCheck.checked){alert("Vui lòng xác nhận đã thanh toán");return}
 alert("✅ Đã ghi nhận đơn hàng! eSIM sẽ được gửi qua email.");
}
updateQR();
</script>

</body>
</html>
