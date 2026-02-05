<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Shop Acc Clash of Clans</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-firestore-compat.js"></script>

<style>
body{margin:0;font-family:Arial;background:#f4f6f8}
header{background:#ff9800;color:#fff;padding:14px;text-align:center;font-size:20px;font-weight:bold}
.container{padding:12px;max-width:900px;margin:auto}
.acc-list{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:12px}
.acc{background:#fff;border-radius:8px;padding:12px;box-shadow:0 2px 6px rgba(0,0,0,.1)}
.acc img{width:100%;border-radius:6px}
.price{color:#e53935;font-weight:bold;margin:6px 0}
button{width:100%;padding:10px;border:none;background:#4caf50;color:#fff;font-size:16px;border-radius:6px}
</style>
</head>

<body>

<header>🔥 SHOP ACC CLASH OF CLANS 🔥</header>

<div class="container">
    <div class="acc-list" id="accList"></div>
</div>

<script>
// 🔴 DÁN FIREBASE CONFIG CỦA BẠN VÀO ĐÂY
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_DOMAIN",
  projectId: "YOUR_PROJECT_ID"
};

firebase.initializeApp(firebaseConfig);
const db = firebase.firestore();

db.collection("accounts").onSnapshot(snapshot => {
    const box = document.getElementById("accList");
    box.innerHTML = "";
    snapshot.forEach(doc => {
        const acc = doc.data();
        box.innerHTML += `
        <div class="acc">
            <img src="${acc.img}">
            <h3>${acc.name}</h3>
            <div>${acc.info}</div>
            <div class="price">${acc.price}</div>
            <button>Mua ngay</button>
        </div>`;
    });
});
</script>

</body>
</html>
