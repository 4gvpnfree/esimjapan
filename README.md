<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Shop Acc Clash of Clans</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #f4f6f8;
}

header {
    background: #ff9800;
    color: #fff;
    padding: 14px;
    text-align: center;
    font-size: 20px;
    font-weight: bold;
}

.container {
    padding: 12px;
    max-width: 900px;
    margin: auto;
}

.acc-list {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 12px;
}

.acc {
    background: #fff;
    border-radius: 8px;
    padding: 12px;
    box-shadow: 0 2px 6px rgba(0,0,0,.1);
}

.acc img {
    width: 100%;
    border-radius: 6px;
}

.acc h3 {
    margin: 8px 0 4px;
}

.price {
    color: #e53935;
    font-weight: bold;
    margin-bottom: 8px;
}

button {
    width: 100%;
    padding: 10px;
    border: none;
    background: #4caf50;
    color: #fff;
    font-size: 16px;
    border-radius: 6px;
    cursor: pointer;
}

button:hover {
    opacity: .9;
}

/* MODAL */
.modal {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,.6);
    justify-content: center;
    align-items: center;
}

.modal-content {
    background: #fff;
    width: 95%;
    max-width: 400px;
    padding: 16px;
    border-radius: 8px;
}

.modal-content h2 {
    margin-top: 0;
}

input {
    width: 100%;
    padding: 10px;
    margin: 8px 0;
    font-size: 16px;
}

.close {
    background: #ccc;
    margin-top: 6px;
}
</style>
</head>

<body>

<header>🔥 SHOP ACC CLASH OF CLANS 🔥</header>

<div class="container">
    <div class="acc-list">

        <div class="acc">
            <img src="https://i.imgur.com/4QfKuz1.png">
            <h3>Town Hall 13</h3>
            <div>Skin: Full</div>
            <div>Gem: 1200</div>
            <div class="price">450.000đ</div>
            <button onclick="buyAcc('TH13 - 450k')">Mua ngay</button>
        </div>

        <div class="acc">
            <img src="https://i.imgur.com/4QfKuz1.png">
            <h3>Town Hall 14</h3>
            <div>Skin: VIP</div>
            <div>Gem: 2500</div>
            <div class="price">750.000đ</div>
            <button onclick="buyAcc('TH14 - 750k')">Mua ngay</button>
        </div>

    </div>
</div>

<!-- MODAL -->
<div class="modal" id="modal">
    <div class="modal-content">
        <h2>Xác nhận mua acc</h2>
        <div id="accName"></div>

        <input type="email" id="email" placeholder="Nhập Gmail nhận acc">

        <div style="margin-top:8px;font-size:14px;">
            💳 <b>Nội dung chuyển khoản:</b><br>
            <span id="transfer"></span>
        </div>

        <button onclick="confirmBuy()">Tôi đã chuyển khoản</button>
        <button class="close" onclick="closeModal()">Đóng</button>
    </div>
</div>

<script>
let selectedAcc = "";

function buyAcc(name) {
    selectedAcc = name;
    document.getElementById("accName").innerText = "Acc: " + name;
    document.getElementById("modal").style.display = "flex";
}

function closeModal() {
    document.getElementById("modal").style.display = "none";
}

function confirmBuy() {
    let email = document.getElementById("email").value;
    if (!email) {
        alert("Vui lòng nhập Gmail");
        return;
    }

    let content = "Mua " + selectedAcc + " - " + email;
    document.getElementById("transfer").innerText = content;

    alert("Vui lòng chuyển khoản với nội dung:\n" + content);
}
</script>

</body>
</html>
