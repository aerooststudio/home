<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="AEROOST STUDIO | توسعه بازی و نرم‌افزار با هوش مصنوعی">
    <title>AEROOST STUDIO | استودیوی خلاق دیجیتال</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&family=Vazirmatn:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Vazirmatn', 'Inter', sans-serif;
            transition: background-color 0.4s ease, color 0.3s ease;
            line-height: 1.6;
        }

        /* ========== رنگ‌های لوگو ========== */
        :root {
            --cyan: #2EC1DE;
            --purple: #7B2CBF;
            --gradient: linear-gradient(135deg, #2EC1DE 0%, #7B2CBF 100%);
            --silver: linear-gradient(145deg, #E5E7EB 0%, #9CA3AF 100%);
        }

        /* ========== تم روشن ========== */
        body.light {
            --bg: #FFFFFF;
            --bg-card: #FFFFFF;
            --text: #0F172A;
            --text-muted: #475569;
            --border: #E2E8F0;
            --shadow: 0 4px 20px rgba(0,0,0,0.03);
            --shadow-hover: 0 20px 35px -12px rgba(0,0,0,0.08);
        }

        /* ========== تم تاریک ========== */
        body.dark {
            --bg: #0A0A0A;
            --bg-card: #1A1A2A;
            --text: #F8FAFC;
            --text-muted: #CBD5E1;
            --border: #2A2A3A;
            --shadow: 0 4px 20px rgba(0,0,0,0.3);
            --shadow-hover: 0 20px 35px -12px rgba(0,0,0,0.5);
        }

        body {
            background: var(--bg);
            color: var(--text);
        }

        /* ========== انیمیشن‌ها ========== */
        @keyframes fadeUp {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        @keyframes scaleIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }
        @keyframes float {
            0%,100% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
        }
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .fade-up { opacity: 0; transform: translateY(50px); transition: all 0.8s cubic-bezier(0.2,0.9,0.4,1.1); }
        .fade-up.visible { opacity: 1; transform: translateY(0); }
        .fade-in { opacity: 0; transition: opacity 0.7s ease; }
        .fade-in.visible { opacity: 1; }
        .scale-in { opacity: 0; transform: scale(0.9); transition: all 0.6s ease; }
        .scale-in.visible { opacity: 1; transform: scale(1); }

        /* ========== هدر ========== */
        .header {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(var(--bg-rgb), 0.85);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--border);
            padding: 1rem 0;
            transition: all 0.3s;
        }
        body.light { --bg-rgb: 255,255,255; }
        body.dark { --bg-rgb: 10,10,10; }
        .header.scrolled { padding: 0.7rem 0; }

        .container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .header-inner {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }

        /* لوگو */
        .logo {
            display: flex;
            align-items: center;
            gap: 1rem;
        }
        .logo img {
            height: 110px;
            width: auto;
            border-radius: 16px;
            transition: transform 0.3s;
        }
        .logo img:hover {
            transform: scale(1.03);
        }
        .logo-text .main {
            font-size: 1.6rem;
            font-weight: 800;
            background: var(--silver);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .logo-text .sub {
            font-size: 0.7rem;
            color: #9CA3AF;
        }

        .nav {
            display: flex;
            gap: 0.3rem;
            flex-wrap: wrap;
        }
        .nav-link {
            padding: 0.55rem 1.3rem;
            font-size: 0.85rem;
            font-weight: 500;
            color: var(--text-muted);
            border-radius: 2rem;
            text-decoration: none;
            transition: 0.25s;
        }
        .nav-link:hover {
            background: rgba(46,193,222,0.1);
            color: var(--cyan);
        }
        .nav-link.active {
            background: var(--gradient);
            color: #0A0A0A;
            font-weight: 600;
        }

        .theme-btn {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 2rem;
            padding: 0.45rem 1rem;
            cursor: pointer;
            display: flex;
            gap: 0.6rem;
            transition: 0.3s;
        }
        .theme-btn:hover {
            border-color: var(--cyan);
            transform: scale(1.02);
        }
        .theme-btn i {
            font-size: 0.85rem;
            color: var(--text-muted);
        }

        /* ========== Hero ========== */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding-top: 5rem;
            background: var(--bg);
        }
        .hero-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }
        .hero-badge {
            display: inline-block;
            background: linear-gradient(135deg, rgba(46,193,222,0.15), rgba(123,44,191,0.15));
            color: var(--cyan);
            padding: 0.3rem 1.2rem;
            border-radius: 2rem;
            font-size: 0.7rem;
            font-weight: 600;
            margin-bottom: 1.5rem;
            border: 1px solid rgba(46,193,222,0.25);
            animation: pulse 2s infinite;
        }
        .hero h1 {
            font-size: 4rem;
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 1.2rem;
        }
        .hero h1 span {
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .hero-desc {
            font-size: 1rem;
            color: var(--text-muted);
            margin-bottom: 2rem;
            line-height: 1.8;
        }
        .hero-highlight {
            background: linear-gradient(135deg, rgba(46,193,222,0.15), rgba(123,44,191,0.15));
            padding: 0.15rem 0.5rem;
            border-radius: 0.4rem;
            font-weight: 600;
            color: var(--cyan);
        }
        .hero-buttons {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            margin-bottom: 2rem;
        }
        .btn-primary {
            background: var(--gradient);
            color: #0A0A0A;
            padding: 1rem 2.2rem;
            border-radius: 3rem;
            font-weight: 700;
            font-size: 0.95rem;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 0.6rem;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }
        .btn-primary::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
        }
        .btn-primary:hover::before { left: 100%; }
        .btn-primary:hover { transform: translateY(-3px); box-shadow: 0 0 25px rgba(46,193,222,0.4); }
        
        .btn-outline {
            border: 1.5px solid var(--border);
            background: transparent;
            color: var(--text);
            padding: 1rem 2.2rem;
            border-radius: 3rem;
            font-weight: 600;
            font-size: 0.95rem;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 0.6rem;
            transition: all 0.3s;
            cursor: pointer;
        }
        .btn-outline:hover { border-color: var(--cyan); color: var(--cyan); transform: translateY(-3px); box-shadow: 0 5px 20px rgba(46,193,222,0.2); }
        
        .hero-stats {
            display: flex;
            gap: 3rem;
        }
        .hero-stats div h4 {
            font-size: 2rem;
            font-weight: 800;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .hero-stats div p {
            font-size: 0.85rem;
            color: var(--text-muted);
        }
        .hero-image i {
            font-size: 10rem;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: float 5s ease-in-out infinite;
        }

        /* ========== بخش‌ها ========== */
        .section {
            padding: 5rem 0;
        }
        .section-title {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 2.5rem;
            position: relative;
        }
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -12px;
            right: 0;
            width: 60px;
            height: 3px;
            background: var(--gradient);
            border-radius: 3px;
        }

        .grid-3, .grid-4, .grid-2 {
            display: grid;
            gap: 1.8rem;
        }
        .grid-3 { grid-template-columns: repeat(auto-fit, minmax(310px, 1fr)); }
        .grid-4 { grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); }
        .grid-2 { grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); }

        /* کارت‌ها */
        .card, .project-card, .skill-card, .faq-card, .blog-card {
            background: var(--bg-card);
            border-radius: 1.5rem;
            padding: 2rem;
            border: 1px solid var(--border);
            transition: all 0.4s cubic-bezier(0.2,0.9,0.4,1.1);
            box-shadow: var(--shadow);
        }
        .card:hover, .project-card:hover, .skill-card:hover, .faq-card:hover, .blog-card:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-hover);
            border-color: var(--cyan);
        }
        .card-icon {
            font-size: 2.5rem;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 1rem;
        }
        .card h3, .blog-card h3 {
            font-size: 1.3rem;
            margin-bottom: 0.75rem;
        }
        .card p, .blog-card p {
            color: var(--text-muted);
            font-size: 0.9rem;
            line-height: 1.7;
        }
        .blog-meta {
            font-size: 0.7rem;
            color: var(--cyan);
            margin-top: 1rem;
            display: flex;
            gap: 1rem;
        }
        .read-more {
            display: inline-block;
            margin-top: 1rem;
            color: var(--cyan);
            text-decoration: none;
            font-weight: 600;
            font-size: 0.85rem;
            transition: 0.2s;
        }
        .read-more:hover { transform: translateX(-5px); display: inline-block; }

        .project-status {
            display: inline-block;
            font-size: 0.7rem;
            padding: 0.25rem 1rem;
            border-radius: 2rem;
            margin-top: 1rem;
        }
        .status-done {
            background: rgba(46,193,222,0.15);
            color: var(--cyan);
            border: 1px solid rgba(46,193,222,0.3);
        }
        .status-building {
            background: rgba(123,44,191,0.15);
            color: var(--purple);
            border: 1px solid rgba(123,44,191,0.3);
        }

        .skill-card {
            text-align: center;
        }
        .skill-card i {
            font-size: 2.5rem;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 1rem;
            display: inline-block;
        }
        .skill-card h3 { font-size: 1.1rem; margin-bottom: 0.5rem; }
        .skill-card p { font-size: 0.8rem; color: var(--text-muted); }

        /* فرآیند کاری */
        .process-steps {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 1.5rem;
        }
        .process-step {
            flex: 1;
            text-align: center;
            padding: 2rem;
            background: var(--bg-card);
            border-radius: 1.5rem;
            border: 1px solid var(--border);
            transition: 0.3s;
        }
        .process-step:hover {
            transform: translateY(-5px);
            border-color: var(--cyan);
        }
        .step-number {
            width: 55px;
            height: 55px;
            background: var(--gradient);
            color: #0A0A0A;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1rem;
            font-size: 1.4rem;
            font-weight: 800;
        }
        .process-step h3 { font-size: 1.2rem; margin-bottom: 0.5rem; }
        .process-step p { font-size: 0.85rem; color: var(--text-muted); line-height: 1.7; }

        .products-showcase {
            background: var(--bg-card);
            border-radius: 1.5rem;
            padding: 2.5rem;
            border: 1px solid var(--border);
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            justify-content: space-between;
            align-items: center;
        }
        .products-showcase .badge {
            background: var(--gradient);
            color: #0A0A0A;
            padding: 0.2rem 1rem;
            border-radius: 2rem;
            font-size: 0.7rem;
            font-weight: 700;
            display: inline-block;
            margin-bottom: 1rem;
        }

        .faq-item {
            background: var(--bg-card);
            border-radius: 1rem;
            border: 1px solid var(--border);
            margin-bottom: 1rem;
            overflow: hidden;
            transition: 0.2s;
        }
        .faq-question {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.2rem 1.5rem;
            cursor: pointer;
            font-weight: 700;
            transition: 0.2s;
        }
        .faq-question:hover { background: rgba(46,193,222,0.05); }
        .faq-question i { color: var(--cyan); transition: transform 0.3s; }
        .faq-answer {
            max-height: 0;
            padding: 0 1.5rem;
            overflow: hidden;
            transition: max-height 0.3s ease, padding 0.3s ease;
            color: var(--text-muted);
            font-size: 0.9rem;
            line-height: 1.7;
        }
        .faq-item.active .faq-answer {
            max-height: 200px;
            padding: 0 1.5rem 1.2rem 1.5rem;
        }
        .faq-item.active .faq-question i { transform: rotate(180deg); }

        /* CTA */
        .cta {
            background: linear-gradient(135deg, rgba(46,193,222,0.12), rgba(123,44,191,0.12));
            border: 1px solid rgba(46,193,222,0.3);
            border-radius: 2rem;
            padding: 4rem;
            text-align: center;
            transition: all 0.3s;
        }
        .cta:hover {
            border-color: rgba(46,193,222,0.6);
            transform: scale(1.01);
        }
        .cta h3 {
            font-size: 2rem;
            margin-bottom: 0.8rem;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .cta p {
            font-size: 1.1rem;
            color: var(--text-muted);
            margin-bottom: 0.5rem;
        }
        .cta .btn-white {
            background: var(--gradient);
            color: #0A0A0A;
            padding: 1rem 2.5rem;
            border-radius: 3rem;
            font-weight: 700;
            font-size: 1rem;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 0.6rem;
            margin-top: 1.5rem;
            transition: all 0.3s;
        }
        .cta .btn-white:hover {
            transform: translateY(-3px);
            box-shadow: 0 0 30px rgba(46,193,222,0.4);
            gap: 0.8rem;
        }

        /* فوتر */
        footer {
            text-align: center;
            padding: 3rem;
            border-top: 1px solid var(--border);
            color: var(--text-muted);
            font-size: 0.85rem;
        }
        .footer-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
            margin-top: 1rem;
        }
        .footer-links a {
            color: var(--text-muted);
            text-decoration: none;
            transition: 0.2s;
        }
        .footer-links a:hover { color: var(--cyan); transform: translateY(-2px); display: inline-block; }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            flex-wrap: wrap;
            margin-top: 1.5rem;
        }
        .social-links a {
            color: var(--text-muted);
            font-size: 1rem;
            text-decoration: none;
            transition: all 0.3s;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.5rem 1.2rem;
            border-radius: 2rem;
            background: rgba(46,193,222,0.1);
            border: 1px solid rgba(46,193,222,0.2);
        }
        .social-links a:hover {
            color: var(--cyan);
            border-color: var(--cyan);
            transform: translateY(-3px);
            gap: 0.7rem;
        }

        .copyright {
            margin-top: 1.5rem;
            padding-top: 1rem;
            border-top: 1px solid var(--border);
            font-size: 0.75rem;
        }

        .view-all {
            text-align: center;
            margin-top: 2rem;
        }

        @media (max-width: 900px) {
            .hero-grid { grid-template-columns: 1fr; text-align: center; gap: 2rem; }
            .hero-stats { justify-content: center; }
            .hero h1 { font-size: 2.5rem; }
            .section-title::after { right: 50%; transform: translateX(50%); width: 60px; }
            .section-title { text-align: center; }
            .process-steps { flex-direction: column; }
            .logo img { height: 55px; }
        }
        @media (max-width: 768px) {
            .container { padding: 0 1.2rem; }
            .header-inner { flex-direction: column; }
            .hero-image i { font-size: 5rem; }
            .products-showcase { flex-direction: column; text-align: center; }
            .cta { padding: 2rem; }
            .cta h3 { font-size: 1.4rem; }
        }
    </style>
