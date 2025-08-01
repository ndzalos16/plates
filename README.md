<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elegance - Handcrafted Plates</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Playfair+Display:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- Font Awesome for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            scroll-behavior: smooth;
        }
        h1, h2, h3 {
            font-family: 'Playfair Display', serif;
        }
        /* Custom styles for animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .animate-fadeIn {
            animation: fadeIn 1s ease-out forwards;
        }

        /* Floating objects animation */
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }
        
        .floating-circle {
            position: absolute;
            background: rgba(147, 197, 253, 0.2);
            border-radius: 50%;
            z-index: 10;
            animation-name: float;
            animation-duration: 4s;
            animation-iteration-count: infinite;
            animation-timing-function: ease-in-out;
            pointer-events: none;
        }

        /* Hero section background image and overlay */
        .hero-background {
            background-image: url('WhatsApp Image 2025-08-01 at 18.49.09_002d80d7.jpg');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
        }

        /* Styles for the modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 100;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.4);
            backdrop-filter: blur(5px);
        }

        .modal-content {
            background-color: #fefefe;
            margin: 15% auto;
            padding: 20px;
            border-radius: 10px;
            width: 90%;
            max-width: 500px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }

        .close-button {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }

        .close-button:hover,
        .close-button:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800">

    <div id="app" class="relative">
        <!-- Header/Navigation -->
        <header class="sticky top-0 z-50 bg-white shadow-sm">
            <nav class="container mx-auto px-4 sm:px-6 lg:px-8 py-4 flex justify-between items-center">
                <!-- Logo with corrected image source -->
                <a href="#hero" class="text-3xl font-bold tracking-tight text-gray-900">
                    <img src="WhatsApp_Image_2025-08-01_at_18.24.15_74ed1a8e-removebg-preview.png" alt="Elegance Logo" class="h-12">
                </a>
                
                <!-- Desktop Navigation Links -->
                <ul class="hidden md:flex space-x-8 text-lg">
                    <li><a href="#hero" class="hover:text-indigo-600 transition-colors duration-300">Home</a></li>
                    <li><a href="#products" class="hover:text-indigo-600 transition-colors duration-300">Products</a></li>
                    <li><a href="#about" class="hover:text-indigo-600 transition-colors duration-300">About</a></li>
                    <li><a href="#contact" class="hover:text-indigo-600 transition-colors duration-300">Contact</a></li>
                </ul>

                <!-- Shopping Cart Icon & Mobile Menu Button with basket count -->
                <div class="flex items-center space-x-4">
                    <button id="cart-button" class="relative text-xl text-gray-600 hover:text-indigo-600 transition-colors duration-300 focus:outline-none">
                        <i class="fas fa-shopping-cart"></i>
                        <span id="basket-count" class="absolute -top-2 -right-2 bg-indigo-600 text-white text-xs rounded-full h-5 w-5 flex items-center justify-center">0</span>
                    </button>
                    <button id="mobile-menu-button" class="md:hidden text-xl text-gray-600 focus:outline-none">
                        <i class="fas fa-bars"></i>
                    </button>
                </div>
            </nav>

            <!-- Mobile Menu (Hidden by default) -->
            <div id="mobile-menu" class="hidden md:hidden bg-white shadow-lg py-4">
                <ul class="flex flex-col items-center space-y-4 text-lg">
                    <li><a href="#hero" class="block py-2 hover:bg-gray-100 w-full text-center" onclick="toggleMobileMenu()">Home</a></li>
                    <li><a href="#products" class="block py-2 hover:bg-gray-100 w-full text-center" onclick="toggleMobileMenu()">Products</a></li>
                    <li><a href="#about" class="block py-2 hover:bg-gray-100 w-full text-center" onclick="toggleMobileMenu()">About</a></li>
                    <li><a href="#contact" class="block py-2 hover:bg-gray-100 w-full text-center" onclick="toggleMobileMenu()">Contact</a></li>
                </ul>
            </div>
        </header>

        <!-- Hero Section -->
        <section id="hero" class="hero-background min-h-screen relative flex items-center py-20 animate-fadeIn overflow-hidden">
            <!-- Semi-transparent overlay for text readability -->
            <div class="absolute inset-0 bg-black opacity-30 z-0"></div>
            <!-- Floating circles background -->
            <div class="absolute inset-0 z-0">
                <div class="floating-circle w-20 h-20" style="top: 10%; left: 15%; animation-delay: 0s;"></div>
                <div class="floating-circle w-24 h-24" style="top: 50%; left: 70%; animation-delay: 2s;"></div>
                <div class="floating-circle w-16 h-16" style="top: 80%; left: 40%; animation-delay: 1s;"></div>
                <div class="floating-circle w-28 h-28" style="top: 30%; left: 90%; animation-delay: 3s;"></div>
            </div>
            <div class="container mx-auto px-4 sm:px-6 lg:px-8 flex items-center justify-center relative z-10 text-white">
                <div class="space-y-6 text-center">
                    <h1 class="text-5xl md:text-6xl lg:text-7xl font-bold leading-tight">
                        Crafted for moments, designed for life.
                    </h1>
                    <p class="text-lg max-w-xl mx-auto">
                        Discover our exquisite collection of handcrafted plates, where artistry meets utility.
                    </p>
                    <a href="#products" class="inline-block px-8 py-4 bg-indigo-600 text-white font-semibold text-lg rounded-full shadow-lg hover:bg-indigo-700 transition-all duration-300">
                        Shop the Collection
                    </a>
                </div>
            </div>
        </section>

        <!-- Featured Products Section -->
        <section id="products" class="py-20 bg-gray-50 animate-fadeIn">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16">
                    <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4">Our Signature Collections</h2>
                    <p class="text-lg text-gray-600 max-w-3xl mx-auto">
                        Explore our best-selling collections, meticulously crafted to elevate your dining experience.
                    </p>
                </div>
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
                    <!-- Product Card 1 -->
                    <div class="bg-white rounded-lg shadow-xl overflow-hidden group hover:shadow-2xl transition-shadow duration-300 transform hover:-translate-y-2">
                        <!-- Updated image source for product 1 -->
                        <img src="402f17b3-2d84-48ea-bd1e-2a42727ec60e-thumbnail.webp" alt="Product 1" class="w-full h-64 object-cover transition-transform duration-300 group-hover:scale-105">
                        <div class="p-6 text-center">
                            <h3 class="text-2xl font-semibold text-gray-900 mb-2" data-name="The Earthstone Collection">The Earthstone Collection</h3>
                            <p class="text-gray-500 mb-4">A blend of organic texture and modern design.</p>
                            <span class="text-xl font-bold text-gray-900" data-price="45.00">R45.00</span>
                            <button class="add-to-basket-btn mt-4 w-full px-6 py-3 bg-gray-900 text-white font-semibold rounded-full hover:bg-gray-700 transition-colors duration-300">
                                Add to Basket
                            </button>
                        </div>
                    </div>
                    <!-- Product Card 2 -->
                    <div class="bg-white rounded-lg shadow-xl overflow-hidden group hover:shadow-2xl transition-shadow duration-300 transform hover:-translate-y-2">
                        <!-- Updated image source for product 2 -->
                        <img src="0193531c-365c-4c07-9df6-ae1e2a7815ce-thumbnail.webp" alt="Product 2" class="w-full h-64 object-cover transition-transform duration-300 group-hover:scale-105">
                        <div class="p-6 text-center">
                            <h3 class="text-2xl font-semibold text-gray-900 mb-2" data-name="The Porcelain Series">The Porcelain Series</h3>
                            <p class="text-gray-500 mb-4">Delicate, timeless, and effortlessly elegant.</p>
                            <span class="text-xl font-bold text-gray-900" data-price="60.00">R60.00</span>
                            <button class="add-to-basket-btn mt-4 w-full px-6 py-3 bg-gray-900 text-white font-semibold rounded-full hover:bg-gray-700 transition-colors duration-300">
                                Add to Basket
                            </button>
                        </div>
                    </div>
                    <!-- Product Card 3 -->
                    <div class="bg-white rounded-lg shadow-xl overflow-hidden group hover:shadow-2xl transition-shadow duration-300 transform hover:-translate-y-2">
                        <!-- Updated image source for product 3 -->
                        <img src="047afd00-b353-47a1-9847-d1b70e628e6c.png" alt="Product 3" class="w-full h-64 object-cover transition-transform duration-300 group-hover:scale-105">
                        <div class="p-6 text-center">
                            <h3 class="text-2xl font-semibold text-gray-900 mb-2" data-name="The Modernist Set">The Modernist Set</h3>
                            <p class="text-gray-500 mb-4">Clean lines and minimalist perfection.</p>
                            <span class="text-xl font-bold text-gray-900" data-price="50.00">R50.00</span>
                            <button class="add-to-basket-btn mt-4 w-full px-6 py-3 bg-gray-900 text-white font-semibold rounded-full hover:bg-gray-700 transition-colors duration-300">
                                Add to Basket
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Us Section -->
        <section id="about" class="py-20 bg-blue-50 animate-fadeIn">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8 grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div class="relative flex justify-center lg:justify-start">
                    <img src="https://placehold.co/600x400/E5E7EB/4B5563?text=Our+Studio" alt="Crafting plates" class="w-full max-w-md md:max-w-xl rounded-xl shadow-2xl">
                </div>
                <div class="space-y-6 text-center lg:text-left">
                    <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4">Our Story</h2>
                    <p class="text-lg text-gray-600 max-w-xl mx-auto lg:mx-0">
                        Founded on a passion for craftsmanship and timeless design, Elegance is more than just a brand—it's a celebration of mindful living. Each plate is a work of art, shaped by skilled hands and fired with care, bringing a touch of intentional beauty to every meal.
                    </p>
                    <p class="text-lg text-gray-600 max-w-xl mx-auto lg:mx-0">
                        We believe that the objects we use every day should tell a story. That's why we source our materials ethically and pour our hearts into every piece we create.
                    </p>
                </div>
            </div>
        </section>

        <!-- CTA Section -->
        <section class="py-20 bg-gray-900 text-white text-center animate-fadeIn">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <h2 class="text-4xl md:text-5xl font-bold mb-4">Ready to Elevate Your Dining?</h2>
                <p class="text-lg max-w-3xl mx-auto mb-8 text-gray-300">
                    Join our community and be the first to know about new collections, exclusive offers, and behind-the-scenes stories.
                </p>
                <a href="#products" class="inline-block px-8 py-4 bg-white text-gray-900 font-semibold text-lg rounded-full shadow-lg hover:bg-gray-200 transition-all duration-300">
                    Explore Our Full Collection
                </a>
            </div>
        </section>

        <!-- Footer -->
        <footer id="contact" class="bg-gray-900 text-gray-300 py-12 animate-fadeIn">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8 text-center">
                <div class="flex justify-center space-x-6 mb-6">
                    <a href="tel:0748482314" class="text-xl hover:text-white transition-colors duration-300" aria-label="Call on WhatsApp"><i class="fab fa-whatsapp"></i></a>
                    <a href="https://www.tiktok.com/@aphiwetofile7?_t=ZM-8yWY47u0RGP&_r=1" target="_blank" class="text-xl hover:text-white transition-colors duration-300" aria-label="Visit our TikTok page"><i class="fab fa-tiktok"></i></a>
                    <a href="#" class="text-xl hover:text-white transition-colors duration-300"><i class="fab fa-instagram"></i></a>
                    <a href="#" class="text-xl hover:text-white transition-colors duration-300"><i class="fab fa-pinterest-p"></i></a>
                    <a href="#" class="text-xl hover:text-white transition-colors duration-300"><i class="fas fa-envelope"></i></a>
                </div>
                <p>&copy; 2025 Elegance. All rights reserved.</p>
            </div>
        </footer>
    </div>

    <!-- The Modal for the order summary -->
    <div id="order-modal" class="modal">
        <div class="modal-content">
            <span class="close-button">&times;</span>
            <h3 class="text-2xl font-bold text-gray-900 mb-4">Your Order</h3>
            <div id="order-summary-content" class="mb-4"></div>
            <button id="order-whatsapp-btn" class="w-full px-6 py-3 bg-green-600 text-white font-semibold rounded-full hover:bg-green-700 transition-colors duration-300">
                Order via WhatsApp
            </button>
        </div>
    </div>

    <script>
        // Global variables for basket and order modal
        let basket = [];
        const whatsappNumber = '27748482314'; // SA number with country code, no + or 00
        
        const cartButton = document.getElementById('cart-button');
        const basketCount = document.getElementById('basket-count');
        const orderModal = document.getElementById('order-modal');
        const closeButton = document.querySelector('.close-button');
        const orderSummaryContent = document.getElementById('order-summary-content');
        const orderWhatsappBtn = document.getElementById('order-whatsapp-btn');

        // Function to update the basket count in the header
        function updateBasketCount() {
            const totalItems = basket.reduce((sum, item) => sum + item.quantity, 0);
            basketCount.textContent = totalItems;
        }

        // Function to add a product to the basket
        function addToBasket(productName, productPrice) {
            const existingItem = basket.find(item => item.name === productName);
            if (existingItem) {
                existingItem.quantity++;
            } else {
                basket.push({ name: productName, price: productPrice, quantity: 1 });
            }
            updateBasketCount();
        }

        // Event listener for all "Add to Basket" buttons
        document.querySelectorAll('.add-to-basket-btn').forEach(button => {
            button.addEventListener('click', () => {
                const productCard = button.closest('.bg-white');
                const productName = productCard.querySelector('h3').getAttribute('data-name');
                const productPrice = parseFloat(productCard.querySelector('span').getAttribute('data-price'));
                addToBasket(productName, productPrice);
            });
        });

        // Event listener to open the order modal
        cartButton.addEventListener('click', () => {
            if (basket.length > 0) {
                let summaryHTML = '<ul class="list-disc pl-5 space-y-2">';
                let total = 0;
                let orderText = "Hello, I would like to place an order for the following items:\n\n";

                basket.forEach(item => {
                    const itemTotal = item.price * item.quantity;
                    summaryHTML += `<li>${item.name} (x${item.quantity}) - R${itemTotal.toFixed(2)}</li>`;
                    orderText += `${item.name} (x${item.quantity}) - R${itemTotal.toFixed(2)}\n`;
                    total += itemTotal;
                });

                summaryHTML += `</ul><div class="mt-4 text-lg font-bold">Total: R${total.toFixed(2)}</div>`;
                orderSummaryContent.innerHTML = summaryHTML;
                
                // Construct the WhatsApp message with order details
                const fullOrderMessage = encodeURIComponent(orderText + `\nTotal: R${total.toFixed(2)}`);
                orderWhatsappBtn.setAttribute('data-message', fullOrderMessage);
                
                orderModal.style.display = 'block';
            } else {
                 alert('Your basket is empty. Please add some items to place an order.');
            }
        });

        // Event listener for the "Order via WhatsApp" button
        orderWhatsappBtn.addEventListener('click', () => {
            const message = orderWhatsappBtn.getAttribute('data-message');
            if (message) {
                window.open(`https://wa.me/${whatsappNumber}?text=${message}`, '_blank');
                orderModal.style.display = 'none';
                basket = []; // Clear the basket after placing the order
                updateBasketCount();
            }
        });

        // Event listeners to close the modal
        closeButton.addEventListener('click', () => {
            orderModal.style.display = 'none';
        });
        window.addEventListener('click', (event) => {
            if (event.target === orderModal) {
                orderModal.style.display = 'none';
            }
        });

        // Mobile menu toggle
        const mobileMenuButton = document.getElementById('mobile-menu-button');
        const mobileMenu = document.getElementById('mobile-menu');

        function toggleMobileMenu() {
            mobileMenu.classList.toggle('hidden');
        }

        mobileMenuButton.addEventListener('click', toggleMobileMenu);

    </script>
</body>
</html>
