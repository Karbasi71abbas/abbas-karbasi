# abbas-karbasi

<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مهندس عباس کرباسی - متخصص نقشه برداری</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Tahoma', 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: all 0.3s ease;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #2c3e50;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #667eea;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: #667eea;
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Mobile Menu */
        .mobile-menu {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .mobile-menu span {
            width: 25px;
            height: 3px;
            background: #333;
            margin: 3px 0;
            transition: 0.3s;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grid" width="10" height="10" patternUnits="userSpaceOnUse"><path d="M 10 0 L 0 0 0 10" fill="none" stroke="rgba(255,255,255,0.1)" stroke-width="0.5"/></pattern></defs><rect width="100" height="100" fill="url(%23grid)"/></svg>');
            opacity: 0.3;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            color: white;
            max-width: 800px;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            animation: slideInUp 1s ease;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            animation: slideInUp 1s ease 0.2s both;
        }

        .cta-button {
            display: inline-block;
            padding: 12px 30px;
            background: linear-gradient(45deg, #ff6b6b, #ffa500);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            animation: slideInUp 1s ease 0.4s both;
            box-shadow: 0 8px 30px rgba(255, 107, 107, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 40px rgba(255, 107, 107, 0.4);
        }

        /* Sections */
        section {
            padding: 80px 0;
            background: white;
            margin: 20px 0;
            border-radius: 20px;
            box-shadow: 0 10px 50px rgba(0, 0, 0, 0.1);
        }

        h2 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 3rem;
            color: #2c3e50;
            position: relative;
        }

        h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            border-radius: 2px;
        }

        /* Services Grid */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .service-card {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .service-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #667eea;
        }

        .service-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #2c3e50;
        }

        /* Gallery */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1rem;
            margin-top: 3rem;
        }

        .gallery-item {
            position: relative;
            height: 200px;
            border-radius: 15px;
            overflow: hidden;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .gallery-item:hover {
            transform: scale(1.05);
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
        }

        .gallery-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.8), rgba(118, 75, 162, 0.8));
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .gallery-item:hover .gallery-overlay {
            opacity: 1;
        }

        .gallery-overlay h4 {
            color: white;
            font-size: 1.2rem;
            text-align: center;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 3rem;
            align-items: center;
        }

        .about-image {
            text-align: center;
        }

        .profile-img {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            object-fit: cover;
            border: 8px solid #667eea;
            box-shadow: 0 20px 40px rgba(102, 126, 234, 0.3);
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #555;
        }

        /* Contact Form */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
            color: #2c3e50;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border: 2px solid #e1e8ed;
            border-radius: 10px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #667eea;
        }

        .submit-btn {
            width: 100%;
            padding: 15px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.3);
        }

        /* Footer */
        footer {
            background: #2c3e50;
            color: white;
            text-align: center;
            padding: 2rem 0;
            border-radius: 20px 20px 0 0;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            color: #667eea;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            color: white;
            font-size: 1.5rem;
            transition: color 0.3s ease;
        }

        .social-links a:hover {
            color: #667eea;
        }

        /* Animations */
        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .mobile-menu {
                display: flex;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .profile-img {
                width: 200px;
                height: 200px;
            }

            .services-grid {
                grid-template-columns: 1fr;
            }

            .gallery-grid {
                grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            }
        }

        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav class="container">
            <div class="logo">مهندس عباس کرباسی</div>
            <ul class="nav-links">
                <li><a href="#home">خانه</a></li>
                <li><a href="#services">خدمات</a></li>
                <li><a href="#gallery">گالری</a></li>
                <li><a href="#about">درباره ما</a></li>
                <li><a href="#contact">تماس</a></li>
            </ul>
            <div class="mobile-menu">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>مهندس عباس کرباسی</h1>
            <p>متخصص نقشه‌برداری و خدمات مهندسی دقیق</p>
            <a href="#services" class="cta-button">مشاهده خدمات</a>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services">
        <div class="container">
            <h2 class="fade-in">خدمات ما</h2>
            <div class="services-grid">
                <div class="service-card fade-in">
                    <div class="service-icon">📐</div>
                    <h3>نقشه‌برداری ملکی</h3>
                    <p>انجام نقشه‌برداری دقیق املاک و مستغلات با استفاده از جدیدترین تجهیزات و روش‌های علمی</p>
                </div>
                <div class="service-card fade-in">
                    <div class="service-icon">🗺️</div>
                    <h3>نقشه‌برداری توپوگرافی</h3>
                    <p>تهیه نقشه‌های توپوگرافی با دقت بالا برای پروژه‌های عمرانی و ساختمانی</p>
                </div>
                <div class="service-card fade-in">
                    <div class="service-icon">🛰️</div>
                    <h3>GPS و مختصات‌یابی</h3>
                    <p>خدمات تعیین مختصات دقیق با استفاده از سیستم‌های ماهواره‌ای پیشرفته</p>
                </div>
                <div class="service-card fade-in">
                    <div class="service-icon">📊</div>
                    <h3>محاسبات مساحت</h3>
                    <p>انجام دقیق محاسبات مساحت و حجم برای پروژه‌های مختلف</p>
                </div>
                <div class="service-card fade-in">
                    <div class="service-icon">🏗️</div>
                    <h3>نظارت پروژه</h3>
                    <p>نظارت و کنترل دقیق بر اجرای پروژه‌های عمرانی و ساختمانی</p>
                </div>
                <div class="service-card fade-in">
                    <div class="service-icon">📋</div>
                    <h3>مشاوره مهندسی</h3>
                    <p>ارائه مشاوره‌های تخصصی در زمینه نقشه‌برداری و مهندسی</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section id="gallery">
        <div class="container">
            <h2 class="fade-in">گالری پروژه‌ها</h2>
            <div class="gallery-grid">
                <div class="gallery-item fade-in">
                    <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='300' height='200'><rect width='300' height='200' fill='%23667eea'/><text x='150' y='100' text-anchor='middle' dy='0.3em' fill='white' font-size='16'>نقشه‌برداری ملکی</text></svg>" alt="نقشه‌برداری ملکی">
                    <div class="gallery-overlay">
                        <h4>نقشه‌برداری ملکی دقیق</h4>
                    </div>
                </div>
                <div class="gallery-item fade-in">
                    <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='300' height='200'><rect width='300' height='200' fill='%23764ba2'/><text x='150' y='100' text-anchor='middle' dy='0.3em' fill='white' font-size='16'>نقشه توپوگرافی</text></svg>" alt="نقشه توپوگرافی">
                    <div class="gallery-overlay">
                        <h4>نقشه‌های توپوگرافی</h4>
                    </div>
                </div>
                <div class="gallery-item fade-in">
                    <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='300' height='200'><rect width='300' height='200' fill='%23ff6b6b'/><text x='150' y='100' text-anchor='middle' dy='0.3em' fill='white' font-size='16'>تجهیزات GPS</text></svg>" alt="تجهیزات GPS">
                    <div class="gallery-overlay">
                        <h4>تجهیزات مدرن GPS</h4>
                    </div>
                </div>
                <div class="gallery-item fade-in">
                    <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='300' height='200'><rect width='300' height='200' fill='%23ffa500'/><text x='150' y='100' text-anchor='middle' dy='0.3em' fill='white' font-size='16'>پروژه عمرانی</text></svg>" alt="پروژه عمرانی">
                    <div class="gallery-overlay">
                        <h4>نظارت پروژه‌های عمرانی</h4>
                    </div>
                </div>
                <div class="gallery-item fade-in">
                    <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='300' height='200'><rect width='300' height='200' fill='%2334495e'/><text x='150' y='100' text-anchor='middle' dy='0.3em' fill='white' font-size='16'>محاسبات دقیق</text></svg>" alt="محاسبات">
                    <div class="gallery-overlay">
                        <h4>محاسبات مساحت دقیق</h4>
                    </div>
                </div>
                <div class="gallery-item fade-in">
                    <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='300' height='200'><rect width='300' height='200' fill='%2327ae60'/><text x='150' y='100' text-anchor='middle' dy='0.3em' fill='white' font-size='16'>مشاوره مهندسی</text></svg>" alt="مشاوره">
                    <div class="gallery-overlay">
                        <h4>خدمات مشاوره‌ای</h4>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <div class="container">
            <h2 class="fade-in">درباره مهندس عباس کرباسی</h2>
            <div class="about-content">
                <div class="about-image fade-in">
                    <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='300' height='300'><circle cx='150' cy='150' r='140' fill='%23667eea'/><text x='150' y='160' text-anchor='middle' dy='0.3em' fill='white' font-size='24'>مهندس کرباسی</text></svg>" alt="مهندس عباس کرباسی" class="profile-img">
                </div>
                <div class="about-text fade-in">
                    <p>مهندس عباس کرباسی با بیش از ۱۵ سال تجربه در زمینه نقشه‌برداری و مهندسی نقشه، خدمات متنوع و با کیفیتی را در سراسر کشور ارائه می‌دهد.</p>
                    
                    <p>تخصص‌های اصلی ما شامل نقشه‌برداری ملکی، توپوگرافی، استفاده از تجهیزات مدرن GPS، و ارائه مشاوره‌های تخصصی می‌باشد.</p>
                    
                    <p>با استفاده از جدیدترین تکنولوژی‌ها و روش‌های علمی، ما متعهد به ارائه دقیق‌ترین و با کیفیت‌ترین خدمات به مشتریان عزیز هستیم.</p>
                    
                    <p><strong>مدارک و گواهی‌نامه‌ها:</strong></p>
                    <ul style="margin-top: 1rem; padding-right: 2rem;">
                        <li>کارشناسی ارشد مهندسی نقشه‌برداری</li>
                        <li>گواهی‌نامه کار با تجهیزات GPS</li>
                        <li>مجوز رسمی نقشه‌برداری از سازمان نظام مهندسی</li>
                        <li>گواهی‌نامه نظارت بر پروژه‌های عمرانی</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="container">
            <h2 class="fade-in">تماس با ما</h2>
            <div class="contact-form fade-in">
                <form>
                    <div class="form-group">
                        <label for="name">نام و نام خانوادگی:</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="phone">شماره تماس:</label>
                        <input type="tel" id="phone" name="phone" required>
                    </div>
                    <div class="form-group">
                        <label for="email">ایمیل:</label>
                        <input type="email" id="email" name="email">
                    </div>
                    <div class="form-group">
                        <label for="service">نوع خدمت مورد نظر:</label>
                        <select id="service" name="service" style="width: 100%; padding: 12px; border: 2px solid #e1e8ed; border-radius: 10px; font-size: 1rem;">
                            <option value="">انتخاب کنید...</option>
                            <option value="property">نقشه‌برداری ملکی</option>
                            <option value="topography">نقشه‌برداری توپوگرافی</option>
                            <option value="gps">خدمات GPS</option>
                            <option value="calculation">محاسبات مساحت</option>
                            <option value="supervision">نظارت پروژه</option>
                            <option value="consultation">مشاوره مهندسی</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="message">پیام شما:</label>
                        <textarea id="message" name="message" rows="5" placeholder="لطفاً توضیحات بیشتری از پروژه خود ارائه دهید..."></textarea>
                    </div>
                    <button type="submit" class="submit-btn">ارسال پیام</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>اطلاعات تماس</h3>
                    <p>📞 تلفن: ۰۹۱۲۳۴۵۶۷۸۹</p>
                    <p>📧 ایمیل: info@karbasi-survey.ir</p>
                    <p>📍 آدرس: تهران، خیابان ولیعصر</p>
                </div>
                <div class="footer-section">
                    <h3>خدمات سریع</h3>
                    <p>• نقشه‌برداری اضطراری</p>
                    <p>• مشاوره رایگان</p>
                    <p>• خدمات ۲۴ ساعته</p>
                </div>
                <div class="footer-section">
                    <h3>شبکه‌های اجتماعی</h3>
                    <div class="social-links">
                        <a href="#">📱</a>
                        <a href="#">📧</a>
                        <a href="#">💼</a>
                    </div>
                </div>
            </div>
            <div style="border-top: 1px solid #444; padding-top: 1rem; margin-top: 2rem;">
                <p>&copy; ۱۴۰۳ مهندس عباس کرباسی. تمامی حقوق محفوظ است.</p>
            </div>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Header background change on scroll
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(255, 255, 255, 0.98)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.95)';
            }
        });

        // Form submission
        document.querySelector('form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('پیام شما با موفقیت ارسال شد! به زودی با شما تماس خواهیم گرفت.');
        });

        // Mobile menu toggle
        const mobileMenu = document.querySelector('.mobile-menu');
        const navLinks = document.querySelector('.nav-links');

        mobileMenu.addEventListener('click', function() {
            navLinks.style.display = navLinks.style.display === 'flex' ? 'none' : 'flex';
        });

        // Gallery hover effects
        document.querySelectorAll('.gallery-item').forEach(item => {
            item.addEventListener('mouseenter', function() {
                this.style.transform = 'scale(1.05) rotateY(5deg)';
            });
            
            item.addEventListener('mouseleave', function() {
                this.style.transform = 'scale(1) rotateY(0deg)';
            });
        });

        // Service cards animation on hover
        document.querySelectorAll('.service-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-15px) scale(1.02)';
                this.style.boxShadow = '0 25px 50px rgba(0, 0, 0, 0.15)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
                this.style.boxShadow = '0 10px 30px rgba(0, 0, 0, 0.1)';
            });
        });

        // Add typing effect to hero text
        function typeWriter(element, text, speed = 100) {
            let i = 0;
            element.innerHTML = '';
            function type() {
                if (i < text.length) {
                    element.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                }
            }
            type();
        }

        // Initialize typing effect after page load
        window.addEventListener('load', function() {
            setTimeout(() => {
                const heroTitle = document.querySelector('.hero h1');
                const heroSubtitle = document.querySelector('.hero p');
                
                if (heroTitle && heroSubtitle) {
                    typeWriter(heroTitle, 'مهندس عباس کرباسی', 150);
                    setTimeout(() => {
                        typeWriter(heroSubtitle, 'متخصص نقشه‌برداری و خدمات مهندسی دقیق', 80);
                    }, 2500);
                }
            }, 1000);
        });

        // Add parallax effect to hero section
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero');
            const rate = scrolled * -0.5;
            
            if (hero) {
                hero.style.transform = `translateY(${rate}px)`;
            }
        });

        // Add counter animation for statistics (if you want to add a stats section later)
        function animateCounters() {
            const counters = document.querySelectorAll('.counter');
            counters.forEach(counter => {
                const target = parseInt(counter.getAttribute('data-target'));
                const count = parseInt(counter.innerText);
                const increment = target / 100;
                
                if (count < target) {
                    counter.innerText = Math.ceil(count + increment);
                    setTimeout(() => animateCounters(), 50);
                } else {
                    counter.innerText = target;
                }
            });
        }

        // Add floating elements animation
        function createFloatingElements() {
            const hero = document.querySelector('.hero');
            for (let i = 0; i < 6; i++) {
                const element = document.createElement('div');
                element.className = 'floating-element';
                element.style.cssText = `
                    position: absolute;
                    width: ${Math.random() * 60 + 20}px;
                    height: ${Math.random() * 60 + 20}px;
                    background: rgba(255, 255, 255, 0.1);
                    border-radius: 50%;
                    top: ${Math.random() * 100}%;
                    left: ${Math.random() * 100}%;
                    animation: float ${Math.random() * 10 + 10}s ease-in-out infinite;
                    z-index: 1;
                `;
                hero.appendChild(element);
            }
        }

        // Add CSS for floating animation
        const floatingCSS = `
            @keyframes float {
                0%, 100% { transform: translateY(0px) rotate(0deg); }
                33% { transform: translateY(-30px) rotate(120deg); }
                66% { transform: translateY(-60px) rotate(240deg); }
            }
        `;
        
        const style = document.createElement('style');
        style.textContent = floatingCSS;
        document.head.appendChild(style);

        // Initialize floating elements
        createFloatingElements();

        // Add loading animation
        window.addEventListener('load', function() {
            document.body.style.opacity = '0';
            document.body.style.transition = 'opacity 0.5s ease';
            
            setTimeout(() => {
                document.body.style.opacity = '1';
            }, 100);
        });

        // Add search functionality (for future use)
        function addSearchFunctionality() {
            const searchInput = document.createElement('input');
            searchInput.type = 'text';
            searchInput.placeholder = 'جستجو...';
            searchInput.style.cssText = `
                padding: 8px 12px;
                border: 2px solid #e1e8ed;
                border-radius: 20px;
                font-size: 0.9rem;
                margin-left: 1rem;
                display: none;
            `;
            
            // Add to navigation (commented out for now)
            // document.querySelector('nav .container').appendChild(searchInput);
        }

        // Add theme toggle functionality (for future dark mode)
        function addThemeToggle() {
            const themeToggle = document.createElement('button');
            themeToggle.innerHTML = '🌙';
            themeToggle.style.cssText = `
                background: none;
                border: none;
                font-size: 1.5rem;
                cursor: pointer;
                padding: 0.5rem;
                border-radius: 50%;
                transition: all 0.3s ease;
            `;
            
            themeToggle.addEventListener('click', function() {
                document.body.classList.toggle('dark-theme');
                this.innerHTML = document.body.classList.contains('dark-theme') ? '☀️' : '🌙';
            });
            
            // Add to navigation (commented out for now)
            // document.querySelector('nav .container').appendChild(themeToggle);
        }

        // Add scroll to top button
        const scrollTopBtn = document.createElement('button');
        scrollTopBtn.innerHTML = '↑';
        scrollTopBtn.style.cssText = `
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border: none;
            border-radius: 50%;
            font-size: 1.5rem;
            cursor: pointer;
            box-shadow: 0 4px 20px rgba(102, 126, 234, 0.3);
            transition: all 0.3s ease;
            opacity: 0;
            visibility: hidden;
            z-index: 1000;
        `;

        scrollTopBtn.addEventListener('click', function() {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });

        document.body.appendChild(scrollTopBtn);

        // Show/hide scroll to top button
        window.addEventListener('scroll', function() {
            if (window.scrollY > 300) {
                scrollTopBtn.style.opacity = '1';
                scrollTopBtn.style.visibility = 'visible';
            } else {
                scrollTopBtn.style.opacity = '0';
                scrollTopBtn.style.visibility = 'hidden';
            }
        });

        // Add contact form validation
        function validateForm() {
            const form = document.querySelector('form');
            const inputs = form.querySelectorAll('input[required], select[required], textarea[required]');
            
            inputs.forEach(input => {
                input.addEventListener('blur', function() {
                    if (!this.value.trim()) {
                        this.style.borderColor = '#e74c3c';
                        this.style.boxShadow = '0 0 5px rgba(231, 76, 60, 0.3)';
                    } else {
                        this.style.borderColor = '#27ae60';
                        this.style.boxShadow = '0 0 5px rgba(39, 174, 96, 0.3)';
                    }
                });
            });
        }

        validateForm();

        console.log('وبسایت مهندس عباس کرباسی با موفقیت بارگذاری شد! 🎉');
    </script>
</html><www class="abbas com"></www>
</body>
