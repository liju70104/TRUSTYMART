<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TRUSTYMART - Your Trusted Shopping Destination</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Reset and Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #ff9900;
            --secondary: #232f3e;
            --light: #f2f2f2;
            --dark: #131921;
            --white: #ffffff;
            --text: #0f1111;
            --success: #007600;
            --danger: #b12704;
            --accent: #ff5a5f;
            --prime: #00a8e1;
            --eco: #2ecc71;
            --ai: #9b59b6;
        }

        body {
            background-color: var(--light);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        button {
            cursor: pointer;
            border: none;
            outline: none;
        }

        .container {
            max-width: 1500px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Header Styles */
        header {
            background-color: var(--dark);
            color: var(--white);
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .header-top {
            display: flex;
            align-items: center;
            padding: 10px 0;
            flex-wrap: wrap;
        }

        .logo {
            display: flex;
            align-items: center;
            margin-right: 20px;
        }

        .logo-icon {
            font-size: 2rem;
            color: var(--primary);
            margin-right: 10px;
        }

        .logo-text {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--white);
        }

        .delivery-info {
            display: flex;
            flex-direction: column;
            margin-right: 20px;
            padding: 5px 10px;
            border: 1px solid rgba(255,255,255,0.3);
            border-radius: 4px;
            cursor: pointer;
        }

        .delivery-location {
            font-size: 0.7rem;
            color: #ccc;
        }

        .delivery-address {
            font-size: 0.9rem;
            font-weight: bold;
        }

        .search-bar {
            flex: 1;
            display: flex;
            margin: 0 20px;
            min-width: 200px;
        }

        .search-bar select {
            background-color: #f3f3f3;
            border: none;
            border-radius: 4px 0 0 4px;
            padding: 0 10px;
            font-size: 0.9rem;
            color: #555;
            cursor: pointer;
        }

        .search-bar input {
            width: 100%;
            padding: 10px 15px;
            border: none;
            font-size: 1rem;
        }

        .search-bar button {
            background-color: var(--primary);
            color: var(--white);
            padding: 0 15px;
            border-radius: 0 4px 4px 0;
            font-size: 1rem;
        }

        .header-actions {
            display: flex;
            align-items: center;
            flex-wrap: wrap;
        }

        .header-action {
            margin-left: 15px;
            display: flex;
            flex-direction: column;
            align-items: center;
            cursor: pointer;
            position: relative;
            padding: 5px;
        }

        .header-action i {
            font-size: 1.5rem;
        }

        .header-action span {
            font-size: 0.8rem;
            margin-top: 2px;
        }

        .cart-count, .wishlist-count, .notification-count {
            background-color: var(--primary);
            color: var(--white);
            border-radius: 50%;
            width: 18px;
            height: 18px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.7rem;
            position: absolute;
            top: 0;
            right: 0;
        }

        .header-bottom {
            background-color: var(--secondary);
            padding: 8px 0;
            overflow-x: auto;
        }

        .nav-links {
            display: flex;
            list-style: none;
            min-width: max-content;
        }

        .nav-links li {
            margin-right: 15px;
        }

        .nav-links a {
            color: var(--white);
            font-size: 0.9rem;
            display: flex;
            align-items: center;
            padding: 5px 10px;
            border-radius: 4px;
            transition: background 0.3s;
            white-space: nowrap;
        }

        .nav-links a:hover, .nav-links a.active {
            background: rgba(255,255,255,0.1);
        }

        .nav-links i {
            margin-right: 5px;
        }

        .hamburger {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: white;
            margin-left: 10px;
        }

        .mobile-menu {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.9);
            z-index: 2000;
            flex-direction: column;
            padding: 20px;
            overflow-y: auto;
        }

        .mobile-menu.active {
            display: flex;
        }

        .mobile-menu-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 1px solid rgba(255,255,255,0.2);
        }

        .mobile-menu-logo {
            display: flex;
            align-items: center;
            color: white;
        }

        .close-menu {
            background: none;
            color: white;
            font-size: 1.5rem;
            border: none;
        }

        .mobile-nav-links {
            list-style: none;
            width: 100%;
        }

        .mobile-nav-links li {
            margin-bottom: 10px;
        }

        .mobile-nav-links a {
            color: white;
            display: flex;
            align-items: center;
            padding: 15px;
            border-radius: 5px;
            background: rgba(255,255,255,0.1);
            font-size: 1.1rem;
        }

        .mobile-nav-links i {
            margin-right: 10px;
            width: 20px;
            text-align: center;
        }

        /* Prime Badge */
        .prime-badge {
            display: inline-flex;
            align-items: center;
            background: linear-gradient(to right, #00a8e1, #007eb9);
            color: white;
            padding: 2px 6px;
            border-radius: 3px;
            font-size: 0.7rem;
            font-weight: bold;
            margin-left: 5px;
        }

        /* AI Assistant */
        .ai-assistant {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, var(--ai), #8e44ad);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            cursor: pointer;
            z-index: 1000;
            transition: transform 0.3s;
        }

        .ai-assistant:hover {
            transform: scale(1.1);
        }

        .ai-chat {
            position: fixed;
            bottom: 90px;
            right: 20px;
            width: 350px;
            height: 450px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 5px 25px rgba(0,0,0,0.2);
            display: none;
            flex-direction: column;
            z-index: 1001;
            overflow: hidden;
        }

        .ai-chat.active {
            display: flex;
        }

        .ai-header {
            background: linear-gradient(135deg, var(--ai), #8e44ad);
            color: white;
            padding: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .ai-close {
            background: none;
            border: none;
            color: white;
            font-size: 1.2rem;
            cursor: pointer;
        }

        .ai-messages {
            flex: 1;
            padding: 15px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .ai-message {
            padding: 10px 15px;
            border-radius: 18px;
            max-width: 80%;
            font-size: 0.9rem;
        }

        .ai-message.user {
            background: var(--primary);
            color: white;
            align-self: flex-end;
        }

        .ai-message.bot {
            background: #f1f1f1;
            color: #333;
            align-self: flex-start;
        }

        .ai-input {
            display: flex;
            padding: 10px;
            border-top: 1px solid #eee;
        }

        .ai-input input {
            flex: 1;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 20px;
            outline: none;
        }

        .ai-input button {
            background: var(--ai);
            color: white;
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            margin-left: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* Sustainability Badge */
        .sustainability-badge {
            display: inline-flex;
            align-items: center;
            background: var(--eco);
            color: white;
            padding: 2px 6px;
            border-radius: 3px;
            font-size: 0.7rem;
            font-weight: bold;
            margin-left: 5px;
        }

        /* AR Preview */
        .ar-preview {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            z-index: 3000;
            display: none;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .ar-preview.active {
            display: flex;
        }

        .ar-content {
            width: 90%;
            height: 70%;
            background: white;
            border-radius: 10px;
            display: flex;
            flex-direction: column;
            overflow: hidden;
        }

        .ar-header {
            padding: 15px;
            background: var(--dark);
            color: white;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .ar-close {
            background: none;
            border: none;
            color: white;
            font-size: 1.2rem;
            cursor: pointer;
        }

        .ar-view {
            flex: 1;
            background: #000;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
        }

        /* Main Content Styles */
        main {
            min-height: calc(100vh - 180px);
            padding: 20px 0;
        }

        .page {
            display: none;
        }

        .page.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Home Page */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://images.unsplash.com/photo-1607082350899-7e105aa886ae?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80');
            background-size: cover;
            background-position: center;
            color: var(--white);
            padding: 40px 20px;
            text-align: center;
            border-radius: 8px;
            margin-bottom: 20px;
        }

        .hero h1 {
            font-size: 2rem;
            margin-bottom: 15px;
        }

        .hero p {
            font-size: 1.1rem;
            max-width: 700px;
            margin: 0 auto 20px;
        }

        .btn {
            display: inline-block;
            background-color: var(--primary);
            color: var(--white);
            padding: 10px 20px;
            border-radius: 4px;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .btn:hover {
            background-color: #e68900;
            transform: translateY(-2px);
        }

        .offers-container {
            background-color: var(--white);
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 20px;
            overflow: hidden;
            position: relative;
        }

        .offers-title {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }

        .offers-title i {
            color: var(--danger);
            margin-right: 10px;
            font-size: 1.5rem;
        }

        .offers-scroll {
            display: flex;
            animation: scroll-right-to-left 30s linear infinite;
        }

        .offer-item {
            min-width: 200px;
            margin-right: 20px;
            background-color: var(--light);
            border-radius: 8px;
            padding: 15px;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            cursor: pointer;
            transition: transform 0.3s;
        }

        .offer-item:hover {
            transform: translateY(-5px);
        }

        .offer-item img {
            width: 100%;
            height: 120px;
            object-fit: cover;
            border-radius: 4px;
            margin-bottom: 10px;
        }

        .offer-price {
            color: var(--danger);
            font-weight: bold;
            font-size: 1.2rem;
        }

        .offer-old-price {
            text-decoration: line-through;
            color: #777;
            font-size: 0.9rem;
        }

        @keyframes scroll-right-to-left {
            0% {
                transform: translateX(100%);
            }
            100% {
                transform: translateX(-100%);
            }
        }

        .categories {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 15px;
            margin-bottom: 20px;
        }

        .category-card {
            background-color: var(--white);
            border-radius: 8px;
            padding: 15px;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
            cursor: pointer;
        }

        .category-card:hover {
            transform: translateY(-5px);
        }

        .category-card i {
            font-size: 2rem;
            color: var(--primary);
            margin-bottom: 10px;
        }

        .category-card h3 {
            font-size: 1rem;
            margin-bottom: 5px;
        }

        .category-card p {
            font-size: 0.8rem;
            color: #666;
        }

        .products {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }

        .product-card {
            background-color: var(--white);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-5px);
        }

        .product-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .product-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            background: var(--accent);
            color: white;
            padding: 3px 8px;
            border-radius: 4px;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .product-info {
            padding: 15px;
        }

        .product-title {
            font-weight: bold;
            margin-bottom: 10px;
            height: 40px;
            overflow: hidden;
        }

        .product-price {
            color: var(--danger);
            font-weight: bold;
            font-size: 1.2rem;
            margin-bottom: 10px;
        }

        .product-rating {
            color: var(--primary);
            margin-bottom: 10px;
        }

        .product-specs {
            font-size: 0.8rem;
            color: #666;
            margin-bottom: 10px;
            height: 60px;
            overflow: hidden;
        }

        .product-actions {
            display: flex;
            gap: 10px;
        }

        .add-to-cart, .buy-now, .wishlist-btn {
            flex: 1;
            padding: 8px 0;
            border-radius: 4px;
            font-weight: bold;
            text-align: center;
            transition: all 0.3s;
        }

        .add-to-cart {
            background-color: var(--primary);
            color: var(--white);
        }

        .add-to-cart:hover {
            background-color: #e68900;
        }

        .buy-now {
            background-color: var(--accent);
            color: var(--white);
        }

        .buy-now:hover {
            background-color: #e04e52;
        }

        .wishlist-btn {
            background-color: transparent;
            border: 1px solid #ddd;
            color: #666;
        }

        .wishlist-btn.active {
            background-color: var(--accent);
            color: white;
            border-color: var(--accent);
        }

        /* Product Detail Page */
        .product-detail {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            background: var(--white);
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 20px;
        }

        .product-gallery {
            flex: 1;
            min-width: 300px;
        }

        .product-main-image {
            width: 100%;
            border-radius: 8px;
            margin-bottom: 10px;
        }

        .product-thumbnails {
            display: flex;
            gap: 10px;
            overflow-x: auto;
        }

        .product-thumbnail {
            width: 80px;
            height: 80px;
            object-fit: cover;
            border-radius: 4px;
            cursor: pointer;
            border: 2px solid transparent;
        }

        .product-thumbnail.active {
            border-color: var(--primary);
        }

        .product-info-detail {
            flex: 1;
            min-width: 300px;
        }

        .product-title-detail {
            font-size: 1.5rem;
            margin-bottom: 10px;
        }

        .product-rating-detail {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }

        .product-price-detail {
            font-size: 1.5rem;
            color: var(--danger);
            margin-bottom: 15px;
        }

        .product-description {
            margin-bottom: 20px;
            line-height: 1.6;
        }

        .product-specifications {
            margin-bottom: 20px;
        }

        .specs-table {
            width: 100%;
            border-collapse: collapse;
        }

        .specs-table td {
            padding: 8px;
            border-bottom: 1px solid #eee;
        }

        .specs-table td:first-child {
            font-weight: bold;
            width: 30%;
        }

        .product-actions-detail {
            display: flex;
            gap: 15px;
            margin-top: 20px;
            flex-wrap: wrap;
        }

        .add-to-cart-detail, .buy-now-detail {
            padding: 12px 20px;
            border-radius: 4px;
            font-weight: bold;
            font-size: 1rem;
            min-width: 150px;
        }

        .add-to-cart-detail {
            background-color: var(--primary);
            color: var(--white);
        }

        .buy-now-detail {
            background-color: var(--accent);
            color: var(--white);
        }

        /* Cart Page */
        .cart-items {
            background: var(--white);
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 20px;
        }

        .cart-item {
            display: flex;
            padding: 15px 0;
            border-bottom: 1px solid #eee;
            flex-wrap: wrap;
        }

        .cart-item:last-child {
            border-bottom: none;
        }

        .cart-item-img {
            width: 120px;
            height: 120px;
            object-fit: cover;
            border-radius: 4px;
            margin-right: 15px;
            margin-bottom: 10px;
        }

        .cart-item-details {
            flex: 1;
            min-width: 200px;
        }

        .cart-item-title {
            font-weight: bold;
            margin-bottom: 5px;
        }

        .cart-item-price {
            color: var(--danger);
            font-weight: bold;
            margin-bottom: 10px;
        }

        .cart-item-actions {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-top: 10px;
        }

        .quantity-selector {
            display: flex;
            align-items: center;
            border: 1px solid #ddd;
            border-radius: 4px;
            overflow: hidden;
        }

        .quantity-btn {
            background: #f5f5f5;
            border: none;
            padding: 5px 10px;
            cursor: pointer;
        }

        .quantity-input {
            width: 40px;
            text-align: center;
            border: none;
            padding: 5px;
        }

        .remove-btn {
            color: var(--danger);
            background: none;
            border: none;
            cursor: pointer;
        }

        .cart-summary {
            background: var(--white);
            border-radius: 8px;
            padding: 20px;
        }

        .summary-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }

        .summary-total {
            font-weight: bold;
            font-size: 1.2rem;
            border-top: 1px solid #eee;
            padding-top: 10px;
            margin-top: 10px;
        }

        /* Orders Page */
        .orders-list {
            background: var(--white);
            border-radius: 8px;
            padding: 20px;
        }

        .order-card {
            border: 1px solid #eee;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 15px;
        }

        .order-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            padding-bottom: 10px;
            border-bottom: 1px solid #eee;
            flex-wrap: wrap;
        }

        .order-id {
            font-weight: bold;
        }

        .order-date {
            color: #666;
        }

        .order-status {
            display: inline-block;
            padding: 5px 10px;
            border-radius: 4px;
            font-size: 0.8rem;
            font-weight: bold;
            margin-top: 5px;
        }

        .status-delivered {
            background-color: #e6f4ea;
            color: var(--success);
        }

        .status-pending {
            background-color: #fef6e6;
            color: #b36b00;
        }

        .status-shipped {
            background-color: #e6f3ff;
            color: #0066c0;
        }

        .order-items {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .order-item {
            display: flex;
            gap: 15px;
        }

        .order-item-img {
            width: 80px;
            height: 80px;
            object-fit: cover;
            border-radius: 4px;
        }

        .order-item-details {
            flex: 1;
        }

        .order-item-title {
            font-weight: bold;
            margin-bottom: 5px;
        }

        .order-item-price {
            color: #666;
        }

        .order-actions {
            display: flex;
            gap: 10px;
            margin-top: 15px;
            flex-wrap: wrap;
        }

        /* Page Titles */
        .page-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
        }

        .page-title i {
            margin-right: 10px;
            color: var(--primary);
        }

        /* Form Styles */
        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }

        /* Card Styles */
        .card {
            background-color: var(--white);
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        /* Footer Styles */
        footer {
            background-color: var(--secondary);
            color: var(--white);
            padding: 30px 0 15px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }

        .footer-column h3 {
            font-size: 1.2rem;
            margin-bottom: 15px;
            color: var(--primary);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 8px;
        }

        .footer-links a {
            color: #ddd;
            transition: color 0.3s ease;
            font-size: 0.9rem;
        }

        .footer-links a:hover {
            color: var(--primary);
        }

        .social-links {
            display: flex;
            gap: 10px;
            margin-top: 15px;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 35px;
            height: 35px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            transition: background-color 0.3s ease;
        }

        .social-links a:hover {
            background-color: var(--primary);
        }

        .copyright {
            text-align: center;
            padding-top: 15px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.8rem;
            color: #aaa;
        }

        /* Toast Notification */
        .toast {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: var(--success);
            color: white;
            padding: 15px 20px;
            border-radius: 5px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.15);
            z-index: 3000;
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.3s ease;
        }

        .toast.show {
            transform: translateY(0);
            opacity: 1;
        }

        /* Login Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 4000;
            align-items: center;
            justify-content: center;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background-color: white;
            padding: 30px;
            border-radius: 8px;
            width: 90%;
            max-width: 400px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.15);
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .close-modal {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #777;
        }

        /* Filter Section */
        .filter-section {
            background: var(--white);
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 20px;
        }

        .filter-title {
            font-weight: bold;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
        }

        .filter-options {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .filter-option {
            background: #f5f5f5;
            border: 1px solid #ddd;
            border-radius: 4px;
            padding: 8px 15px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .filter-option.active {
            background: var(--primary);
            color: white;
            border-color: var(--primary);
        }

        /* Responsive Styles */
        @media (max-width: 992px) {
            .header-top {
                justify-content: space-between;
            }
            
            .search-bar {
                order: 3;
                width: 100%;
                margin: 10px 0 0;
            }
            
            .hamburger {
                display: block;
            }
            
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
        }

        @media (max-width: 768px) {
            .header-action span {
                display: none;
            }
            
            .header-action {
                margin-left: 10px;
            }
            
            .hero {
                padding: 30px 15px;
            }
            
            .categories {
                grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
                gap: 10px;
            }
            
            .products {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
                gap: 15px;
            }
            
            .product-detail {
                flex-direction: column;
            }
            
            .product-actions-detail {
                flex-direction: column;
            }
            
            .add-to-cart-detail, .buy-now-detail {
                width: 100%;
            }
            
            .cart-item {
                flex-direction: column;
            }
            
            .cart-item-img {
                width: 100%;
                height: auto;
                margin-right: 0;
            }
        }

        @media (max-width: 576px) {
            .logo-text {
                font-size: 1.2rem;
            }
            
            .hero h1 {
                font-size: 1.5rem;
            }
            
            .categories {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .products {
                grid-template-columns: 1fr;
            }
            
            .product-actions {
                flex-direction: column;
            }
            
            .order-header {
                flex-direction: column;
            }
            
            .order-item {
                flex-direction: column;
            }
            
            .order-item-img {
                width: 100%;
                height: auto;
            }
            
            .order-actions {
                flex-direction: column;
            }
            
            .footer-content {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header Section -->
    <header>
        <div class="container">
            <div class="header-top">
                <div class="logo">
                    <i class="fas fa-shopping-bag logo-icon"></i>
                    <span class="logo-text">TRUSTYMART</span>
                </div>
                
                <div class="delivery-info" onclick="showLocationModal()">
                    <span class="delivery-location">Deliver to</span>
                    <span class="delivery-address">Dindigul 624001</span>
                </div>
                
                <div class="search-bar">
                    <select id="search-category">
                        <option value="all">All</option>
                        <option value="electronics">Electronics</option>
                        <option value="fashion">Fashion</option>
                        <option value="home">Home & Kitchen</option>
                        <option value="beauty">Beauty</option>
                    </select>
                    <input type="text" id="search-input" placeholder="Search for products, brands and more">
                    <button id="search-btn"><i class="fas fa-search"></i></button>
                </div>
                
                <div class="header-actions">
                    <div class="header-action" onclick="showLoginModal()">
                        <i class="fas fa-user"></i>
                        <span>Account</span>
                    </div>
                    <div class="header-action" onclick="showPage('orders')">
                        <i class="fas fa-box"></i>
                        <span>Orders</span>
                    </div>
                    <div class="header-action" onclick="showPage('notifications')">
                        <i class="fas fa-bell"></i>
                        <span>Notifications</span>
                        <div class="notification-count">3</div>
                    </div>
                    <div class="header-action wishlist-icon" onclick="showPage('wishlist')">
                        <i class="fas fa-heart"></i>
                        <span>Wishlist</span>
                        <div class="wishlist-count">12</div>
                    </div>
                    <div class="header-action cart-icon" onclick="showPage('cart')">
                        <i class="fas fa-shopping-cart"></i>
                        <span>Cart</span>
                        <div class="cart-count">8</div>
                    </div>
                </div>
                
                <div class="hamburger" id="hamburger">
                    <i class="fas fa-bars"></i>
                </div>
            </div>
            
            <div class="header-bottom">
                <ul class="nav-links">
                    <li><a href="#" onclick="showPage('home')" class="active"><i class="fas fa-home"></i> Home</a></li>
                    <li><a href="#" onclick="showPage('categories')"><i class="fas fa-list"></i> Categories</a></li>
                    <li><a href="#" onclick="showPage('deals')"><i class="fas fa-tag"></i> Today's Deals</a></li>
                    <li><a href="#" onclick="showPage('prime')"><i class="fas fa-crown"></i> TRUSTYMART Prime</a></li>
                    <li><a href="#" onclick="showPage('support')"><i class="fas fa-headset"></i> Customer Service</a></li>
                    <li><a href="#" onclick="showPage('location')"><i class="fas fa-map-marker-alt"></i> Location</a></li>
                </ul>
            </div>
        </div>
    </header>

    <!-- Mobile Menu -->
    <div class="mobile-menu" id="mobile-menu">
        <div class="mobile-menu-header">
            <div class="mobile-menu-logo">
                <i class="fas fa-shopping-bag logo-icon"></i>
                <span class="logo-text">TRUSTYMART</span>
            </div>
            <button class="close-menu" id="close-menu">
                <i class="fas fa-times"></i>
            </button>
        </div>
        
        <ul class="mobile-nav-links">
            <li><a href="#" onclick="showPage('home'); closeMobileMenu();"><i class="fas fa-home"></i> Home</a></li>
            <li><a href="#" onclick="showPage('categories'); closeMobileMenu();"><i class="fas fa-list"></i> Categories</a></li>
            <li><a href="#" onclick="showPage('deals'); closeMobileMenu();"><i class="fas fa-tag"></i> Today's Deals</a></li>
            <li><a href="#" onclick="showPage('prime'); closeMobileMenu();"><i class="fas fa-crown"></i> TRUSTYMART Prime</a></li>
            <li><a href="#" onclick="showPage('support'); closeMobileMenu();"><i class="fas fa-headset"></i> Customer Service</a></li>
            <li><a href="#" onclick="showPage('location'); closeMobileMenu();"><i class="fas fa-map-marker-alt"></i> Location</a></li>
            <li><a href="#" onclick="showPage('profile'); closeMobileMenu();"><i class="fas fa-user"></i> Account</a></li>
            <li><a href="#" onclick="showPage('orders'); closeMobileMenu();"><i class="fas fa-box"></i> Orders</a></li>
            <li><a href="#" onclick="showPage('notifications'); closeMobileMenu();"><i class="fas fa-bell"></i> Notifications</a></li>
            <li><a href="#" onclick="showPage('wishlist'); closeMobileMenu();"><i class="fas fa-heart"></i> Wishlist</a></li>
            <li><a href="#" onclick="showPage('cart'); closeMobileMenu();"><i class="fas fa-shopping-cart"></i> Cart</a></li>
        </ul>
    </div>

    <!-- AI Assistant -->
    <div class="ai-assistant" id="ai-assistant">
        <i class="fas fa-robot"></i>
    </div>

    <div class="ai-chat" id="ai-chat">
        <div class="ai-header">
            <h3>TRUSTYMART AI Assistant</h3>
            <button class="ai-close" id="ai-close">
                <i class="fas fa-times"></i>
            </button>
        </div>
        <div class="ai-messages" id="ai-messages">
            <div class="ai-message bot">
                Hello! I'm your TRUSTYMART AI assistant. How can I help you today?
            </div>
        </div>
        <div class="ai-input">
            <input type="text" id="ai-input" placeholder="Ask me anything...">
            <button id="ai-send"><i class="fas fa-paper-plane"></i></button>
        </div>
    </div>

    <!-- AR Preview -->
    <div class="ar-preview" id="ar-preview">
        <div class="ar-content">
            <div class="ar-header">
                <h3>AR Product Preview</h3>
                <button class="ar-close" id="ar-close">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <div class="ar-view">
                <p>AR Preview would appear here in a real implementation</p>
            </div>
        </div>
    </div>

    <!-- Login Modal -->
    <div class="modal" id="login-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Sign In</h2>
                <button class="close-modal" onclick="closeLoginModal()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <div class="form-group">
                <label for="login-email">Email or mobile phone number</label>
                <input type="text" id="login-email">
            </div>
            <div class="form-group">
                <label for="login-password">Password</label>
                <input type="password" id="login-password">
            </div>
            <button class="btn" style="width: 100%;" onclick="login()">Continue</button>
            <p style="margin-top: 15px; text-align: center; font-size: 0.9rem;">
                By continuing, you agree to TRUSTYMART's <a href="#" style="color: var(--prime);">Conditions of Use</a> and <a href="#" style="color: var(--prime);">Privacy Notice</a>.
            </p>
            <hr style="margin: 20px 0;">
            <p style="text-align: center; font-size: 0.9rem;">
                New to TRUSTYMART? <a href="#" style="color: var(--prime);" onclick="showRegisterModal()">Create your account</a>
            </p>
        </div>
    </div>

    <!-- Register Modal -->
    <div class="modal" id="register-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Create Account</h2>
                <button class="close-modal" onclick="closeRegisterModal()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <div class="form-group">
                <label for="register-name">Your name</label>
                <input type="text" id="register-name">
            </div>
            <div class="form-group">
                <label for="register-email">Email</label>
                <input type="email" id="register-email">
            </div>
            <div class="form-group">
                <label for="register-password">Password</label>
                <input type="password" id="register-password" placeholder="At least 6 characters">
            </div>
            <div class="form-group">
                <label for="register-password-again">Re-enter password</label>
                <input type="password" id="register-password-again">
            </div>
            <button class="btn" style="width: 100%;" onclick="register()">Create your TRUSTYMART account</button>
            <p style="margin-top: 15px; text-align: center; font-size: 0.9rem;">
                By creating an account, you agree to TRUSTYMART's <a href="#" style="color: var(--prime);">Conditions of Use</a> and <a href="#" style="color: var(--prime);">Privacy Notice</a>.
            </p>
            <hr style="margin: 20px 0;">
            <p style="text-align: center; font-size: 0.9rem;">
                Already have an account? <a href="#" style="color: var(--prime);" onclick="showLoginModal()">Sign in</a>
            </p>
        </div>
    </div>

    <!-- Main Content -->
    <main>
        <div class="container">
            <!-- Home Page -->
            <div id="home" class="page active">
                <div class="hero">
                    <h1>Welcome to TRUSTYMART</h1>
                    <p>India's fastest growing e-commerce platform with 1M+ products across 100+ categories</p>
                    <a href="#" class="btn" onclick="showPage('categories')">Shop Now</a>
                </div>

                <div class="offers-container">
                    <div class="offers-title">
                        <i class="fas fa-bolt"></i>
                        <h2>Today's Hot Deals</h2>
                    </div>
                    <div class="offers-scroll">
                        <!-- Offers will be dynamically added -->
                    </div>
                </div>

                <h2 class="page-title"><i class="fas fa-th-large"></i> Shop by Category</h2>
                <div class="categories">
                    <div class="category-card" onclick="showPage('electronics')">
                        <i class="fas fa-laptop"></i>
                        <h3>Electronics</h3>
                        <p>Mobiles, Laptops & more</p>
                    </div>
                    <div class="category-card" onclick="showPage('fashion')">
                        <i class="fas fa-tshirt"></i>
                        <h3>Fashion</h3>
                        <p>Clothing, Footwear & more</p>
                    </div>
                    <div class="category-card" onclick="showPage('home')">
                        <i class="fas fa-home"></i>
                        <h3>Home & Kitchen</h3>
                        <p>Appliances, Furniture & more</p>
                    </div>
                    <div class="category-card" onclick="showPage('beauty')">
                        <i class="fas fa-spa"></i>
                        <h3>Beauty</h3>
                        <p>Makeup, Skincare & more</p>
                    </div>
                    <div class="category-card" onclick="showPage('sports')">
                        <i class="fas fa-dumbbell"></i>
                        <h3>Sports</h3>
                        <p>Fitness, Outdoor & more</p>
                    </div>
                    <div class="category-card" onclick="showPage('books')">
                        <i class="fas fa-book"></i>
                        <h3>Books</h3>
                        <p>Fiction, Education & more</p>
                    </div>
                    <div class="category-card" onclick="showPage('toys')">
                        <i class="fas fa-gamepad"></i>
                        <h3>Toys & Games</h3>
                        <p>Kids toys, Board games</p>
                    </div>
                    <div class="category-card" onclick="showPage('automotive')">
                        <i class="fas fa-car"></i>
                        <h3>Automotive</h3>
                        <p>Car accessories, Parts</p>
                    </div>
                </div>

                <h2 class="page-title"><i class="fas fa-fire"></i> Featured Products</h2>
                <div class="products" id="featured-products">
                    <!-- Featured products will be dynamically added -->
                </div>
            </div>

            <!-- Product Detail Page -->
            <div id="product-detail" class="page">
                <!-- Product detail content will be dynamically loaded here -->
            </div>

            <!-- Categories Page -->
            <div id="categories" class="page">
                <h2 class="page-title"><i class="fas fa-list"></i> All Categories</h2>
                <p>Browse products by category</p>
                <div class="categories">
                    <div class="category-card" onclick="showPage('electronics')">
                        <i class="fas fa-laptop"></i>
                        <h3>Electronics</h3>
                        <p>Mobiles, Laptops & more</p>
                    </div>
                    <div class="category-card" onclick="showPage('fashion')">
                        <i class="fas fa-tshirt"></i>
                        <h3>Fashion</h3>
                        <p>Clothing, Footwear & more</p>
                    </div>
                    <div class="category-card" onclick="showPage('home')">
                        <i class="fas fa-home"></i>
                        <h3>Home & Kitchen</h3>
                        <p>Appliances, Furniture & more</p>
                    </div>
                    <div class="category-card" onclick="showPage('beauty')">
                        <i class="fas fa-spa"></i>
                        <h3>Beauty</h3>
                        <p>Makeup, Skincare & more</p>
                    </div>
                    <div class="category-card" onclick="showPage('sports')">
                        <i class="fas fa-dumbbell"></i>
                        <h3>Sports</h3>
                        <p>Fitness, Outdoor & more</p>
                    </div>
                    <div class="category-card" onclick="showPage('books')">
                        <i class="fas fa-book"></i>
                        <h3>Books</h3>
                        <p>Fiction, Education & more</p>
                    </div>
                    <div class="category-card" onclick="showPage('toys')">
                        <i class="fas fa-gamepad"></i>
                        <h3>Toys & Games</h3>
                        <p>Kids toys, Board games</p>
                    </div>
                    <div class="category-card" onclick="showPage('automotive')">
                        <i class="fas fa-car"></i>
                        <h3>Automotive</h3>
                        <p>Car accessories, Parts</p>
                    </div>
                    <div class="category-card" onclick="showPage('grocery')">
                        <i class="fas fa-shopping-basket"></i>
                        <h3>Grocery</h3>
                        <p>Food, Beverages & more</p>
                    </div>
                    <div class="category-card" onclick="showPage('health')">
                        <i class="fas fa-heartbeat"></i>
                        <h3>Health & Personal Care</h3>
                        <p>Medicines, Supplements</p>
                    </div>
                </div>
            </div>

            <!-- Electronics Category -->
            <div id="electronics" class="page">
                <h2 class="page-title"><i class="fas fa-laptop"></i> Electronics</h2>
                <p>Latest gadgets and electronic devices</p>
                
                <div class="filter-section">
                    <div class="filter-title">
                        <i class="fas fa-filter"></i> Filter by:
                    </div>
                    <div class="filter-options">
                        <div class="filter-option active" data-filter="all">All</div>
                        <div class="filter-option" data-filter="mobile">Mobile Phones</div>
                        <div class="filter-option" data-filter="laptop">Laptops</div>
                        <div class="filter-option" data-filter="audio">Audio</div>
                        <div class="filter-option" data-filter="camera">Cameras</div>
                    </div>
                </div>
                
                <div class="products" id="electronics-products">
                    <!-- Electronics products will be dynamically added -->
                </div>
            </div>

            <!-- Fashion Category -->
            <div id="fashion" class="page">
                <h2 class="page-title"><i class="fas fa-tshirt"></i> Fashion</h2>
                <p>Trendy clothes, footwear and accessories</p>
                
                <div class="filter-section">
                    <div class="filter-title">
                        <i class="fas fa-filter"></i> Filter by:
                    </div>
                    <div class="filter-options">
                        <div class="filter-option active" data-filter="all">All</div>
                        <div class="filter-option" data-filter="men">Men</div>
                        <div class="filter-option" data-filter="women">Women</div>
                        <div class="filter-option" data-filter="kids">Kids</div>
                        <div class="filter-option" data-filter="footwear">Footwear</div>
                    </div>
                </div>
                
                <div class="products" id="fashion-products">
                    <!-- Fashion products will be dynamically added -->
                </div>
            </div>

            <!-- Home & Kitchen Category -->
            <div id="home" class="page">
                <h2 class="page-title"><i class="fas fa-home"></i> Home & Kitchen</h2>
                <p>Everything for your home and kitchen</p>
                
                <div class="filter-section">
                    <div class="filter-title">
                        <i class="fas fa-filter"></i> Filter by:
                    </div>
                    <div class="filter-options">
                        <div class="filter-option active" data-filter="all">All</div>
                        <div class="filter-option" data-filter="furniture">Furniture</div>
                        <div class="filter-option" data-filter="kitchen">Kitchen</div>
                        <div class="filter-option" data-filter="decor">Home Decor</div>
                        <div class="filter-option" data-filter="appliances">Appliances</div>
                    </div>
                </div>
                
                <div class="products" id="home-products">
                    <!-- Home products will be dynamically added -->
                </div>
            </div>

            <!-- Beauty Category -->
            <div id="beauty" class="page">
                <h2 class="page-title"><i class="fas fa-spa"></i> Beauty</h2>
                <p>Cosmetics, skincare and personal care</p>
                
                <div class="filter-section">
                    <div class="filter-title">
                        <i class="fas fa-filter"></i> Filter by:
                    </div>
                    <div class="filter-options">
                        <div class="filter-option active" data-filter="all">All</div>
                        <div class="filter-option" data-filter="skincare">Skincare</div>
                        <div class="filter-option" data-filter="makeup">Makeup</div>
                        <div class="filter-option" data-filter="haircare">Haircare</div>
                        <div class="filter-option" data-filter="fragrance">Fragrance</div>
                    </div>
                </div>
                
                <div class="products" id="beauty-products">
                    <!-- Beauty products will be dynamically added -->
                </div>
            </div>

            <!-- Sports Category -->
            <div id="sports" class="page">
                <h2 class="page-title"><i class="fas fa-dumbbell"></i> Sports</h2>
                <p>Fitness equipment and outdoor gear</p>
                <div class="products" id="sports-products">
                    <!-- Sports products will be dynamically added -->
                </div>
            </div>

            <!-- Books Category -->
            <div id="books" class="page">
                <h2 class="page-title"><i class="fas fa-book"></i> Books</h2>
                <p>Best sellers and educational books</p>
                <div class="products" id="books-products">
                    <!-- Books products will be dynamically added -->
                </div>
            </div>

            <!-- Today's Deals Page -->
            <div id="deals" class="page">
                <h2 class="page-title"><i class="fas fa-tag"></i> Today's Deals</h2>
                <p>Special offers and discounts</p>
                <div class="products" id="deals-products">
                    <!-- Deals products will be dynamically added -->
                </div>
            </div>

            <!-- TRUSTYMART Prime Page -->
            <div id="prime" class="page">
                <h2 class="page-title"><i class="fas fa-crown"></i> TRUSTYMART Prime</h2>
                <div class="hero" style="background: linear-gradient(to right, #00a8e1, #007eb9);">
                    <h1>Experience TRUSTYMART Prime</h1>
                    <p>Free delivery, exclusive deals, and premium content with your Prime membership</p>
                    <a href="#" class="btn" style="background: white; color: #00a8e1;">Try Prime for FREE</a>
                </div>
                
                <div class="card">
                    <h3>Prime Benefits</h3>
                    <div style="display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 20px; margin-top: 20px;">
                        <div style="text-align: center;">
                            <i class="fas fa-shipping-fast" style="font-size: 2.5rem; color: var(--prime);"></i>
                            <h4>FREE One-Day Delivery</h4>
                            <p>On millions of items</p>
                        </div>
                        <div style="text-align: center;">
                            <i class="fas fa-video" style="font-size: 2.5rem; color: var(--prime);"></i>
                            <h4>Prime Video</h4>
                            <p>Stream thousands of movies and TV shows</p>
                        </div>
                        <div style="text-align: center;">
                            <i class="fas fa-music" style="font-size: 2.5rem; color: var(--prime);"></i>
                            <h4>Prime Music</h4>
                            <p>Over 2 million songs ad-free</p>
                        </div>
                        <div style="text-align: center;">
                            <i class="fas fa-book" style="font-size: 2.5rem; color: var(--prime);"></i>
                            <h4>Prime Reading</h4>
                            <p>Thousands of books to borrow</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Cart Page -->
            <div id="cart" class="page">
                <h2 class="page-title"><i class="fas fa-shopping-cart"></i> Shopping Cart</h2>
                
                <div class="cart-items" id="cart-items">
                    <!-- Cart items will be dynamically added -->
                </div>
                
                <div class="cart-summary">
                    <h3>Order Summary</h3>
                    <div class="summary-item">
                        <span>Subtotal (<span id="cart-count">0</span> items):</span>
                        <span>₹<span id="cart-subtotal">0</span></span>
                    </div>
                    <div class="summary-item">
                        <span>Shipping:</span>
                        <span id="shipping-cost">₹0</span>
                    </div>
                    <div class="summary-item">
                        <span>Tax:</span>
                        <span>₹<span id="cart-tax">0</span></span>
                    </div>
                    <div class="summary-item summary-total">
                        <span>Total:</span>
                        <span>₹<span id="cart-total">0</span></span>
                    </div>
                    <button class="btn" style="width: 100%; margin-top: 15px;">Proceed to Checkout</button>
                </div>
            </div>

            <!-- Orders Page -->
            <div id="orders" class="page">
                <h2 class="page-title"><i class="fas fa-box"></i> My Orders</h2>
                
                <div class="orders-list" id="orders-list">
                    <!-- Orders will be dynamically added -->
                </div>
            </div>

            <!-- Wishlist Page -->
            <div id="wishlist" class="page">
                <h2 class="page-title"><i class="fas fa-heart"></i> My Wishlist</h2>
                <p>Your saved items</p>
                <div class="products" id="wishlist-products">
                    <!-- Wishlist items will be dynamically added -->
                </div>
            </div>

            <!-- Notifications Page -->
            <div id="notifications" class="page">
                <h2 class="page-title"><i class="fas fa-bell"></i> Notifications</h2>
                <div class="card">
                    <h3>Order Updates</h3>
                    <div class="order-item">
                        <div style="flex: 1;">
                            <h4>Your order #TRM-2023-001 has been shipped</h4>
                            <p>Your iPhone 14 Pro Max is on its way and will be delivered by tomorrow.</p>
                            <span style="font-size: 0.8rem; color: #666;">2 hours ago</span>
                        </div>
                        <button class="btn" style="padding: 5px 10px; font-size: 0.8rem;">Track Order</button>
                    </div>
                </div>
                <div class="card">
                    <h3>Deals & Offers</h3>
                    <div class="order-item">
                        <div style="flex: 1;">
                            <h4>Special offer on electronics</h4>
                            <p>Get up to 40% off on smartphones and laptops. Limited time offer!</p>
                            <span style="font-size: 0.8rem; color: #666;">1 day ago</span>
                        </div>
                        <button class="btn" style="padding: 5px 10px; font-size: 0.8rem;">Shop Now</button>
                    </div>
                </div>
            </div>

            <!-- Support Page -->
            <div id="support" class="page">
                <h2 class="page-title"><i class="fas fa-headset"></i> Customer Support</h2>
                <p>Get help with your orders and account</p>
                <div class="card">
                    <h3>Contact Us</h3>
                    <p>Email: support@trustymart.com</p>
                    <p>Phone: 1-800-123-4567</p>
                    <p>Live Chat: Available 24/7</p>
                </div>
                <div class="card">
                    <h3>FAQs</h3>
                    <div class="faq-item">
                        <h4>How can I track my order?</h4>
                        <p>You can track your order from the "My Orders" section in your account.</p>
                    </div>
                    <div class="faq-item">
                        <h4>What is your return policy?</h4>
                        <p>We offer 30-day return policy for most items. Some restrictions apply.</p>
                    </div>
                </div>
            </div>

            <!-- Profile Page -->
            <div id="profile" class="page">
                <h2 class="page-title"><i class="fas fa-user"></i> My Profile</h2>
                <p>Manage your account settings</p>
                <div class="card">
                    <h3>Personal Information</h3>
                    <div class="form-group">
                        <label for="name">Full Name</label>
                        <input type="text" id="name" value="Rajesh Kumar">
                    </div>
                    <div class="form-group">
                        <label for="email">Email Address</label>
                        <input type="email" id="email" value="rajesh.kumar@example.com">
                    </div>
                    <div class="form-group">
                        <label for="phone">Phone Number</label>
                        <input type="tel" id="phone" value="+91 98765 43210">
                    </div>
                    <button class="btn">Save Changes</button>
                </div>
            </div>

            <!-- Location Page -->
            <div id="location" class="page">
                <h2 class="page-title"><i class="fas fa-map-marker-alt"></i> Store Locations</h2>
                <p>Find TRUSTYMART stores near you</p>
                <div class="card">
                    <h3>Dindigul, Tamil Nadu</h3>
                    <p>123 Main Street, Dindigul</p>
                    <p>Phone: +91 98765 43210</p>
                    <p>Hours: 9:00 AM - 9:00 PM</p>
                </div>
                <div class="card">
                    <h3>Chennai, Tamil Nadu</h3>
                    <p>456 Anna Salai, Chennai</p>
                    <p>Phone: +91 98765 43211</p>
                    <p>Hours: 10:00 AM - 10:00 PM</p>
                </div>
            </div>

            <!-- Other category pages would follow similar structure -->
        </div>
    </main>

    <!-- Toast Notification -->
    <div class="toast" id="toast"></div>

    <!-- Footer Section -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Shop</h3>
                    <ul class="footer-links">
                        <li><a href="#" onclick="showPage('categories')">All Categories</a></li>
                        <li><a href="#" onclick="showPage('deals')">Today's Deals</a></li>
                        <li><a href="#">New Arrivals</a></li>
                        <li><a href="#">Best Sellers</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Help & Settings</h3>
                    <ul class="footer-links">
                        <li><a href="#" onclick="showPage('support')">Customer Service</a></li>
                        <li><a href="#" onclick="showPage('orders')">Track Orders</a></li>
                        <li><a href="#">Returns & Refunds</a></li>
                        <li><a href="#">Shipping Information</a></li>
                        <li><a href="#">Help Center</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>About TRUSTYMART</h3>
                    <ul class="footer-links">
                        <li><a href="#">About Us</a></li>
                        <li><a href="#">Careers</a></li>
                        <li><a href="#">Press</a></li>
                        <li><a href="#">Corporate Information</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Connect With Us</h3>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                    <p style="margin-top: 15px; font-size: 0.9rem;">Download our app:</p>
                    <div style="display: flex; gap: 10px; margin-top: 10px;">
                        <button class="btn" style="padding: 8px 15px; font-size: 0.8rem;">
                            <i class="fab fa-apple"></i> App Store
                        </button>
                        <button class="btn" style="padding: 8px 15px; font-size: 0.8rem;">
                            <i class="fab fa-google-play"></i> Google Play
                        </button>
                    </div>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 TRUSTYMART. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Enhanced Product Database with more fields and innovative features
        const products = {
            // Electronics
            'p1': {
                id: 'p1',
                title: 'iPhone 14 Pro Max 256GB',
                price: '1,39,999',
                oldPrice: '1,49,999',
                rating: 4.8,
                category: 'electronics',
                subcategory: 'mobile',
                image: 'https://images.unsplash.com/photo-1592750475338-74b7b21085ab?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80',
                description: 'The iPhone 14 Pro Max features a 6.7-inch Super Retina XDR display, A16 Bionic chip, and advanced camera system with 48MP Main camera.',
                specifications: {
                    'Display': '6.7-inch Super Retina XDR',
                    'Chip': 'A16 Bionic',
                    'Storage': '256GB',
                    'Camera': '48MP Main, 12MP Ultra Wide, 12MP Telephoto',
                    'Battery': 'Up to 29 hours video playback'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 3, // 1-5 scale
                arEnabled: true,
                reviews: [
                    { user: 'Rajesh K.', rating: 5, comment: 'Amazing phone with great camera quality!' },
                    { user: 'Priya S.', rating: 4, comment: 'Good battery life and performance.' }
                ]
            },
            'p2': {
                id: 'p2',
                title: 'Samsung Galaxy S23 Ultra',
                price: '1,24,999',
                oldPrice: '1,34,999',
                rating: 4.7,
                category: 'electronics',
                subcategory: 'mobile',
                image: 'https://images.unsplash.com/photo-1610945265064-0e34e5519bbf?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                description: 'Samsung Galaxy S23 Ultra with S Pen, 200MP camera, and Snapdragon 8 Gen 2 processor.',
                specifications: {
                    'Display': '6.8-inch Dynamic AMOLED 2X',
                    'Processor': 'Snapdragon 8 Gen 2',
                    'RAM': '12GB',
                    'Storage': '512GB',
                    'Camera': '200MP Main, 12MP Ultra Wide, 10MP Telephoto',
                    'Battery': '5000mAh'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 4,
                arEnabled: true,
                reviews: [
                    { user: 'Vikram R.', rating: 5, comment: 'Excellent display and camera performance!' }
                ]
            },
            'p3': {
                id: 'p3',
                title: 'MacBook Pro 16-inch M2 Max',
                price: '2,49,999',
                oldPrice: '2,69,999',
                rating: 4.9,
                category: 'electronics',
                subcategory: 'laptop',
                image: 'https://images.unsplash.com/photo-1517336714731-489689fd1ca8?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2072&q=80',
                description: 'MacBook Pro with M2 Max chip, 16-inch Liquid Retina XDR display, and up to 22 hours of battery life.',
                specifications: {
                    'Display': '16.2-inch Liquid Retina XDR',
                    'Chip': 'Apple M2 Max',
                    'Memory': '32GB',
                    'Storage': '1TB SSD',
                    'Battery': 'Up to 22 hours',
                    'Ports': 'MagSafe 3, HDMI, SDXC card slot'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 4,
                arEnabled: false,
                reviews: []
            },
            'p4': {
                id: 'p4',
                title: 'Sony WH-1000XM5 Headphones',
                price: '29,999',
                oldPrice: '34,999',
                rating: 4.6,
                category: 'electronics',
                subcategory: 'audio',
                image: 'https://images.unsplash.com/photo-1583394838336-acd977736f90?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2068&q=80',
                description: 'Industry-leading noise cancellation with 30-hour battery life and quick charging.',
                specifications: {
                    'Noise Cancellation': 'Industry-leading',
                    'Battery Life': 'Up to 30 hours',
                    'Charging': 'Quick Charge (10 min for 5 hours)',
                    'Connectivity': 'Bluetooth 5.2, NFC',
                    'Weight': '250g'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 3,
                arEnabled: false,
                reviews: [
                    { user: 'Anita M.', rating: 5, comment: 'Best noise cancellation I have ever experienced!' }
                ]
            },
            'p5': {
                id: 'p5',
                title: 'Apple Watch Series 8',
                price: '45,999',
                oldPrice: '52,999',
                rating: 4.5,
                category: 'electronics',
                subcategory: 'wearable',
                image: 'https://images.unsplash.com/photo-1579586337278-3f436c25d4a1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                description: 'Apple Watch Series 8 with advanced health features and always-on display.',
                specifications: {
                    'Display': 'Always-On Retina LTPO OLED',
                    'Processor': 'Apple S8 SiP',
                    'Health Monitoring': 'ECG, Blood Oxygen, Temperature Sensing',
                    'Connectivity': 'GPS + Cellular, Wi-Fi, Bluetooth',
                    'Water Resistance': '50 meters'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 3,
                arEnabled: false,
                reviews: []
            },
            'p6': {
                id: 'p6',
                title: 'Canon EOS R5 Camera',
                price: '3,49,999',
                oldPrice: '3,99,999',
                rating: 4.8,
                category: 'electronics',
                subcategory: 'camera',
                image: 'https://images.unsplash.com/photo-1502920917128-1aa500764cbd?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                description: 'Professional full-frame mirrorless camera with 45MP sensor and 8K video recording.',
                specifications: {
                    'Sensor': '45MP Full-Frame CMOS',
                    'Processor': 'DIGIC X',
                    'Video': '8K 30p, 4K 120p',
                    'Autofocus': 'Dual Pixel CMOS AF II',
                    'Stabilization': '5-axis In-body Image Stabilization'
                },
                primeEligible: false,
                inStock: true,
                deliveryDate: '2-3 days',
                sustainability: 2,
                arEnabled: false,
                reviews: []
            },
            'p7': {
                id: 'p7',
                title: 'Samsung 55" QLED 4K TV',
                price: '89,999',
                oldPrice: '1,09,999',
                rating: 4.4,
                category: 'electronics',
                subcategory: 'tv',
                image: 'https://images.unsplash.com/photo-1593359677879-a4bb92f829d1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                description: 'Samsung 55-inch QLED 4K Smart TV with Quantum HDR and Alexa built-in.',
                specifications: {
                    'Display': '55-inch QLED 4K',
                    'HDR': 'Quantum HDR',
                    'Smart Features': 'Tizen OS, Alexa Built-in',
                    'Audio': 'Dolby Atmos',
                    'Connectivity': '4x HDMI, 3x USB, Wi-Fi'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 3,
                arEnabled: true,
                reviews: []
            },
            'p8': {
                id: 'p8',
                title: 'PlayStation 5 Console',
                price: '54,999',
                oldPrice: '59,999',
                rating: 4.7,
                category: 'electronics',
                subcategory: 'gaming',
                image: 'https://images.unsplash.com/photo-1606813907291-d86efa9b94db?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2015&q=80',
                description: 'PlayStation 5 console with Ultra HD Blu-ray and 825GB SSD storage.',
                specifications: {
                    'CPU': 'AMD Ryzen Zen 2',
                    'GPU': 'AMD Radeon RDNA 2',
                    'Memory': '16GB GDDR6',
                    'Storage': '825GB SSD',
                    'Resolution': 'Up to 8K',
                    'Features': '4K Blu-ray, 3D Audio'
                },
                primeEligible: true,
                inStock: false,
                deliveryDate: 'Out of stock',
                sustainability: 2,
                arEnabled: false,
                reviews: []
            },
            // Fashion products
            'p9': {
                id: 'p9',
                title: 'Men\'s Cotton T-Shirt (Pack of 3)',
                price: '899',
                oldPrice: '1,299',
                rating: 4.2,
                category: 'fashion',
                subcategory: 'men',
                image: 'https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2080&q=80',
                description: 'Premium cotton t-shirts in assorted colors. Perfect for everyday wear.',
                specifications: {
                    'Material': '100% Cotton',
                    'Fit': 'Regular',
                    'Sleeve': 'Short Sleeve',
                    'Care': 'Machine Wash',
                    'Pack': '3 T-shirts'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 5,
                arEnabled: false,
                reviews: []
            },
            'p10': {
                id: 'p10',
                title: 'Women\'s Ethnic Kurti',
                price: '1,299',
                oldPrice: '1,799',
                rating: 4.3,
                category: 'fashion',
                subcategory: 'women',
                image: 'https://images.unsplash.com/photo-1595777457583-95e059d581b8?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80',
                description: 'Beautiful printed kurti with intricate embroidery work.',
                specifications: {
                    'Material': 'Cotton Blend',
                    'Length': 'Knee Length',
                    'Sleeve': 'Three-Quarter',
                    'Care': 'Dry Clean Only',
                    'Occasion': 'Casual, Festive'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 4,
                arEnabled: false,
                reviews: []
            },
            'p11': {
                id: 'p11',
                title: 'Nike Air Max 270 Shoes',
                price: '12,999',
                oldPrice: '15,999',
                rating: 4.5,
                category: 'fashion',
                subcategory: 'footwear',
                image: 'https://images.unsplash.com/photo-1542291026-7eec264c27ff?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                description: 'Nike Air Max 270 with the tallest Air unit yet for all-day comfort.',
                specifications: {
                    'Upper Material': 'Breathable Mesh',
                    'Sole': 'Rubber with Max Air Cushioning',
                    'Closure': 'Lace-up',
                    'Weight': 'Approx. 320g (per shoe)',
                    'Recommended Use': 'Running, Casual Wear'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 3,
                arEnabled: true,
                reviews: []
            },
            'p12': {
                id: 'p12',
                title: 'Leather Handbag for Women',
                price: '3,499',
                oldPrice: '4,999',
                rating: 4.4,
                category: 'fashion',
                subcategory: 'women',
                image: 'https://images.unsplash.com/photo-1584917865442-de89df76afd3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                description: 'Genuine leather handbag with multiple compartments and adjustable strap.',
                specifications: {
                    'Material': 'Genuine Leather',
                    'Compartments': 'Main compartment, 2 inner pockets',
                    'Strap': 'Adjustable, Detachable',
                    'Closure': 'Zipper',
                    'Dimensions': '30x20x10 cm'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 2,
                arEnabled: false,
                reviews: []
            },
            // Home & Kitchen products
            'p13': {
                id: 'p13',
                title: 'Non-Stick Cookware Set (10 Pcs)',
                price: '4,999',
                oldPrice: '6,999',
                rating: 4.3,
                category: 'home',
                subcategory: 'kitchen',
                image: 'https://images.unsplash.com/photo-1586023492125-27b2c045efd7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2058&q=80',
                description: 'Complete non-stick cookware set with induction base.',
                specifications: {
                    'Material': 'Hard Anodized Aluminum',
                    'Pieces': '10 Pieces',
                    'Coating': '3-layer Non-Stick',
                    'Compatibility': 'Gas, Electric, Induction',
                    'Warranty': '10 Years'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 4,
                arEnabled: true,
                reviews: []
            },
            'p14': {
                id: 'p14',
                title: 'Queen Size Bed with Storage',
                price: '24,999',
                oldPrice: '29,999',
                rating: 4.6,
                category: 'home',
                subcategory: 'furniture',
                image: 'https://images.unsplash.com/photo-1505693416388-ac5ce068fe85?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                description: 'Queen size bed with hydraulic storage and headboard.',
                specifications: {
                    'Size': 'Queen (60x78 inches)',
                    'Material': 'Engineered Wood',
                    'Storage': 'Hydraulic Lift Mechanism',
                    'Assembly': 'Required',
                    'Weight Capacity': '300 kg'
                },
                primeEligible: false,
                inStock: true,
                deliveryDate: '3-4 days',
                sustainability: 4,
                arEnabled: true,
                reviews: []
            },
            'p15': {
                id: 'p15',
                title: 'Sofa Set (3+1+1)',
                price: '34,999',
                oldPrice: '42,999',
                rating: 4.5,
                category: 'home',
                subcategory: 'furniture',
                image: 'https://images.unsplash.com/photo-1555041469-a586c61ea9bc?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                description: 'L-shaped sofa set with premium fabric and wooden legs.',
                specifications: {
                    'Configuration': '3 Seater + 1 Seater + 1 Seater',
                    'Material': 'Premium Fabric',
                    'Filling': 'High Density Foam',
                    'Legs': 'Solid Wood',
                    'Assembly': 'Professional Assembly Included'
                },
                primeEligible: false,
                inStock: true,
                deliveryDate: '5-7 days',
                sustainability: 4,
                arEnabled: true,
                reviews: []
            },
            // Beauty products
            'p16': {
                id: 'p16',
                title: 'Lakme Absolute Skin Gloss Gel Crème',
                price: '699',
                oldPrice: '899',
                rating: 4.2,
                category: 'beauty',
                subcategory: 'skincare',
                image: 'https://images.unsplash.com/photo-1596462502278-27bfdc403348?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2080&q=80',
                description: 'Skin gloss gel crème for a dewy, radiant finish.',
                specifications: {
                    'Type': 'Gel Crème',
                    'Skin Type': 'All Skin Types',
                    'SPF': 'SPF 20',
                    'Volume': '50g',
                    'Finish': 'Dewy, Radiant'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 3,
                arEnabled: false,
                reviews: []
            },
            'p17': {
                id: 'p17',
                title: 'Maybelline New York Lipstick',
                price: '499',
                oldPrice: '649',
                rating: 4.4,
                category: 'beauty',
                subcategory: 'makeup',
                image: 'https://images.unsplash.com/photo-1586495777744-4413f21062fa?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1915&q=80',
                description: 'Creamy matte lipstick with intense color payoff.',
                specifications: {
                    'Finish': 'Matte',
                    'Weight': '4.2g',
                    'Shades': '12 Available',
                    'Longevity': 'Up to 12 hours',
                    'Formula': 'Creamy, Non-Drying'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 2,
                arEnabled: false,
                reviews: []
            },
            // Sports products
            'p18': {
                id: 'p18',
                title: 'Yoga Mat Premium 8mm',
                price: '1,299',
                oldPrice: '1,799',
                rating: 4.3,
                category: 'sports',
                subcategory: 'fitness',
                image: 'https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                description: 'Premium TPE yoga mat with excellent grip and cushioning.',
                specifications: {
                    'Material': 'TPE (Thermoplastic Elastomer)',
                    'Thickness': '8mm',
                    'Size': '183x61 cm',
                    'Weight': '1.2 kg',
                    'Features': 'Non-Slip, Eco-Friendly'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 5,
                arEnabled: false,
                reviews: []
            },
            'p19': {
                id: 'p19',
                title: 'Dumbbell Set 20kg',
                price: '2,999',
                oldPrice: '3,999',
                rating: 4.5,
                category: 'sports',
                subcategory: 'fitness',
                image: 'https://images.unsplash.com/photo-1534258936925-c58bed479fcb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2031&q=80',
                description: 'Adjustable dumbbell set with multiple weight options.',
                specifications: {
                    'Weight Range': '5-20kg',
                    'Material': 'Cast Iron, Chrome',
                    'Grip': 'Textured for Secure Hold',
                    'Storage': 'Includes Stand',
                    'Adjustment': 'Quick Dial System'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 3,
                arEnabled: false,
                reviews: []
            },
            // Books
            'p20': {
                id: 'p20',
                title: 'The Psychology of Money',
                price: '399',
                oldPrice: '499',
                rating: 4.7,
                category: 'books',
                subcategory: 'non-fiction',
                image: 'https://images.unsplash.com/photo-1544716278-ca5e3f4abd8c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80',
                description: 'Timeless lessons on wealth, greed, and happiness.',
                specifications: {
                    'Author': 'Morgan Housel',
                    'Pages': '256',
                    'Publisher': 'Harriman House',
                    'Language': 'English',
                    'Genre': 'Personal Finance'
                },
                primeEligible: true,
                inStock: true,
                deliveryDate: 'Tomorrow',
                sustainability: 5,
                arEnabled: false,
                reviews: []
            },
            // Add more products as needed...
        };

        // Shopping cart
        let cart = {};
        let wishlist = {};
        let orders = {};
        let user = null;

        // AI Assistant responses
        const aiResponses = {
            greetings: [
                "Hello! How can I assist you with your shopping today?",
                "Hi there! I'm your TRUSTYMART assistant. What can I help you find?",
                "Welcome to TRUSTYMART! How can I make your shopping experience better?"
            ],
            help: [
                "I can help you find products, track orders, or answer questions about TRUSTYMART services.",
                "You can ask me about product availability, deals, shipping information, or account issues.",
                "I'm here to help with any shopping-related questions you might have."
            ],
            products: [
                "We have a wide range of products across categories like electronics, fashion, home, and more.",
                "You can browse our categories to find exactly what you're looking for.",
                "Check out our Today's Deals section for special offers and discounts."
            ],
            orders: [
                "You can track your orders in the 'My Orders' section of your account.",
                "For order-related issues, please visit the Orders page or contact customer support.",
                "Most orders are delivered within 2-5 business days, with Prime members getting faster delivery."
            ],
            returns: [
                "We offer a 30-day return policy for most items. Some restrictions may apply.",
                "You can initiate returns from the 'My Orders' section of your account.",
                "For return-related queries, please visit our Returns & Refunds policy page."
            ],
            default: [
                "I'm not sure I understand. Can you please rephrase your question?",
                "I'm still learning! Could you try asking that differently?",
                "I don't have an answer for that yet. Please contact our customer support for assistance."
            ]
        };

        // Function to show a specific page and hide others
        function showPage(pageId) {
            // Hide all pages
            const pages = document.querySelectorAll('.page');
            pages.forEach(page => {
                page.classList.remove('active');
            });
            
            // Update active nav link
            const navLinks = document.querySelectorAll('.nav-links a');
            navLinks.forEach(link => {
                link.classList.remove('active');
            });
            
            // Show the selected page
            const targetPage = document.getElementById(pageId);
            if (targetPage) {
                targetPage.classList.add('active');
                
                // Load page-specific content
                if (pageId === 'home') {
                    loadHomePage();
                } else if (pageId === 'cart') {
                    loadCartPage();
                } else if (pageId === 'wishlist') {
                    loadWishlistPage();
                } else if (pageId === 'orders') {
                    loadOrdersPage();
                } else if (pageId.endsWith('-products')) {
                    loadCategoryPage(pageId.replace('-products', ''));
                }
            } else {
                console.error(`Page with ID '${pageId}' not found`);
            }
            
            // Scroll to top
            window.scrollTo(0, 0);
            
            // Close mobile menu if open
            closeMobileMenu();
        }

        // Function to load home page content
        function loadHomePage() {
            loadFeaturedProducts();
            loadOffers();
        }

        // Function to load featured products
        function loadFeaturedProducts() {
            const featuredContainer = document.getElementById('featured-products');
            if (!featuredContainer) return;
            
            let featuredHTML = '';
            const featuredIds = ['p1', 'p2', 'p3', 'p4', 'p9', 'p11', 'p13', 'p15'];
            
            featuredIds.forEach(productId => {
                const product = products[productId];
                if (product) {
                    featuredHTML += createProductCard(product);
                }
            });
            
            featuredContainer.innerHTML = featuredHTML;
        }

        // Function to load offers
        function loadOffers() {
            const offersContainer = document.querySelector('.offers-scroll');
            if (!offersContainer) return;
            
            let offersHTML = '';
            const offerIds = ['p1', 'p4', 'p9', 'p11', 'p13', 'p16'];
            
            offerIds.forEach(productId => {
                const product = products[productId];
                if (product) {
                    offersHTML += `
                        <div class="offer-item" onclick="showProductDetail('${product.id}')">
                            <img src="${product.image}" alt="${product.title}">
                            <h3>${product.title}</h3>
                            <div class="offer-price">₹${product.price}</div>
                            <div class="offer-old-price">₹${product.oldPrice}</div>
                        </div>
                    `;
                }
            });
            
            offersContainer.innerHTML = offersHTML;
        }

        // Function to create product card HTML
        function createProductCard(product) {
            let stars = '';
            for (let i = 1; i <= 5; i++) {
                if (i <= Math.floor(product.rating)) {
                    stars += '<i class="fas fa-star"></i>';
                } else if (i === Math.ceil(product.rating) && !Number.isInteger(product.rating)) {
                    stars += '<i class="fas fa-star-half-alt"></i>';
                } else {
                    stars += '<i class="far fa-star"></i>';
                }
            }
            
            const isInWishlist = wishlist[product.id] ? 'active' : '';
            const primeBadge = product.primeEligible ? '<span class="prime-badge">PRIME</span>' : '';
            const sustainabilityBadge = product.sustainability >= 4 ? '<span class="sustainability-badge">ECO</span>' : '';
            const stockStatus = product.inStock ? 
                `<p style="color: var(--success); font-size: 0.8rem; margin-bottom: 5px;">In stock</p>` : 
                `<p style="color: var(--danger); font-size: 0.8rem; margin-bottom: 5px;">Out of stock</p>`;
            const deliveryInfo = product.primeEligible && product.inStock ? 
                `<p style="color: var(--prime); font-size: 0.8rem; margin-bottom: 5px;">FREE delivery ${product.deliveryDate}</p>` : 
                `<p style="color: #666; font-size: 0.8rem; margin-bottom: 5px;">Delivery ${product.deliveryDate}</p>`;
            const arButton = product.arEnabled ? 
                `<button class="wishlist-btn" onclick="event.stopPropagation(); showARPreview('${product.id}')" style="margin-top: 5px;">
                    <i class="fas fa-cube"></i> AR View
                </button>` : '';
            
            return `
                <div class="product-card" onclick="showProductDetail('${product.id}')">
                    <div class="product-badge">${product.oldPrice ? 'Sale' : 'New'}</div>
                    <img src="${product.image}" alt="${product.title}" class="product-img">
                    <div class="product-info">
                        <div class="product-title">${product.title} ${primeBadge} ${sustainabilityBadge}</div>
                        <div class="product-rating">
                            ${stars}
                            <span>(${product.rating})</span>
                        </div>
                        ${stockStatus}
                        ${deliveryInfo}
                        <div class="product-specs">${product.description.substring(0, 100)}...</div>
                        <div class="product-price">₹${product.price} ${product.oldPrice ? `<span style="text-decoration: line-through; color: #777; font-size: 1rem;">₹${product.oldPrice}</span>` : ''}</div>
                        <div class="product-actions">
                            <button class="add-to-cart" onclick="event.stopPropagation(); addToCart('${product.id}')" ${!product.inStock ? 'disabled' : ''}>Add to Cart</button>
                            <button class="buy-now" onclick="event.stopPropagation(); buyNow('${product.id}')" ${!product.inStock ? 'disabled' : ''}>Buy Now</button>
                            <button class="wishlist-btn ${isInWishlist}" onclick="event.stopPropagation(); toggleWishlist('${product.id}')">
                                <i class="fas fa-heart"></i>
                            </button>
                        </div>
                        ${arButton}
                    </div>
                </div>
            `;
        }

        // Function to load category page
        function loadCategoryPage(category) {
            const categoryContainer = document.getElementById(`${category}-products`);
            if (!categoryContainer) return;
            
            let categoryHTML = '';
            
            Object.values(products).forEach(product => {
                if (product.category === category) {
                    categoryHTML += createProductCard(product);
                }
            });
            
            categoryContainer.innerHTML = categoryHTML;
            
            // Add filter functionality
            setupFilters(category);
        }

        // Function to setup filters
        function setupFilters(category) {
            const filterOptions = document.querySelectorAll('.filter-option');
            filterOptions.forEach(option => {
                option.addEventListener('click', function() {
                    // Remove active class from all options
                    filterOptions.forEach(opt => opt.classList.remove('active'));
                    // Add active class to clicked option
                    this.classList.add('active');
                    
                    const filter = this.getAttribute('data-filter');
                    filterProducts(category, filter);
                });
            });
        }

        // Function to filter products
        function filterProducts(category, filter) {
            const categoryContainer = document.getElementById(`${category}-products`);
            if (!categoryContainer) return;
            
            let filteredHTML = '';
            
            Object.values(products).forEach(product => {
                if (product.category === category && (filter === 'all' || product.subcategory === filter)) {
                    filteredHTML += createProductCard(product);
                }
            });
            
            categoryContainer.innerHTML = filteredHTML;
        }

        // Function to show product detail
        function showProductDetail(productId) {
            const product = products[productId];
            if (!product) {
                console.error(`Product with ID '${productId}' not found`);
                return;
            }
            
            const productDetailPage = document.getElementById('product-detail');
            let stars = '';
            for (let i = 1; i <= 5; i++) {
                if (i <= Math.floor(product.rating)) {
                    stars += '<i class="fas fa-star"></i>';
                } else if (i === Math.ceil(product.rating) && !Number.isInteger(product.rating)) {
                    stars += '<i class="fas fa-star-half-alt"></i>';
                } else {
                    stars += '<i class="far fa-star"></i>';
                }
            }
            
            let specifications = '';
            for (const [key, value] of Object.entries(product.specifications)) {
                specifications += `
                    <tr>
                        <td>${key}</td>
                        <td>${value}</td>
                    </tr>
                `;
            }
            
            const isInWishlist = wishlist[product.id] ? 'active' : '';
            const primeBadge = product.primeEligible ? '<span class="prime-badge">PRIME</span>' : '';
            const sustainabilityBadge = product.sustainability >= 4 ? '<span class="sustainability-badge">ECO-FRIENDLY</span>' : '';
            const stockStatus = product.inStock ? 
                `<p style="color: var(--success); font-size: 1rem; margin-bottom: 10px;"><i class="fas fa-check-circle"></i> In stock</p>` : 
                `<p style="color: var(--danger); font-size: 1rem; margin-bottom: 10px;"><i class="fas fa-times-circle"></i> Out of stock</p>`;
            const deliveryInfo = product.primeEligible && product.inStock ? 
                `<p style="color: var(--prime); font-size: 1rem; margin-bottom: 10px;"><i class="fas fa-shipping-fast"></i> FREE delivery ${product.deliveryDate}</p>` : 
                `<p style="color: #666; font-size: 1rem; margin-bottom: 10px;"><i class="fas fa-truck"></i> Delivery ${product.deliveryDate}</p>`;
            const arButton = product.arEnabled ? 
                `<button class="wishlist-btn" onclick="showARPreview('${product.id}')">
                    <i class="fas fa-cube"></i> View in AR
                </button>` : '';
            
            // Reviews section
            let reviewsHTML = '';
            if (product.reviews && product.reviews.length > 0) {
                reviewsHTML = '<h3 style="margin-top: 20px;">Customer Reviews</h3>';
                product.reviews.forEach(review => {
                    let reviewStars = '';
                    for (let i = 1; i <= 5; i++) {
                        if (i <= review.rating) {
                            reviewStars += '<i class="fas fa-star" style="color: var(--primary);"></i>';
                        } else {
                            reviewStars += '<i class="far fa-star" style="color: var(--primary);"></i>';
                        }
                    }
                    
                    reviewsHTML += `
                        <div style="border-bottom: 1px solid #eee; padding: 10px 0;">
                            <div style="display: flex; align-items: center; margin-bottom: 5px;">
                                ${reviewStars}
                                <span style="margin-left: 10px; font-weight: bold;">${review.user}</span>
                            </div>
                            <p>${review.comment}</p>
                        </div>
                    `;
                });
            }
            
            productDetailPage.innerHTML = `
                <div style="margin-bottom: 20px;">
                    <a href="#" onclick="showPage('home')" style="color: var(--primary);"><i class="fas fa-arrow-left"></i> Back to Home</a>
                </div>
                
                <div class="product-detail">
                    <div class="product-gallery">
                        <img src="${product.image}" class="product-main-image" id="main-image-${product.id}">
                    </div>
                    <div class="product-info-detail">
                        <h1 class="product-title-detail">${product.title} ${primeBadge} ${sustainabilityBadge}</h1>
                        <div class="product-rating-detail">
                            ${stars}
                            <span>${product.rating} | 1,234 ratings</span>
                        </div>
                        ${stockStatus}
                        ${deliveryInfo}
                        <div class="product-price-detail">₹${product.price} ${product.oldPrice ? `<span style="text-decoration: line-through; color: #777; font-size: 1rem;">₹${product.oldPrice}</span>` : ''}</div>
                        <div class="product-description">
                            ${product.description}
                        </div>
                        <div class="product-specifications">
                            <h3>Specifications</h3>
                            <table class="specs-table">
                                ${specifications}
                            </table>
                        </div>
                        <div class="product-actions-detail">
                            <button class="add-to-cart-detail" onclick="addToCart('${product.id}')" ${!product.inStock ? 'disabled' : ''}>Add to Cart</button>
                            <button class="buy-now-detail" onclick="buyNow('${product.id}')" ${!product.inStock ? 'disabled' : ''}>Buy Now</button>
                            <button class="wishlist-btn ${isInWishlist}" onclick="toggleWishlist('${product.id}')">
                                <i class="fas fa-heart"></i> ${isInWishlist ? 'Remove from Wishlist' : 'Add to Wishlist'}
                            </button>
                            ${arButton}
                        </div>
                    </div>
                </div>
                ${reviewsHTML}
            `;
            
            showPage('product-detail');
        }

        // Function to add product to cart
        function addToCart(productId) {
            const product = products[productId];
            if (!product) return;
            
            if (!product.inStock) {
                showToast('This product is currently out of stock');
                return;
            }
            
            if (cart[productId]) {
                cart[productId].quantity += 1;
            } else {
                cart[productId] = {
                    product: product,
                    quantity: 1
                };
            }
            
            updateCartCount();
            showToast(`${product.title} added to cart!`);
        }

        // Function to buy now
        function buyNow(productId) {
            const product = products[productId];
            if (!product.inStock) {
                showToast('This product is currently out of stock');
                return;
            }
            
            addToCart(productId);
            showPage('cart');
        }

        // Function to toggle wishlist
        function toggleWishlist(productId) {
            const product = products[productId];
            if (!product) return;
            
            if (wishlist[productId]) {
                delete wishlist[productId];
                showToast(`${product.title} removed from wishlist`);
            } else {
                wishlist[productId] = product;
                showToast(`${product.title} added to wishlist`);
            }
            
            updateWishlistCount();
            
            // Refresh the current page if it's the wishlist page
            if (document.getElementById('wishlist').classList.contains('active')) {
                loadWishlistPage();
            }
        }

        // Function to load cart page
        function loadCartPage() {
            const cartItemsContainer = document.getElementById('cart-items');
            if (!cartItemsContainer) return;
            
            if (Object.keys(cart).length === 0) {
                cartItemsContainer.innerHTML = '<p>Your cart is empty</p>';
                updateCartSummary(0, 0);
                return;
            }
            
            let cartHTML = '';
            let subtotal = 0;
            
            Object.values(cart).forEach(item => {
                const product = item.product;
                const itemTotal = parseInt(product.price.replace(/,/g, '')) * item.quantity;
                subtotal += itemTotal;
                
                cartHTML += `
                    <div class="cart-item">
                        <img src="${product.image}" alt="${product.title}" class="cart-item-img">
                        <div class="cart-item-details">
                            <div class="cart-item-title">${product.title}</div>
                            <div class="cart-item-price">₹${product.price}</div>
                            <div class="cart-item-actions">
                                <div class="quantity-selector">
                                    <button class="quantity-btn" onclick="updateCartQuantity('${product.id}', ${item.quantity - 1})">-</button>
                                    <input type="text" class="quantity-input" value="${item.quantity}" readonly>
                                    <button class="quantity-btn" onclick="updateCartQuantity('${product.id}', ${item.quantity + 1})">+</button>
                                </div>
                                <button class="remove-btn" onclick="removeFromCart('${product.id}')">Remove</button>
                            </div>
                        </div>
                    </div>
                `;
            });
            
            cartItemsContainer.innerHTML = cartHTML;
            updateCartSummary(subtotal, Math.round(subtotal * 0.18)); // 18% tax
        }

        // Function to update cart quantity
        function updateCartQuantity(productId, newQuantity) {
            if (newQuantity < 1) {
                removeFromCart(productId);
                return;
            }
            
            if (cart[productId]) {
                cart[productId].quantity = newQuantity;
                loadCartPage();
            }
        }

        // Function to remove from cart
        function removeFromCart(productId) {
            if (cart[productId]) {
                delete cart[productId];
                updateCartCount();
                loadCartPage();
                showToast('Item removed from cart');
            }
        }

        // Function to update cart summary
        function updateCartSummary(subtotal, tax) {
            const cartCount = Object.values(cart).reduce((total, item) => total + item.quantity, 0);
            const shipping = subtotal > 499 ? 0 : 40;
            
            document.getElementById('cart-count').textContent = cartCount;
            document.getElementById('cart-subtotal').textContent = subtotal.toLocaleString('en-IN');
            document.getElementById('cart-tax').textContent = tax.toLocaleString('en-IN');
            document.getElementById('shipping-cost').textContent = `₹${shipping}`;
            document.getElementById('cart-total').textContent = (subtotal + tax + shipping).toLocaleString('en-IN');
        }

        // Function to update cart count in header
        function updateCartCount() {
            const cartCount = Object.values(cart).reduce((total, item) => total + item.quantity, 0);
            document.querySelector('.cart-count').textContent = cartCount;
        }

        // Function to update wishlist count in header
        function updateWishlistCount() {
            const wishlistCount = Object.keys(wishlist).length;
            document.querySelector('.wishlist-count').textContent = wishlistCount;
        }

        // Function to load wishlist page
        function loadWishlistPage() {
            const wishlistContainer = document.getElementById('wishlist-products');
            if (!wishlistContainer) return;
            
            if (Object.keys(wishlist).length === 0) {
                wishlistContainer.innerHTML = '<p>Your wishlist is empty</p>';
                return;
            }
            
            let wishlistHTML = '';
            
            Object.values(wishlist).forEach(product => {
                wishlistHTML += createProductCard(product);
            });
            
            wishlistContainer.innerHTML = wishlistHTML;
        }

        // Function to load orders page
        function loadOrdersPage() {
            const ordersContainer = document.getElementById('orders-list');
            if (!ordersContainer) return;
            
            if (Object.keys(orders).length === 0) {
                ordersContainer.innerHTML = '<p>You have no orders yet</p>';
                return;
            }
            
            // In a real app, you would load actual orders
            ordersContainer.innerHTML = `
                <div class="order-card">
                    <div class="order-header">
                        <div>
                            <div class="order-id">Order #TRM-2023-001</div>
                            <div class="order-date">Placed on October 15, 2023</div>
                        </div>
                        <div class="order-status status-delivered">Delivered</div>
                    </div>
                    <div class="order-items">
                        <div class="order-item">
                            <img src="https://images.unsplash.com/photo-1496181133206-80ce9b88a853?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2071&q=80" alt="Laptop" class="order-item-img">
                            <div class="order-item-details">
                                <div class="order-item-title">Dell XPS 13 Laptop - 16GB RAM, 512GB SSD</div>
                                <div class="order-item-price">₹1,29,999</div>
                            </div>
                        </div>
                    </div>
                    <div class="order-actions">
                        <button class="btn">View Order Details</button>
                        <button class="btn" style="background: transparent; border: 1px solid #ddd;">Buy Again</button>
                    </div>
                </div>
            `;
        }

        // Function to show toast notification
        function showToast(message) {
            const toast = document.getElementById('toast');
            toast.textContent = message;
            toast.classList.add('show');
            
            setTimeout(() => {
                toast.classList.remove('show');
            }, 3000);
        }

        // AI Assistant functions
        function toggleAIChat() {
            const aiChat = document.getElementById('ai-chat');
            aiChat.classList.toggle('active');
        }

        function sendAIMessage() {
            const input = document.getElementById('ai-input');
            const messages = document.getElementById('ai-messages');
            const userMessage = input.value.trim();
            
            if (userMessage) {
                // Add user message
                messages.innerHTML += `<div class="ai-message user">${userMessage}</div>`;
                input.value = '';
                
                // Generate AI response
                setTimeout(() => {
                    const response = generateAIResponse(userMessage);
                    messages.innerHTML += `<div class="ai-message bot">${response}</div>`;
                    messages.scrollTop = messages.scrollHeight;
                }, 1000);
                
                messages.scrollTop = messages.scrollHeight;
            }
        }

        function generateAIResponse(message) {
            message = message.toLowerCase();
            
            if (message.includes('hello') || message.includes('hi') || message.includes('hey')) {
                return aiResponses.greetings[Math.floor(Math.random() * aiResponses.greetings.length)];
            } else if (message.includes('help') || message.includes('support')) {
                return aiResponses.help[Math.floor(Math.random() * aiResponses.help.length)];
            } else if (message.includes('product') || message.includes('item') || message.includes('buy')) {
                return aiResponses.products[Math.floor(Math.random() * aiResponses.products.length)];
            } else if (message.includes('order') || message.includes('track') || message.includes('delivery')) {
                return aiResponses.orders[Math.floor(Math.random() * aiResponses.orders.length)];
            } else if (message.includes('return') || message.includes('refund')) {
                return aiResponses.returns[Math.floor(Math.random() * aiResponses.returns.length)];
            } else {
                return aiResponses.default[Math.floor(Math.random() * aiResponses.default.length)];
            }
        }

        // AR Preview function
        function showARPreview(productId) {
            const product = products[productId];
            if (!product) return;
            
            document.getElementById('ar-preview').classList.add('active');
        }

        function closeARPreview() {
            document.getElementById('ar-preview').classList.remove('active');
        }

        // Login/Register Modal Functions
        function showLoginModal() {
            document.getElementById('login-modal').classList.add('active');
        }

        function closeLoginModal() {
            document.getElementById('login-modal').classList.remove('active');
        }

        function showRegisterModal() {
            closeLoginModal();
            document.getElementById('register-modal').classList.add('active');
        }

        function closeRegisterModal() {
            document.getElementById('register-modal').classList.remove('active');
        }

        function login() {
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;
            
            if (email && password) {
                // In a real app, you would validate credentials with a backend
                user = { name: 'Rajesh Kumar', email: email };
                showToast('Login successful!');
                closeLoginModal();
            } else {
                showToast('Please enter email and password');
            }
        }

        function register() {
            const name = document.getElementById('register-name').value;
            const email = document.getElementById('register-email').value;
            const password = document.getElementById('register-password').value;
            const passwordAgain = document.getElementById('register-password-again').value;
            
            if (name && email && password && passwordAgain) {
                if (password === passwordAgain) {
                    // In a real app, you would register the user with a backend
                    user = { name: name, email: email };
                    showToast('Registration successful!');
                    closeRegisterModal();
                } else {
                    showToast('Passwords do not match');
                }
            } else {
                showToast('Please fill all fields');
            }
        }

        // Mobile menu functions
        function openMobileMenu() {
            document.getElementById('mobile-menu').classList.add('active');
        }

        function closeMobileMenu() {
            document.getElementById('mobile-menu').classList.remove('active');
        }

        // Search function
        function searchProducts() {
            const query = document.getElementById('search-input').value.trim();
            const category = document.getElementById('search-category').value;
            
            if (query) {
                showToast(`Searching for "${query}" in ${category}`);
                // In a real app, you would implement actual search functionality
            }
        }

        // Initialize the app
        function initApp() {
            // Set home page as active by default
            showPage('home');
            
            // Add event listeners to navigation links
            document.querySelectorAll('.nav-links a').forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const pageId = this.getAttribute('onclick').match(/'([^']+)'/)[1];
                    showPage(pageId);
                    
                    // Update active nav link
                    document.querySelectorAll('.nav-links a').forEach(l => l.classList.remove('active'));
                    this.classList.add('active');
                });
            });
            
            // Add event listeners to header actions
            document.querySelectorAll('.header-action').forEach(action => {
                action.addEventListener('click', function() {
                    const pageId = this.getAttribute('onclick').match(/'([^']+)'/)[1];
                    if (pageId) {
                        showPage(pageId);
                    }
                });
            });
            
            // Add event listener to search button
            document.getElementById('search-btn').addEventListener('click', searchProducts);
            
            // Add event listener to search input for Enter key
            document.getElementById('search-input').addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    searchProducts();
                }
            });
            
            // Hamburger menu toggle
            document.getElementById('hamburger').addEventListener('click', openMobileMenu);
            document.getElementById('close-menu').addEventListener('click', closeMobileMenu);
            
            // Close mobile menu when clicking outside
            document.getElementById('mobile-menu').addEventListener('click', function(e) {
                if (e.target === this) {
                    closeMobileMenu();
                }
            });
            
            // Close modals when clicking outside
            document.querySelectorAll('.modal').forEach(modal => {
                modal.addEventListener('click', function(e) {
                    if (e.target === this) {
                        this.classList.remove('active');
                    }
                });
            });
            
            // AI Assistant event listeners
            document.getElementById('ai-assistant').addEventListener('click', toggleAIChat);
            document.getElementById('ai-close').addEventListener('click', toggleAIChat);
            document.getElementById('ai-send').addEventListener('click', sendAIMessage);
            document.getElementById('ai-input').addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    sendAIMessage();
                }
            });
            
            // AR Preview event listeners
            document.getElementById('ar-close').addEventListener('click', closeARPreview);
            
            // Initialize counts
            updateCartCount();
            updateWishlistCount();
            
            // Add some sample cart items
            addToCart('p1');
            addToCart('p4');
            addToCart('p9');
            addToCart('p11');
            
            // Add some sample wishlist items
            wishlist['p2'] = products['p2'];
            wishlist['p3'] = products['p3'];
            wishlist['p5'] = products['p5'];
            wishlist['p12'] = products['p12'];
            updateWishlistCount();
        }

        // Initialize the app when DOM is loaded
        document.addEventListener('DOMContentLoaded', initApp);
    </script>
</body>
</html>
