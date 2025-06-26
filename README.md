# Clickbuy.kg
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Магазин: товары из Китая</title>
  <style>
    body { margin:0; font-family:Arial,sans-serif; background:#f5f5f5; }
    header { background:#c00; color:#fff; padding:20px; text-align:center; font-size:1.5em; }
    .container { display:flex; flex-wrap:wrap; justify-content:center; padding:20px; }
    .product { background:#fff; border-radius:5px; margin:10px; width:250px; box-shadow:0 2px 5px rgba(0,0,0,0.1); display:flex; flex-direction:column; }
    .product img { width:100%; height:180px; object-fit:cover; }
    .content { padding:15px; flex-grow:1; }
    .content h3 { margin:0 0 10px; font-size:1.1em; }
    .content p { font-size:0.9em; color:#555; }
    .price { margin:15px 0; font-size:1.2em; color:green; font-weight:bold; }
    .btn { background:#c00; color:#fff; border:none; padding:10px; cursor:pointer; font-size:1em; width:100%; }
    .btn:hover { background:#a00; }
    @media (max-width: 600px) {
      .product { width:100%; margin:10px 0; }
    }
  </style>
</head>
<body>

<header>Магазин товаров из Китая</header>
<div class="container" id="product-list"></div>

<script>
  const yuanToKgs = 12.5;
  const products = [
    { name:"Bluetooth-наушники TWS", description:"Bluetooth 5.0, 4 ч работы", priceYuan:45, image:"https://via.placeholder.com/250x180?text=Наушники" },
    { name:"Массажная щетка", description:"Электрическая щетка для лица", priceYuan:20, image:"https://via.placeholder.com/250x180?text=Щетка" },
    { name:"USB лампа", description:"Гибкая LED-лампа для ноутбука", priceYuan:8, image:"https://via.placeholder.com/250x180?text=Лампа" }
  ];
  const container = document.getElementById("product-list");
  products.forEach(p => {
    const kgs = Math.round(p.priceYuan * yuanToKgs);
    const el = document.createElement("div");
    el.className = "product";
    el.innerHTML = `
      <img src="${p.image}" alt="${p.name}">
      <div class="content">
        <h3>${p.name}</h3>
        <p>${p.description}</p>
        <div class="price">${kgs} сом</div>
        <button class="btn" onclick="order('${p.name}')">Заказать</button>
      </div>`;
    container.appendChild(el);
  });

  function order(productName) {
    alert(`Вы заказали: ${productName}`);
  }
</script>

</body>
</html>
