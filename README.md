# 🛒 Web Bán Quần Áo (Full Code - Deploy GitHub)

## 📁 Cấu trúc project
```
clothing-shop/
├── index.html
├── package.json
├── vite.config.js
└── src/
    ├── main.jsx
    ├── App.jsx
    └── style.css
```

---

## 📦 package.json
```json
{
  "name": "clothing-shop",
  "private": true,
  "version": "1.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "vite": "^5.0.0"
  }
}
```

---

## ⚡ vite.config.js
```js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
})
```

---

## 🌐 index.html
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

---

## 🚀 src/main.jsx
```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App'
import './style.css'

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
)
```

---

## 🎨 src/style.css
```css
body {
  font-family: Arial, sans-serif;
  margin: 0;
  background: #f5f5f5;
}

.container {
  max-width: 1200px;
  margin: auto;
  padding: 20px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
}

.card {
  background: white;
  padding: 15px;
  border-radius: 10px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

button {
  background: #007bff;
  color: white;
  border: none;
  padding: 8px 12px;
  border-radius: 6px;
  cursor: pointer;
}
```

---

## 🧠 src/App.jsx
```jsx
import React, { useState } from 'react'

const products = [
  { id: 1, name: 'Áo thun', price: 150000, img: 'https://via.placeholder.com/200' },
  { id: 2, name: 'Quần jeans', price: 300000, img: 'https://via.placeholder.com/200' },
  { id: 3, name: 'Áo hoodie', price: 350000, img: 'https://via.placeholder.com/200' }
]

export default function App() {
  const [cart, setCart] = useState([])

  const addToCart = (item) => {
    setCart([...cart, item])
  }

  const total = cart.reduce((sum, i) => sum + i.price, 0)

  return (
    <div className="container">
      <h1>🛍 Shop Quần Áo</h1>

      <div className="grid">
        {products.map(p => (
          <div className="card" key={p.id}>
            <img src={p.img} width="100%" />
            <h3>{p.name}</h3>
            <p>{p.price.toLocaleString()}đ</p>
            <button onClick={() => addToCart(p)}>Thêm</button>
          </div>
        ))}
      </div>

      <h2>🛒 Giỏ hàng</h2>
      {cart.map((c, i) => (
        <p key={i}>{c.name} - {c.price.toLocaleString()}đ</p>
      ))}

      <h3>Tổng: {total.toLocaleString()}đ</h3>
    </div>
  )
}
```

---

## 🚀 Cách up lên GitHub

### 1. Tạo project
```bash
npm create vite@latest clothing-shop
cd clothing-shop
npm install
```

### 2. Thay toàn bộ file bằng code trên

### 3. Chạy thử
```bash
npm run dev
```

### 4. Push GitHub
```bash
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/USERNAME/REPO.git
git push -u origin main
```

---

## 🌍 Deploy web miễn phí
Bạn có thể deploy bằng:
- Vercel
- Netlify

Chỉ cần connect GitHub là chạy luôn.

---

## 👉 Nếu bạn muốn nâng cấp
Mình có thể làm thêm:
- Thanh toán Momo / chuyển khoản
- Admin đăng sản phẩm
- Backend NodeJS + database
- Giao diện giống Shopee

Chỉ cần nói: "nâng cấp web" là mình build tiếp cho bạn 🔥
