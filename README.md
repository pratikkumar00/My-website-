<!DOCTYPE html><html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Premium Course Marketplace</title>
    <style>
        body { font-family: Arial, sans-serif; background-color: #f5f5f5; margin: 0; padding: 0; }
        .header { background-color: #232f3e; padding: 15px; color: white; text-align: center; }
        .container { max-width: 1200px; margin: auto; padding: 20px; }
        .product { display: inline-block; width: 30%; margin: 20px; padding: 15px; background: white; border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); }
        .cart { margin-top: 20px; padding: 20px; background: white; border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); }
        button { background-color: #ff9900; border: none; padding: 10px 20px; border-radius: 5px; cursor: pointer; }
        button:hover { background-color: #e68a00; }
    </style>
</head>
<body>
    <div class="header">
        <h1>Premium Course Marketplace</h1>
    </div><div class="container">
    <h2>Available Courses</h2>
    <div id="products">
        <div class="product">
            <h3>Web Development Mastery</h3>
            <p>Price: $50</p>
            <button onclick="addToCart('Web Development Mastery', 50)">Buy Now</button>
        </div>
        <div class="product">
            <h3>Python for Beginners</h3>
            <p>Price: $40</p>
            <button onclick="addToCart('Python for Beginners', 40)">Buy Now</button>
        </div>
        <div class="product">
            <h3>Digital Marketing Pro</h3>
            <p>Price: $70</p>
            <button onclick="addToCart('Digital Marketing Pro', 70)">Buy Now</button>
        </div>
    </div>
    
    <div class="cart">
        <h2>Your Cart</h2>
        <ul id="cart-items"></ul>
        <p>Total: $<span id="total">0</span></p>
        <button onclick="checkout()">Checkout</button>
    </div>
</div>

<script>
    let cart = [];
    function addToCart(product, price) {
        cart.push({ product, price });
        updateCart();
    }
    function updateCart() {
        let cartList = document.getElementById("cart-items");
        let total = 0;
        cartList.innerHTML = "";
        cart.forEach(item => {
            let li = document.createElement("li");
            li.textContent = `${item.product} - $${item.price}`;
            cartList.appendChild(li);
            total += item.price;
        });
        document.getElementById("total").textContent = total;
    }
    function checkout() {
        alert("Payment system coming soon!");
    }
</script>

</body>
</html>
