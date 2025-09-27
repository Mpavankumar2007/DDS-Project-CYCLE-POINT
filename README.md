<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CyclePoint - Premium Bike Rentals</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #f52008;
            --primary-light: #f60202;
            --secondary: #f39c12;
            --light: #f8f9fa;
            --dark: #343a40;
            --gray: #6c757d;
            --white: #ffffff;
            --border-radius: 8px;
            --box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--dark);
            background-color: var(--light);
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        .btn {
            display: inline-block;
            padding: 12px 24px;
            background-color: var(--primary);
            color: var(--white);
            border: none;
            border-radius: var(--border-radius);
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            text-align: center;
        }

        .btn:hover {
            background-color: var(--primary-light);
            transform: translateY(-2px);
        }

        .btn-secondary {
            background-color: var(--secondary);
        }

        .btn-secondary:hover {
            background-color: #e67e22;
        }

        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
        }

        .btn-outline:hover {
            background-color: var(--primary);
            color: var(--white);
        }

        header {
            background-color: var(--white);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            display: flex;
            align-items: center;
        }

        .logo i {
            margin-right: 10px;
        }

        .nav-menu {
            display: flex;
            list-style: none;
        }

        .nav-menu li {
            margin-left: 30px;
        }

        .nav-menu a {
            font-weight: 500;
            transition: var(--transition);
        }

        .nav-menu a:hover {
            color: var(--primary);
        }

        .mobile-toggle {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://images.unsplash.com/photo-1488646953014-85cb44e25828?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1332&q=80');
            background-size: cover;
            background-position: center;
            color: var(--white);
            padding: 100px 0;
            text-align: center;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 30px;
        }

        .hero-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 30px;
        }

        .features {
            padding: 80px 0;
            background-color: var(--white);
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 15px;
        }

        .section-title p {
            color: var(--gray);
            max-width: 600px;
            margin: 0 auto;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background-color: var(--white);
            padding: 30px;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            text-align: center;
            transition: var(--transition);
        }

        .feature-card:hover {
            transform: translateY(-10px);
        }

        .feature-icon {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 20px;
        }

        .feature-card h3 {
            margin-bottom: 15px;
        }

        .bike-showcase {
            padding: 80px 0;
            background-color: #f8f9fa;
        }

        .bike-filters {
            display: flex;
            justify-content: center;
            margin-bottom: 40px;
            flex-wrap: wrap;
            gap: 10px;
        }

        .filter-btn {
            padding: 8px 20px;
            background-color: var(--white);
            border: 1px solid #ddd;
            border-radius: 30px;
            cursor: pointer;
            transition: var(--transition);
        }

        .filter-btn.active, .filter-btn:hover {
            background-color: var(--primary);
            color: var(--white);
            border-color: var(--primary);
        }

        .bike-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .bike-card {
            background-color: var(--white);
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--box-shadow);
            transition: var(--transition);
        }

        .bike-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .bike-image {
            height: 200px;
            overflow: hidden;
        }

        .bike-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .bike-card:hover .bike-image img {
            transform: scale(1.05);
        }

        .bike-info {
            padding: 20px;
        }

        .bike-info h3 {
            margin-bottom: 10px;
        }

        .bike-meta {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            color: var(--gray);
        }

        .bike-price {
            font-weight: 700;
            color: var(--primary);
            font-size: 1.2rem;
        }

        .how-it-works {
            padding: 80px 0;
            background-color: var(--white);
        }

        .steps {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .step {
            text-align: center;
            position: relative;
        }

        .step-number {
            width: 50px;
            height: 50px;
            background-color: var(--primary);
            color: var(--white);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: 700;
            margin: 0 auto 20px;
        }

        .testimonials {
            padding: -80px 0;
            background-color: #f8f9fa;
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .testimonial-card {
            background-color: var(--white);
            padding: 30px;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
        }

        .testimonial-text {
            margin-bottom: 20px;
            font-style: italic;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
        }

        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            overflow: hidden;
            margin-right: 15px;
        }

        .author-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .author-info h4 {
            margin-bottom: 5px;
        }

        .cta {
            padding: 80px 0;
            background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.8)), url('https://images.unsplash.com/photo-1532298229144-0ec0c57515c7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1122&q=80');
            background-size: cover;
            background-position: center;
            color: var(--white);
            text-align: center;
        }

        footer {
            background-color: var(--dark);
            color: var(--white);
            padding: 60px 0 30px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-column h3 {
            margin-bottom: 20px;
            font-size: 1.2rem;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #ccc;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: var(--white);
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }

        .social-links a:hover {
            background-color: var(--primary);
        }

        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #ccc;
        }

        @media (max-width: 992px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .nav-menu {
                position: fixed;
                top: 80px;
                left: -100%;
                flex-direction: column;
                background-color: var(--white);
                width: 100%;
                height: calc(100vh - 80px);
                padding: 40px;
                transition: var(--transition);
                box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            }
            
            .nav-menu.active {
                left: 0;
            }
            
            .nav-menu li {
                margin: 15px 0;
            }
            
            .mobile-toggle {
                display: block;
            }
            
            .hero-buttons {
                flex-direction: column;
            }
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
            
            .footer-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-container">
            <a href="#" class="logo">
                <i class="fas fa-bicycle"></i>
                CyclePoint
            </a>
            
            <div class="mobile-toggle">
                <i class="fas fa-bars"></i>
            </div>
            
            <ul class="nav-menu">
                <li><a href="#">Home</a></li>
                <li><a href="#bikes">Bikes</a></li>
                <li><a href="#how-it-works">How It Works</a></li>
                <li><a href="#pricing">Pricing</a></li>
                <li><a href="#contact">Contact</a></li>
                <li><a href="#" class="btn">Book Now</a></li>
            </ul>
        </div>
    </header>

    <section class="hero">
        <div class="container hero-content">
            <h1>Explore The World On Two Wheels</h1>
            <p>Rent premium quality bicycles for your next adventure. Hourly, daily, and weekly rentals available at affordable prices.</p>
            <div class="hero-buttons">
                <a href="#bikes" class="btn">Browse Bikes</a>
                <a href="#how-it-works" class="btn btn-outline">How It Works</a>
            </div>
        </div>
    </section>

    <section class="features">
        <div class="container">
            <div class="section-title">
                <h2>Why Choose CyclePoint</h2>
                <p>We provide the best bike rental experience with premium quality bikes and exceptional service</p>
            </div>
            
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-cogs"></i>
                    </div>
                    <h3>Premium Bikes</h3>
                    <p>Our bikes are regularly serviced and maintained to ensure a smooth and safe ride.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-map-marked-alt"></i>
                    </div>
                    <h3>Guided Routes</h3>
                    <p>Get access to curated cycling routes tailored to your skill level and preferences.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-headset"></i>
                    </div>
                    <h3>24/7 Support</h3>
                    <p>Our team is available around the clock to assist with any issues during your rental period.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-tag"></i>
                    </div>
                    <h3>Flexible Pricing</h3>
                    <p>Choose from hourly, daily, or weekly rental options to suit your needs and budget.</p>
                </div>
            </div>
        </div>
    </section>

    <section class="bike-showcase" id="bikes">
        <div class="container">
            <div class="section-title">
                <h2>Our Bike Collection</h2>
                <p>Choose from our wide selection of well-maintained bicycles for all types of terrain</p>
            </div>
            
            <div class="bike-filters">
                <button class="filter-btn active">All Bikes</button>
                <button class="filter-btn">Mountain</button>
                <button class="filter-btn">Road</button>
                <button class="filter-btn">Hybrid</button>
                <button class="filter-btn">Electric</button>
            </div>
            
            <div class="bike-grid">
                <div class="bike-card">
                    <div class="bike-image">
                        <img src="https://images.unsplash.com/photo-1485965120184-e220f721d03e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="Premium mountain bike with rugged tires and suspension for off-road trails">
                    </div>
                    <div class="bike-info">
                        <h3>Mountain Pro X1</h3>
                        <div class="bike-meta">
                            <span>Mountain Bike</span>
                            <span class="bike-price">$25/day</span>
                        </div>
                        <p>Perfect for off-road adventures and challenging trails with front suspension and durable frame.</p>
                        <a href="#" class="btn">Rent Now</a>
                    </div>
                </div>
                
                <div class="bike-card">
                    <div class="bike-image">
                        <img src="https://images.unsplash.com/photo-1571068316344-75bc76f77890?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="Sleek road bike with drop handlebars and lightweight frame for speed">
                    </div>
                    <div class="bike-info">
                        <h3>Road Warrior 500</h3>
                        <div class="bike-meta">
                            <span>Road Bike</span>
                            <span class="bike-price">$20/day</span>
                        </div>
                        <p>Lightweight carbon frame with drop handlebars designed for speed and long distance road cycling.</p>
                        <a href="#" class="btn">Rent Now</a>
                    </div>
                </div>
                
                <div class="bike-card">
                    <div class="bike-image">
                        <img src="https://images.unsplash.com/photo-1585036156171-384164a8c675?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="Modern hybrid bicycle with upright riding position and comfortable seat">
                    </div>
                    <div class="bike-info">
                        <h3>City Cruiser</h3>
                        <div class="bike-meta">
                            <span>Hybrid Bike</span>
                            <span class="bike-price">$15/day</span>
                        </div>
                        <p>Comfortable upright riding position perfect for city commuting and casual weekend rides.</p>
                        <a href="#" class="btn">Rent Now</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="how-it-works" id="how-it-works">
        <div class="container">
            <div class="section-title">
                <h2>How It Works</h2>
                <p>Renting a bike has never been easier. Just follow these simple steps</p>
            </div>
            
            <div class="steps">
                <div class="step">
                    <div class="step-number">1</div>
                    <h3>Choose Your Bike</h3>
                    <p>Browse our collection and select the perfect bike for your needs.</p>
                </div>
                
                <div class="step">
                    <div class="step-number">2</div>
                    <h3>Book Online</h3>
                    <p>Select your rental period and complete the booking process.</p>
                </div>
                
                <div class="step">
                    <div class="step-number">3</div>
                    <h3>Pick Up & Ride</h3>
                    <p>Visit our location to pick up your bike and start your adventure.</p>
                </div>
                
                <div class="step">
                    <div class="step-number">4</div>
                    <h3>Return & Share</h3>
                    <p>Return the bike and share your experience with us!</p>
                </div>
            </div>
        </div>
    </section>

    <section class="testimonials">
        <div class="container">
            <div class="section-title">
                <h2>What Our Customers Say</h2>
                <p>Hear from people who have experienced our bike rental service</p>
            </div>
            
            <div class="testimonial-grid">
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "The mountain bike I rented was in perfect condition and made my trail riding experience amazing. Will definitely rent again!"
                    </div>
                </div>
                
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "I rented a hybrid bike for a week to explore the city. The process was seamless and the bike was comfortable and reliable."
                    </div>
                </div>
                
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "The electric bike made it possible for me to keep up with my family on our cycling holiday. Great service and quality bikes!"
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="cta">
        <div class="container">
            <div class="section-title">
                <h2>Ready to Start Cycling.</h2>
                <p>Book your bike today start building your physic better.</p>
            </div>
            <a href="#" class="btn btn-secondary">Reserve Your Bike Now</a>
        </div>
    </section>

    <footer id="contact">
        <div class="container">
            <div class="footer-grid">
                <div class="footer-column">
                    <h3>CyclePoint</h3>
                    <p>Providing quality bike rentals for adventures of all kinds since 2025.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#">Home</a></li>
                        <li><a href="#bikes">Bike Collection</a></li>
                        <li><a href="#how-it-works">How It Works</a></li>
                        <li><a href="#pricing">Pricing</a></li>
                        <li><a href="#contact">Contact Us</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Contact Info</h3>
                    <ul class="footer-links">
                        <li><i class="fas fa-map-marker-alt"></i> CyclePoint, Parul University.</li>
                        <li><i class="fas fa-phone"></i> 9014570225 </li>
                        <li><i class="fas fa-envelope"></i> cycleexpress123@gmail.com</li>
                        <li><i class="fas fa-clock"></i> Mon-Sat: 8AM - 8PM</li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Newsletter</h3>
                    <p>Subscribe to our newsletter for special offers and updates</p>
                    <form>
                        <input type="email" placeholder="Your Email" style="padding: 10px; width: 100%; margin-bottom: 10px; border-radius: 4px; border: none;">
                        <button type="submit" class="btn" style="width: 100%;">Subscribe</button>
                    </form>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2025 CyclePoint. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        const mobileToggle = document.querySelector('.mobile-toggle');
        const navMenu = document.querySelector('.nav-menu');
        
        mobileToggle.addEventListener('click', () => {
            navMenu.classList.toggle('active');
            mobileToggle.querySelector('i').classList.toggle('fa-bars');
            mobileToggle.querySelector('i').classList.toggle('fa-times');
        });
        
        const filterButtons = document.querySelectorAll('.filter-btn');
        
        filterButtons.forEach(button => {
            button.addEventListener('click', () => {
                filterButtons.forEach(btn => btn.classList.remove('active'));
                button.classList.add('active');
            });
        });
    </script>
</body>
</html>
