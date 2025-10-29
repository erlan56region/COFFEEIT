<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ITCOFE - Цифровая трансформация будущего</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #0a0a0a;
            --secondary: #ff3e3e;
            --accent: #00cc88;
            --accent-light: #66ffcc;
            --light: #f5f5f7;
            --dark: #1a1a1a;
            --text: #0d0d0d;
            --text-secondary: #404040;
            --card-bg: #ffffff;
            --gradient: linear-gradient(135deg, #ff3e3e 0%, #00cc88 100%);
            --grid-color: rgba(0, 0, 0, 0.03);
            --glass: rgba(255, 255, 255, 0.08);
            --glass-border: rgba(255, 255, 255, 0.12);
            --neon-glow: 0 0 10px rgba(255, 62, 62, 0.7), 0 0 20px rgba(255, 62, 62, 0.5), 0 0 30px rgba(255, 62, 62, 0.3);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Space Grotesk', sans-serif;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            background-color: var(--light);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 15% 50%, rgba(255, 62, 62, 0.03) 0%, transparent 25%),
                radial-gradient(circle at 85% 30%, rgba(0, 204, 136, 0.03) 0%, transparent 25%);
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Навигация - цифровой стиль */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(10, 10, 10, 0.85);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            z-index: 1000;
            padding: 20px 0;
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            border-bottom: 1px solid var(--glass-border);
        }
        
        nav.scrolled {
            padding: 15px 0;
            background: rgba(10, 10, 10, 0.95);
            box-shadow: 0 5px 30px rgba(0, 0, 0, 0.2);
        }
        
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 28px;
            font-weight: 700;
            color: var(--light);
            text-decoration: none;
            display: flex;
            align-items: center;
            letter-spacing: -1px;
            transition: all 0.3s ease;
            padding: 10px 20px;
            border-radius: 12px;
            position: relative;
            overflow: hidden;
            background: var(--glass);
            border: 1px solid var(--glass-border);
        }
        
        .logo::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.7s ease;
        }
        
        .logo:hover::before {
            left: 100%;
        }
        
        .logo:hover {
            transform: translateY(-2px);
            box-shadow: var(--neon-glow);
        }
        
        .logo span {
            color: var(--secondary);
            margin-left: 2px;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 20px;
            position: relative;
        }
        
        .nav-links a {
            text-decoration: none;
            color: var(--light);
            font-weight: 500;
            transition: all 0.3s ease;
            font-size: 16px;
            position: relative;
            padding: 12px 20px;
            border-radius: 10px;
            display: block;
            overflow: hidden;
            background: var(--glass);
            border: 1px solid transparent;
        }
        
        .nav-links a::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--gradient);
            transition: left 0.4s ease;
            z-index: -1;
            opacity: 0;
        }
        
        .nav-links a:hover {
            color: var(--light);
            border-color: var(--glass-border);
        }
        
        .nav-links a:hover::before {
            left: 0;
            opacity: 1;
        }
        
        .nav-links a.active {
            background: rgba(255, 62, 62, 0.1);
            border-color: var(--secondary);
            box-shadow: 0 0 15px rgba(255, 62, 62, 0.3);
        }
        
        /* Герой секция - цифровая эстетика */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
            background: 
                radial-gradient(ellipse at 20% 50%, rgba(255, 62, 62, 0.15) 0%, transparent 50%),
                radial-gradient(ellipse at 80% 20%, rgba(0, 204, 136, 0.15) 0%, transparent 50%),
                linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            color: var(--light);
        }
        
        .digital-grid {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(rgba(255, 255, 255, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: gridMove 20s linear infinite;
        }
        
        @keyframes gridMove {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }
        
        .floating-elements {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
        }
        
        .floating-element {
            position: absolute;
            background: var(--glass);
            border: 1px solid var(--glass-border);
            border-radius: 10px;
            animation: float 15s infinite ease-in-out;
        }
        
        @keyframes float {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            25% { transform: translate(10px, -15px) rotate(5deg); }
            50% { transform: translate(-5px, -10px) rotate(-3deg); }
            75% { transform: translate(15px, 5px) rotate(2deg); }
        }
        
        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 800px;
            margin-left: 10%;
        }
        
        .hero h1 {
            font-size: 5rem;
            font-weight: 700;
            margin-bottom: 30px;
            line-height: 1;
            color: var(--light);
            letter-spacing: -2px;
            transform: translateX(-100px);
            opacity: 0;
            animation: slideIn 1s ease 0.5s forwards;
            text-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            background: linear-gradient(135deg, #fff 0%, #ccc 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .hero p {
            font-size: 1.4rem;
            margin-bottom: 40px;
            color: rgba(255, 255, 255, 0.8);
            max-width: 600px;
            transform: translateX(-100px);
            opacity: 0;
            animation: slideIn 1s ease 0.8s forwards;
        }
        
        .btn {
            display: inline-block;
            padding: 18px 45px;
            background: transparent;
            color: var(--light);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            border: 2px solid var(--secondary);
            cursor: pointer;
            transform: translateX(-100px);
            opacity: 0;
            animation: slideIn 1s ease 1.1s forwards;
            position: relative;
            overflow: hidden;
            border-radius: 12px;
            letter-spacing: 0.5px;
            background: var(--glass);
            backdrop-filter: blur(10px);
        }
        
        .btn:before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--gradient);
            transition: 0.5s;
            z-index: -1;
        }
        
        .btn:hover {
            color: var(--primary);
            transform: translateY(-5px);
            box-shadow: var(--neon-glow);
        }
        
        .btn:hover:before {
            left: 0;
        }
        
        .btn:active {
            transform: translateY(-2px);
        }
        
        .btn-secondary {
            border-color: var(--accent);
        }
        
        .btn-secondary:hover {
            box-shadow: 0 0 10px rgba(0, 204, 136, 0.7), 0 0 20px rgba(0, 204, 136, 0.5), 0 0 30px rgba(0, 204, 136, 0.3);
        }
        
        .scroll-indicator {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            color: var(--light);
            font-size: 14px;
            display: flex;
            flex-direction: column;
            align-items: center;
            opacity: 0;
            animation: fadeIn 1s ease 1.5s forwards;
            cursor: pointer;
            padding: 15px;
            border-radius: 50%;
            transition: all 0.3s ease;
            background: var(--glass);
            border: 1px solid var(--glass-border);
        }
        
        .scroll-indicator:hover {
            background-color: rgba(255, 255, 255, 0.1);
            transform: translateX(-50%) translateY(-5px);
        }
        
        .scroll-indicator i {
            margin-top: 10px;
            animation: bounce 2s infinite;
        }
        
        /* Секции */
        section {
            padding: 120px 0;
            position: relative;
        }
        
        .section-title {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 80px;
            position: relative;
            color: var(--text);
            letter-spacing: -1px;
            padding-left: 20px;
        }
        
        .section-title::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            height: 100%;
            width: 5px;
            background: var(--gradient);
            border-radius: 5px;
        }
        
        /* О компании - цифровая культура */
        .about {
            background-color: var(--light);
        }
        
        .about-content {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 80px;
            align-items: start;
        }
        
        .about-text h3 {
            font-size: 2rem;
            margin-bottom: 25px;
            color: var(--text);
            font-weight: 600;
        }
        
        .about-text p {
            margin-bottom: 25px;
            color: var(--text-secondary);
            font-size: 1.1rem;
            line-height: 1.8;
        }
        
        .stats {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 30px;
            margin-top: 50px;
        }
        
        .stat-item {
            padding: 40px 30px;
            background: var(--card-bg);
            border: 1px solid rgba(0, 0, 0, 0.1);
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
            cursor: pointer;
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
        }
        
        .stat-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--gradient);
            transition: left 0.5s ease;
            z-index: 0;
            opacity: 0;
        }
        
        .stat-item:hover::before {
            left: 0;
            opacity: 0.05;
        }
        
        .stat-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }
        
        .stat-value {
            font-size: 3.5rem;
            font-weight: 700;
            color: var(--secondary);
            margin-bottom: 10px;
            position: relative;
            z-index: 1;
        }
        
        .stat-label {
            color: var(--text-secondary);
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            position: relative;
            z-index: 1;
        }
        
        /* Услуги - цифровая трансформация */
        .services {
            background: linear-gradient(135deg, var(--primary) 0%, #1a1a2e 100%);
            color: var(--light);
        }
        
        .services .section-title {
            color: var(--light);
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
        }
        
        .service-item {
            padding: 50px 40px;
            background: var(--glass);
            border: 1px solid var(--glass-border);
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
            border-radius: 20px;
            overflow: hidden;
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
        }
        
        .service-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--gradient);
            transition: left 0.5s ease;
            z-index: 0;
            opacity: 0;
        }
        
        .service-item:hover::before {
            left: 0;
            opacity: 0.1;
        }
        
        .service-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }
        
        .service-icon {
            font-size: 3rem;
            margin-bottom: 25px;
            color: var(--accent);
            position: relative;
            z-index: 1;
        }
        
        .service-item h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--light);
            position: relative;
            z-index: 1;
        }
        
        .service-item p {
            color: rgba(255, 255, 255, 0.7);
            position: relative;
            z-index: 1;
            line-height: 1.8;
        }
        
        /* Интернет-магазин */
        .shop {
            background-color: var(--light);
        }
        
        .shop-header {
            text-align: center;
            margin-bottom: 60px;
        }
        
        .shop-badge {
            display: inline-block;
            padding: 8px 20px;
            background: var(--gradient);
            color: white;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 20px;
            animation: pulse 2s infinite;
        }
        
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }
        
        .product-card {
            background: var(--card-bg);
            border-radius: 16px;
            overflow: hidden;
            transition: all 0.4s ease;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            border: 1px solid rgba(0, 0, 0, 0.05);
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }
        
        .product-image {
            height: 200px;
            background: linear-gradient(135deg, #f5f5f7 0%, #e0e0e0 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }
        
        .product-image i {
            font-size: 4rem;
            color: var(--text-secondary);
            opacity: 0.7;
        }
        
        .product-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--secondary);
            color: white;
            padding: 5px 10px;
            border-radius: 12px;
            font-size: 0.8rem;
            font-weight: 600;
        }
        
        .product-content {
            padding: 25px;
        }
        
        .product-category {
            color: var(--text-secondary);
            font-size: 0.9rem;
            margin-bottom: 8px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        
        .product-title {
            font-size: 1.3rem;
            margin-bottom: 12px;
            color: var(--text);
        }
        
        .product-description {
            color: var(--text-secondary);
            font-size: 0.95rem;
            margin-bottom: 20px;
            line-height: 1.6;
        }
        
        .product-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .product-price {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--secondary);
        }
        
        .product-actions {
            display: flex;
            gap: 10px;
        }
        
        .product-btn {
            padding: 10px 20px;
            background: transparent;
            border: 1px solid var(--secondary);
            color: var(--secondary);
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 600;
        }
        
        .product-btn:hover {
            background: var(--secondary);
            color: white;
        }
        
        .product-btn.secondary {
            border-color: var(--accent);
            color: var(--accent);
        }
        
        .product-btn.secondary:hover {
            background: var(--accent);
            color: white;
        }
        
        .coming-soon {
            text-align: center;
            padding: 80px 0;
        }
        
        .coming-soon i {
            font-size: 4rem;
            color: var(--text-secondary);
            margin-bottom: 20px;
        }
        
        .coming-soon h3 {
            font-size: 2rem;
            margin-bottom: 15px;
            color: var(--text);
        }
        
        .coming-soon p {
            color: var(--text-secondary);
            max-width: 500px;
            margin: 0 auto 30px;
        }
        
        /* Работы - улучшена интерактивность */
        .works {
            background: linear-gradient(135deg, var(--primary) 0%, #1a1a2e 100%);
            color: var(--light);
        }
        
        .works .section-title {
            color: var(--light);
        }
        
        .works-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 40px;
        }
        
        .work-item {
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            opacity: 0;
            transform: translateY(30px);
            background: var(--glass);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            overflow: hidden;
            cursor: pointer;
            backdrop-filter: blur(10px);
        }
        
        .work-item.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        .work-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }
        
        .work-img {
            height: 240px;
            overflow: hidden;
            margin-bottom: 0;
        }
        
        .work-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .work-item:hover .work-img img {
            transform: scale(1.05);
        }
        
        .work-content {
            padding: 30px;
        }
        
        .work-content h3 {
            margin-bottom: 15px;
            font-size: 1.5rem;
            color: var(--light);
        }
        
        .work-content p {
            color: rgba(255, 255, 255, 0.7);
            font-size: 1rem;
            margin-bottom: 20px;
            line-height: 1.6;
        }
        
        .work-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }
        
        .work-tag {
            background: transparent;
            color: var(--accent);
            padding: 8px 16px;
            font-size: 0.8rem;
            border: 1px solid var(--accent);
            border-radius: 20px;
            transition: all 0.3s ease;
        }
        
        .work-tag:hover {
            background: var(--accent);
            color: white;
        }
        
        /* Контакты - улучшена интерактивность */
        .contact {
            background-color: var(--light);
        }
        
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 80px;
        }
        
        .contact-info h3 {
            margin-bottom: 25px;
            font-size: 1.8rem;
            color: var(--text);
        }
        
        .contact-info p {
            margin-bottom: 20px;
            color: var(--text-secondary);
            display: flex;
            align-items: center;
            transition: all 0.3s ease;
            padding: 12px 0;
            border-radius: 8px;
        }
        
        .contact-info p:hover {
            color: var(--text);
            transform: translateX(5px);
            background: rgba(0, 0, 0, 0.03);
        }
        
        .contact-info i {
            margin-right: 15px;
            color: var(--secondary);
            width: 20px;
            font-size: 1.2rem;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 30px;
        }
        
        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background: transparent;
            color: var(--text);
            text-decoration: none;
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 0, 0, 0.1);
            border-radius: 12px;
            position: relative;
            overflow: hidden;
            background: var(--card-bg);
        }
        
        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--gradient);
            transition: left 0.4s ease;
            z-index: -1;
        }
        
        .social-link:hover::before {
            left: 0;
        }
        
        .social-link:hover {
            color: var(--primary);
            transform: translate(-3px, -3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 18px;
            margin-bottom: 25px;
            border: none;
            background: var(--card-bg);
            color: var(--text);
            font-size: 1rem;
            border: 1px solid rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.03);
        }
        
        .contact-form input:focus,
        .contact-form textarea:focus {
            outline: none;
            border-color: var(--secondary);
            box-shadow: 0 0 0 2px rgba(255, 62, 62, 0.2);
            transform: translate(-2px, -2px);
        }
        
        .contact-form input::placeholder,
        .contact-form textarea::placeholder {
            color: rgba(0, 0, 0, 0.4);
        }
        
        .contact-form textarea {
            height: 150px;
            resize: vertical;
        }
        
        .contact-form .btn {
            background: transparent;
            color: var(--text);
            border: 2px solid var(--secondary);
            padding: 18px 45px;
            cursor: pointer;
            transition: all 0.3s ease;
            border-radius: 12px;
            width: 100%;
        }
        
        .contact-form .btn:hover {
            background: var(--secondary);
            color: white;
            transform: translate(-3px, -3px);
            box-shadow: 0 10px 20px rgba(255, 62, 62, 0.2);
        }
        
        /* Благотворительность и спонсорство */
        .charity {
            background-color: var(--light);
        }
        
        .charity-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            margin-bottom: 60px;
        }
        
        .charity-text h3 {
            font-size: 2rem;
            margin-bottom: 25px;
            color: var(--text);
            font-weight: 600;
        }
        
        .charity-text p {
            margin-bottom: 25px;
            color: var(--text-secondary);
            font-size: 1.1rem;
            line-height: 1.8;
        }
        
        .charity-stats {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 30px;
        }
        
        .charity-stat {
            padding: 30px;
            background: var(--card-bg);
            border: 1px solid rgba(0, 0, 0, 0.1);
            transition: all 0.4s ease;
            position: relative;
            cursor: pointer;
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            text-align: center;
        }
        
        .charity-stat:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }
        
        .charity-stat i {
            font-size: 3rem;
            color: var(--accent);
            margin-bottom: 15px;
        }
        
        .charity-stat h4 {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: var(--text);
        }
        
        .charity-stat p {
            color: var(--text-secondary);
        }
        
        .sponsorship-programs {
            margin-top: 80px;
        }
        
        .programs-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 40px;
        }
        
        .program-card {
            padding: 40px 30px;
            background: var(--card-bg);
            border: 1px solid rgba(0, 0, 0, 0.1);
            transition: all 0.4s ease;
            position: relative;
            cursor: pointer;
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            text-align: center;
        }
        
        .program-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }
        
        .program-card i {
            font-size: 3rem;
            color: var(--secondary);
            margin-bottom: 20px;
        }
        
        .program-card h4 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--text);
        }
        
        .program-card p {
            color: var(--text-secondary);
            margin-bottom: 20px;
        }
        
        .program-btn {
            display: inline-block;
            padding: 12px 25px;
            background: transparent;
            color: var(--secondary);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            border: 2px solid var(--secondary);
            border-radius: 8px;
        }
        
        .program-btn:hover {
            background: var(--secondary);
            color: white;
        }
        
        /* Футер */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 80px 0 30px;
            border-top: 1px solid var(--glass-border);
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 40px;
            margin-bottom: 50px;
        }
        
        .footer-logo {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 20px;
            color: white;
        }
        
        .footer-logo span {
            color: var(--secondary);
        }
        
        .footer-info p {
            color: rgba(255, 255, 255, 0.7);
            margin-bottom: 20px;
            line-height: 1.8;
        }
        
        .footer-column h4 {
            margin-bottom: 20px;
            font-size: 1.2rem;
            color: var(--accent);
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column li {
            margin-bottom: 12px;
        }
        
        .footer-column a {
            color: rgba(255, 255, 255, 0.7);
            text-decoration: none;
            transition: color 0.3s ease;
            padding: 8px 0;
            display: block;
            border-radius: 6px;
            transition: all 0.3s ease;
        }
        
        .footer-column a:hover {
            color: white;
            transform: translateX(5px);
            background: var(--glass);
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid var(--glass-border);
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.9rem;
        }
        
        /* Анимации */
        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateX(-100px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
        
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0);
            }
            40% {
                transform: translateY(-10px);
            }
            60% {
                transform: translateY(-5px);
            }
        }
        
        /* Адаптивность */
        @media (max-width: 1200px) {
            .hero-content {
                margin-left: 5%;
            }
            
            .about-content {
                grid-template-columns: 1fr;
            }
            
            .charity-content {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                grid-template-columns: 1fr 1fr;
            }
        }
        
        @media (max-width: 992px) {
            .contact-content {
                grid-template-columns: 1fr;
            }
            
            .hero h1 {
                font-size: 4rem;
            }
        }
        
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .mobile-menu-btn {
                display: block;
                background: none;
                border: none;
                color: var(--light);
                font-size: 1.5rem;
                cursor: pointer;
                background: var(--glass);
                border: 1px solid var(--glass-border);
                padding: 10px;
                border-radius: 8px;
            }
            
            .hero h1 {
                font-size: 3rem;
            }
            
            .section-title {
                font-size: 2.5rem;
            }
            
            .stats {
                grid-template-columns: 1fr;
            }
            
            .charity-stats {
                grid-template-columns: 1fr;
            }
            
            .works-grid {
                grid-template-columns: 1fr;
            }
            
            .products-grid {
                grid-template-columns: 1fr;
            }
            
            .programs-grid {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                grid-template-columns: 1fr;
            }
        }

        /* Новые элементы для улучшения кликабельности */
        .clickable {
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .clickable:hover {
            transform: translateY(-3px);
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
    </style>
</head>
<body>
    <!-- Навигация -->
    <nav id="navbar">
        <div class="container nav-container">
            <a href="#" class="logo">ITCO<span>FE</span></a>
            <ul class="nav-links">
                <li><a href="#about">О компании</a></li>
                <li><a href="#services">Услуги</a></li>
                <li><a href="#shop" class="active">Магазин</a></li>
                <li><a href="#works">Проекты</a></li>
                <li><a href="#charity">Благотворительность</a></li>
                <li><a href="#contact">Контакты</a></li>
            </ul>
            <button class="mobile-menu-btn">
                <i class="fas fa-bars"></i>
            </button>
        </div>
    </nav>

    <!-- Герой секция -->
    <section class="hero">
        <div class="digital-grid"></div>
        <div class="floating-elements" id="floatingElements"></div>
        <div class="container hero-content">
            <h1>ЦИФРОВАЯ ТРАНСФОРМАЦИЯ</h1>
            <p>ITCOFE создает будущее цифровых технологий. Мы разрабатываем инновационные решения, которые меняют правила игры в эпоху цифровой экономики.</p>
            <a href="#shop" class="btn">Исследовать продукты</a>
            <a href="#charity" class="btn btn-secondary">Узнать о благотворительности</a>
        </div>
        <div class="scroll-indicator" onclick="scrollToSection('about')">
            Узнать больше
            <i class="fas fa-chevron-down"></i>
        </div>
    </section>

    <!-- О компании -->
    <section id="about" class="about">
        <div class="container">
            <h2 class="section-title">ЦИФРОВАЯ КУЛЬТУРА</h2>
            <div class="about-content">
                <div class="about-text">
                    <h3>Инновации как образ жизни</h3>
                    <p>ITCOFE была основана в 2010 году с миссией трансформировать цифровой ландшафт. Мы верим, что технологии должны служить людям и улучшать качество жизни.</p>
                    <p>Наша команда состоит из более чем 2000 талантливых специалистов, которые работают на стыке технологий и бизнеса, создавая решения для цифровой эпохи.</p>
                    <p>Мы гордимся тем, что наши продукты используют более 500 компаний из списка Fortune 1000, и мы продолжаем расширять границы возможного в технологической индустрии.</p>
                    
                    <div class="stats">
                        <div class="stat-item clickable">
                            <div class="stat-value">30B+</div>
                            <div class="stat-label">Капитализация</div>
                        </div>
                        <div class="stat-item clickable">
                            <div class="stat-value">15</div>
                            <div class="stat-label">Стран присутствия</div>
                        </div>
                        <div class="stat-item clickable">
                            <div class="stat-value">2000+</div>
                            <div class="stat-label">Сотрудников</div>
                        </div>
                        <div class="stat-item clickable">
                            <div class="stat-value">500+</div>
                            <div class="stat-label">Клиентов Fortune 1000</div>
                        </div>
                    </div>
                </div>
                <div class="about-text">
                    <h3>Наша философия</h3>
                    <p>Мы верим в силу цифровой трансформации как инструмента создания лучшего будущего. Наши решения построены на принципах открытости, инноваций и устойчивого развития.</p>
                    <p>Цифровая культура в ITCOFE — это постоянное обучение, экспериментирование и стремление к совершенству. Мы поощряем нестандартное мышление и смелые идеи.</p>
                    <p>Каждый наш продукт — это шаг к более connected, intelligent и sustainable будущему.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Услуги -->
    <section id="services" class="services">
        <div class="container">
            <h2 class="section-title">ЦИФРОВЫЕ РЕШЕНИЯ</h2>
            <div class="services-grid">
                <div class="service-item">
                    <div class="service-icon">
                        <i class="fas fa-brain"></i>
                    </div>
                    <h3>Искусственный интеллект</h3>
                    <p>Разрабатываем передовые AI-решения для автоматизации бизнес-процессов, анализа данных и создания интеллектуальных систем.</p>
                </div>
                <div class="service-item">
                    <div class="service-icon">
                        <i class="fas fa-link"></i>
                    </div>
                    <h3>Блокчейн технологии</h3>
                    <p>Создаем безопасные и прозрачные блокчейн-решения для финансового сектора, логистики и управления цепочками поставок.</p>
                </div>
                <div class="service-item">
                    <div class="service-icon">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <h3>Кибербезопасность</h3>
                    <p>Обеспечиваем комплексную защиту цифровых активов с использованием машинного обучения и передовых технологий.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Интернет-магазин -->
    <section id="shop" class="shop">
        <div class="container">
            <div class="shop-header">
                <span class="shop-badge">НОВИНКА</span>
                <h2 class="section-title">ИНТЕРНЕТ-МАГАЗИН</h2>
                <p>Откройте для себя наши цифровые продукты и решения</p>
            </div>
            
            <div class="products-grid">
                <div class="product-card">
                    <div class="product-image">
                        <i class="fas fa-robot"></i>
                        <span class="product-badge">ХИТ</span>
                    </div>
                    <div class="product-content">
                        <div class="product-category">AI решение</div>
                        <h3 class="product-title">NeuraMind Pro</h3>
                        <p class="product-description">Продвинутая платформа искусственного интеллекта для бизнес-аналитики и прогнозирования</p>
                        <div class="product-footer">
                            <div class="product-price">$299</div>
                            <div class="product-actions">
                                <button class="product-btn secondary">Подробнее</button>
                                <button class="product-btn">В корзину</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="product-card">
                    <div class="product-image">
                        <i class="fas fa-lock"></i>
                    </div>
                    <div class="product-content">
                        <div class="product-category">Безопасность</div>
                        <h3 class="product-title">SecureChain Enterprise</h3>
                        <p class="product-description">Корпоративное блокчейн-решение для безопасных транзакций и хранения данных</p>
                        <div class="product-footer">
                            <div class="product-price">$499</div>
                            <div class="product-actions">
                                <button class="product-btn secondary">Подробнее</button>
                                <button class="product-btn">В корзину</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="product-card">
                    <div class="product-image">
                        <i class="fas fa-cloud"></i>
                        <span class="product-badge">НОВИНКА</span>
                    </div>
                    <div class="product-content">
                        <div class="product-category">Облако</div>
                        <h3 class="product-title">CloudFlow Suite</h3>
                        <p class="product-description">Комплексное облачное решение для управления бизнес-процессами и данными</p>
                        <div class="product-footer">
                            <div class="product-price">$199</div>
                            <div class="product-actions">
                                <button class="product-btn secondary">Подробнее</button>
                                <button class="product-btn">В корзину</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="coming-soon">
                <i class="fas fa-tools"></i>
                <h3>Раздел в разработке</h3>
                <p>Мы активно работаем над расширением ассортимента нашего магазина. Скоро здесь появятся новые цифровые продукты и услуги.</p>
                <a href="#contact" class="btn">Узнать о новинках первым</a>
            </div>
        </div>
    </section>

    <!-- Работы -->
    <section id="works" class="works">
        <div class="container">
            <h2 class="section-title">НАШИ ПРОЕКТЫ</h2>
            <div class="works-grid">
                <div class="work-item">
                    <div class="work-img">
                        <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="AI платформа">
                    </div>
                    <div class="work-content">
                        <h3>NeuraMind AI</h3>
                        <p>Передовая платформа искусственного интеллекта для анализа больших данных и прогнозирования трендов. Используется финансовыми институтами по всему миру.</p>
                        <div class="work-tags">
                            <span class="work-tag">AI</span>
                            <span class="work-tag">Machine Learning</span>
                            <span class="work-tag">Big Data</span>
                        </div>
                    </div>
                </div>
                <div class="work-item">
                    <div class="work-img">
                        <img src="https://images.unsplash.com/photo-1558494949-ef010cbdcc31?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Блокчейн решение">
                    </div>
                    <div class="work-content">
                        <h3>SecureChain</h3>
                        <p>Инновационная блокчейн-платформа для безопасных транзакций и хранения данных. Применяется в государственном и финансовом секторах.</p>
                        <div class="work-tags">
                            <span class="work-tag">Blockchain</span>
                            <span class="work-tag">Security</span>
                            <span class="work-tag">FinTech</span>
                        </div>
                    </div>
                </div>
                <div class="work-item">
                    <div class="work-img">
                        <img src="https://images.unsplash.com/photo-1563013544-824ae1b704d3?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Кибербезопасность">
                    </div>
                    <div class="work-content">
                        <h3>CyberShield</h3>
                        <p>Комплексная система кибербезопасности с использованием машинного обучения для обнаружения и предотвращения угроз в реальном времени.</p>
                        <div class="work-tags">
                            <span class="work-tag">Cybersecurity</span>
                            <span class="work-tag">ML</span>
                            <span class="work-tag">Threat Detection</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Благотворительность и спонсорство -->
    <section id="charity" class="charity">
        <div class="container">
            <h2 class="section-title">БЛАГОТВОРИТЕЛЬНОСТЬ И СПОНСОРСТВО</h2>
            <div class="charity-content">
                <div class="charity-text">
                    <h3>Наша социальная ответственность</h3>
                    <p>В ITCOFE мы верим, что технологии должны служить не только бизнесу, но и обществу. С момента основания компании мы активно участвуем в благотворительных и социальных проектах по всему миру.</p>
                    <p>Наша цель — использовать технологии для решения глобальных проблем, таких как неравенство в образовании, доступ к медицинским услугам и защита окружающей среды.</p>
                    <p>Ежегодно мы направляем не менее 5% нашей прибыли на благотворительные инициативы и спонсорство образовательных программ в области технологий.</p>
                </div>
                <div class="charity-text">
                    <h3>Наши достижения</h3>
                    <p>За последние 5 лет мы поддержали более 100 образовательных программ по всему миру, предоставили технологии для 50 медицинских учреждений и помогли более 1000 студентов получить образование в области IT.</p>
                    <p>Наши сотрудники активно участвуют в волонтерских программах, посвящая более 10 000 часов в год социальным проектам.</p>
                </div>
            </div>
            
            <div class="charity-stats">
                <div class="charity-stat">
                    <i class="fas fa-graduation-cap"></i>
                    <h4>100+</h4>
                    <p>Образовательных программ</p>
                </div>
                <div class="charity-stat">
                    <i class="fas fa-hands-helping"></i>
                    <h4>10,000+</h4>
                    <p>Волонтерских часов в год</p>
                </div>
                <div class="charity-stat">
                    <i class="fas fa-dollar-sign"></i>
                    <h4>5%</h4>
                    <p>Прибыли на благотворительность</p>
                </div>
                <div class="charity-stat">
                    <i class="fas fa-globe"></i>
                    <h4>25</h4>
                    <p>Стран, где мы помогаем</p>
                </div>
            </div>
            
            <div class="sponsorship-programs">
                <h3 class="section-title">НАШИ ПРОГРАММЫ</h3>
                <div class="programs-grid">
                    <div class="program-card">
                        <i class="fas fa-laptop-code"></i>
                        <h4>IT Образование</h4>
                        <p>Поддержка образовательных программ в области технологий для молодежи из социально незащищенных слоев населения.</p>
                        <a href="#" class="program-btn">Узнать больше</a>
                    </div>
                    <div class="program-card">
                        <i class="fas fa-heartbeat"></i>
                        <h4>Медицинские технологии</h4>
                        <p>Предоставление передовых технологий для медицинских учреждений в развивающихся странах.</p>
                        <a href="#" class="program-btn">Узнать больше</a>
                    </div>
                    <div class="program-card">
                        <i class="fas fa-leaf"></i>
                        <h4>Экологические инициативы</h4>
                        <p>Финансирование и технологическая поддержка проектов по защите окружающей среды и устойчивому развитию.</p>
                        <a href="#" class="program-btn">Узнать больше</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Контакты -->
    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">СВЯЖИТЕСЬ С НАМИ</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <h3>Наши контакты</h3>
                    <p><i class="fas fa-map-marker-alt"></i> <strong>Адрес:</strong> 123 Innovation Drive, Silicon Valley, CA 94025</p>
                    <p><i class="fas fa-phone"></i> <strong>Телефон:</strong> +1 (650) 123-4567</p>
                    <p><i class="fas fa-envelope"></i> <strong>Email:</strong> info@itcofe.com</p>
                    <p><i class="fas fa-clock"></i> <strong>Часы работы:</strong> Пн-Пт: 9:00-18:00</p>
                    
                    <div class="social-links">
                        <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
                <form class="contact-form" id="contactForm">
                    <input type="text" placeholder="Ваше имя" required>
                    <input type="email" placeholder="Ваш email" required>
                    <input type="text" placeholder="Тема" required>
                    <textarea placeholder="Ваше сообщение" required></textarea>
                    <button type="submit" class="btn">Отправить сообщение</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Футер -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-info">
                    <div class="footer-logo">ITCO<span>FE</span></div>
                    <p>Смелые решения для цифровой эпохи. Бросаем вызов традициям, создавая технологии, которые меняют правила игры.</p>
                </div>
                <div class="footer-column">
                    <h4>Компания</h4>
                    <ul>
                        <li><a href="#about">О нас</a></li>
                        <li><a href="#services">Услуги</a></li>
                        <li><a href="#shop">Магазин</a></li>
                        <li><a href="#works">Проекты</a></li>
                        <li><a href="#charity">Благотворительность</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h4>Услуги</h4>
                    <ul>
                        <li><a href="#">Искусственный интеллект</a></li>
                        <li><a href="#">Блокчейн</a></li>
                        <li><a href="#">Кибербезопасность</a></li>
                        <li><a href="#">Облачные решения</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h4>Ресурсы</h4>
                    <ul>
                        <li><a href="#">Блог</a></li>
                        <li><a href="#">Документация</a></li>
                        <li><a href="#">Поддержка</a></li>
                        <li><a href="#">Карьера</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 ITCOFE. Все права защищены. Капитализация: $30 млрд.</p>
            </div>
        </div>
    </footer>

    <script>
        // Плавная прокрутка для навигационных ссылок
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // Функция для прокрутки к секции
        function scrollToSection(sectionId) {
            const section = document.getElementById(sectionId);
            if (section) {
                window.scrollTo({
                    top: section.offsetTop - 80,
                    behavior: 'smooth'
                });
            }
        }
        
        // Анимация появления элементов при скролле
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);
        
        // Наблюдаем за элементами, которые должны появляться при скролле
        document.querySelectorAll('.work-item, .service-item, .stat-item, .product-card, .charity-stat, .program-card').forEach(el => {
            observer.observe(el);
        });
        
        // Изменение навигации при скролле
        window.addEventListener('scroll', () => {
            const nav = document.getElementById('navbar');
            if (window.scrollY > 100) {
                nav.classList.add('scrolled');
            } else {
                nav.classList.remove('scrolled');
            }
        });
        
        // Обработка формы
        const contactForm = document.getElementById('contactForm');
        if (contactForm) {
            contactForm.addEventListener('submit', function(e) {
                e.preventDefault();
                const submitBtn = this.querySelector('.btn');
                submitBtn.textContent = 'Отправка...';
                submitBtn.disabled = true;
                
                // Имитация отправки формы
                setTimeout(() => {
                    submitBtn.textContent = 'Сообщение отправлено!';
                    submitBtn.style.backgroundColor = 'var(--accent)';
                    submitBtn.style.borderColor = 'var(--accent)';
                    
                    setTimeout(() => {
                        submitBtn.textContent = 'Отправить сообщение';
                        submitBtn.disabled = false;
                        submitBtn.style.backgroundColor = '';
                        submitBtn.style.borderColor = 'var(--secondary)';
                        contactForm.reset();
                    }, 3000);
                }, 1500);
            });
        }
        
        // Добавление класса hover для всех интерактивных элементов
        document.querySelectorAll('.clickable, .btn, .nav-links a, .social-link, .work-item, .stat-item, .service-item, .product-card, .product-btn, .charity-stat, .program-card').forEach(el => {
            el.addEventListener('mouseenter', function() {
                this.style.cursor = 'pointer';
            });
        });
        
        // Создание плавающих элементов в герое
        function createFloatingElements() {
            const container = document.getElementById('floatingElements');
            const elementCount = 8;
            
            for (let i = 0; i < elementCount; i++) {
                const element = document.createElement('div');
                element.classList.add('floating-element');
                
                // Случайные размеры и позиции
                const size = Math.random() * 60 + 20;
                const posX = Math.random() * 90;
                const posY = Math.random() * 90;
                const delay = Math.random() * 15;
                const duration = Math.random() * 10 + 15;
                
                element.style.width = `${size}px`;
                element.style.height = `${size}px`;
                element.style.left = `${posX}%`;
                element.style.top = `${posY}%`;
                element.style.animationDelay = `${delay}s`;
                element.style.animationDuration = `${duration}s`;
                
                container.appendChild(element);
            }
        }
        
        // Инициализация плавающих элементов после загрузки страницы
        window.addEventListener('load', createFloatingElements);
        
        // Обработка кнопок в магазине
        document.querySelectorAll('.product-btn').forEach(btn => {
            btn.addEventListener('click', function(e) {
                e.preventDefault();
                if (this.textContent === 'В корзину') {
                    this.textContent = 'Добавлено!';
                    this.style.backgroundColor = 'var(--accent)';
                    this.style.borderColor = 'var(--accent)';
                    this.style.color = 'white';
                    
                    setTimeout(() => {
                        this.textContent = 'В корзину';
                        this.style.backgroundColor = '';
                        this.style.borderColor = 'var(--secondary)';
                        this.style.color = 'var(--secondary)';
                    }, 2000);
                }
            });
        });
    </script>
</body>
</html>
