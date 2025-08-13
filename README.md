<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Women’s Suits Shop - Prototype</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; padding: 0; background-color: #f4f4f4; }
    header { background-color: #9b59b6; color: white; padding: 15px; text-align: center; }
    .products { display: flex; flex-wrap: wrap; padding: 20px; }
    .product { background: white; border: 1px solid #ddd; border-radius: 5px; margin: 10px; padding: 10px; width: 200px; }
    .product img { width: 100%; border-radius: 5px; }
    .cart { position: fixed; top: 20px; right: 20px; background: #fff; border: 1px solid #ddd; padding: 10px; border-radius: 5px; }
    button { background-color: #9b59b6; color: white; border: none; padding: 10px; border-radius: 5px; cursor: pointer; }
    button:hover { background-color: #8e44ad; }
  </style>
</head>
<body>
  <header>
    <h1>Women’s Suits Shop</h1>
  </header>
  <div class="cart">
    🛒 Cart: <span id="cart-count">0</span>
  </div>
  <div class="products" id="product-list"></div>
  <script>
    const products = [
      { id: 1, name: 'Elegant Cotton Suit', price: 1500, image: 'https://via.placeholder.com/200' },
      { id: 2, name: 'Silk Party Suit', price: 2500, image: 'https://via.placeholder.com/200' },
      { id: 3, name: 'Designer Anarkali', price: 3000, image: 'https://via.placeholder.com/200' }
    ];
    let cart = [];function renderProducts() {
  const productList = document.getElementById('product-list');
  productList.innerHTML = '';
  products.forEach(product => {
    const div = document.createElement('div');
    div.className = 'product';
    div.innerHTML = `
      <img src="${product.image}" alt="${product.name}">
      <h3>${product.name}</h3>
      <p>₹${product.price}</p>
      <button onclick="addToCart(${product.id})">Add to Cart</button>
    `;
    productList.appendChild(div);
  });
}

function addToCart(id) {
  const product = products.find(p => p.id === id);
  cart.push(product);
  document.getElementById('cart-count').textContent = cart.length;
}

renderProducts();

  </script>
</body>
</html>
