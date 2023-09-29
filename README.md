/* # totalitycorp-frontend-challenge */
/* totalitycorp-frontend-challenge */

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Store</title>
    <style>
        /* Styles for header */
        header {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 10px;
        }

        header h1 {
            margin: 0;
            font-size: 2rem;
        }

        /* Styles for product listing */
        .product {
            border: 1px solid #ccc;
            padding: 10px;
            margin: 10px;
        }

        .product h3 {
            margin: 0;
        }

        .product p {
            margin: 5px 0;
        }

        .add-to-cart {
            background-color: #007bff;
            color: #fff;
            border: none;
            padding: 5px 10px;
            border-radius: 3px;
            cursor: pointer;
        }

        /* Styles for shopping cart */
        #cart {
            border: 1px solid #ccc;
            padding: 10px;
            margin: 10px;
        }

        #cart p {
            margin: 5px 0;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 5px 0;
        }

        .remove-from-cart {
            background-color: #dc3545;
            color: #fff;
            border: none;
            padding: 5px 10px;
            border-radius: 3px;
            cursor: pointer;
        }

        /* Styles for checkout form */
        #checkout-form {
            border: 1px solid #ccc;
            padding: 10px;
            margin: 10px;
        }

        #checkout-form label {
            display: block;
            margin-bottom: 5px;
        }

        #checkout-form input[type="text"],
        #checkout-form input[type="email"],
        #checkout-form textarea {
            width: 100%;
            padding: 5px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 3px;
        }

        #place-order {
            background-color: #28a745;
            color: #fff;
            border: none;
            padding: 10px 20px;
            border-radius: 3px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <header>
        <h1>Online Store</h1>
    </header>

    <div class="product">
        <h3>Product 1</h3>
        <p>Price: $30</p>
        <button class="add-to-cart">Add to Cart</button>
    </div>

    <div class="product">
        <h3>Product 2</h3>
        <p>Price: $55</p>
        <button class="add-to-cart">Add to Cart</button>
    </div>

    <div id="cart">
        <h2>Shopping Cart</h2>
        <div class="cart-item">
            <p>Product 1 - $30 x 2</p>
            <button class="remove-from-cart">Remove</button>
        </div>
        <div class="cart-item">
            <p>Product 2 - $55 x 1</p>
            <button class="remove-from-cart">Remove</button>
        </div>
        <p>Total Items: 3</p>
        <p>Total Cost: $115</p>
    </div>

    <form id="checkout-form">
        <h2>Checkout</h2>
        <label for="name">Name:</label>
        <input type="text" id="name" required>
        <label for="address">Address:</label>
        <textarea id="address" required></textarea>
        <label for="email">Email:</label>
        <input type="email" id="email" required>
        <button id="place-order">Place Order</button>
    </form>

    <script>
        // JavaScript for adding and removing items from the cart
        const addToCartButtons = document.querySelectorAll('.add-to-cart');
        const removeFromCartButtons = document.querySelectorAll('.remove-from-cart');

        addToCartButtons.forEach((button) => {
            button.addEventListener('click', () => {
                // Add your code to add items to the cart here
            });
        });

        removeFromCartButtons.forEach((button) => {
            button.addEventListener('click', () => {
                // Add your code to remove items from the cart here
            });
        });
    </script>
</body>
</html>

