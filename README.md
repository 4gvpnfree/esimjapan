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
header,.Header,#header,#Header1,.header,.header-wrSoftbank Nhật Bản</h1>
  <p>Internet tốc độ cao • Nhận QR qua email • Không cần SIM vật lý</p>
</div>

<div class="container">
<form id="orderForm"
 action="https://formsubmit.co/chungthanh18072003@gmail.com"
 method="POST">

<select id="package" name="Goi_eSIM" onchange="updateQR()">
  <option data-price="150000">3 ngày – 3GB/ngày</option>
  <option data-price="230000">5 ngày – 5GB/ngày</option>
  <option data-price="320000">7 ngày – 7GB</option>
  <option data-price="150000">10 ngày – 10GB/ngày</option>
  <option data-price="230000">15 ngày – 15GB/ngày</option>
  <option data-price="320000">20 ngày – 20GB</option>
  <option data-price="450000">30 ngày – Không giới hạn</option>
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
    <div class="transfer-content" id="transferText"></div>
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

<input type="hidden" name="_subject" value="🔔 Đơn hàng eSIM Nhật">
<input type="hidden" name="_captcha" value="false">
<input type="hidden" name="_next" value="">

<button type="button" onclick="submitOrder()">Đặt mua eSIM</button>
</form>
</div>

<!-- NÚT HỖ TRỢ -->
<div class="support-buttons">
  <a href="https://zalo.me/0858712745" class="support-btn support-zalo" target="_blank">
    <i class="fa-solid fa-comment-dots"></i>
  </a>
  <a href="https://www.facebook.com/profile.php?id=100083581842218"
     class="support-btn support-messenger" target="_blank">
    <i class="fa-brands fa-facebook-messenger"></i>
  </a>
</div>

<script>
const ACCOUNT="1807200320033";
const emailInput=document.getElementById("email");

function updateQR(){
  const pkg=document.getElementById("package");
  const price=pkg.options[pkg.selectedIndex].dataset.price;
  const email=emailInput.value || "CHUA_CO_EMAIL";

  const content = `ESIM JAPAN | ${price} | ${email}`;

  document.getElementById("priceText").innerText =
    "Giá: " + Number(price).toLocaleString("vi-VN") + "đ";

  document.getElementById("transferText").innerText = content;

  document.getElementById("qrImage").src =
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
  orderForm.submit();
}

updateQR();
</script>

</body>
</html>
