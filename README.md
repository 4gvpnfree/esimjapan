<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Admin Shop Acc</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-firestore-compat.js"></script>

<style>
body{font-family:Arial;background:#f4f6f8;padding:10px}
.box{background:#fff;padding:12px;border-radius:8px;max-width:500px;margin:auto}
input{width:100%;padding:10px;margin:6px 0}
button{width:100%;padding:10px;background:#4caf50;color:#fff;border:none;font-size:16px;border-radius:6px}
.acc{background:#eee;padding:8px;border-radius:6px;margin-top:6px}
.del{background:#e53935;margin-top:4px}
</style>
</head>

<body>

<div class="box">
<h3>⚙️ ADMIN ĐĂNG ACC</h3>

<input id="name" placeholder="Tên acc">
<input id="info" placeholder="Thông tin">
<input id="price" placeholder="Giá">
<input id="img" placeholder="Link ảnh">

<button onclick="addAcc()">➕ Đăng acc</button>

<div id="list"></div>
</div>

<script>
// 🔴 DÁN FIREBASE CONFIG GIỐNG INDEX
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_DOMAIN",
  projectId: "YOUR_PROJECT_ID"
};

firebase.initializeApp(firebaseConfig);
const db = firebase.firestore();

function addAcc(){
    if(!name.value || !price.value){
        alert("Thiếu thông tin");
        return;
    }

    db.collection("accounts").add({
        name:name.value,
        info:info.value,
        price:price.value,
        img:img.value || "https://i.imgur.com/4QfKuz1.png"
    });

    name.value=info.value=price.value=img.value="";
}

db.collection("accounts").onSnapshot(snapshot=>{
    list.innerHTML="";
    snapshot.forEach(doc=>{
        const a = doc.data();
        list.innerHTML+=`
        <div class="acc">
            <b>${a.name}</b> - ${a.price}<br>
            <button class="del" onclick="delAcc('${doc.id}')">❌ Xoá</button>
        </div>`;
    });
});

function delAcc(id){
    if(confirm("Xoá acc?")){
        db.collection("accounts").doc(id).delete();
    }
}
</script>

</body>
</html>
