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

header,.Header,#header,#Header1,.header,.header-wrapper{
  display:none!important;
}

.banner{
  width:100%;
  background:linear-gradient(135deg,#d32f2f,#ff7043);
  color:#fff;
  padding:26px 16px 40px;
  text-align:center;
}
.banner h1{margin:0;font-size:26px}
.banner p{margin-top:6px;font-size:15px;opacity:.95}

.container{
  width:100%;
  max-width:600px;
  margin:0 auto 28px;
  background:#fff;
  padding:16px;
  border-radius:16px;
  box-shadow:0 10px 25px rgba(0,0,0,.12);
}

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

.note{
  width:100%;
  background:#fff7d6;
  padding:14px;
  border-radius:14px;
  margin-top:14px;
  font-size:13px;
}

.note h3{
  margin:0 0 8px;
  font-size:15px;
}

.note p{
  margin:6px 0;
  font-size:13px;
  display:flex;
  align-items:center;
  gap:6px;
  flex-wrap:wrap;
}

.copy-btn{
  padding:4px 8px;
  font-size:12px;
  border:none;
  border-radius:6px;
  background:#4caf50;
  color:#fff;
  cursor:pointer;
}

.qr-box{
  width:100%;
  margin-top:14px;
  display:flex;
  flex-direction:column;
  align-items:center;
}

.qr-box img{
  width:100%;
  max-width:280px;
  border-radius:14px;
  background:#fff;
  padding:10px;
}

.transfer-content{
  width:100%;
  max-width:320px;
  background:#eee;
  padding:8px;
  border-radius:8px;
  font-size:11px;
  text-align:center;
  margin-top:8px;
  word-break:break-word;
}

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
</style>
</head>

<body>

<div class="banner">
  <h1>🇯🇵 eSIM Nhật Bản</h1>
  <p>Internet tốc độ cao • Nhận QR qua email • Không cần SIM vật lý</p>
</div>

<div class="container">
<form id="orderForm">

<select id="package" onchange="updateQR()">
  <option data-price="150000">3 ngày – 1GB/ngày</option>
  <option data-price="230000">5 ngày – 2GB/ngày</option>
  <option data-price="320000">7 ngày – 5GB</option>
  <option data-price="450000">10 ngày – Không giới hạn</option>
</select>

<div class="price" id="priceText">Giá: 150.000đ</div>

<input type="email" id="email"
 placeholder="Nhập email nhận eSIM"
 required
 oninput="updateQR()">

<div class="note">
  <h3>💳 Thanh toán QR MB Bank</h3>

  <p><b>Số TK:</b> 1807200320033
    <button type="button" class="copy-btn" onclick="copyText('stk')">📋</button>
  </p>

  <p><b>Chủ TK:</b> DO THANH CHUNG</p>

  <div class="qr-box">
    <img id="qrImage">
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

<button type="button" onclick="submitOrder()">Đặt mua eSIM</button>
</form>
</div>

<script>
const ACCOUNT = "1807200320033";

function updateQR(){
  const pkg = document.getElementById("package");
  const price = pkg.options[pkg.selectedIndex].dataset.price;
  const email = document.getElementById("email").value.trim() || "chua-nhap-email";

  const content = `ESIM JAPAN | ${price} | ${email}`;

  document.getElementById("priceText").innerText =
    "Giá: " + Number(price).toLocaleString("vi-VN") + "đ";

  document.getElementById("transferText").innerText = content;

  document.getElementById("qrImage").src =
    `https://img.vietqr.io/image/MB-${ACCOUNT}-qr_only.png?amount=${price}&addInfo=${encodeURIComponent(content)}`;
}

updateQR();

function submitOrder(){
  if(!paidCheck.checked){
    alert("⚠️ Vui lòng xác nhận đã thanh toán");
    return;
  }
  alert("✅ Đã ghi nhận đơn hàng! Vui lòng chuyển khoản đúng nội dung để xử lý nhanh.");
}
</script>

</body>
</html>
</body>
</html>
