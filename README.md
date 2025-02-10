<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fashion Webshop</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; }
        .product { display: inline-block; margin: 20px; padding: 10px; border: 1px solid #ccc; }
        .product img { width: 150px; height: 150px; }
        .cart { margin-top: 20px; }
    </style>
</head>
<body>
    <h1>Welkom bij onze Fashion Webshop!</h1>
    <div id="products">
        <div class="product">
            <img src="shirt.jpg" alt="T-shirt">
            <h2>T-shirt</h2>
            <p>€19,99</p>
            <button onclick="addToCart('T-shirt', 19.99)">Toevoegen aan winkelwagen</button>
        </div>
        <div class="product">
            <img src="sneakers.jpg" alt="Sneakers">
            <h2>Sneakers</h2>
            <p>€49,99</p>
            <button onclick="addToCart('Sneakers', 49.99)">Toevoegen aan winkelwagen</button>
        </div>
    </div>
    
    <h2>Winkelwagen</h2>
    <div id="cart" class="cart">
        <p>Je winkelwagen is leeg.</p>
    </div>
    
    <script>
        let cart = [];
        function addToCart(name, price) {
            cart.push({ name, price });
            updateCart();
        }
        function updateCart() {
            let cartDiv = document.getElementById("cart");
            cartDiv.innerHTML = "";
            cart.forEach(item => {
                let p = document.createElement("p");
                p.textContent = `${item.name} - €${item.price.toFixed(2)}`;
                cartDiv.appendChild(p);
            });
        }
    </script>
</body>
</html>
