/* # totalitycorp-frontend-challenge */
/* totalitycorp-frontend-challenge */

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Store</title>
    <style>
        /* Add your CSS styles here */
    </style>
</head>
<body>
    <header>
        <h1>Online Store</h1>
    </header>

    <main>
        <section id="product-list">
            <h2>Product Listing</h2>
            <div class="product">
                <h3>Product 1</h3>
                <p>Price: $30</p>
                <button class="add-to-cart" data-product-id="1">Add to Cart</button>
            </div>
            <div class="product">
                <h3>Product 2</h3>
                <p>Price: $55</p>
                <button class="add-to-cart" data-product-id="2">Add to Cart</button>
            </div>
            <!-- Add more products here -->
        </section>

        <section id="cart">
            <h2>Shopping Cart</h2>
            <div id="cart-items">
                <!-- Shopping cart items go here -->
            </div>
            <p>Total Items: <span id="total-items">0</span></p>
            <p>Total Cost: $<span id="total-cost">0.00</span></p>
        </section>

        <section id="checkout">
            <h2>Checkout</h2>
            <form id="checkout-form">
                <label for="name">Name:</label>
                <input type="text" id="name" required>
                <label for="address">Address:</label>
                <textarea id="address" required></textarea>
                <label for="email">Email:</label>
                <input type="email" id="email" required>
                <button id="place-order">Place Order</button>
            </form>
        </section>
    </main>

    <script>
        // JavaScript for adding and removing items from the cart
        const addToCartButtons = document.querySelectorAll('.add-to-cart');
        const cartItemsContainer = document.getElementById('cart-items');
        const totalItemsElement = document.getElementById('total-items');
        const totalCostElement = document.getElementById('total-cost');
        const checkoutForm = document.getElementById('checkout-form');
        const cart = [];

        addToCartButtons.forEach((button) => {
            button.addEventListener('click', () => {
                const productId = parseInt(button.getAttribute('data-product-id'));
                const product = {
                    id: productId,
                    name: `Product ${productId}`,
                    price: productId === 1 ? 30 : 55,
                };

                cart.push(product);
                displayCart();
            });
        });

        function displayCart() {
            cartItemsContainer.innerHTML = '';
            let totalItems = 0;
            let totalCost = 0;

            cart.forEach((product) => {
                totalItems++;
                totalCost += product.price;

                const cartItemElement = document.createElement('div');
                cartItemElement.classList.add('cart-item');
                cartItemElement.innerHTML = `
                    <p>${product.name} - $${product.price.toFixed(2)}</p>
                    <button class="remove-from-cart" data-product-id="${product.id}">Remove</button>
                `;

                cartItemsContainer.appendChild(cartItemElement);
            });

            totalItemsElement.textContent = totalItems;
            totalCostElement.textContent = totalCost.toFixed(2);
        }

        cartItemsContainer.addEventListener('click', (event) => {
            if (event.target.classList.contains('remove-from-cart')) {
                const productId = parseInt(event.target.getAttribute('data-product-id'));
                const productIndex = cart.findIndex((product) => product.id === productId);

                if (productIndex !== -1) {
                    cart.splice(productIndex, 1);
                    displayCart();
                }
            }
        });

        checkoutForm.addEventListener('submit', (event) => {
            event.preventDefault();
            // Implement your checkout logic here
            alert('Order placed successfully!');
            cart.length = 0; // Clear the cart after placing the order
            displayCart();
        });
    </script>
</body>
</html>

