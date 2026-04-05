<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Shop Quần Áo</title>

<style>
body {
  margin: 0;
  font-family: Arial;
}

/* HEADER */
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 30px;
  border-bottom: 1px solid #ddd;
}

.logo {
  font-weight: bold;
  font-size: 20px;
}

.menu a {
  margin: 0 10px;
  text-decoration: none;
  color: black;
}

.cart {
  position: relative;
  cursor: pointer;
}

.cart span {
  position: absolute;
  top: -5px;
  right: -10px;
  background: red;
  color: white;
  font-size: 12px;
  padding: 2px 6px;
  border-radius: 50%;
}

/* TITLE */
.title {
  text-align: center;
  margin: 20px;
  font-size: 24px;
}

/* GRID */
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 20px;
  padding: 20px;
}

/* PRODUCT */
.product {
  text-align: center;
}

.product img {
  width: 100%;
  border-radius: 10px;
  transition: 0.3s;
}

.product img:hover {
  transform: scale(1.05);
}

.product button {
  margin-top: 10px;
  padding: 8px;
  border: none;
  background: black;
  color: white;
  cursor: pointer;
}

/* CART BOX */
.cart-box {
  position: fixed;
  top: 70px;
  right: 20px;
  width: 300px;
  background: white;
  border: 1px solid #ddd;
  padding: 15px;
  display: none;
}
</style>
</head>

<body>

<!-- HEADER -->
<div class="header">
  <div class="logo">OLD SAILOR</div>

  <div class="menu">
    <a href="#">Trang chủ</a>
    <a href="#">Sản phẩm</a>
    <a href="#">Sale</a>
  </div>

  <div class="cart" onclick="toggleCart()">
    🛒 <span id="count">0</span>
  </div>
</div>

<div class="title">NEW ARRIVAL</div>

<!-- PRODUCTS -->
<div class="grid" id="products"></div>

<!-- CART -->
<div class="cart-box" id="cartBox">
  <h3>Giỏ hàng</h3>
  <div id="cart"></div>
  <h4 id="total"></h4>
</div>

<script>
const products = [
  {
    id: 1,
    name: "Áo thun đen",
    price: 325000,
    img: "https://i.imgur.com/1.jpg"
  },
  {
    id: 2,
    name: "Áo thun trắng",
    price: 325000,
    img: "https://i.imgur.com/2.jpg"
  },
  {
    id: 3,
    name: "Áo nâu",
    price: 325000,
    img: "https://i.imgur.com/3.jpg"
  },
  {
    id: 4,
    name: "Áo basic",
    price: 325000,
    img: "https://i.imgur.com/4.jpg"
  }
];

let cart = JSON.parse(localStorage.getItem("cart")) || [];

function renderProducts() {
  const el = document.getElementById("products");
  el.innerHTML = "";

  products.forEach(p => {
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

function addToCart(id) {
  const p = products.find(x => x.id === id);
  cart.push(p);
  save();
  renderCart();
}

function renderCart() {
  const el = document.getElementById("cart");
  const totalEl = document.getElementById("total");
  const countEl = document.getElementById("count");

  el.innerHTML = "";

  cart.forEach((c, i) => {
    el.innerHTML += `
      <p>${c.name} 
      <button onclick="removeItem(${i})">x</button></p>
    `;
  });

  const total = cart.reduce((s, i) => s + i.price, 0);

  totalEl.innerText = "Tổng: " + total.toLocaleString() + "đ";
  countEl.innerText = cart.length;
}

function removeItem(i) {
  cart.splice(i, 1);
  save();
  renderCart();
}

function save() {
  localStorage.setItem("cart", JSON.stringify(cart));
}

function toggleCart() {
  const box = document.getElementById("cartBox");
  box.style.display = box.style.display === "block" ? "none" : "block";
}

renderProducts();
renderCart();
</script>

</body>
</html>
