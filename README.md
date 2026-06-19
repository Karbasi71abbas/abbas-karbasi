<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>مهندسی نقشه‌برداری و GIS - عباس کرباسی</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;700&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'Vazirmatn', Tahoma, Arial, sans-serif;
    background: #F4F7FB;
    color: #1a1a2e;
    direction: rtl;
  }

  header {
    background: white;
    border-bottom: 1px solid #e3eaf5;
    padding: 1rem 2rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: sticky;
    top: 0;
    z-index: 100;
  }

  .logo {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 16px;
    font-weight: 700;
    color: #1565C0;
  }

  .logo-icon {
    width: 38px;
    height: 38px;
    background: #1565C0;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  nav a {
    color: #444;
    text-decoration: none;
    font-size: 14px;
    margin-right: 1.5rem;
  }

  nav a:hover { color: #1565C0; }

  .hero {
    background: linear-gradient(135deg, #0D47A1 0%, #1565C0 50%, #1976D2 100%);
    color: white;
    padding: 5rem 2rem;
    text-align: center;
  }

  .hero-badge {
    display: inline-block;
    background: rgba(255,255,255,0.15);
    border: 1px solid rgba(255,255,255,0.3);
    padding: 6px 18px;
    border-radius: 20px;
    font-size: 12px;
    letter-spacing: 2px;
    margin-bottom: 1.5rem;
  }

  .hero h1 {
    font-size: 36px;
    font-weight: 700;
    margin-bottom: 1rem;
    line-height: 1.5;
  }

  .hero p {
    font-size: 16px;
    opacity: 0.9;
    margin-bottom: 2rem;
    line-height: 1.9;
    max-width: 550px;
    margin-left: auto;
    margin-right: auto;
  }

  .hero-btns { display: flex; gap: 12px; justify-content: center; flex-wrap: wrap; }

  .btn-white {
    background: white;
    color: #1565C0;
    border: none;
    padding: 12px 32px;
    border-radius: 28px;
    font-size: 15px;
    font-weight: 500;
    cursor: pointer;
    font-family: inherit;
    text-decoration: none;
    display: inline-block;
  }

  .btn-outline {
    background: transparent;
    color: white;
    border: 1.5px solid rgba(255,255,255,0.6);
    padding: 12px 32px;
    border-radius: 28px;
    font-size: 15px;
    font-weight: 500;
    cursor: pointer;
    font-family: inherit;
    text-decoration: none;
    display: inline-block;
  }

  .section { padding: 4rem 2rem; max-width: 1000px; margin: 0 auto; }

  .section-label {
    font-size: 12px;
    color: #1976D2;
    letter-spacing: 2px;
    text-align: center;
    margin-bottom: 0.5rem;
    font-weight: 500;
  }

  .section-title {
    font-size: 24px;
    font-weight: 700;
    color: #1a1a2e;
    text-align: center;
    margin-bottom: 0.75rem;
  }

  .section-sub {
    font-size: 14px;
    color: #666;
    text-align: center;
    margin-bottom: 2.5rem;
    line-height: 1.8;
  }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 16px;
  }

  .service-card {
    background: white;
    border: 1px solid #e3eaf5;
    border-radius: 14px;
    padding: 1.5rem 1.25rem;
    text-align: center;
    transition: transform 0.2s, box-shadow 0.2s;
  }

  .service-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 8px 24px rgba(21,101,192,0.12);
  }

  .service-icon {
    width: 56px;
    height: 56px;
    background: #E3F2FD;
    border-radius: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 1rem;
    font-size: 26px;
  }

  .service-card h3 {
    font-size: 14px;
    font-weight: 700;
    color: #1a1a2e;
    margin-bottom: 0.5rem;
  }

  .service-card p {
    font-size: 12px;
    color: #666;
    line-height: 1.7;
  }

  .about-section {
    background: white;
    border-top: 1px solid #e3eaf5;
    border-bottom: 1px solid #e3eaf5;
  }

  .about-inner {
    max-width: 1000px;
    margin: 0 auto;
    padding: 4rem 2rem;
    display: flex;
    gap: 3rem;
    align-items: center;
    flex-wrap: wrap;
  }

  .about-avatar {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    background: linear-gradient(135deg, #1565C0, #42A5F5);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    font-size: 50px;
    color: white;
  }

  .about-text { flex: 1; min-width: 260px; }

  .about-text h2 {
    font-size: 22px;
    font-weight: 700;
    color: #1a1a2e;
    margin-bottom: 0.25rem;
  }

  .about-title-sub {
    font-size: 13px;
    color: #1976D2;
    font-weight: 500;
    margin-bottom: 1rem;
  }

  .about-text p {
    font-size: 14px;
    color: #555;
    line-height: 1.9;
  }

  .stats {
    display: flex;
    gap: 2rem;
    margin-top: 1.5rem;
    flex-wrap: wrap;
  }

  .stat { text-align: center; }
  .stat-num { font-size: 28px; font-weight: 700; color: #1565C0; }
  .stat-label { font-size: 12px; color: #888; margin-top: 2px; }

  .contact-section { background: #F4F7FB; }

  .contact-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 16px;
    margin-top: 0;
  }

  .contact-card {
    background: white;
    border: 1px solid #e3eaf5;
    border-radius: 14px;
    padding: 1.5rem;
    display: flex;
    align-items: center;
    gap: 1rem;
  }

  .contact-icon {
    width: 48px;
    height: 48px;
    background: #E3F2FD;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
    flex-shrink: 0;
  }

  .contact-info label {
    font-size: 11px;
    color: #999;
    display: block;
    margin-bottom: 4px;
  }

  .contact-info a, .contact-info span {
    font-size: 14px;
    font-weight: 500;
    color: #1565C0;
    text-decoration: none;
    word-break: break-all;
  }

  .cta-section {
    background: linear-gradient(135deg, #0D47A1, #1976D2);
    color: white;
    text-align: center;
    padding: 4rem 2rem;
  }

  .cta-section h2 { font-size: 26px; font-weight: 700; margin-bottom: 0.75rem; }
  .cta-section p { font-size: 15px; opacity: 0.85; margin-bottom: 2rem; line-height: 1.8; }

  footer {
    background: #0D47A1;
    color: rgba(255,255,255,0.6);
    text-align: center;
    padding: 1.5rem;
    font-size: 12px;
  }

  @media (max-width: 600px) {
    .hero h1 { font-size: 24px; }
    nav { display: none; }
    .about-inner { flex-direction: column; text-align: center; }
  }
</style>
</head>
<body>

<header>
  <div class="logo">
    <div class="logo-icon">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <polygon points="3 6 9 3 15 6 21 3 21 18 15 21 9 18 3 21"/>
        <line x1="9" y1="3" x2="9" y2="18"/>
        <line x1="15" y1="6" x2="15" y2="21"/>
      </svg>
    </div>
    GIS کرباسی
  </div>
  <nav>
    <a href="#services">خدمات</a>
    <a href="#about">درباره ما</a>
    <a href="#contact">تماس</a>
  </nav>
</header>

<section class="hero">
  <div class="hero-badge">GIS · نقشه‌برداری · عکس‌های هوایی</div>
  <h1>مهندسی نقشه‌برداری<br>و خدمات GIS</h1>
  <p>ارائه خدمات تخصصی نقشه‌برداری زمینی، نرم‌افزارهای GIS<br>و تهیه عکس‌های هوایی قدیمی با دقت و کیفیت بالا</p>
  <div class="hero-btns">
    <a href="#contact" class="btn-white">تماس با ما</a>
    <a href="#services" class="btn-outline">مشاهده خدمات</a>
  </div>
</section>

<div id="services">
<div class="section">
  <p class="section-label">SERVICES</p>
  <h2 class="section-title">خدمات ما</h2>
  <p class="section-sub">طیف گسترده‌ای از خدمات تخصصی نقشه‌برداری و GIS برای پروژه‌های شما</p>
  <div class="services-grid">
    <div class="service-card">
      <div class="service-icon">🗺️</div>
      <h3>نقشه‌برداری زمینی</h3>
      <p>برداشت دقیق زمینی با تجهیزات مدرن و استانداردهای روز</p>
    </div>
    <div class="service-card">
      <div class="service-icon">💻</div>
      <h3>نرم‌افزارهای GIS</h3>
      <p>پردازش، تحلیل و مدیریت داده‌های مکانی و جغرافیایی</p>
    </div>
    <div class="service-card">
      <div class="service-icon">📷</div>
      <h3>عکس‌های هوایی قدیمی</h3>
      <p>تهیه، بازیابی و ارائه تصاویر هوایی تاریخی و آرشیوی</p>
    </div>
    <div class="service-card">
      <div class="service-icon">📐</div>
      <h3>نقشه کاداستر</h3>
      <p>تعیین حدود، مساحت و تهیه نقشه‌های ثبتی اراضی</p>
    </div>
    <div class="service-card">
      <div class="service-icon">📡</div>
      <h3>سیستم‌های GPS</h3>
      <p>مختصات‌گیری دقیق و پیاده‌سازی نقشه در زمین</p>
    </div>
    <div class="service-card">
      <div class="service-icon">📋</div>
      <h3>گزارش‌های فنی</h3>
      <p>مستندسازی، تهیه و ارائه گزارش‌های تخصصی مهندسی</p>
    </div>
  </div>
</div>
</div>

<div id="about" class="about-section">
  <div class="about-inner">
    <div class="about-avatar">👷</div>
    <div class="about-text">
      <h2>عباس کرباسی</h2>
      <p class="about-title-sub">مهندس نقشه‌برداری و متخصص GIS</p>
      <p>با سال‌ها تجربه در حوزه نقشه‌برداری، سیستم‌های اطلاعات جغرافیایی (GIS) و تهیه عکس‌های هوایی قدیمی، آماده ارائه خدمات تخصصی به افراد، شرکت‌ها و سازمان‌های دولتی و خصوصی هستم. دقت، سرعت و کیفیت از اصول اساسی کار ماست.</p>
      <div class="stats">
        <div class="stat">
          <div class="stat-num">+۱۰۰</div>
          <div class="stat-label">پروژه اجرا شده</div>
        </div>
        <div class="stat">
          <div class="stat-num">+۱۵</div>
          <div class="stat-label">سال تجربه</div>
        </div>
        <div class="stat">
          <div class="stat-num">۱۰۰٪</div>
          <div class="stat-label">رضایت مشتری</div>
        </div>
      </div>
    </div>
  </div>
</div>

<div id="contact" class="contact-section">
<div class="section">
  <p class="section-label">CONTACT</p>
  <h2 class="section-title">تماس با ما</h2>
  <p class="section-sub">برای مشاوره رایگان و استعلام قیمت با ما در تماس باشید</p>
  <div class="contact-grid">
    <div class="contact-card">
      <div class="contact-icon">📞</div>
      <div class="contact-info">
        <label>شماره تماس</label>
        <a href="tel:+989172947239">۰۹۱۷۲۹۴۷۲۳۹</a>
      </div>
    </div>
    <div class="contact-card">
      <div class="contact-icon">✉️</div>
      <div class="contact-info">
        <label>ایمیل</label>
        <a href="mailto:abbas.karbasi.gis@gmail.com">abbas.karbasi.gis@gmail.com</a>
      </div>
    </div>
    <div class="contact-card">
      <div class="contact-icon">🎓</div>
      <div class="contact-info">
        <label>تخصص</label>
        <span>مهندسی نقشه‌برداری و GIS</span>
      </div>
    </div>
  </div>
</div>
</div>

<section class="cta-section">
  <h2>برای پروژه خود آماده‌اید؟</h2>
  <p>همین حالا با ما تماس بگیرید و مشاوره رایگان دریافت کنید</p>
  <a href="tel:+989172947239" class="btn-white">تماس بگیرید</a>
</section>

<footer>
  © ۱۴۰۳ مهندسی نقشه‌برداری و GIS - عباس کرباسی | تمامی حقوق محفوظ است
</footer>

</body>
</html>
