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

.banner{
  width:100%;
  background:linear-gradient(135deg,#d32f2f,#ff7043);
  color:#fff;
  padding:26px 16px 40px;
  text-align:center;
}

.container{
  width:100%;
  max-width:600px;
  margin:20px auto;
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
  padding:16px;
  border-radius:16px;
  margin-top:18px;
  font-size:13px;
}

.copy-btn{
  background:#ff7043;
  color:#fff;
  border:none;
  padding:10px;
  border-radius:10px;
  font-weight:bold;
  cursor:pointer;
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
  <p>Internet tốc độ cao • Nhận QR qua email</p>
</div>

<!-- ====== ĐĂNG NHẬP / ĐĂNG KÝ ====== -->
<div class="container" id="authBox">
  <h3 style="text-align:center">🔐 Tài khoản khách hàng</h3>
  <input type="text" id="username" placeholder="Tên đăng nhập">
  <input type="password" id="password" placeholder="Mật khẩu">
  <button type="button" onclick="register()">Đăng ký</button>
  <button type="button" onclick="login()">Đăng nhập</button>
  <p id="authMessage" style="text-align:center;font-size:13px;margin-top:10px"></p>
</div>

<!-- ====== FORM MUA ESIM ====== -->
<div class="container" id="mainShop" style="display:none;">
<form id="orderForm"
 action="https://formsubmit.co/chungthanh18072003@gmail.com"
 method="POST">

<select id="package" name="Goi_eSIM" onchange="updateQR()">
  <option value="150000">3 ngày – 1GB/ngày</option>
  <option value="230000">5 ngày – 2GB/ngày</option>
  <option value="320000">7 ngày – 5GB</option>
  <option value="450000">10 ngày – Không giới hạn</option>
</select>

<div class="price" id="priceText"></div>

<input type="email" id="email" name="Email_khach"
 placeholder="Nhập email nhận eSIM"
 required oninput="updateQR()">

<div class="note">
  <h3>💳 Thanh toán QR MB Bank</h3>
  <div><b>STK:</b> 1807200320033</div>
  <div><b>Chủ TK:</b> DO THANH CHUNG</div>

  <div style="margin-top:12px;text-align:center">
    <img id="qrImage" style="max-width:220px;width:100%">
    <div id="transferText" style="margin-top:8px;font-size:12px"></div>
  </div>
</div>

<div class="confirm-box">
  <input type="checkbox" id="paidCheck">
  <label for="paidCheck">
    <i class="fa-solid fa-circle-check"></i>
    Tôi đã thanh toán
  </label>
</div>

<button type="button" onclick="submitOrder()">Đặt mua eSIM</button>
</form>
</div>

<script>
const ACCOUNT="1807200320033";

/* ====== TÀI KHOẢN ====== */
function register(){
  const user=username.value;
  const pass=password.value;

  if(!user||!pass){
    showMsg("⚠️ Nhập đủ thông tin","red");return;
  }

  if(localStorage.getItem(user)){
    showMsg("❌ Tài khoản tồn tại","red");return;
  }

  localStorage.setItem(user,pass);
  showMsg("✅ Đăng ký thành công","green");
}

function login(){
  const user=username.value;
  const pass=password.value;

  if(localStorage.getItem(user)===pass){
    localStorage.setItem("loggedIn",user);
    authBox.style.display="none";
    mainShop.style.display="block";
  }else{
    showMsg("❌ Sai thông tin","red");
  }
}

function showMsg(text,color){
  authMessage.innerText=text;
  authMessage.style.color=color;
}

window.onload=function(){
  if(localStorage.getItem("loggedIn")){
    authBox.style.display="none";
    mainShop.style.display="block";
  }
  updateQR();
};

/* ====== ESIM ====== */
function updateQR(){
  const pkg=document.getElementById("package");
  const price=pkg.value;
  const name=pkg.options[pkg.selectedIndex].text;
  const email=document.getElementById("email").value||"CHUA_CO_EMAIL";

  priceText.innerText="Giá: "+Number(price).toLocaleString("vi-VN")+"đ";

  const content=`ESIM JAPAN | ${name} | ${price} | ${email}`;
  transferText.innerText=content;

  qrImage.src=
  `https://img.vietqr.io/image/MB-${ACCOUNT}-qr_only.png?amount=${price}&addInfo=${encodeURIComponent(content)}`;
}

function submitOrder(){
  if(!paidCheck.checked){
    alert("Vui lòng xác nhận đã thanh toán");return;
  }
  alert("Đã ghi nhận đơn hàng!");
  orderForm.submit();
}
</script>

</body>
</html>
