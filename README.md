# 🛒 FULL CODE HOÀN CHỈNH WEB BÁN QUẦN ÁO (1 PROJECT CHẠY LUÔN)

👉 Copy toàn bộ cấu trúc này lên GitHub là chạy được

---

# 📁 CẤU TRÚC
```
clothing-shop/
├── server/
│   ├── index.js
│   └── package.json
└── client/
    ├── index.html
    ├── package.json
    ├── vite.config.js
    └── src/
        ├── main.jsx
        └── App.jsx
```

---

# ⚙️ BACKEND

## server/package.json
```json
{
  "name": "server",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "start": "node index.js"
  },
  "dependencies": {
    "express": "^4.18.2",
    "cors": "^2.8.5"
  }
}
```

## server/index.js
```js
const express = require('express')
const cors = require('cors')

const app = express()
app.use(cors())
app.use(express.json())

let products = [
  { id: 1, name: 'Áo thun', price: 150000 },
  { id: 2, name: 'Quần jeans', price: 300000 },
  { id: 3, name: 'Áo hoodie', price: 350000 }
]

let orders = []

app.get('/products', (req, res) => {
  res.json(products)
})

app.post('/order', (req, res) => {
  orders.push(req.body)
  res.json({ message: 'Đặt hàng thành công' })
})

app.listen(3000, () => console.log('Server: http://localhost:3000'))
```

---

# 🎨 FRONTEND

## client/package.json
```json
{
  "name": "client",
  "private": true,
  "version": "1.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "vite": "^5.0.0",
    "@vitejs/plugin-react": "^4.0.0"
  }
}
```

## client/vite.config.js
```js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
})
```

## client/index.html
```html
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Shop Quần Áo</title>
</head>
<body>
  <div id="root"></div>
  <script type="module" src="/src/main.jsx"></script>
</body>
</html>
```

## client/src/main.jsx
```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App'

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
)
```

## client/src/App.jsx
```jsx
import { useEffect, useState } from "react";

export default function App() {
  const [products, setProducts] = useState([]);
  const [cart, setCart] = useState([]);

  useEffect(() => {
    fetch("http://localhost:3000/products")
      .then(res => res.json())
      .then(setProducts);
  }, []);

  const addToCart = (p) => {
    setCart([...cart, p]);
  };

  const checkout = () => {
    fetch("http://localhost:3000/order", {
      method: "POST",
      headers: {
        "Content-Type": "application/json"
      },
      body: JSON.stringify(cart)
    })
      .then(res => res.json())
      .then(data => alert(data.message));
  };

  const total = cart.reduce((sum, i) => sum + i.price, 0);

  return (
    <div style={{ padding: 20 }}>
      <h1>🛍 Shop Quần Áo</h1>

      <h2>Sản phẩm</h2>
      {products.map(p => (
        <div key={p.id}>
          {p.name} - {p.price.toLocaleString()}đ
          <button onClick={() => addToCart(p)}> Thêm</button>
        </div>
      ))}

      <h2>🛒 Giỏ hàng</h2>
      {cart.map((c, i) => (
        <div key={i}>{c.name}</div>
      ))}

      <h3>Tổng: {total.toLocaleString()}đ</h3>

      <button onClick={checkout}>Đặt hàng</button>
    </div>
  );
}
```

---

# 🚀 CHẠY PROJECT

## 1. Backend
```bash
cd server
npm install
node index.js
```

## 2. Frontend
```bash
cd client
npm install
npm run dev
```

👉 Truy cập: http://localhost:5173

---

# 📤 PUSH GITHUB

```bash
git init
git add .
git commit -m "shop quan ao"
git branch -M main
git remote add origin https://github.com/USERNAME/clothing-shop.git
git push -u origin main
```

---

# ✅ KẾT QUẢ
- Có web bán quần áo
- Có giỏ hàng
- Có API backend
- Có đặt hàng

---

# ⚠️ NÂNG CẤP (KHI BẠN CẦN)
- Database (MongoDB)
- Admin đăng sản phẩm
- Upload ảnh
- Thanh toán Momo

👉 Muốn làm bản kiếm tiền: nói mình "làm shop pro" 🔥
