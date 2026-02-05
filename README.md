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
header,.Header,#header,#Header1,.header,.header-wrapper{display:none!important}

.banner{
  background:linear-gradient(135deg,#d32f2f,#ff7043);
  color:#fff;
  padding:26px 16px 40px;
  text-align:center;
}
.container{
  max-width:600px;
  margin:-20px auto 30px;
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
button:disabled{opacity:.6;cursor:not-allowed}

.price{text-align:center;font-size:19px;font-weight:bold;color:#e53935}

.note{
  background:#fff7d6;
  padding:12px;
  border-radius:12px;
  margin-top:14px;
  font-size:13px;
}

.pay-block{margin-bottom:12px}
.copy-btn{
  background:#ff7043;
  color:#fff;
  border:none;
  padding:10px;
  border-radius:10px;
  font-weight:bold;
  cursor:pointer;
  margin-top:6px;
}

.qr-box{text-align:center}
.qr-box img{
  max-width:240px;
  border-radius:12px;
  background:#fff;
  padding:8px;
}

.transfer-content{
  background:#eee;
  padding:6px;
  border-radius:6px;
  font-size:11px;
  margin-top:6px;
}

.confirm-box{margin-top:14px}
.confirm-box input{display:none}
.confirm-box label{
  display:flex;
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

.loading{
  display:none;
  margin-top:12px;
  text-align:center;
  color:#e53935;
  font-weight:bold;
}
</style>
</head>

<body>

<div class="banner">
  <h1>🇯🇵 eSIM Nhật Bản</h1>
  <p>Internet tốc độ cao • Nhận QR qua email • Không cần SIM vật lý</p>
</div>

<div class="container">
<form id="orderForm" action="https://formsubmit.co/chungthanh18072003@gmail.com" method="POST">

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
<b>Số TK:</b> <span id="stkText">1807200320033</span>
<button type="button" class="copy-btn" onclick="copyText('stkText')">Sao chép số TK</button>
</div>

<div class="pay-block">
<b>Chủ TK:</b> <span id="ctkText">DO THANH CHUNG</span>
<button type="button" class="copy-btn" onclick="copyText('ctkText')">Sao chép chủ TK</button>
</div>

<div class="qr-box">
<img id="qrImage" alt="QR Thanh toán">
<div class="transfer-content" id="transferText"></div>
</div>

<button type="button" class="copy-btn" onclick="copyText('transferText')">
Sao chép nội dung chuyển khoản
</button>

<p style="font-size:12px;color:#c0392b;text-align:center;margin-top:6px">
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

<input type="hidden" name="_subject" value="🔔 Đơn hàng eSIM Nhật">
<input type="hidden" name="_captcha" value="false">

<button type="button" id="submitBtn" onclick="submitOrder()">Đặt mua eSIM</button>
<div class="loading" id="loadingText">⏳ Đang gửi đơn hàng...</div>

</form>
</div>

<script>
const ACCOUNT = "1807200320033";

const form = document.getElementById("orderForm");
const btn = document.getElementById("submitBtn");
const loading = document.getElementById("loadingText");

const packageSelect = document.getElementById("package");
const emailInput = document.getElementById("email");
const priceText = document.getElementById("priceText");
const transferText = document.getElementById("transferText");
const qrImage = document.getElementById("qrImage");
const paidCheck = document.getElementById("paidCheck");

function updateQR(){
  const option = packageSelect.options[packageSelect.selectedIndex];
  const price = option.dataset.price;
  const email = emailInput.value || "CHUA_CO_EMAIL";

  const content = `ESIM JAPAN | ${price} | ${email}`;

  priceText.innerText =
    "Giá: " + Number(price).toLocaleString("vi-VN") + "đ";

  transferText.innerText = content;

  qrImage.src =
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

  btn.disabled = true;
  loading.style.display = "block";

  fetch(form.action,{
    method:"POST",
    body:new FormData(form),
    headers:{Accept:"application/json"}
  })
  .then(()=>{
    alert("✅ Đã ghi nhận đơn hàng! QR eSIM sẽ được gửi qua email.");
  })
  .catch(()=>{
    alert("⚠️ Có lỗi khi gửi đơn, vui lòng thử lại");
  })
  .finally(()=>{
    btn.disabled = false;
    loading.style.display = "none";
  });
}

updateQR();
</script>

</body>
</html>
