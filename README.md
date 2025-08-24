<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio</title>
    <style>
        /* Global Styles */
        :root {
            --primary-color: #3498db;
            --secondary-color: #2c3e50;
            --accent-color: #e74c3c;
            --light-color: #f9f9f9;
            --dark-color: #333;
            --gray-color: #666;
            --light-gray: #eee;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            line-height: 1.6;
            color: var(--dark-color);
            background-color: #fff;
        }
        
        a {
            text-decoration: none;
            color: inherit;
        }
        
        ul {
            list-style: none;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .btn {
            display: inline-block;
            background: var(--primary-color);
            color: #fff;
            padding: 10px 20px;
            border-radius: 5px;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .btn:hover {
            background: #2980b9;
            transform: translateY(-2px);
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid var(--primary-color);
            color: var(--primary-color);
        }
        
        .btn-outline:hover {
            background: var(--primary-color);
            color: #fff;
        }
        
        .section {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            font-size: 36px;
            color: var(--secondary-color);
            position: relative;
        }
        
        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: var(--primary-color);
            margin: 15px auto;
        }
        
        /* Header */
        header {
            background: #fff;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            z-index: 1000;
            transition: all 0.3s ease;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
            color: var(--secondary-color);
        }
        
        .nav-links {
            display: flex;
        }
        
        .nav-links li {
            margin-left: 30px;
        }
        
        .nav-links a {
            font-weight: 500;
            transition: color 0.3s;
        }
        
        .nav-links a:hover {
            color: var(--primary-color);
        }
        
        .hamburger {
            display: none;
            cursor: pointer;
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            background: var(--light-color);
            padding-top: 80px;
        }
        
        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 50px;
        }
        
        .hero-text {
            flex: 1;
        }
        
        .hero-text h1 {
            font-size: 48px;
            margin-bottom: 20px;
            color: var(--secondary-color);
        }
        
        .hero-text p {
            font-size: 18px;
            margin-bottom: 30px;
            color: var(--gray-color);
        }
        
        .hero-btns {
            display: flex;
            gap: 15px;
        }
        
        .hero-image {
            flex: 1;
            text-align: center;
            background: var(--primary-color);
            color: white;
            padding: 50px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        
        /* About Section */
        .about {
            background: #fff;
        }
        
        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }
        
        .about-text {
            flex: 1;
        }
        
        .about-text h3 {
            font-size: 24px;
            margin-bottom: 20px;
            color: var(--secondary-color);
        }
        
        .about-text p {
            margin-bottom: 15px;
            color: var(--gray-color);
        }
        
        .skills {
            flex: 1;
        }
        
        .skill-item {
            margin-bottom: 20px;
        }
        
        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }
        
        .skill-bar {
            height: 10px;
            background: var(--light-gray);
            border-radius: 5px;
            overflow: hidden;
        }
        
        .skill-progress {
            height: 100%;
            background: var(--primary-color);
            border-radius: 5px;
        }
        
        /* Todo App Section */
        .todo-app {
            background: var(--light-color);
        }
        
        .todo-container {
            max-width: 800px;
            margin: 0 auto;
            background: #fff;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .todo-header {
            text-align: center;
            margin-bottom: 30px;
        }
        
        .todo-header h3 {
            font-size: 24px;
            color: var(--secondary-color);
            margin-bottom: 10px;
        }
        
        .input-container {
            display: flex;
            margin-bottom: 20px;
        }
        
        #todo-input {
            flex: 1;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px 0 0 5px;
            font-size: 16px;
            outline: none;
        }
        
        #todo-input:focus {
            border-color: var(--primary-color);
        }
        
        #add-btn {
            padding: 12px 20px;
            background: var(--primary-color);
            color: white;
            border: none;
            border-radius: 0 5px 5px 0;
            cursor: pointer;
            font-size: 16px;
            transition: background 0.3s;
        }
        
        #add-btn:hover {
            background: #2980b9;
        }
        
        .filter-container {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }
        
        .filter-btn {
            padding: 8px 15px;
            background: var(--light-gray);
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .filter-btn.active {
            background: var(--primary-color);
            color: white;
        }
        
        .todo-list {
            margin-bottom: 20px;
            max-height: 400px;
            overflow-y: auto;
        }
        
        .todo-item {
            display: flex;
            align-items: center;
            padding: 12px 15px;
            border-bottom: 1px solid #eee;
            transition: all 0.3s;
        }
        
        .todo-item:hover {
            background: #f9f9f9;
        }
        
        .todo-text {
            flex: 1;
            margin-left: 15px;
            word-break: break-word;
        }
        
        .completed .todo-text {
            text-decoration: line-through;
            color: #aaa;
        }
        
        .delete-btn {
            background: var(--accent-color);
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 5px;
            cursor: pointer;
            margin-left: 10px;
            transition: background 0.3s;
        }
        
        .delete-btn:hover {
            background: #c0392b;
        }
        
        .no-tasks {
            text-align: center;
            padding: 30px;
            color: #aaa;
        }
        
        .stats {
            text-align: center;
            color: var(--gray-color);
            font-size: 14px;
        }
        
        /* Products Section */
        .products {
            background: #fff;
        }
        
        .products-container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .controls {
            display: flex;
            justify-content: space-between;
            margin-bottom: 30px;
            flex-wrap: wrap;
            gap: 20px;
        }
        
        .filter-section, .sort-section {
            display: flex;
            align-items: center;
            gap: 15px;
            flex-wrap: wrap;
        }
        
        select, input {
            padding: 10px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 14px;
            outline: none;
        }
        
        select:focus, input:focus {
            border-color: var(--primary-color);
        }
        
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }
        
        .product-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: all 0.3s;
            padding: 20px;
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }
        
        .product-image-placeholder {
            height: 150px;
            background: var(--light-gray);
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 15px;
            color: var(--gray-color);
        }
        
        .product-info {
            padding: 10px 0;
        }
        
        .product-title {
            font-size: 18px;
            margin-bottom: 10px;
            color: var(--secondary-color);
        }
        
        .product-category {
            display: inline-block;
            background: var(--light-gray);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 12px;
            color: var(--gray-color);
            margin-bottom: 10px;
        }
        
        .product-price {
            font-size: 20px;
            font-weight: bold;
            color: var(--secondary-color);
            margin-bottom: 10px;
        }
        
        .product-rating {
            color: #f39c12;
            margin-bottom: 15px;
            font-size: 14px;
        }
        
        .no-products {
            grid-column: 1 / -1;
            text-align: center;
            padding: 50px;
            color: #aaa;
        }
        
        /* Contact Section */
        .contact {
            background: var(--light-color);
        }
        
        .contact-content {
            display: flex;
            gap: 50px;
        }
        
        .contact-info {
            flex: 1;
        }
        
        .contact-info h3 {
            font-size: 24px;
            margin-bottom: 20px;
            color: var(--secondary-color);
        }
        
        .contact-info p {
            margin-bottom: 30px;
            color: var(--gray-color);
        }
        
        .contact-details div {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .contact-details i {
            margin-right: 15px;
            color: var(--primary-color);
            font-size: 20px;
        }
        
        .contact-form {
            flex: 1;
            background: #fff;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--secondary-color);
        }
        
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }
        
        .form-group textarea {
            height: 150px;
            resize: vertical;
        }
        
        /* Footer */
        footer {
            background: var(--secondary-color);
            color: #fff;
            padding: 50px 0 20px;
        }
        
        .footer-content {
            display: flex;
            justify-content: space-between;
            margin-bottom: 30px;
            flex-wrap: wrap;
            gap: 30px;
        }
        
        .footer-section {
            flex: 1;
            min-width: 250px;
        }
        
        .footer-section h3 {
            margin-bottom: 20px;
            font-size: 18px;
        }
        
        .footer-section p, .footer-section a {
            color: #bbb;
            margin-bottom: 10px;
            display: block;
            transition: color 0.3s;
        }
        
        .footer-section a:hover {
            color: #fff;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            transition: all 0.3s;
        }
        
        .social-links a:hover {
            background: var(--primary-color);
            transform: translateY(-5px);
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #bbb;
            font-size: 14px;
        }
        
        /* Responsive Design */
        @media (max-width: 992px) {
            .hero-content, .about-content, .contact-content {
                flex-direction: column;
            }
            
            .hero-text, .about-text, .skills, .contact-info, .contact-form {
                margin-bottom: 40px;
            }
            
            .hero-image {
                order: -1;
            }
        }
        
        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 70px;
                left: 0;
                right: 0;
                background: #fff;
                flex-direction: column;
                padding: 20px;
                box-shadow: 0 5px 10px rgba(0,0,0,0.1);
            }
            
            .nav-links.active {
                display: flex;
            }
            
            .nav-links li {
                margin: 10px 0;
            }
            
            .hamburger {
                display: block;
            }
            
            .section-title {
                font-size: 30px;
            }
            
            .hero-text h1 {
                font-size: 36px;
            }
            
            .hero-btns {
                flex-direction: column;
            }
            
            .controls {
                flex-direction: column;
            }
            
            .filter-section, .sort-section {
                flex-direction: column;
                align-items: flex-start;
            }
        }
    </style>
    <!-- Font Awesome for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">MyPortfolio</div>
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#todo">Todo App</a></li>
                    <li><a href="#products">Products</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <div class="hamburger">
                    <i class="fas fa-bars"></i>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero section">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1>Hi, I'm Alex Johnson</h1>
                    <p>Full Stack Developer with expertise in building modern web applications and responsive websites.</p>
                    <div class="hero-btns">
                        <a href="#contact" class="btn">Hire Me</a>
                        <a href="#about" class="btn btn-outline">Learn More</a>
                    </div>
                </div>
                <div class="hero-image">
                    <h2>Web Developer</h2>
                    <p>Creating digital experiences</p>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about section">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <div class="about-text">
                    <h3>Who I Am</h3>
                    <p>I'm a passionate developer with over 5 years of experience in web development. I specialize in creating beautiful, functional, and user-friendly digital experiences.</p>
                    <p>My journey in tech started when I built my first website at 15, and since then I've been constantly learning and expanding my skill set to stay at the forefront of web technologies.</p>
                    <p>When I'm not coding, you can find me hiking in the mountains, playing guitar, or reading science fiction novels.</p>
                </div>
                <div class="skills">
                    <h3>My Skills</h3>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>HTML/CSS</span>
                            <span>95%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 95%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>JavaScript</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 90%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>React</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 85%;"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Node.js</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 80%;"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Todo App Section -->
    <section id="todo" class="todo-app section">
        <div class="container">
            <h2 class="section-title">Todo App</h2>
            <div class="todo-container">
                <div class="todo-header">
                    <h3>My Todo List</h3>
                    <p>Organize your tasks and boost your productivity</p>
                </div>
                
                <div class="input-container">
                    <input type="text" id="todo-input" placeholder="Add a new task...">
                    <button id="add-btn">Add</button>
                </div>
                
                <div class="filter-container">
                    <button class="filter-btn active" data-filter="all">All</button>
                    <button class="filter-btn" data-filter="active">Active</button>
                    <button class="filter-btn" data-filter="completed">Completed</button>
                </div>
                
                <ul class="todo-list" id="todo-list">
                    <!-- Todo items will be added here dynamically -->
                </ul>
                
                <div class="stats" id="stats">
                    <span id="remaining-count">0</span> tasks remaining
                </div>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="products section">
        <div class="container">
            <h2 class="section-title">Product Showcase</h2>
            <div class="products-container">
                <div class="controls">
                    <div class="filter-section">
                        <h3>Filter:</h3>
                        <select id="category-filter">
                            <option value="all">All Categories</option>
                            <option value="electronics">Electronics</option>
                            <option value="clothing">Clothing</option>
                            <option value="home">Home & Garden</option>
                            <option value="books">Books</option>
                        </select>
                        
                        <div>
                            <label for="price-range">Price Range:</label>
                            <input type="range" id="price-range" min="0" max="1000" value="1000">
                            <span id="price-value">Up to $1000</span>
                        </div>
                    </div>
                    
                    <div class="sort-section">
                        <h3>Sort by:</h3>
                        <select id="sort-by">
                            <option value="default">Default</option>
                            <option value="price-asc">Price: Low to High</option>
                            <option value="price-desc">Price: High to Low</option>
                            <option value="rating-desc">Rating: High to Low</option>
                        </select>
                    </div>
                </div>
                
                <div class="products-grid" id="products-grid">
                    <!-- Products will be loaded here dynamically -->
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact section">
        <div class="container">
            <h2 class="section-title">Contact Me</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <h3>Get In Touch</h3>
                    <p>Have a project in mind or want to discuss potential opportunities? Feel free to reach out!</p>
                    
                    <div class="contact-details">
                        <div>
                            <i class="fas fa-map-marker-alt"></i>
                            <span>123 Main Street, San Francisco, CA</span>
                        </div>
                        <div>
                            <i class="fas fa-phone"></i>
                            <span>+1 (555) 123-4567</span>
                        </div>
                        <div>
                            <i class="fas fa-envelope"></i>
                            <span>alex@example.com</span>
                        </div>
                    </div>
                    
                    <div class="social-links">
                        <a href="#"><i class="fab fa-github"></i></a>
                        <a href="#"><i class="fab fa-linkedin"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
                
                <div class="contact-form">
                    <form id="contact-form">
                        <div class="form-group">
                            <label for="name">Name</label>
                            <input type="text" id="name" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" required>
                        </div>
                        <div class="form-group">
                            <label for="subject">Subject</label>
                            <input type="text" id="subject" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" required></textarea>
                        </div>
                        <button type="submit" class="btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>About</h3>
                    <p>Full stack developer specializing in modern web technologies and creating exceptional digital experiences.</p>
                </div>
                <div class="footer-section">
                    <h3>Quick Links</h3>
                    <a href="#home">Home</a>
                    <a href="#about">About</a>
                    <a href="#todo">Todo App</a>
                    <a href="#products">Products</a>
                    <a href="#contact">Contact</a>
                </div>
                <div class="footer-section">
                    <h3>Contact Info</h3>
                    <a href="#"><i class="fas fa-phone"></i> +1 (555) 123-4567</a>
                    <a href="#"><i class="fas fa-envelope"></i> alex@example.com</a>
                    <a href="#"><i class="fas fa-map-marker-alt"></i> San Francisco, CA</a>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2023 Alex Johnson. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Mobile menu toggle
        document.querySelector('.hamburger').addEventListener('click', function() {
            document.querySelector('.nav-links').classList.toggle('active');
        });
        
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
                
                // Close mobile menu if open
                document.querySelector('.nav-links').classList.remove('active');
            });
        });
        
        // Change header style on scroll
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 50) {
                header.style.boxShadow = '0 2px 10px rgba(0,0,0,0.1)';
            } else {
                header.style.boxShadow = 'none';
            }
        });
        
        // Todo App Functionality
        document.addEventListener('DOMContentLoaded', function() {
            const todoInput = document.getElementById('todo-input');
            const addBtn = document.getElementById('add-btn');
            const todoList = document.getElementById('todo-list');
            const filterBtns = document.querySelectorAll('.filter-btn');
            const remainingCount = document.getElementById('remaining-count');
            
            let todos = JSON.parse(localStorage.getItem('todos')) || [];
            let currentFilter = 'all';
            
            // Render todos based on current filter
            function renderTodos() {
                todoList.innerHTML = '';
                
                const filteredTodos = todos.filter(todo => {
                    if (currentFilter === 'all') return true;
                    if (currentFilter === 'active') return !todo.completed;
                    if (currentFilter === 'completed') return todo.completed;
                });
                
                if (filteredTodos.length === 0) {
                    todoList.innerHTML = '<div class="no-tasks">No tasks found</div>';
                    return;
                }
                
                filteredTodos.forEach(todo => {
                    const todoItem = document.createElement('li');
                    todoItem.className = `todo-item ${todo.completed ? 'completed' : ''}`;
                    todoItem.dataset.id = todo.id;
                    
                    todoItem.innerHTML = `
                        <input type="checkbox" ${todo.completed ? 'checked' : ''}>
                        <span class="todo-text">${todo.text}</span>
                        <button class="delete-btn">Delete</button>
                    `;
                    
                    todoList.appendChild(todoItem);
                    
                    // Add event listeners
                    const checkbox = todoItem.querySelector('input[type="checkbox"]');
                    const deleteBtn = todoItem.querySelector('.delete-btn');
                    
                    checkbox.addEventListener('change', function() {
                        toggleTodoComplete(todo.id);
                    });
                    
                    deleteBtn.addEventListener('click', function() {
                        deleteTodo(todo.id);
                    });
                });
                
                updateStats();
            }
            
            // Add new todo
            function addTodo() {
                const text = todoInput.value.trim();
                if (text === '') return;
                
                const newTodo = {
                    id: Date.now(),
                    text,
                    completed: false
                };
                
                todos.push(newTodo);
                saveTodos();
                todoInput.value = '';
                renderTodos();
            }
            
            // Toggle todo complete status
            function toggleTodoComplete(id) {
                todos = todos.map(todo => {
                    if (todo.id === id) {
                        return { ...todo, completed: !todo.completed };
                    }
                    return todo;
                });
                
                saveTodos();
                renderTodos();
            }
            
            // Delete todo
            function deleteTodo(id) {
                todos = todos.filter(todo => todo.id !== id);
                saveTodos();
                renderTodos();
            }
            
            // Save todos to localStorage
            function saveTodos() {
                localStorage.setItem('todos', JSON.stringify(todos));
            }
            
            // Update stats
            function updateStats() {
                const activeTodos = todos.filter(todo => !todo.completed).length;
                remainingCount.textContent = activeTodos;
            }
            
            // Event listeners
            addBtn.addEventListener('click', addTodo);
            
            todoInput.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    addTodo();
                }
            });
            
            filterBtns.forEach(btn => {
                btn.addEventListener('click', function() {
                    filterBtns.forEach(b => b.classList.remove('active'));
                    this.classList.add('active');
                    currentFilter = this.dataset.filter;
                    renderTodos();
                });
            });
            
            // Initial render
            renderTodos();
        });
        
        // Product Listing Functionality
        document.addEventListener('DOMContentLoaded', function() {
            const productsGrid = document.getElementById('products-grid');
            const categoryFilter = document.getElementById('category-filter');
            const priceRange = document.getElementById('price-range');
            const priceValue = document.getElementById('price-value');
            const sortBy = document.getElementById('sort-by');
            
            // Sample product data
            const products = [
                {
                    id: 1,
                    title: "Wireless Headphones",
                    category: "electronics",
                    price: 99.99,
                    rating: 4.5
                },
                {
                    id: 2,
                    title: "Smart Watch",
                    category: "electronics",
                    price: 199.99,
                    rating: 4.2
                },
                {
                    id: 3,
                    title: "Cotton T-Shirt",
                    category: "clothing",
                    price: 24.99,
                    rating: 4.0
                },
                {
                    id: 4,
                    title: "Leather Wallet",
                    category: "clothing",
                    price: 49.99,
                    rating: 4.7
                },
                {
                    id: 5,
                    title: "Coffee Maker",
                    category: "home",
                    price: 79.99,
                    rating: 4.3
                },
                {
                    id: 6,
                    title: "Indoor Plant",
                    category: "home",
                    price: 29.99,
                    rating: 4.8
                },
                {
                    id: 7,
                    title: "Bestseller Novel",
                    category: "books",
                    price: 14.99,
                    rating: 4.6
                },
                {
                    id: 8,
                    title: "Programming Book",
                    category: "books",
                    price: 39.99,
                    rating: 4.4
                }
            ];
            
            let filteredProducts = [...products];
            
            // Render products
            function renderProducts() {
                productsGrid.innerHTML = '';
                
                if (filteredProducts.length === 0) {
                    productsGrid.innerHTML = '<div class="no-products">No products match your filters</div>';
                    return;
                }
                
                filteredProducts.forEach(product => {
                    const productCard = document.createElement('div');
                    productCard.className = 'product-card';
                    
                    productCard.innerHTML = `
                        <div class="product-image-placeholder">
                            ${product.title}
                        </div>
                        <div class="product-info">
                            <h3 class="product-title">${product.title}</h3>
                            <span class="product-category">${product.category}</span>
                            <div class="product-price">$${product.price.toFixed(2)}</div>
                            <div class="product-rating">${'★'.repeat(Math.floor(product.rating))}${'☆'.repeat(5 - Math.floor(product.rating))} (${product.rating})</div>
                            <button class="btn add-to-cart">Add to Cart</button>
                        </div>
                    `;
                    
                    productsGrid.appendChild(productCard);
                    
                    // Add event listener to Add to Cart button
                    productCard.querySelector('.add-to-cart').addEventListener('click', function() {
                        alert(`${product.title} added to cart!`);
                    });
                });
            }
            
            // Filter products
            function filterProducts() {
                const category = categoryFilter.value;
                const maxPrice = parseInt(priceRange.value);
                
                filteredProducts = products.filter(product => {
                    // Category filter
                    if (category !== 'all' && product.category !== category) {
                        return false;
                    }
                    
                    // Price filter
                    if (product.price > maxPrice) {
                        return false;
                    }
                    
                    return true;
                });
                
                sortProducts();
            }
            
            // Sort products
            function sortProducts() {
                const sortValue = sortBy.value;
                
                switch (sortValue) {
                    case 'price-asc':
                        filteredProducts.sort((a, b) => a.price - b.price);
                        break;
                    case 'price-desc':
                        filteredProducts.sort((a, b) => b.price - a.price);
                        break;
                    case 'rating-desc':
                        filteredProducts.sort((a, b) => b.rating - a.rating);
                        break;
                    default:
                        // Default sorting (by ID or whatever original order)
                        filteredProducts.sort((a, b) => a.id - b.id);
                }
                
                renderProducts();
            }
            
            // Event listeners
            categoryFilter.addEventListener('change', filterProducts);
            
            priceRange.addEventListener('input', function() {
                priceValue.textContent = `Up to $${this.value}`;
                filterProducts();
            });
            
            sortBy.addEventListener('change', sortProducts);
            
            // Initial render
            filterProducts();
        });
        
        // Contact Form Submission
        document.getElementById('contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form values
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const subject = document.getElementById('subject').value;
            const message = document.getElementById('message').value;
            
            // Here you would typically send the data to a server
            // For this example, we'll just show an alert
            alert(`Thank you, ${name}! Your message has been sent. We'll get back to you soon.`);
            
            // Reset form
            this.reset();
        });
    </script>
</body>
</html>
