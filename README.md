<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Shop Quần Áo</title>

<style>
body { margin:0; font-family: Arial; }

/* TOP BAR */
.topbar {
  background: black;
  color: white;
  padding: 5px 20px;
  font-size: 13px;
  display:flex;
  justify-content: space-between;
}

/* HEADER */
.header {
  display:flex;
  align-items:center;
  justify-content: space-between;
  padding:15px 20px;
  border-bottom:1px solid #ddd;
}

.logo { font-size:24px; font-weight:bold; }

.menu a {
  margin:0 10px;
  text-decoration:none;
  color:black;
}

.search input {
  padding:8px;
  border-radius:20px;
  border:1px solid #ccc;
}

/* CART */
.cart {
  position:relative;
  cursor:pointer;
}
.cart span {
  position:absolute;
  top:-5px;
  right:-10px;
  background:red;
  color:white;
  border-radius:50%;
  padding:2px 6px;
}

/* BANNER */
.banner {
  height:300px;
  background:url('https://images.unsplash.com/photo-1521334884684-d80222895322') center/cover;
  color:white;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:30px;
  font-weight:bold;
}

/* GRID */
.grid {
  display:grid;
  grid-template-columns: repeat(auto-fit,minmax(220px,1fr));
  gap:20px;
  padding:20px;
}

.product {
  text-align:center;
}

.product img {
  width:100%;
  border-radius:10px;
  transition:0.3s;
}
.product img:hover {
  transform:scale(1.05);
}

button {
  margin-top:10px;
  padding:8px;
  background:black;
  color:white;
  border:none;
  cursor:pointer;
}

/* CART BOX */
.cart-box {
  position:fixed;
  right:20px;
  top:70px;
  width:300px;
  background:white;
  border:1px solid #ddd;
  padding:10px;
  display:none;
}

/* CHAT BUTTON */
.chat {
  position:fixed;
  left:20px;
  bottom:20px;
}

.chat button {
  display:block;
  margin:5px 0;
  border-radius:20px;
}
</style>
</head>

<body>

<!-- TOP -->
<div class="topbar">
  <div>Miễn phí ship đơn > 500k</div>
  <div>📞 099999999</div>
</div>

<!-- HEADER -->
<div class="header">
  <div class="logo">HYPERX</div>

  <div class="menu">
    <a href="#">Trang chủ</a>
    <a href="#">Sản phẩm</a>
    <a href="#">Tin tức</a>
    <a href="#">Liên hệ</a>
  </div>

  <div class="search">
    <input placeholder="Tìm sản phẩm...">
  </div>

  <div class="cart" onclick="toggleCart()">
    🛒 <span id="count">0</span>
  </div>
</div>

<!-- BANNER -->
<div class="banner">
  HYPEBEAST & LUXURY
</div>

<!-- PRODUCTS -->
<div class="grid" id="products"></div>

<!-- CART -->
<div class="cart-box" id="cartBox">
  <h3>Giỏ hàng</h3>
  <div id="cart"></div>
  <h4 id="total"></h4>
</div>

<!-- CHAT -->
<div class="chat">
  <button style="background:#0a8f3c">Chat Zalo</button>
  <button style="background:#1877f2">Chat Facebook</button>
  <button style="background:red">Hotline</button>
</div>

<script>
const products = [
  {id:1,name:"Áo thun đen",price:300000,img:"https://picsum.photos/300?1"},
  {id:2,name:"Áo trắng",price:320000,img:"https://picsum.photos/300?2"},
  {id:3,name:"Áo nâu",price:350000,img:"https://picsum.photos/300?3"},
  {id:4,name:"Áo form rộng",price:280000,img:"https://picsum.photos/300?4"}
];

let cart = JSON.parse(localStorage.getItem("cart")) || [];

function renderProducts(){
  const el = document.getElementById("products");
  el.innerHTML="";
  products.forEach(p=>{
    el.innerHTML += `
      <div class="product">
        <img src="${p.img}">
        <p>${p.name}</p>
        <b>${p.price.toLocaleString()}đ</b><br>
        <button onclick="addToCart(${p.id})">Thêm</button>
      </div>
    `;
  });
}

function addToCart(id){
  const p = products.find(x=>x.id===id);
  cart.push(p);
  save();
  renderCart();
}

function renderCart(){
  const el=document.getElementById("cart");
  const totalEl=document.getElementById("total");
  const countEl=document.getElementById("count");

  el.innerHTML="";
  cart.forEach((c,i)=>{
    el.innerHTML += `<p>${c.name} <button onclick="removeItem(${i})">x</button></p>`;
  });

  const total = cart.reduce((s,i)=>s+i.price,0);
  totalEl.innerText="Tổng: "+total.toLocaleString()+"đ";
  countEl.innerText=cart.length;
}

function removeItem(i){
  cart.splice(i,1);
  save();
  renderCart();
}

function save(){
  localStorage.setItem("cart",JSON.stringify(cart));
}

function toggleCart(){
  const box=document.getElementById("cartBox");
  box.style.display = box.style.display==="block"?"none":"block";
}

renderProducts();
renderCart();
</script>

</body>
</html>
