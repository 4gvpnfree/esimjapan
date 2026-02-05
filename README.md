<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Shop Acc Clash of Clans</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{
    margin:0;
    font-family:Arial,sans-serif;
    background:#f4f6f8
}
header{
    background:#ff9800;
    color:#fff;
    padding:14px;
    text-align:center;
    font-size:20px;
    font-weight:bold
}
.container{
    padding:12px;
    max-width:900px;
    margin:auto
}
.acc-list{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:12px
}
.acc{
    background:#fff;
    border-radius:8px;
    padding:12px;
    box-shadow:0 2px 6px rgba(0,0,0,.1)
}
.acc img{
    width:100%;
    border-radius:6px
}
.price{
    color:#e53935;
    font-weight:bold;
    margin:6px 0
}
button{
    width:100%;
    padding:10px;
    border:none;
    background:#4caf50;
    color:#fff;
    font-size:16px;
    border-radius:6px;
    cursor:pointer
}

/* modal */
.modal{
    display:none;
    position:fixed;
    inset:0;
    background:rgba(0,0,0,.6);
    justify-content:center;
    align-items:center
}
.modal-content{
    background:#fff;
    width:95%;
    max-width:400px;
    padding:16px;
    border-radius:8px
}
input{
    width:100%;
    padding:10px;
    margin:8px 0;
    font-size:16px
}
.close{background:#ccc}
</style>
</head>

<body>

<header>🔥 SHOP ACC CLASH OF CLANS 🔥</header>

<div class="container">
    <div class="acc-list" id="accList"></div>
</div>

<!-- MODAL -->
<div class="modal" id="modal">
    <div class="modal-content">
        <h3>Xác nhận mua acc</h3>
        <div id="accName"></div>
        <input id="email" placeholder="Nhập Gmail nhận acc">

        <div style="font-size:14px;margin:6px 0">
            Nội dung chuyển khoản:<br>
            <b id="transfer"></b>
        </div>

        <button onclick="confirmBuy()">Tôi đã chuyển khoản</button>
        <button class="close" onclick="closeModal()">Đóng</button>
    </div>
</div>

<script>
let accList = JSON.parse(localStorage.getItem("accList")) || [];
let selectedAcc = "";

function renderAcc(){
    const box = document.getElementById("accList");
    box.innerHTML = "";

    if(accList.length === 0){
        box.innerHTML = "<p>Chưa có acc nào</p>";
        return;
    }

    accList.forEach(acc=>{
        box.innerHTML += `
        <div class="acc">
            <img src="${acc.img}">
            <h3>${acc.name}</h3>
            <div>${acc.info}</div>
            <div class="price">${acc.price}</div>
            <button onclick="buyAcc('${acc.name}','${acc.price}')">Mua ngay</button>
        </div>`;
    });
}

function buyAcc(name,price){
    selectedAcc = name+" - "+price;
    accName.innerText = selectedAcc;
    modal.style.display="flex";
}

function closeModal(){
    modal.style.display="none";
}

function confirmBuy(){
    let email = document.getElementById("email").value;
    if(!email){
        alert("Nhập Gmail");
        return;
    }
    let text = "Mua "+selectedAcc+" - "+email;
    transfer.innerText = text;
    alert("Chuyển khoản với nội dung:\n"+text);
}

renderAcc();
</script>

</body>
</html>
