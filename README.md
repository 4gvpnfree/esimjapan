<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Shop Quần Áo</title>
  <style>
    body {
      font-family: Arial;
      padding: 20px;
      background: #f5f5f5;
    }

    h1 {
      text-align: center;
    }

    /* GIỎ HÀNG GÓC PHẢI */
    .cart-icon {
      position: fixed;
      top: 20px;
      right: 20px;
      background: #007bff;
      color: white;
      padding: 10px 15px;
      border-radius: 20px;
      cursor: pointer;
    }

    .cart-count {
      background: red;
      border-radius: 50%;
      padding: 2px 6px;
      margin-left: 5px;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 20px;
    }

    .product {
      background: white;
      padding: 15px;
      border-radius: 10px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }

    button {
      background: #007bff;
      color: white;
      border: none;
      padding: 8px;
      cursor: pointer;
      border-radius: 5px;
    }

    /* BOX GIỎ HÀNG */
    .cart-box {
      position: fixed;
      top: 60px;
      right: 20px;
      width: 300px;
      background: white;
      padding: 15px;
      border-radius: 10px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.2);
      display: none;
    }
  </style>
</head>
<body>

<h1>🛍 Shop Quần Áo</h1>

<!-- ICON GIỎ HÀNG -->
<div class="cart-icon" onclick="toggleCart()">
  🛒 <span class="cart-count" id="cartCount">0</span>
</div>

<h2>Sản phẩm</h2>
<div class="grid" id="products"></div>

<!-- GIỎ HÀNG -->
<div class="cart-box" id="cartBox">
  <h3>Giỏ hàng</h3>
  <div id="cart"></div>
  <h4 id="total"></h4>
</div>

<script>
const products = [
  { id: 1, name: "Áo thun", price: 150000 },
  { id: 2, name: "Quần jeans", price: 300000 },
  { id: 3, name: "Áo hoodie", price: 350000 }
];

let cart = JSON.parse(localStorage.getItem("cart")) || [];

function renderProducts() {
  const el = document.getElementById("products");
  el.innerHTML = "";

  products.forEach(p => {
    el.innerHTML += `
      <div class="product">
        <h3>${p.name}</h3>
        <p>${p.price.toLocaleString()}đ</p>
        <button onclick="addToCart(${p.id})">Thêm</button>
      </div>
    `;
  });
}

function addToCart(id) {
  const product = products.find(p => p.id === id);
  cart.push(product);
  saveCart();
  renderCart();
}

function saveCart() {
  localStorage.setItem("cart", JSON.stringify(cart));
}

function renderCart() {
  const el = document.getElementById("cart");
  const totalEl = document.getElementById("total");
  const countEl = document.getElementById("cartCount");

  el.innerHTML = "";

  cart.forEach((c, i) => {
    el.innerHTML += `
      <p>
        ${c.name} - ${c.price.toLocaleString()}đ 
        <button onclick="removeItem(${i})">X</button>
      </p>
    `;
  });

  const total = cart.reduce((sum, i) => sum + i.price, 0);

  totalEl.innerText = "Tổng: " + total.toLocaleString() + "đ";
  countEl.innerText = cart.length;
}

function removeItem(index) {
  cart.splice(index, 1);
  saveCart();
  renderCart();
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
