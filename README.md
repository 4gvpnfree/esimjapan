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
  margin:0;padding:0;width:100%;overflow-x:hidden;
  font-family:Arial,sans-serif;
  background:linear-gradient(180deg,#f0f6ff,#f9f9f9);
}
header,.Header,#header,#Header1,.header,.header-wrapper{display:none!important;}
.banner{
  background:linear-gradient(135deg,#d32f2f,#ff7043);
  color:#fff;padding:26px 16px 40px;text-align:center;
}
.container{
  max-width:600px;margin:0 auto 28px;background:#fff;
  padding:16px;border-radius:16px;
  box-shadow:0 10px 25px rgba(0,0,0,.12);
}
select,input,button{
  width:100%;padding:12px;margin-top:12px;font-size:16px;
}
button{
  background:linear-gradient(135deg,#e53935,#ff7043);
  color:#fff;border:none;border-radius:10px;
  font-weight:bold;cursor:pointer;
}
.price{text-align:center;font-size:19px;font-weight:bold;color:#e53935;margin-top:10px;}
.note{
  background:#fff7d6;padding:12px;border-radius:12px;margin-top:14px;font-size:13px;
}
.copy-btn{
  margin-top:6px;background:#ff7043;color:#fff;border:none;
  border-radius:6px;padding:6px 10px;font-size:12px;font-weight:bold;
}
.notice{
  margin-top:8px;font-size:12px;color:#d32f2f;font-weight:bold;text-align:center;
}
.qr-box{margin-top:10px;display:flex;flex-direction:column;align-items:center;}
.qr-box img{max-width:240px;border-radius:12px;background:#fff;padding:8px;}
.transfer-content{
  width:100%;background:#eee;padding:6px;border-radius:6px;
  font-size:11px;text-align:center;margin-top:6px;
}
.confirm-box{margin-top:14px}
.confirm-box input{display:none}
.confirm-box label{
  display:flex;align-items:center;gap:10px;padding:12px;
  border:2px dashed #ccc;border-radius:12px;cursor:pointer;
  font-weight:bold;color:#555;
}
.confirm-box input:checked+label{
  border-color:#4caf50;background:#e8f5e9;color:#2e7d32;
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

<select id="package" name="Goi_eSIM">
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
  <button type="button" class="copy-btn" data-copy="1807200320033" onclick="copyBtn(this)">Sao chép số TK</button>

  <p><b>Chủ TK:</b> DO THANH CHUNG</p>
  <button type="button" class="copy-btn" data-copy="DO THANH CHUNG" onclick="copyBtn(this)">Sao chép chủ TK</button>

  <div class="qr-box">
    <img id="qrImage">
    <div class="transfer-content" id="transferText"></div>
    <button type="button" class="copy-btn" onclick="copyTransfer()">Sao chép nội dung chuyển khoản</button>
    <div class="notice">⚠️ Vui lòng điền đúng nội dung chuyển khoản để được xử lý nhanh</div>
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
const ACCOUNT="1807200320033";
const emailInput=document.getElementById("email");
const pkg=document.getElementById("package");

function updateQR(){
  const price=pkg.options[pkg.selectedIndex].dataset.price;
  const email=emailInput.value || "EMAIL";
  const content=`ESIM JAPAN | ${price} | ${email}`;
  priceText.innerText="Giá: "+Number(price).toLocaleString("vi-VN")+"đ";
  transferText.innerText=content;
  qrImage.src=`https://img.vietqr.io/image/MB-${ACCOUNT}-qr_only.png?amount=${price}&addInfo=${encodeURIComponent(content)}`;
}
pkg.onchange=updateQR;
emailInput.oninput=updateQR;
updateQR();

function submitOrder(){
  if(!paidCheck.checked){
    alert("⚠️ Vui lòng xác nhận đã thanh toán");
    return;
  }

  const data=new FormData(orderForm);

  fetch("https://formsubmit.co/ajax/chungthanh18072003@gmail.com",{
    method:"POST",
    body:data,
    headers:{Accept:"application/json"}
  })
  .then(()=>alert("✅ Đã ghi nhận đơn hàng!\nVui lòng kiểm tra email nhận eSIM."))
  .catch(()=>alert("❌ Lỗi gửi đơn, vui lòng thử lại."));
}

function copyBtn(btn){
  copyText(btn.dataset.copy,btn);
}
function copyTransfer(){
  copyText(transferText.innerText);
}
function copyText(text,btn){
  const t=document.createElement("textarea");
  t.value=text;document.body.appendChild(t);
  t.select();document.execCommand("copy");
  document.body.removeChild(t);
  if(btn){
    const old=btn.innerText;
    btn.innerText="Đã sao chép";
    setTimeout(()=>btn.innerText=old,1500);
  }
}
</script>

</body>
</html>
