import React, { useState } from "react";

const productsData = [
  { id: 1, name: "Áo thun basic", price: 150000, image: "https://via.placeholder.com/150" },
  { id: 2, name: "Quần jeans", price: 300000, image: "https://via.placeholder.com/150" },
  { id: 3, name: "Áo hoodie", price: 350000, image: "https://via.placeholder.com/150" },
];

export default function App() {
  const [cart, setCart] = useState([]);

  const addToCart = (product) => {
    setCart([...cart, product]);
  };

  const total = cart.reduce((sum, item) => sum + item.price, 0);

  return (
    <div className="p-6">
      <h1 className="text-2xl font-bold mb-4">Shop Quần Áo</h1>

      <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
        {productsData.map((product) => (
          <div key={product.id} className="border rounded-2xl p-4 shadow">
            <img src={product.image} alt="" className="mb-2" />
            <h2 className="font-semibold">{product.name}</h2>
            <p>{product.price.toLocaleString()}đ</p>
            <button
              onClick={() => addToCart(product)}
              className="mt-2 bg-blue-500 text-white px-3 py-1 rounded-xl"
            >
              Thêm vào giỏ
            </button>
          </div>
        ))}
      </div>

      <div className="mt-6">
        <h2 className="text-xl font-bold">Giỏ hàng</h2>
        {cart.length === 0 ? (
          <p>Chưa có sản phẩm</p>
        ) : (
          <ul>
            {cart.map((item, index) => (
              <li key={index}>
                {item.name} - {item.price.toLocaleString()}đ
              </li>
            ))}
          </ul>
        )}
        <p className="mt-2 font-bold">Tổng: {total.toLocaleString()}đ</p>
      </div>
    </div>
  );
}
