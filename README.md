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

.banner{
  background:linear-gradient(135deg,#d32f2f,#ff7043);
  color:#fff;
  padding:26px 16px 40px;
  text-align:center;
}
.banner h1{margin:0;font-size:26px}
.banner p{margin-top:6px;font-size:15px}

.container{
  max-width:600px;
  margin:0 auto 30px;
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
  background:#fff7d6;
  padding:12px;
  border-radius:12px;
  margin-top:14px;
  font-size:13px;
}

.copy-btn{
  background:#eee;
  border:none;
  border-radius:6px;
  padding:4px 8px;
  margin-left:6px;
  cursor:pointer;
  font-size:12px;
}

.qr-box{
  margin-top:10px;
  text-align:center;
}

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
  word-break:break-word;
}

.confirm-box{
  margin-top:14px;
}
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
  <p>Internet tốc độ cao • Nhận QR qua email</p>
</div>

<div class="container">
<form id="orderForm" action="https://formsubmit.co/chungthanh18072003@gmail.com" method="POST">

<select id="package" name="Goi_eSIM">
  <option data-price="150000">3 ngày – 1GB/ngày</option>
  <option data-price="230000">5 ngày – 2GB/ngày</option>
  <option data-price="320000">7 ngày – 5GB</option>
  <option data-price="450000">10 ngày – Không giới hạn</option>
</select>

<div class="price" id="priceText">Giá: 150.000đ</div>

<input type="email" id="email" name="Email_khach" placeholder="Nhập email nhận eSIM" required>

<div class="note">
  <h3>💳 Thanh toán MB Bank</h3>

  <p>
    <b>Số TK:</b> 1807200320033
    <button type="button" class="copy-btn" onclick="copyText('1807200320033')">📋</button>
  </p>

  <p>
    <b>Chủ TK:</b> DO THANH CHUNG
    <button type="button" class="copy-btn" onclick="copyText('DO THANH CHUNG')">📋</button>
  </p>

  <div class="qr-box">
    <img id="qrImage">
    <div class="transfer-content" id="transferText"></div>

    <button type="button" class="copy-btn" onclick="copyTransfer()">
      📋 Sao chép nội dung chuyển khoản
    </button>

    <p style="color:#c62828;font-weight:bold;margin-top:6px">
      ⚠️ Vui lòng nhập ĐÚNG nội dung chuyển khoản để được xử lý nhanh
    </p>
  </div>
</div>

<div class="confirm-box">
  <input type="checkbox" id="paidCheck">
  <label for="paidCheck">
    <i class="fa-solid fa-circle-check"></i>
    Tôi đã thanh toán
  </label>
</div>

<input type="hidden" name="_captcha" value="false">

<button type="button" onclick="submitOrder()">Đặt mua eSIM</button>
</form>
</div>

<script>
const ACCOUNT="1807200320033";
const pkg=document.getElementById("package");
const email=document.getElementById("email");
const transfer=document.getElementById("transferText");
const form=document.getElementById("orderForm");

function updateQR(){
  const price=pkg.options[pkg.selectedIndex].dataset.price;
  const mail=email.value||"EMAIL";
  const content=`ESIM JAPAN | ${price} | ${mail}`;

  document.getElementById("priceText").innerText=
    "Giá: "+Number(price).toLocaleString("vi-VN")+"đ";

  transfer.innerText=content;

  document.getElementById("qrImage").src=
    `https://img.vietqr.io/image/MB-${ACCOUNT}-qr_only.png?amount=${price}&addInfo=${encodeURIComponent(content)}`;
}

pkg.onchange=updateQR;
email.oninput=updateQR;
updateQR();

function copyText(text){
  const t=document.createElement("textarea");
  t.value=text;
  document.body.appendChild(t);
  t.select();
  document.execCommand("copy");
  document.body.removeChild(t);
  alert("✅ Đã sao chép");
}

function copyTransfer(){
  copyText(transfer.innerText);
}

function submitOrder(){
  if(!paidCheck.checked){
    alert("⚠️ Vui lòng xác nhận đã thanh toán");
    return;
  }

  fetch(form.action,{
    method:"POST",
    body:new FormData(form),
    headers:{Accept:"application/json"}
  }).then(()=>{
    alert("✅ Đã ghi nhận đơn hàng!\nQR eSIM sẽ được gửi qua email.");
    form.reset();
    updateQR();
  });
}
</script>

</body>
</html>
