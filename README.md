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

    .cart {
      margin-top: 30px;
      background: white;
      padding: 15px;
      border-radius: 10px;
    }
  </style>
</head>
<body>

<h1>🛍 Shop Quần Áo</h1>

<h2>Sản phẩm</h2>
<div class="grid" id="products"></div>

<div class="cart">
  <h2>🛒 Giỏ hàng</h2>
  <div id="cart"></div>
  <h3 id="total"></h3>
</div>

<script>
const products = [
  { id: 1, name: "Áo thun", price: 150000 },
  { id: 2, name: "Quần jeans", price: 300000 },
  { id: 3, name: "Áo hoodie", price: 350000 }
];

let cart = [];

// load giỏ hàng từ localStorage
if (localStorage.getItem("cart")) {
  cart = JSON.parse(localStorage.getItem("cart"));
}

function renderProducts() {
  const el = document.getElementById("products");
  el.innerHTML = "";

  products.forEach(p => {
    el.innerHTML += `
      <div class="product">
        <h3>${p.name}</h3>
        <p>${p.price.toLocaleString()}đ</p>
        <button onclick="addToCart(${p.id})">Thêm vào giỏ</button>
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

  el.innerHTML = "";

  cart.forEach((c, index) => {
    el.innerHTML += `
      <p>
        ${c.name} - ${c.price.toLocaleString()}đ 
        <button onclick="removeItem(${index})">X</button>
      </p>
    `;
  });

  const total = cart.reduce((sum, i) => sum + i.price, 0);
  totalEl.innerText = "Tổng: " + total.toLocaleString() + "đ";
}

function removeItem(index) {
  cart.splice(index, 1);
  saveCart();
  renderCart();
}

renderProducts();
renderCart();
</script>

</body>
</html>