</head>
<body class="dark">
    <header class="header">
        <div class="container header-inner">
            <div class="logo">
                <img src="image.png" alt="AEROOST STUDIO Logo" onerror="this.style.display='none';">
                <div class="logo-text">
                    <div class="main">AEROOST</div>
                    <div class="sub">STUDIO</div>
                </div>
            </div>
            <div class="nav">
                <a href="#" class="nav-link active">خانه</a>
                <a href="#" class="nav-link">خدمات</a>
                <a href="#" class="nav-link">بازی‌ها و برنامه‌ها</a>
                <a href="#" class="nav-link">وبلاگ</a>
                <a href="#" class="nav-link">تماس</a>
                <a href="#" class="nav-link">درباره</a>
            </div>
            <button class="theme-btn" id="themeToggle">
                <i class="fas fa-sun"></i>
                <i class="fas fa-moon"></i>
            </button>
        </div>
    </header>

    <main>
        <div class="container">
            <!-- Hero -->
            <section class="hero">
                <div class="hero-grid">
                    <div class="fade-up">
                        <span class="hero-badge">✨ AI-POWERED STUDIO</span>
                        <h1><span>AEROOST</span> STUDIO</h1>
                        <p class="hero-desc">
                            <span class="hero-highlight">توسعه بازی</span> · <span class="hero-highlight">نرم‌افزار سفارشی</span> · <span class="hero-highlight">اپلیکیشن موبایل</span> · <span class="hero-highlight">هوش مصنوعی</span>
                        </p>
                        <div class="hero-buttons">
                            <a href="#" class="btn-primary"><i class="fas fa-arrow-left"></i> مشاهده محصولات</a>
                            <a href="#" class="btn-outline"><i class="fas fa-cog"></i> مشاهده خدمات</a>
                        </div>
                        <div class="hero-stats">
                            <div><h4>۲+</h4><p>سال تجربه</p></div>
                            <div><h4>۱۰+</h4><p>پروژه انجام شده</p></div>
                        </div>
                    </div>
                    <div class="hero-image">
                        <i class="fas fa-microchip"></i>
                    </div>
                </div>
            </section>

            <!-- خدمات من -->
            <section class="section">
                <h2 class="section-title fade-up">خدمات من</h2>
                <div class="grid-3">
                    <div class="card scale-in"><div class="card-icon"><i class="fas fa-gamepad"></i></div><h3>توسعه بازی حرفه‌ای</h3><p>طراحی و ساخت بازی‌های موبایل و کامپیوتر با گرافیک بالا، گیم‌پلی روان و بهینه‌سازی شده برای تمام پلتفرم‌ها</p></div>
                    <div class="card scale-in"><div class="card-icon"><i class="fas fa-laptop-code"></i></div><h3>نرم‌افزار سفارشی</h3><p>توسعه پنل‌های مدیریت حرفه‌ای، داشبوردهای تحلیلی و سیستم‌های تحت وب با معماری مدرن و امنیت بالا</p></div>
                    <div class="card scale-in"><div class="card-icon"><i class="fas fa-brain"></i></div><h3>هوش مصنوعی و چت‌بات</h3><p>ساخت چت‌بات‌های هوشمند، سیستم‌های پیشنهاددهنده و یکپارچه‌سازی مدل‌های زبانی پیشرفته در پروژه‌ها</p></div>
                    <div class="card scale-in"><div class="card-icon"><i class="fas fa-music"></i></div><h3>اپلیکیشن پخش آهنگ</h3><p>طراحی پلیرهای حرفه‌ای موسیقی با امکانات پیشرفته مانند پخش آفلاین، لیست‌های هوشمند و یکپارچه‌سازی با سرویس‌های مختلف</p></div>
                    <div class="card scale-in"><div class="card-icon"><i class="fas fa-video"></i></div><h3>ویرایشگر ویدیو</h3><p>توسعه ابزارهای ویرایش ویدیو با قابلیت‌های برش، ادغام، افزودن افکت، زیرنویس و خروجی با کیفیت بالا</p></div>
                    <div class="card scale-in"><div class="card-icon"><i class="fas fa-image"></i></div><h3>ویرایشگر عکس</h3><p>ساخت اپلیکیشن‌های ویرایش عکس حرفه‌ای با فیلترهای متنوع، ابزارهای تنظیم رنگ، افکت‌های ویژه و پردازش هوشمند</p></div>
                </div>
            </section>

            <!-- پروژه‌ها -->
            <section class="section">
                <h2 class="section-title fade-up">پروژه‌های من</h2>
                <div class="grid-2">
                    <div class="project-card scale-in"><i class="fas fa-th" style="font-size:2rem; color:var(--cyan); margin-bottom:1rem;"></i><h3>بازی ۲۰۴۸ حرفه‌ای</h3><p>بازی معمایی و فکری با گرافیک مدرن، انیمیشن‌های روان و گیم‌پلی اعتیادآور</p><span class="project-status status-done">✓ تکمیل شده</span></div>
                    <div class="project-card scale-in"><i class="fas fa-comment-dots" style="font-size:2rem; color:var(--cyan); margin-bottom:1rem;"></i><h3>چت‌بات هوش مصنوعی</h3><p>سیستم پاسخگوی هوشمند با قابلیت پردازش زبان طبیعی و یادگیری از تعاملات</p><span class="project-status status-done">✓ تکمیل شده</span></div>
                    <div class="project-card scale-in"><i class="fas fa-tachometer-alt" style="font-size:2rem; color:var(--cyan); margin-bottom:1rem;"></i><h3>سایت پنل مدیریت</h3><p>داشبورد مدیریت کامل با نمودارهای تعاملی و گزارش‌گیری پیشرفته</p><span class="project-status status-done">✓ تکمیل شده</span></div>
                    <div class="project-card scale-in"><i class="fas fa-music" style="font-size:2rem; color:var(--cyan); margin-bottom:1rem;"></i><h3>برنامه پخش آهنگ</h3><p>پلیر حرفه‌ای موسیقی با امکانات پیشرفته و رابط کاربری زیبا</p><span class="project-status status-done">✓ تکمیل شده</span></div>
                    <div class="project-card scale-in"><i class="fas fa-video" style="font-size:2rem; color:var(--cyan); margin-bottom:1rem;"></i><h3>ویرایشگر ویدیو</h3><p>ابزار ویرایش ویدیو با قابلیت‌های حرفه‌ای و خروجی با کیفیت بالا</p><span class="project-status status-done">✓ تکمیل شده</span></div>
                    <div class="project-card scale-in"><i class="fas fa-image" style="font-size:2rem; color:var(--cyan); margin-bottom:1rem;"></i><h3>ویرایشگر عکس</h3><p>اپلیکیشن ویرایش عکس با فیلترهای متنوع و ابزارهای حرفه‌ای</p><span class="project-status status-done">✓ تکمیل شده</span></div>
                    <div class="project-card scale-in"><i class="fas fa-puzzle-piece" style="font-size:2rem; color:var(--purple); margin-bottom:1rem;"></i><h3>بازی کلمه‌یار</h3><p>بازی فکری حدس کلمه با هوش مصنوعی، سطوح مختلف و بیش از ۳۰۰۰ کلمه</p><span class="project-status status-building">⚡ در حال ساخت</span></div>
                </div>
            </section>

            <!-- تکنولوژی‌های من -->
            <section class="section">
                <h2 class="section-title fade-up">تکنولوژی‌های من</h2>
                <div class="grid-4">
                    <div class="skill-card scale-in"><i class="fab fa-unity"></i><h3>Unity</h3><p>توسعه بازی‌های دوبعدی و سه‌بعدی حرفه‌ای</p></div>
                    <div class="skill-card scale-in"><i class="fab fa-python"></i><h3>Python</h3><p>هوش مصنوعی، یادگیری ماشین و بک‌اند</p></div>
                    <div class="skill-card scale-in"><i class="fab fa-js"></i><h3>JavaScript</h3><p>توسعه وب پویا و تعاملی</p></div>
                    <div class="skill-card scale-in"><i class="fab fa-react"></i><h3>React</h3><p>ساخت رابط‌های کاربری مدرن و سریع</p></div>
                    <div class="skill-card scale-in"><i class="fas fa-mobile-alt"></i><h3>Flutter</h3><p>توسعه اپلیکیشن‌های چندسکویی</p></div>
                    <div class="skill-card scale-in"><i class="fas fa-robot"></i><h3>OpenAI API</h3><p>یکپارچه‌سازی هوش مصنوعی پیشرفته</p></div>
                    <div class="skill-card scale-in"><i class="fas fa-database"></i><h3>AI & ML</h3><p>مدل‌های زبانی و یادگیری ماشین</p></div>
                    <div class="skill-card scale-in"><i class="fas fa-code"></i><h3>C# / C++</h3><p>برنامه‌نویسی سطح بالا و بهینه</p></div>
                </div>
            </section>

            <!-- چطور کار می‌کنم؟ -->
            <section class="section">
                <h2 class="section-title fade-up">چطور با هم کار می‌کنیم؟</h2>
                <div class="process-steps">
                    <div class="process-step fade-up"><div class="step-number">۱</div><h3>گفتگو و ایده‌پردازی</h3><p>در این مرحله، ایده شما را با دقت گوش می‌دهم، نیازها را تحلیل می‌کنم و بهترین مسیر برای اجرای پروژه را مشخص می‌کنیم. این مرحله کاملاً رایگان است.</p></div>
                    <div class="process-step fade-up"><div class="step-number">۲</div><h3>طراحی و برنامه‌ریزی</h3><p>ساختار پروژه طراحی می‌شود، معماری فنی مشخص می‌گردد و یک نقشه راه دقیق برای توسعه تهیه می‌شود تا همه چیز شفاف باشد.</p></div>
                    <div class="process-step fade-up"><div class="step-number">۳</div><h3>توسعه با هوش مصنوعی</h3><p>با استفاده از قدرتمندترین ابزارهای هوش مصنوعی، کدنویسی انجام می‌شود که باعث افزایش سرعت، کاهش خطا و کیفیت بسیار بالاتر می‌گردد.</p></div>
                    <div class="process-step fade-up"><div class="step-number">۴</div><h3>آزمایش و تحویل</h3><p>پروژه به طور کامل تست می‌شود، باگ‌ها رفع می‌گردند و در نهایت تحویل داده می‌شود. پشتیبانی ۳ ماهه نیز ارائه می‌شود.</p></div>
                </div>
            </section>

            <!-- وبلاگ -->
            <section class="section">
                <h2 class="section-title fade-up">آخرین مطالب وبلاگ</h2>
                <div class="grid-3">
                    <div class="blog-card scale-in">
                        <i class="fas fa-newspaper" style="font-size:2rem; color:var(--cyan); margin-bottom:1rem;"></i>
                        <h3>بهترین ابزارهای هوش مصنوعی برای توسعه بازی</h3>
                        <p>معرفی قدرتمندترین ابزارهای AI که فرآیند توسعه بازی را متحول می‌کنند...</p>
                        <div class="blog-meta"><span><i class="far fa-calendar"></i> ۱۵ خرداد ۱۴۰۴</span><span><i class="far fa-clock"></i> ۵ دقیقه مطالعه</span></div>
                        <a href="#" class="read-more">ادامه مطلب ←</a>
                    </div>
                    <div class="blog-card scale-in">
                        <i class="fas fa-code" style="font-size:2rem; color:var(--cyan); margin-bottom:1rem;"></i>
                        <h3>چگونه با AI یک چت‌بات حرفه‌ای بسازیم؟</h3>
                        <p>آموزش گام به گام ساخت چت‌بات هوشمند با استفاده از OpenAI API و Python...</p>
                        <div class="blog-meta"><span><i class="far fa-calendar"></i> ۸ خرداد ۱۴۰۴</span><span><i class="far fa-clock"></i> ۸ دقیقه مطالعه</span></div>
                        <a href="#" class="read-more">ادامه مطلب ←</a>
                    </div>
                    <div class="blog-card scale-in">
                        <i class="fas fa-gamepad" style="font-size:2rem; color:var(--cyan); margin-bottom:1rem;"></i>
                        <h3>معرفی موتورهای بازیسازی: Unity در مقابل Unreal</h3>
                        <p>مقایسه دو موتور قدرتمند بازیسازی و راهنمای انتخاب برای پروژه شما...</p>
                        <div class="blog-meta"><span><i class="far fa-calendar"></i> ۱ خرداد ۱۴۰۴</span><span><i class="far fa-clock"></i> ۶ دقیقه مطالعه</span></div>
                        <a href="#" class="read-more">ادامه مطلب ←</a>
                    </div>
                </div>
                <div class="view-all">
                    <a href="#" class="btn-outline"><i class="fas fa-arrow-left"></i> مشاهده همه مقالات</a>
                </div>
            </section>

            <!-- محصولات -->
            <section class="section">
                <div class="products-showcase fade-up">
                    <div>
                        <span class="badge">🔥 جدیدترین ساخته‌های من</span>
                        <h3 style="font-size:1.4rem;">بازی‌ها و برنامه‌های AEROOST</h3>
                        <p>بازی‌های فکری، اپلیکیشن‌های کاربردی و ابزارهای هوشمند</p>
                        <div style="display:flex; gap:0.5rem; margin-top:1rem; flex-wrap:wrap;">
                            <span style="background:rgba(46,193,222,0.1); padding:0.2rem 1rem; border-radius:2rem;">🎮 ۲۰۴۸</span>
                            <span style="background:rgba(46,193,222,0.1); padding:0.2rem 1rem; border-radius:2rem;">🎲 کلمه‌یار</span>
                            <span style="background:rgba(46,193,222,0.1); padding:0.2rem 1rem; border-radius:2rem;">📊 پنل مدیریت</span>
                            <span style="background:rgba(46,193,222,0.1); padding:0.2rem 1rem; border-radius:2rem;">🤖 چت‌بات</span>
                            <span style="background:rgba(46,193,222,0.1); padding:0.2rem 1rem; border-radius:2rem;">🎵 پخش آهنگ</span>
                            <span style="background:rgba(46,193,222,0.1); padding:0.2rem 1rem; border-radius:2rem;">🎬 ویرایشگر</span>
                        </div>
                    </div>
                    <i class="fas fa-cubes" style="font-size:3rem; background:var(--gradient); -webkit-background-clip:text; background-clip:text; color:transparent;"></i>
                </div>
            </section>

            <!-- سوالات متداول -->
            <section class="section">
                <h2 class="section-title fade-up">سوالات متداول</h2>
                <div class="faq-list">
                    <div class="faq-item"><div class="faq-question"><span>⏱️ زمان ساخت پروژه چقدر است؟</span><i class="fas fa-chevron-down"></i></div><div class="faq-answer">زمان بستگی به پیچیدگی پروژه دارد، اما معمولاً بین ۲ ماه تا ۸ ماه. با کمک AI فرآیند توسعه بسیار سریع‌تر از روش‌های سنتی است.</div></div>
                    <div class="faq-item"><div class="faq-question"><span>💰 هزینه خدمات چقدر است؟</span><i class="fas fa-chevron-down"></i></div><div class="faq-answer">هزینه بر اساس نوع، پیچیدگی و زمان تقریبی پروژه تعیین می‌شود. برای دریافت قیمت دقیق، از طریق تلگرام با من در ارتباط باشید.</div></div>
                    <div class="faq-item"><div class="faq-question"><span>🔧 آیا پشتیبانی بعد از تحویل دارید؟</span><i class="fas fa-chevron-down"></i></div><div class="faq-answer">بله، پس از تحویل پروژه، پشتیبانی فنی و رفع باگ‌های احتمالی به مدت ۳ ماه کاملاً رایگان ارائه می‌شود.</div></div>
                    <div class="faq-item"><div class="faq-question"><span>💻 از چه فناوری‌هایی استفاده می‌کنید؟</span><i class="fas fa-chevron-down"></i></div><div class="faq-answer">Unity برای بازی، Python و OpenAI API برای هوش مصنوعی، Flutter برای اپلیکیشن موبایل، React برای وب و C#/C++ برای برنامه‌نویسی سطح بالا.</div></div>
                    <div class="faq-item"><div class="faq-question"><span>📱 چه نوع پروژه‌هایی انجام می‌دهید؟</span><i class="fas fa-chevron-down"></i></div><div class="faq-answer">بازی‌های موبایل و کامپیوتر، اپلیکیشن‌های کاربردی، نرم‌افزارهای مدیریتی، چت‌بات‌های هوشمند، ویرایشگرهای ویدیو و عکس، و هر پروژه خلاقانه دیگر.</div></div>
                    <div class="faq-item"><div class="faq-question"><span>🤝 چگونه می‌توانم با شما همکاری کنم؟</span><i class="fas fa-chevron-down"></i></div><div class="faq-answer">کافی است از طریق تلگرام با من در ارتباط باشید. ایده خود را بگویید، مشاوره اولیه رایگان است و سپس برنامه همکاری را مشخص می‌کنیم.</div></div>
                </div>
            </section>

            <!-- CTA -->
            <div class="cta fade-up">
                <h3>آماده شروع پروژه خود هستید؟</h3>
                <p>با هوش مصنوعی، پروژه‌ات را سریع‌تر و حرفه‌ای‌تر از همیشه بساز</p>
                <p style="font-size:0.85rem; opacity:0.7;">مشاوره اولیه کاملاً رایگان</p>
                <a href="#" class="btn-white"><i class="fab fa-telegram"></i> شروع همکاری در تلگرام <i class="fas fa-arrow-left"></i></a>
            </div>
        </div>

        <!-- فوتر -->
        <footer>
            <div class="footer-links">
                <a href="#">خانه</a>
                <a href="#">خدمات</a>
                <a href="#">بازی‌ها و برنامه‌ها</a>
                <a href="#">وبلاگ</a>
                <a href="#">تماس</a>
                <a href="#">درباره</a>
            </div>
            
            <div class="social-links">
                <a href="https://t.me/Aeroost_Studio" target="_blank"><i class="fab fa-telegram"></i> کانال تلگرام</a>
                <a href="https://t.me/Aeroost_Studio_admin" target="_blank"><i class="fab fa-telegram-plane"></i> ادمین</a>
            </div>
            
            <div class="copyright">
                <span>© ۲۰۲۶ AEROOST STUDIO</span>
            </div>
        </footer>
    </main>

    <script>
        // تم روشن/تاریک
        const themeToggle = document.getElementById('themeToggle');
        const body = document.body;
        const saved = localStorage.getItem('aeroost_theme') || 'dark';
        body.classList.add(saved);
        themeToggle.addEventListener('click', () => {
            body.classList.toggle('light');
            body.classList.toggle('dark');
            localStorage.setItem('aeroost_theme', body.classList.contains('light') ? 'light' : 'dark');
        });

        // انیمیشن اسکرول
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(e => e.isIntersecting && e.target.classList.add('visible'));
        }, { threshold: 0.1 });
        document.querySelectorAll('.fade-up, .fade-in, .scale-in').forEach(el => observer.observe(el));

        // هدر اسکرول
        window.addEventListener('scroll', () => {
            document.querySelector('.header').classList.toggle('scrolled', window.scrollY > 50);
        });

        // FAQ آکاردئون
        document.querySelectorAll('.faq-item').forEach(item => {
            const question = item.querySelector('.faq-question');
            question.addEventListener('click', () => {
                const isActive = item.classList.contains('active');
                document.querySelectorAll('.faq-item').forEach(i => i.classList.remove('active'));
                if (!isActive) item.classList.add('active');
            });
        });
        document.querySelector('.faq-item')?.classList.add('active');
    </script>
</body>
</html>
