<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DesignSnap - AI Interior Design</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #6c5ce7;
            --secondary: #a29bfe;
            --accent: #fd79a8;
            --light: #f7f7ff;
            --dark: #2d3436;
        }
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        body {
            background: #f8f9fa;
            color: var(--dark);
            line-height: 1.6;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        header {
            background: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            padding: 20px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .logo {
            font-size: 28px;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
            display: flex;
            align-items: center;
        }
        .logo i {
            margin-right: 10px;
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
            transition: all 0.3s ease;
        }
        nav ul li a:hover {
            color: var(--primary);
        }
        .hero {
            padding: 160px 0 80px;
            text-align: center;
            background: linear-gradient(135deg, #f0f4ff 0%, #e6f7ff 100%);
        }
        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
            line-height: 1.2;
        }
        .hero h1 span {
            color: var(--primary);
        }
        .hero p {
            font-size: 20px;
            max-width: 700px;
            margin: 0 auto 40px;
            color: #495057;
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
        }
        .btn:hover {
            background: #5d4de0;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(108, 92, 231, 0.4);
        }
        .btn-accent {
            background: var(--accent);
        }
        .btn-accent:hover {
            background: #fc5d96;
        }
        .features {
            padding: 80px 0;
            background: white;
        }
        .section-title {
            text-align: center;
            font-size: 36px;
            margin-bottom: 50px;
        }
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        .feature-card {
            background: #fff;
            border-radius: 20px;
            padding: 40px 30px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
        }
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(108, 92, 231, 0.15);
        }
        .feature-icon {
            width: 80px;
            height: 80px;
            background: rgba(108, 92, 231, 0.1);
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
        }
        .download-section {
            padding: 80px 0;
            text-align: center;
            background: linear-gradient(135deg, var(--primary), #5d4de0);
            color: white;
        }
        .app-badges {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
            flex-wrap: wrap;
        }
        .app-badge {
            background: black;
            color: white;
            padding: 15px 30px;
            border-radius: 12px;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .app-badge.android {
            background: #3ddc84;
            color: black;
        }
        footer {
            background: #2d3436;
            color: white;
            padding: 60px 0 30px;
        }
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
        }
        .footer-col h3 {
            font-size: 20px;
            margin-bottom: 20px;
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
        }
        .copyright {
            text-align: center;
            padding-top: 30px;
            margin-top: 40px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #adb5bd;
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 36px;
            }
            nav ul {
                display: none;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-container">
            <a href="#" class="logo">
                <i class="fas fa-paint-roller"></i>
                DesignSnap
            </a>
            <nav>
                <ul>
                    <li><a href="#features">Features</a></li>
                    <li><a href="#download">Download</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <h1>Transform Your Space with <span>AI Magic</span></h1>
            <p>DesignSnap uses augmented reality to help you visualize furniture in your room instantly. Redesign any space in seconds!</p>
            <div style="display: flex; gap: 15px; justify-content: center; margin-top: 30px;">
                <a href="#download" class="btn">Download App</a>
                <a href="#features" class="btn btn-accent">View Demo</a>
            </div>
        </div>
    </section>

    <section class="features" id="features">
        <div class="container">
            <h2 class="section-title">Amazing Features</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-vr-cardboard"></i>
                    </div>
                    <h3>AR Room Scanning</h3>
                    <p>See furniture in your actual space before buying with precision measurements</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-robot"></i>
                    </div>
                    <h3>AI Design Assistant</h3>
                    <p>Get instant style recommendations tailored to your preferences</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-palette"></i>
                    </div>
                    <h3>Style Generator</h3>
                    <p>Experiment with thousands of design styles with one tap</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-shopping-cart"></i>
                    </div>
                    <h3>Shop the Look</h3>
                    <p>Purchase items directly through our curated marketplace</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-users"></i>
                    </div>
                    <h3>Collaboration</h3>
                    <p>Design together with family or professionals in real-time</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-ruler-combined"></i>
                    </div>
                    <h3>Precise Measurements</h3>
                    <p>Accurate room dimensions and furniture fitting predictions</p>
                </div>
            </div>
        </div>
    </section>

    <section class="download-section" id="download">
        <div class="container">
            <h2 class="section-title">Download DesignSnap Today</h2>
            <p style="font-size: 20px; max-width: 600px; margin: 0 auto 40px;">Available on iOS and Android devices</p>
            
            <div class="app-badges">
                <a href="#" class="app-badge">
                    <i class="fab fa-apple fa-2x"></i>
                    <div>
                        <div>Download on the</div>
                        <div style="font-weight:bold;font-size:24px">App Store</div>
                    </div>
                </a>
                
                <a href="#" class="app-badge android">
                    <i class="fab fa-android fa-2x"></i>
                    <div>
                        <div>GET IT ON</div>
                        <div style="font-weight:bold;font-size:24px">Google Play</div>
                    </div>
                </a>
            </div>
        </div>
    </section>

    <footer id="contact">
        <div class="container">
            <div class="footer-grid">
                <div class="footer-col">
                    <h3>DesignSnap</h3>
                    <p>Transform any space with the power of AI and augmented reality. Professional interior design made accessible.</p>
                    <div style="display: flex; gap: 15px; margin-top: 20px;">
                        <a href="#" style="color: white;"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" style="color: white;"><i class="fab fa-instagram"></i></a>
                        <a href="#" style="color: white;"><i class="fab fa-twitter"></i></a>
                        <a href="#" style="color: white;"><i class="fab fa-pinterest-p"></i></a>
                    </div>
                </div>
                
                <div class="footer-col">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#features">Features</a></li>
                        <li><a href="#download">Download</a></li>
                        <li><a href="#">Pricing</a></li>
                        <li><a href="#">Testimonials</a></li>
                        <li><a href="#">Blog</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h3>Resources</h3>
                    <ul class="footer-links">
                        <li><a href="#">Design Guides</a></li>
                        <li><a href="#">Style Gallery</a></li>
                        <li><a href="#">Tutorial Videos</a></li>
                        <li><a href="#">FAQs</a></li>
                        <li><a href="#">Support Center</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h3>Contact Us</h3>
                    <ul class="footer-links">
                        <li><i class="fas fa-envelope"></i> support@designsnap.app</li>
                        <li><i class="fas fa-phone"></i> +1 (800) DS-HELP</li>
                        <li><i class="fas fa-map-marker-alt"></i> San Francisco, CA</li>
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
    </script>
</body>
</html>
