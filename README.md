<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Shoe Store</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            background-image: url('https://cdn.builderfly.com/wp/assets/sell-online/sell-shoes1a.jpg');
            background-size: cover;
            background-position: center;
            color: black; /* Set text color to black */
        }
        h1, h2, h3 {
            text-align: center;
            text-shadow: 1px 1px 2px rgba(255, 255, 255, 0.7); /* Light shadow for better readability */
        }
        .container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
        }
        .item {
            background: rgba(255, 255, 255, 0.8);
            border: 1px solid #ccc;
            border-radius: 5px;
            margin: 10px;
            padding: 20px;
            width: 200px;
            text-align: center;
        }
        .item img {
            max-width: 100%;
            height: auto;
            border-radius: 5px;
        }
        .item button {
            background-color: #28a745;
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            border-radius: 5px;
        }
        .item button:hover {
            background-color: #218838;
        }
        .modal, .payment-modal {
            display: none;
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.5);
        }
        .modal-content, .payment-content {
            background-color: #fefefe;
            margin: 15% auto;
            padding: 20px;
            border: 1px solid #888;
            width: 300px;
            text-align: center;
            border-radius: 5px;
        }
        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }
        .close:hover,
        .close:focus {
            color: black; /* Change close button hover color to black */
            text-decoration: none;
            cursor: pointer;
        }
        input[type="email"], input[type="password"], input[type="text"] {
            width: 90%;
            padding: 10px;
            margin: 5px 0;
        }
        button[type="submit"], button[type="button"] {
            background-color: #007bff;
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            border-radius: 5px;
        }
        button[type="submit"]:hover, button[type="button"]:hover {
            background-color: #0056b3;
        }
        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 5px 0;
        }
        .cart-item button {
            background-color: #dc3545;
        }
        .cart-item button:hover {
            background-color: #c82333;
        }
        .basket {
            margin-top: 40px;
            text-align: center;
            padding: 20px;
            background: rgba(255, 255, 255, 0.8);
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        footer {
            text-align: center;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.8);
            position: relative;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>

<h1>DENNIS ENTERPRISE</h1>
<div class="container">
    <!-- Shoe items with images -->
    <div class="item">
        <img src="https://www.makingsenseofcents.com/wp-content/uploads/2023/09/best-place-to-sell-shoes-1024x682.jpg" alt="Shoe 1">
        <h2>Item 1</h2>
        <p>Price: Ksh 5000</p>
        <button onclick="addToBasket('Item 1', 5000)">Add to Basket</button>
    </div>
    <div class="item">
        <img src="https://cdn.prod.website-files.com/601411ff11c3efbd2603b7c9/63b6c9324cd6e274eaae8053_how-to-sell-shoes-shopify-featured.jpg" alt="Shoe 2">
        <h2>Item 2</h2>
        <p>Price: Ksh 6000</p>
        <button onclick="addToBasket('Item 2', 6000)">Add to Basket</button>
    </div>
    <div class="item">
        <img src="https://via.placeholder.com/200" alt="Shoe 3">
        <h2>Item 3</h2>
        <p>Price: Ksh 7000</p>
        <button onclick="addToBasket('Item 3', 7000)">Add to Basket</button>
    </div>
    <div class="item">
        <img src="https://via.placeholder.com/200" alt="Shoe 4">
        <h2>Item 4</h2>
        <p>Price: Ksh 8000</p>
        <button onclick="addToBasket('Item 4', 8000)">Add to Basket</button>
    </div>
    <div class="item">
        <img src="https://encrypted-tbn3.gstatic.com/shopping?q=tbn:ANd9GcRRHEG46FPMRupMJ9Gf2NfASwZXRVFH1vmp-9-JEvddYF19mIJUDcO2kwCfct5NDWLacVDviYSJbsl9qW1xR_ceGqX89RzuAPuC1Ub-9lnqGIg7wcBPlgRE7QARi5PvM2qLI_Z1-YQ&usqp=CAc" alt="Shoe 5">
        <h2>Item 5</h2>
        <p>Price: Ksh 9000</p>
        <button onclick="addToBasket('Item 5', 9000)">Add to Basket</button>
    </div>
    <div class="item">
        <img src="https://via.placeholder.com/200" alt="Shoe 6">
        <h2>Item 6</h2>
        <p>Price: Ksh 4000</p>
        <button onclick="addToBasket('Item 6', 4000)">Add to Basket</button>
    </div>
    <div class="item">
        <img src="https://via.placeholder.com/200" alt="Shoe 7">
        <h2>Item 7</h2>
        <p>Price: Ksh 4500</p>
        <button onclick="addToBasket('Item 7', 4500)">Add to Basket</button>
    </div>
    <div class="item">
        <img src="https://via.placeholder.com/200" alt="Shoe 8">
        <h2>Item 8</h2>
        <p>Price: Ksh 3000</p>
        <button onclick="addToBasket('Item 8', 3000)">Add to Basket</button>
    </div>
    <div class="item">
        <img src="https://via.placeholder.com/200" alt="Shoe 9">
        <h2>Item 9</h2>
        <p>Price: Ksh 3500</p>
        <button onclick="addToBasket('Item 9', 3500)">Add to Basket</button>
    </div>
    <div class="item">
        <img src="https://via.placeholder.com/200" alt="Shoe 10">
        <h2>Item 10</h2>
        <p>Price: Ksh 5500</p>
        <button onclick="addToBasket('Item 10', 5500)">Add to Basket</button>
    </div>
</div>

<!-- Modal for login -->
<div id="loginModal" class="modal">
    <div class="modal-content">
        <span class="close" onclick="closeModal()">&times;</span>
        <h2>Sign In</h2>
        <form id="loginForm" onsubmit="return handleLogin(event)">
            <input type="email" id="email" placeholder="Email" required><br>
            <input type="password" id="password" placeholder="Password" required><br>
            <button type="submit">Log In</button>
        </form>
    </div>
</div>

<!-- Basket -->
<div class="basket">
    <h2>Your Basket</h2>
    <div id="cartItems"></div>
    <div>Total Price: Ksh <span id="totalPrice">0</span></div>
    <button id="paymentButton" style="display:none;" onclick="showPaymentMethod()">Proceed to Payment</button>
</div>

<!-- Modal for payment -->
<div id="paymentModal" class="payment-modal">
    <div class="payment-content">
        <span class="close" onclick="closePaymentModal()">&times;</span>
        <h2>Payment Method</h2>
        <select id="paymentMethod" onchange="togglePaymentFields()">
            <option value="">Select Method</option>
            <option value="credit">Credit Card</option>
            <option value="paypal">PayPal</option>
            <option value="mpesa">M-Pesa</option>
        </select>
        <div id="creditFields" style="display: none;">
            <input type="text" placeholder="Card Number">
            <input type="text" placeholder="Expiry Date">
            <input type="text" placeholder="CVV">
        </div>
        <div id="paypalFields" style="display: none;">
            <input type="text" placeholder="PayPal Email">
        </div>
        <div id="mpesaFields" style="display: none;">
            <input type="text" placeholder="Phone Number" required>
            <input type="text" id="mpesaPin" placeholder="M-Pesa PIN (Ksh)" readonly>
        </div>
        <button onclick="completePayment()">Pay</button>
    </div>
</div>

<footer>
    <p>&copy; 2024 Online Shoe Store. All rights reserved.</p>
</footer>

<script>
    let cart = [];
    let totalPrice = 0;
    let isSignedIn = false;

    function addToBasket(shoe, price) {
        if (!isSignedIn) {
            showSignInModal();
            return;
        }
        if (cart.length < 10) {
            cart.push({ shoe, price });
            totalPrice += price;
            updateCartDisplay();
        } else {
            alert('You can only add up to 10 items to your basket.');
        }
    }

    function updateCartDisplay() {
        const cartItemsDiv = document.getElementById('cartItems');
        cartItemsDiv.innerHTML = '';
        cart.forEach((item, index) => {
            cartItemsDiv.innerHTML += `<div class="cart-item">${item.shoe} - Ksh ${item.price} <button onclick="removeFromCart(${index})">Remove</button></div>`;
        });
        document.getElementById('totalPrice').innerText = totalPrice;
        document.getElementById('paymentButton').style.display = cart.length > 0 ? 'block' : 'none';
    }

    function removeFromCart(index) {
        totalPrice -= cart[index].price;
        cart.splice(index, 1);
        updateCartDisplay();
    }

    function showSignInModal() {
        document.getElementById('loginModal').style.display = 'block';
    }

    function closeModal() {
        document.getElementById('loginModal').style.display = 'none';
    }

    function handleLogin(event) {
        event.preventDefault();
        const email = document.getElementById('email').value;
        const password = document.getElementById('password').value;

        if (email && password) {
            isSignedIn = true; // User is now signed in
            alert('Successfully logged in! You can now add items to your basket.');
            closeModal();
        } else {
            alert('Please enter valid details.');
        }
    }

    function showPaymentMethod() {
        document.getElementById('paymentModal').style.display = 'block';
        document.getElementById('mpesaPin').value = totalPrice; // Set M-Pesa PIN input to total amount
    }

    function closePaymentModal() {
        document.getElementById('paymentModal').style.display = 'none';
        document.getElementById('paymentMethod').value = '';
        togglePaymentFields();
    }

    function togglePaymentFields() {
        const method = document.getElementById('paymentMethod').value;
        document.getElementById('creditFields').style.display = method === 'credit' ? 'block' : 'none';
        document.getElementById('paypalFields').style.display = method === 'paypal' ? 'block' : 'none';
        document.getElementById('mpesaFields').style.display = method === 'mpesa' ? 'block' : 'none';
    }

    function completePayment() {
        const method = document.getElementById('paymentMethod').value;
        let validPayment = false;

        if (method === 'credit') {
            validPayment = true; // Simplified for demonstration
        } else if (method === 'paypal') {
            validPayment = true; // Simplified for demonstration
        } else if (method === 'mpesa') {
            const phoneNumber = document.querySelector('#mpesaFields input[type="text"]').value;
            const mpesaPin = document.getElementById('mpesaPin').value;
            if (phoneNumber) {
                validPayment = true; // Simplified for demonstration
            } else {
                alert('Please enter your phone number.');
                return;
            }
        }

        if (validPayment) {
            alert('Payment successful! Thank you for your purchase.');
            closePaymentModal();
            cart = [];
            totalPrice = 0;
            updateCartDisplay();
        } else {
            alert('Payment failed. Please check your details.');
        }
    }

    // Close modal when clicking outside of it
    window.onclick = function(event) {
        const modal = document.getElementById('loginModal');
        const paymentModal = document.getElementById('paymentModal');
        if (event.target == modal) {
            closeModal();
        }
        if (event.target == paymentModal) {
            closePaymentModal();
        }
    }
</script>

</body>
</html>
