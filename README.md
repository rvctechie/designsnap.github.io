<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DesignSnap - AI-Powered Interior Design App</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Global Styles */
        :root {
            --primary: #4361ee;
            --secondary: #3f37c9;
            --accent: #ff6b6b;
            --light: #f8f9fa;
            --dark: #212529;
            --success: #4cc9f0;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #fff;
            color: var(--dark);
            overflow-x: hidden;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        section {
            padding: 80px 0;
        }
        
        .btn {
            display: inline-block;
            padding: 14px 32px;
            background: var(--primary);
            color: white;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 18px;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(67, 97, 238, 0.3);
        }
        
        .btn:hover {
            background: var(--secondary);
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(67, 97, 238, 0.4);
        }
        
        .btn-accent {
            background: var(--accent);
            box-shadow: 0 4px 15px rgba(255, 107, 107, 0.3);
        }
        
        .btn-accent:hover {
            background: #ff5252;
            box-shadow: 0 6px 20px rgba(255, 107, 107, 0.4);
        }
        
        .section-title {
            font-size: 42px;
            font-weight: 700;
            text-align: center;
            margin-bottom: 20px;
            color: var(--dark);
        }
        
        .section-subtitle {
            font-size: 22px;
            text-align: center;
            color: #6c757d;
            max-width: 700px;
            margin: 0 auto 60px;
            line-height: 1.6;
        }
        
        /* Header Styles */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            padding: 20px 0;
            transition: all 0.3s ease;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            font-size: 28px;
            font-weight: 800;
            color: var(--primary);
            text-decoration: none;
        }
        
        .logo i {
            margin-right: 10px;
            font-size: 32px;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 30px;
        }
        
        nav ul li a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 600;
            font-size: 17px;
            transition: all 0.3s ease;
        }
        
        nav ul li a:hover {
            color: var(--primary);
        }
        
        .nav-btns {
            display: flex;
            align-items: center;
        }
        
        .mobile-toggle {
            display: none;
            font-size: 24px;
            cursor: pointer;
        }
        
        /* Hero Section */
        .hero {
            padding: 180px 0 100px;
            background: linear-gradient(135deg, #f0f4ff 0%, #e6f7ff 100%);
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: "";
            position: absolute;
            top: -200px;
            right: -200px;
            width: 600px;
            height: 600px;
            border-radius: 50%;
            background: linear-gradient(135deg, rgba(67, 97, 238, 0.1) 0%, rgba(63, 55, 201, 0.05) 100%);
        }
        
        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .hero-text {
            flex: 1;
            max-width: 600px;
        }
        
        .hero-title {
            font-size: 60px;
            font-weight: 800;
            line-height: 1.2;
            margin-bottom: 20px;
            color: var(--dark);
        }
        
        .hero-title span {
            color: var(--primary);
        }
        
        .hero-subtitle {
            font-size: 22px;
            color: #495057;
            margin-bottom: 40px;
            line-height: 1.6;
        }
        
        .hero-btns {
            display: flex;
            gap: 20px;
            margin-bottom: 40px;
        }
        
        .hero-stats {
            display: flex;
            gap: 40px;
        }
        
        .stat-item h3 {
            font-size: 32px;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 5px;
        }
        
        .stat-item p {
            color: #6c757d;
            font-size: 18px;
        }
        
        .hero-image {
            flex: 1;
            position: relative;
            display: flex;
            justify-content: center;
        }
        
        .phone-mockup {
            width: 300px;
            height: auto;
            border-radius: 40px;
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.2);
            transform: perspective(1000px) rotateY(-10deg);
            transition: transform 0.5s ease;
            z-index: 2;
        }
        
        .phone-mockup:hover {
            transform: perspective(1000px) rotateY(0deg);
        }
        
        /* Features Section */
        .features {
            background: white;
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
        }
        
        .feature-card {
            background: #fff;
            border-radius: 20px;
            padding: 40px 30px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
            border: 1px solid #e9ecef;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(67, 97, 238, 0.15);
        }
        
        .feature-icon {
            width: 80px;
            height: 80px;
            background: rgba(67, 97, 238, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 25px;
        }
        
        .feature-icon i {
            font-size: 36px;
            color: var(--primary);
        }
        
        .feature-card h3 {
            font-size: 24px;
            margin-bottom: 15px;
            color: var(--dark);
        }
        
        .feature-card p {
            color: #6c757d;
            line-height: 1.6;
        }
        
        /* How It Works */
        .how-it-works {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
        }
        
        .steps-container {
            display: flex;
            justify-content: space-between;
            gap: 40px;
            margin-top: 60px;
        }
        
        .step {
            flex: 1;
            text-align: center;
            position: relative;
        }
        
        .step:not(:last-child)::after {
            content: "";
            position: absolute;
            top: 80px;
            right: -60px;
            width: 60px;
            height: 2px;
            background: var(--primary);
        }
        
        .step-number {
            width: 60px;
            height: 60px;
            background: var(--primary);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            font-weight: 700;
            margin: 0 auto 25px;
        }
        
        .step h3 {
            font-size: 22px;
            margin-bottom: 15px;
        }
        
        .step p {
            color: #6c757d;
            line-height: 1.6;
        }
        
        /* Pricing Section */
        .pricing {
            background: white;
        }
        
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .pricing-card {
            background: #fff;
            border-radius: 20px;
            padding: 50px 30px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            border: 1px solid #e9ecef;
            position: relative;
            transition: all 0.3s ease;
        }
        
        .pricing-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(67, 97, 238, 0.15);
        }
        
        .pricing-card.popular {
            border: 2px solid var(--primary);
            transform: scale(1.05);
        }
        
        .popular-badge {
            position: absolute;
            top: -15px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--accent);
            color: white;
            padding: 5px 20px;
            border-radius: 20px;
            font-size: 14px;
            font-weight: 600;
        }
        
        .pricing-card h3 {
            font-size: 24px;
            margin-bottom: 15px;
            color: var(--dark);
        }
        
        .price {
            font-size: 48px;
            font-weight: 700;
            margin-bottom: 30px;
            color: var(--primary);
        }
        
        .price span {
            font-size: 18px;
            color: #6c757d;
        }
        
        .pricing-features {
            list-style: none;
            margin-bottom: 40px;
        }
        
        .pricing-features li {
            padding: 12px 0;
            border-bottom: 1px solid #e9ecef;
            color: #495057;
        }
        
        .pricing-features li:last-child {
            border-bottom: none;
        }
        
        .pricing-features li i {
            color: var(--success);
            margin-right: 10px;
        }
        
        /* Testimonials */
        .testimonials {
            background: linear-gradient(135deg, #f0f4ff 0%, #e6f7ff 100%);
        }
        
        .testimonials-container {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .testimonial-card {
            background: white;
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            margin-bottom: 30px;
            position: relative;
        }
        
        .testimonial-card::before {
            content: """;
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 80px;
            color: rgba(67, 97, 238, 0.1);
            font-family: Georgia, serif;
            line-height: 1;
        }
        
        .testimonial-text {
            font-size: 18px;
            line-height: 1.8;
            color: #495057;
            margin-bottom: 25px;
        }
        
        .testimonial-author {
            display: flex;
            align-items: center;
        }
        
        .author-img {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            margin-right: 15px;
            background: #4361ee;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 24px;
        }
        
        .author-info h4 {
            font-size: 20px;
            margin-bottom: 5px;
        }
        
        .author-info p {
            color: #6c757d;
        }
        
        /* CTA Section */
        .cta {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            text-align: center;
            padding: 100px 0;
        }
        
        .cta .section-title, 
        .cta .section-subtitle {
            color: white;
        }
        
        .cta .section-subtitle {
            opacity: 0.9;
        }
        
        .cta-form {
            max-width: 500px;
            margin: 40px auto 0;
            display: flex;
        }
        
        .cta-form input {
            flex: 1;
            padding: 18px 25px;
            border: none;
            border-radius: 50px 0 0 50px;
            font-size: 16px;
        }
        
        .cta-form button {
            border-radius: 0 50px 50px 0;
            padding: 18px 30px;
        }
        
        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 80px 0 30px;
        }
        
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 60px;
        }
        
        .footer-col h3 {
            font-size: 20px;
            margin-bottom: 25px;
            position: relative;
        }
        
        .footer-col h3::after {
            content: "";
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 40px;
            height: 3px;
            background: var(--accent);
        }
        
        .footer-col p {
            color: #adb5bd;
            line-height: 1.8;
            margin-bottom: 20px;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
        }
        
        .social-links a {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            background: var(--primary);
            transform: translateY(-5px);
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 12px;
        }
        
        .footer-links a {
            color: #adb5bd;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .footer-links a:hover {
            color: white;
            padding-left: 5px;
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #adb5bd;
            font-size: 14px;
        }
        
        /* Responsive Styles */
        @media (max-width: 992px) {
            .hero-content {
                flex-direction: column;
                text-align: center;
            }
            
            .hero-text {
                margin-bottom: 60px;
            }
            
            .hero-stats {
                justify-content: center;
            }
            
            .steps-container {
                flex-direction: column;
                gap: 60px;
            }
            
            .step:not(:last-child)::after {
                display: none;
            }
        }
        
        @media (max-width: 768px) {
            .section-title {
                font-size: 36px;
            }
            
            .section-subtitle {
                font-size: 18px;
            }
            
            .hero-title {
                font-size: 42px;
            }
            
            .hero-subtitle {
                font-size: 18px;
            }
            
            .hero-btns {
                flex-direction: column;
                gap: 15px;
            }
            
            nav ul {
                display: none;
            }
            
            .mobile-toggle {
                display: block;
            }
            
            .cta-form {
                flex-direction: column;
                gap: 15px;
            }
            
            .cta-form input,
            .cta-form button {
                width: 100%;
                border-radius: 50px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <a href="#" class="logo">
                <i class="fas fa-paint-roller"></i>
                DesignSnap
            </a>
            
            <nav>
                <ul>
                    <li><a href="#features">Features</a></li>
                    <li><a href="#how-it-works">How It Works</a></li>
                    <li><a href="#pricing">Pricing</a></li>
                    <li><a href="#testimonials">Testimonials</a></li>
                </ul>
            </nav>
            
            <div class="nav-btns">
                <a href="#download" class="btn">Download</a>
                <div class="mobile-toggle">
                    <i class="fas fa-bars"></i>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container hero-content">
            <div class="hero-text">
                <h1 class="hero-title">Transform Your Space with <span>AI-Powered Design</span></h1>
                <p class="hero-subtitle">DesignSnap uses augmented reality and artificial intelligence to help you visualize, design, and transform any room in seconds. Professional results without the cost.</p>
                
                <div class="hero-btns">
                    <a href="#download" class="btn">Download App</a>
                    <a href="#pricing" class="btn btn-accent">View Plans</a>
                </div>
                
                <div class="hero-stats">
                    <div class="stat-item">
                        <h3>250K+</h3>
                        <p>Happy Users</p>
                    </div>
                    <div class="stat-item">
                        <h3>4.9★</h3>
                        <p>App Store Rating</p>
                    </div>
                    <div class="stat-item">
                        <h3>95%</h3>
                        <p>Design Accuracy</p>
                    </div>
                </div>
            </div>
            
            <div class="hero-image">
                <img src="https://images.unsplash.com/photo-1585123334904-845d60e97b29?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="DesignSnap App Preview" class="phone-mockup">
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="features">
        <div class="container">
            <h2 class="section-title">Powerful Design Features</h2>
            <p class="section-subtitle">Everything you need to transform your space with professional results, right from your phone.</p>
            
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-vr-cardboard"></i>
                    </div>
                    <h3>Augmented Reality</h3>
                    <p>Visualize furniture and decor in your actual space using AR technology. See how items fit before you buy.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-robot"></i>
                    </div>
                    <h3>AI Design Assistant</h3>
                    <p>Get instant design recommendations tailored to your space, style preferences, and budget.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-palette"></i>
                    </div>
                    <h3>Style Generator</h3>
                    <p>Experiment with thousands of design styles from minimalist to maximalist with one tap.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-shopping-cart"></i>
                    </div>
                    <h3>Shop the Look</h3>
                    <p>Purchase furniture and decor directly through our marketplace with exclusive discounts.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-leaf"></i>
                    </div>
                    <h3>Sustainability Score</h3>
                    <p>See the environmental impact of your design choices and discover eco-friendly alternatives.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-users"></i>
                    </div>
                    <h3>Collaboration Mode</h3>
                    <p>Design together in real-time with family, friends, or professional designers.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- How It Works Section -->
    <section class="how-it-works" id="how-it-works">
        <div class="container">
            <h2 class="section-title">How DesignSnap Works</h2>
            <p class="section-subtitle">Transform any room in just 4 simple steps. Professional results in minutes.</p>
            
            <div class="steps-container">
                <div class="step">
                    <div class="step-number">1</div>
                    <h3>Scan Your Space</h3>
                    <p>Use your phone's camera to scan the room you want to redesign. Our AI detects walls, floors, and dimensions.</p>
                </div>
                
                <div class="step">
                    <div class="step-number">2</div>
                    <h3>Choose Your Style</h3>
                    <p>Select from dozens of design styles or let our AI recommend options based on your preferences.</p>
                </div>
                
                <div class="step">
                    <div class="step-number">3</div>
                    <h3>Customize & Visualize</h3>
                    <p>Drag and drop furniture, change colors, and see your design come to life in AR.</p>
                </div>
                
                <div class="step">
                    <div class="step-number">4</div>
                    <h3>Implement & Shop</h3>
                    <p>Get a shopping list, step-by-step implementation guide, and buy everything with one tap.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Pricing Section -->
    <section class="pricing" id="pricing">
        <div class="container">
            <h2 class="section-title">Simple, Transparent Pricing</h2>
            <p class="section-subtitle">Choose the plan that works for you. All plans include core features.</p>
            
            <div class="pricing-grid">
                <div class="pricing-card">
                    <h3>Free</h3>
                    <div class="price">$0 <span>/ forever</span></div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check"></i> Basic room scanning</li>
                        <li><i class="fas fa-check"></i> 3 design styles</li>
                        <li><i class="fas fa-check"></i> 5 furniture placements/day</li>
                        <li><i class="fas fa-check"></i> Standard resolution renders</li>
                        <li><i class="fas fa-times"></i> AI design assistant</li>
                        <li><i class="fas fa-times"></i> Premium styles</li>
                        <li><i class="fas fa-times"></i> Shopping discounts</li>
                    </ul>
                    <a href="#download" class="btn">Get Started</a>
                </div>
                
                <div class="pricing-card popular">
                    <div class="popular-badge">MOST POPULAR</div>
                    <h3>Pro</h3>
                    <div class="price">$9.99 <span>/ month</span></div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check"></i> Advanced room scanning</li>
                        <li><i class="fas fa-check"></i> 50+ design styles</li>
                        <li><i class="fas fa-check"></i> Unlimited placements</li>
                        <li><i class="fas fa-check"></i> 4K resolution renders</li>
                        <li><i class="fas fa-check"></i> AI design assistant</li>
                        <li><i class="fas fa-check"></i> Premium styles</li>
                        <li><i class="fas fa-check"></i> 10% shopping discount</li>
                    </ul>
                    <a href="#download" class="btn">Start Free Trial</a>
                </div>
                
                <div class="pricing-card">
                    <h3>Professional</h3>
                    <div class="price">$49.99 <span>/ month</span></div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check"></i> Everything in Pro</li>
                        <li><i class="fas fa-check"></i> Commercial license</li>
                        <li><i class="fas fa-check"></i> Client presentation tools</li>
                        <li><i class="fas fa-check"></i> Branded exports</li>
                        <li><i class="fas fa-check"></i> Priority support</li>
                        <li><i class="fas fa-check"></i> Project management</li>
                        <li><i class="fas fa-check"></i> 15% shopping discount</li>
                    </ul>
                    <a href="#download" class="btn">Try Professional</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="testimonials" id="testimonials">
        <div class="container">
            <h2 class="section-title">What Our Users Say</h2>
            <p class="section-subtitle">Join thousands of satisfied users who transformed their spaces with DesignSnap.</p>
            
            <div class="testimonials-container">
                <div class="testimonial-card">
                    <p class="testimonial-text">"DesignSnap completely changed how I approach interior design. As a real estate agent, I can now stage homes virtually for clients, saving thousands in physical staging costs. The AR feature is incredibly accurate!"</p>
                    <div class="testimonial-author">
                        <div class="author-img">SJ</div>
                        <div class="author-info">
                            <h4>Sarah Johnson</h4>
                            <p>Real Estate Professional</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card">
                    <p class="testimonial-text">"I used to spend hours trying to visualize furniture in my space. With DesignSnap, I can try dozens of arrangements in minutes. The AI suggestions are surprisingly good and helped me discover styles I never would have considered."</p>
                    <div class="testimonial-author">
                        <div class="author-img">MT</div>
                        <div class="author-info">
                            <h4>Michael Thompson</h4>
                            <p>Homeowner</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card">
                    <p class="testimonial-text">"As a freelance interior designer, DesignSnap has cut my concept development time in half. The collaboration feature lets me work with clients in real-time, and the professional plan pays for itself with the shopping discounts alone."</p>
                    <div class="testimonial-author">
                        <div class="author-img">ER</div>
                        <div class="author-info">
                            <h4>Emily Rodriguez</h4>
                            <p>Interior Designer</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="cta" id="download">
        <div class="container">
            <h2 class="section-title">Ready to Transform Your Space?</h2>
            <p class="section-subtitle">Join over 250,000 users who are designing their dream homes with DesignSnap.</p>
            
            <div class="cta-form">
                <input type="email" placeholder="Enter your email address">
                <button class="btn btn-accent">Get Started</button>
            </div>
            
            <div style="margin-top: 30px; display: flex; justify-content: center; gap: 20px;">
                <a href="#" class="btn" style="background: #000;">
                    <i class="fab fa-apple"></i> App Store
                </a>
                <a href="#" class="btn" style="background: #3DDC84; color: #000;">
                    <i class="fab fa-android"></i> Google Play
                </a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-col">
                    <h3>DesignSnap</h3>
                    <p>Transform any space with the power of augmented reality and artificial intelligence. Professional interior design made accessible to everyone.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-pinterest-p"></i></a>
                    </div>
                </div>
                
                <div class="footer-col">
                    <h3>Company</h3>
                    <ul class="footer-links">
                        <li><a href="#">About Us</a></li>
                        <li><a href="#">Careers</a></li>
                        <li><a href="#">Press</a></li>
                        <li><a href="#">Blog</a></li>
                        <li><a href="#">Contact Us</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h3>Resources</h3>
                    <ul class="footer-links">
                        <li><a href="#">Design Ideas</a></li>
                        <li><a href="#">Style Guides</a></li>
                        <li><a href="#">Tutorials</a></li>
                        <li><a href="#">Inspiration Gallery</a></li>
                        <li><a href="#">Designer Directory</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h3>Support</h3>
                    <ul class="footer-links">
                        <li><a href="#">Help Center</a></li>
                        <li><a href="#">FAQs</a></li>
                        <li><a href="#">Community</a></li>
                        <li><a href="#">Partnerships</a></li>
                        <li><a href="#">Affiliate Program</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2023 DesignSnap. All rights reserved. | Privacy Policy | Terms of Service</p>
            </div>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
        
        // Header scroll effect
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.padding = '10px 0';
                header.style.boxShadow = '0 2px 10px rgba(0, 0, 0, 0.1)';
            } else {
                header.style.padding = '20px 0';
                header.style.boxShadow = '0 2px 20px rgba(0, 0, 0, 0.1)';
            }
        });
        
        // Mobile menu toggle
        const mobileToggle = document.querySelector('.mobile-toggle');
        const nav = document.querySelector('nav ul');
        
        mobileToggle.addEventListener('click', function() {
            nav.style.display = nav.style.display === 'flex' ? 'none' : 'flex';
        });
    </scr<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DesignSnap - AI Interior Design App</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Color Scheme */
        :root {
            --primary: #6c5ce7;
            --secondary: #a29bfe;
            --accent: #fd79a8;
            --light: #f7f7ff;
            --dark: #2d3436;
            --success: #00b894;
        }
        
        /* Reset & Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f8f9fa;
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        section {
            padding: 80px 0;
        }
        
        h1, h2, h3, h4 {
            margin-bottom: 20px;
            color: var(--dark);
        }
        
        p {
            margin-bottom: 15px;
        }
        
        img {
            max-width: 100%;
        }
        
        /* Buttons */
        .btn {
            display: inline-block;
            padding: 14px 32px;
            background: var(--primary);
            color: white;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 18px;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(108, 92, 231, 0.3);
        }
        
        .btn:hover {
            background: #5d4de0;
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(108, 92, 231, 0.4);
        }
        
        .btn-accent {
            background: var(--accent);
            box-shadow: 0 4px 15px rgba(253, 121, 168, 0.3);
        }
        
        .btn-accent:hover {
            background: #fc5d96;
            box-shadow: 0 6px 20px rgba(253, 121, 168, 0.4);
        }
        
        .btn-light {
            background: white;
            color: var(--primary);
        }
        
        .btn-light:hover {
            background: #f0f0ff;
        }
        
        /* Header */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            padding: 20px 0;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            font-size: 28px;
            font-weight: 800;
            color: var(--primary);
            text-decoration: none;
        }
        
        .logo i {
            margin-right: 10px;
            font-size: 32px;
        }
        
        /* Hero Section */
        .hero {
            padding: 180px 0 100px;
            background: linear-gradient(135deg, #f0f4ff 0%, #e6f7ff 100%);
            position: relative;
            overflow: hidden;
        }
        
        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .hero-text {
            flex: 1;
            max-width: 600px;
        }
        
        .hero-title {
            font-size: 60px;
            font-weight: 800;
            line-height: 1.2;
            margin-bottom: 20px;
        }
        
        .hero-title span {
            color: var(--primary);
        }
        
        .hero-subtitle {
            font-size: 22px;
            color: #495057;
            margin-bottom: 40px;
        }
        
        .hero-btns {
            display: flex;
            gap: 20px;
            margin-bottom: 40px;
        }
        
        .hero-st
