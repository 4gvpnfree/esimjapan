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
  height:240px;
  position:relative;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  text-align:center;
  color:#fff;
  border-radius:0 0 25px 25px;
  overflow:hidden;
  background-size:cover;
  background-positiBản</button>
  <button type="button" class="country-btn" onclick="changeCountry('vietnam', this)">🇻🇳 Việt Nam</button>
</div>

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
    <div class="pay-row"><b>Số TK:</b> <span id="stkText">1807200320033</span></div>
    <button type="button" class="copy-btn" onclick="copyText('stkText')">Sao chép số TK</button>
  </div>

  <div class="pay-block">
    <div class="pay-row"><b>Chủ TK:</b> <span id="ctkText">DO THANH CHUNG</span></div>
    <button type="button" class="copy-btn" onclick="copyText('ctkText')">Sao chép chủ TK</button>
  </div>

  <div class="qr-box">
    <img id="qrImage" alt="QR Thanh toán">
    <div class="transfer-box">
  <div class="transfer-label">📌 Nội dung chuyển khoản</div>
  <div class="transfer-content" id="transferText"></div>
</div>
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
    Thanh toán và đồng ý điều khoản!
  </label>
</div>



<button type="button" onclick="submitOrder()">Đặt mua eSIM</button>
</form>
</div>
<!-- NÚT HỖ TRỢ -->
<div class="support-buttons">
  <a href="https://zalo.me/0858712745" 
     class="support-btn support-zalo" 
     target="_blank">
    <i class="fa-solid fa-comment-dots"></i>
  </a>

  <a href="https://www.facebook.com/profile.php?id=100083581842218"
     class="support-btn support-messenger"
     target="_blank">
    <i class="fa-brands fa-facebook-messenger"></i>
  </a>
</div>

<script>
const ACCOUNT="1807200320033";
const emailInput=document.getElementById("email");
let currentCountry="japan";

const vietnamPackages=[
  {name:"7 ngày – 4GB/ngày",price:90000},
  {name:"15 ngày – 6GB/ngày",price:150000},
  {name:"30 ngày – 8GB/ngày",price:250000}
];

const japanPackages=[
  {name:"3 ngày – 1GB/ngày",price:150000},
  {name:"5 ngày – 2GB/ngày",price:230000},
  {name:"7 ngày – 5GB",price:320000},
  {name:"10 ngày – Không giới hạn",price:450000}
];

function changeCountry(country,btn){
  currentCountry=country;
  const banner=document.getElementById("mainBanner");

if(country==="japan"){
  banner.style.backgroundImage=
  "url('https://images.unsplash.com/photo-1549692520-acc6669e2f0c')";
}else{
  banner.style.backgroundImage=
  "url('https://images.unsplash.com/photo-1528127269322-539801943592')";
}
  document.querySelectorAll(".country-btn").forEach(b=>b.classList.remove("active"));
  btn.classList.add("active");

  const pkgSelect=document.getElementById("package");
  pkgSelect.innerHTML="";

  const list=country==="japan"?japanPackages:vietnamPackages;

  list.forEach(p=>{
    const option=document.createElement("option");
    option.textContent=p.name;
    option.dataset.price=p.price;
    pkgSelect.appendChild(option);
  });

  updateQR();
}

function updateQR(){
  const pkg=document.getElementById("package");
  const price=pkg.options[pkg.selectedIndex].dataset.price;
  const email=emailInput.value||"CHUA_CO_EMAIL";

  const content=`ESIM ${currentCountry.toUpperCase()} | ${price} | ${email}`;

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
    alert("⚠️ Vui lòng xác nhận đã thanh toán");
    return;
  }
  alert("✅ Đã ghi nhận đơn hàng! QR eSIM sẽ được gửi qua email.");
}

updateQR();
  
function randomViewer(){
  const el=document.getElementById("viewerCount");
  setInterval(()=>{
    const random=120+Math.floor(Math.random()*20);
    el.innerText=random;
  },3000);
}

randomViewer();
</script>
<div class="trust-box">
  <h3>🔒 Cam kết - Nhận Esim ngay sau khi thanh toán</h3>

  <div class="trust-item">
    <i class="fa-solid fa-shield-halved"></i>
    <div>
      <b>Kích hoạt nhanh chỉ trong 30 giây</b>
      <p>QR eSIM được gửi tự động qua email sau khi xác nhận thanh toán.</p>
    </div>
  </div>

  <div class="trust-item">
    <i class="fa-solid fa-bolt"></i>
    <div>
      <b>Tốc độ cao – Không giới hạn data</b>
      <p>Sử dụng ổn định tại sân bay, tàu điện, khách sạn.</p>
    </div>
  </div>

  <div class="trust-item">
    <i class="fa-solid fa-headset"></i>
    <div>
      <b>Hỗ trợ 24/7</b>
      <p>Liên hệ Zalo hoặc Messenger bên dưới để được hỗ trợ nhanh 24/24.</p>
    </div>
  </div>
</div>
<div class="social-proof">

  <div class="stars">
    ⭐⭐⭐⭐⭐
  </div>

  <div class="review-text">
    Hơn 19.200+ khách hàng hài lòng khi sử dụng eSIM tại shop
  </div>

  <div class="counter-box">
    👥 Khách đang xem: <span id="viewerCount">126</span>
  </div>

  <div class="big-sale">
    🏆 Đã bán <span id="saleCount">1298</span> đơn tháng này
  </div>

</div>

</body>
</html>
