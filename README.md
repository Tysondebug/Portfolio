<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes" />
    <title>Tyson_Owner Team • Hack | Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800;900&family=Rajdhani:wght@300;400;500;600;700&display=swap" rel="stylesheet" />
    <style>
        /* ===== RESET & BASE ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --neon-pink: #ff006e;
            --neon-cyan: #00f5ff;
            --neon-purple: #b300ff;
            --neon-green: #00ff88;
            --neon-yellow: #ffe600;
            --neon-orange: #ff6600;
            --dark-bg: #0a0a12;
            --dark-card: rgba(16, 16, 35, 0.85);
            --glass-border: rgba(0, 245, 255, 0.12);
            --text-primary: #f0f0ff;
            --text-secondary: #b0b0d0;
        }

        html {
            scroll-behavior: smooth;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: 'Rajdhani', sans-serif;
            background: var(--dark-bg);
            color: var(--text-primary);
            min-height: 100vh;
            overflow-x: hidden;
            line-height: 1.6;
            position: relative;
        }

        /* ===== ANIMATED BG (lightened for mobile battery) ===== */
        .bg-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            overflow: hidden;
            pointer-events: none;
        }

        .bg-canvas .orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.15;
            animation: orbFloat 20s ease-in-out infinite alternate;
        }

        .bg-canvas .orb:nth-child(1) {
            width: 300px;
            height: 300px;
            background: var(--neon-pink);
            top: -10%;
            left: -30%;
            animation-duration: 25s;
        }

        .bg-canvas .orb:nth-child(2) {
            width: 280px;
            height: 280px;
            background: var(--neon-cyan);
            bottom: -10%;
            right: -30%;
            animation-duration: 20s;
            animation-delay: 3s;
        }

        .bg-canvas .orb:nth-child(3) {
            width: 200px;
            height: 200px;
            background: var(--neon-purple);
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            animation-duration: 30s;
            animation-delay: 5s;
        }

        @keyframes orbFloat {
            0% {
                transform: translate(0, 0) scale(1);
            }
            33% {
                transform: translate(30px, -20px) scale(1.1);
            }
            66% {
                transform: translate(-15px, 30px) scale(0.9);
            }
            100% {
                transform: translate(20px, -10px) scale(1.05);
            }
        }

        /* ===== SCANLINES (lighter) ===== */
        body::after {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: repeating-linear-gradient(0deg,
                    transparent,
                    transparent 2px,
                    rgba(0, 0, 0, 0.02) 2px,
                    rgba(0, 0, 0, 0.02) 4px);
            pointer-events: none;
            z-index: 999;
        }

        /* ===== GRID OVERLAY ===== */
        .grid-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: linear-gradient(rgba(0, 245, 255, 0.01) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 245, 255, 0.01) 1px, transparent 1px);
            background-size: 40px 40px;
            pointer-events: none;
            z-index: 1;
        }

        /* ===== CONTAINER (Mobile-First) ===== */
        .container {
            max-width: 100%;
            margin: 0 auto;
            padding: 0 12px;
            position: relative;
            z-index: 2;
        }

        /* ===== HEADER ===== */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            padding: 8px 0;
            background: rgba(10, 10, 18, 0.92);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-bottom: 1px solid var(--glass-border);
            transition: all 0.3s ease;
        }

        header.scrolled {
            background: rgba(10, 10, 18, 0.98);
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.6);
            border-bottom-color: var(--neon-cyan);
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 6px;
        }

        .logo-wrap {
            display: flex;
            align-items: center;
            gap: 8px;
            text-decoration: none;
            flex-shrink: 1;
            min-width: 0;
        }

        .logo-img {
            width: 34px;
            height: 34px;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid var(--neon-cyan);
            box-shadow: 0 0 12px rgba(0, 245, 255, 0.15);
            flex-shrink: 0;
        }

        .logo-text {
            font-family: 'Orbitron', sans-serif;
            font-size: 0.8rem;
            font-weight: 700;
            background: linear-gradient(135deg, var(--neon-cyan), var(--neon-pink));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: 0.2px;
            line-height: 1.1;
            white-space: nowrap;
        }

        .logo-text span {
            font-weight: 400;
            font-size: 0.5rem;
            -webkit-text-fill-color: var(--text-secondary);
            background: none;
            display: block;
            font-family: 'Rajdhani', sans-serif;
            letter-spacing: 0.3px;
        }

        /* ===== HAMBURGER ===== */
        .hamburger {
            display: flex;
            flex-direction: column;
            gap: 4px;
            cursor: pointer;
            padding: 8px 4px;
            background: none;
            border: none;
            z-index: 1001;
            flex-shrink: 0;
        }

        .hamburger span {
            display: block;
            width: 24px;
            height: 2.5px;
            background: var(--text-primary);
            border-radius: 2px;
            transition: all 0.3s ease;
        }

        .hamburger.active span:nth-child(1) {
            transform: rotate(45deg) translate(4px, 5px);
        }
        .hamburger.active span:nth-child(2) {
            opacity: 0;
        }
        .hamburger.active span:nth-child(3) {
            transform: rotate(-45deg) translate(4px, -5px);
        }

        /* ===== NAV LINKS (Mobile Overlay) ===== */
        .nav-links {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100vh;
            background: rgba(10, 10, 18, 0.98);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            flex-direction: column;
            padding: 80px 24px 40px;
            gap: 8px;
            border-bottom: none;
            transform: translateX(100%);
            transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            overflow-y: auto;
            justify-content: flex-start;
            align-items: stretch;
            z-index: 999;
            display: flex;
            list-style: none;
        }

        .nav-links.open {
            transform: translateX(0);
        }

        .nav-links a {
            font-size: 1.1rem;
            padding: 14px 16px;
            color: var(--text-primary);
            text-align: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.04);
            text-decoration: none;
            font-weight: 600;
            font-family: 'Rajdhani', sans-serif;
            transition: all 0.2s ease;
            border-radius: 8px;
            min-height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .nav-links a:active {
            background: rgba(255, 255, 255, 0.04);
        }

        .nav-cta {
            background: linear-gradient(135deg, var(--neon-pink), var(--neon-purple)) !important;
            color: #fff !important;
            font-weight: 700 !important;
            box-shadow: 0 0 20px rgba(255, 0, 110, 0.2);
            border: none !important;
            margin-top: 8px;
        }

        .nav-cta:active {
            transform: scale(0.97);
        }

        /* ===== HERO (Mobile First) ===== */
        .hero {
            padding: 90px 0 40px;
            text-align: center;
            position: relative;
            min-height: 100vh;
            display: flex;
            align-items: center;
        }

        .hero-content {
            width: 100%;
            animation: fadeUp 0.6s ease-out;
        }

        @keyframes fadeUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero-badge {
            display: inline-block;
            padding: 4px 14px;
            border-radius: 50px;
            font-size: 0.6rem;
            font-weight: 600;
            letter-spacing: 0.8px;
            text-transform: uppercase;
            background: rgba(0, 245, 255, 0.06);
            border: 1px solid var(--neon-cyan);
            color: var(--neon-cyan);
            margin-bottom: 16px;
            font-family: 'Orbitron', sans-serif;
            word-break: break-word;
        }

        .hero h1 {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(1.9rem, 9vw, 2.8rem);
            font-weight: 900;
            line-height: 1.1;
            margin-bottom: 8px;
            background: linear-gradient(135deg, var(--neon-cyan), var(--neon-pink), var(--neon-purple));
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientMove 4s ease-in-out infinite alternate;
            word-break: break-word;
        }

        @keyframes gradientMove {
            0% {
                background-position: 0% 50%;
            }
            100% {
                background-position: 100% 50%;
            }
        }

        .hero h2 {
            font-size: clamp(1rem, 4vw, 1.3rem);
            font-weight: 400;
            color: var(--text-secondary);
            margin-bottom: 12px;
            font-family: 'Rajdhani', sans-serif;
        }

        .hero h2 strong {
            color: var(--neon-cyan);
            font-weight: 600;
        }

        .hero p {
            max-width: 100%;
            margin: 0 auto 20px;
            font-size: clamp(0.9rem, 3vw, 1rem);
            color: var(--text-secondary);
            line-height: 1.6;
            padding: 0 2px;
        }

        .hero-btns {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
        }

        /* ===== BUTTONS (Mobile Touch) ===== */
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 6px;
            padding: 12px 20px;
            border-radius: 50px;
            font-family: 'Rajdhani', sans-serif;
            font-weight: 700;
            font-size: clamp(0.8rem, 3vw, 0.9rem);
            text-decoration: none;
            color: #fff;
            border: none;
            cursor: pointer;
            transition: all 0.2s ease;
            letter-spacing: 0.3px;
            min-height: 46px;
            touch-action: manipulation;
            flex: 1 1 auto;
            min-width: 120px;
        }

        .btn:active {
            transform: scale(0.95);
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--neon-pink), var(--neon-purple));
            box-shadow: 0 0 20px rgba(255, 0, 110, 0.15);
        }

        .btn-cyan {
            background: linear-gradient(135deg, var(--neon-cyan), #0099ff);
            box-shadow: 0 0 20px rgba(0, 245, 255, 0.1);
        }

        .btn-outline {
            background: transparent;
            border: 2px solid var(--neon-cyan);
            color: var(--neon-cyan);
        }

        .btn-glow {
            animation: pulseGlow 2.5s ease-in-out infinite;
        }

        @keyframes pulseGlow {
            0%,
            100% {
                box-shadow: 0 0 10px rgba(255, 0, 110, 0.1);
            }
            50% {
                box-shadow: 0 0 30px rgba(255, 0, 110, 0.3);
            }
        }

        /* ===== SECTION ===== */
        .section {
            padding: 50px 0;
        }

        .section-title {
            text-align: center;
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(1.6rem, 7vw, 2rem);
            font-weight: 700;
            margin-bottom: 30px;
            position: relative;
            color: #fff;
            line-height: 1.2;
        }

        .section-title .highlight {
            background: linear-gradient(135deg, var(--neon-cyan), var(--neon-pink));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 60px;
            height: 3px;
            margin: 10px auto 0;
            background: linear-gradient(90deg, var(--neon-cyan), var(--neon-pink));
            border-radius: 4px;
            box-shadow: 0 0 15px rgba(0, 245, 255, 0.1);
        }

        /* ===== ABOUT ===== */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 24px;
            align-items: center;
        }

        .about-image-wrap {
            position: relative;
            border-radius: 14px;
            overflow: hidden;
            border: 2px solid var(--glass-border);
            max-width: 300px;
            margin: 0 auto;
            width: 100%;
        }

        .about-image-wrap img {
            width: 100%;
            display: block;
        }

        .about-text h3 {
            font-size: clamp(1.3rem, 6vw, 1.6rem);
            font-weight: 700;
            font-family: 'Orbitron', sans-serif;
            margin-bottom: 10px;
            background: linear-gradient(135deg, var(--neon-cyan), var(--neon-pink));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-align: center;
        }

        .about-text p {
            color: var(--text-secondary);
            font-size: clamp(0.9rem, 3vw, 1rem);
            margin-bottom: 16px;
            text-align: center;
            line-height: 1.6;
        }

        .about-stats {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
            margin: 14px 0;
        }

        .stat-item {
            background: var(--dark-card);
            padding: 12px 10px;
            border-radius: 10px;
            border: 1px solid var(--glass-border);
            backdrop-filter: blur(4px);
            text-align: center;
        }

        .stat-item .label {
            font-size: 0.6rem;
            text-transform: uppercase;
            letter-spacing: 0.6px;
            color: var(--text-secondary);
            font-weight: 600;
        }

        .stat-item .value {
            font-size: clamp(0.85rem, 3vw, 1rem);
            font-weight: 700;
            color: #fff;
            margin-top: 2px;
            word-break: break-word;
        }

        .stat-item .value i {
            color: var(--neon-cyan);
            margin-right: 4px;
        }

        /* ===== SKILLS ===== */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
        }

        .skill-card {
            background: var(--dark-card);
            border-radius: 12px;
            padding: 18px 12px;
            border: 1px solid var(--glass-border);
            backdrop-filter: blur(4px);
            text-align: center;
            transition: all 0.2s ease;
        }

        .skill-card:active {
            transform: scale(0.96);
        }

        .skill-card .icon {
            font-size: 1.8rem;
            margin-bottom: 6px;
            display: inline-block;
            background: linear-gradient(135deg, var(--neon-cyan), var(--neon-pink));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .skill-card h3 {
            font-size: clamp(0.85rem, 3vw, 1rem);
            font-weight: 700;
            margin-bottom: 4px;
            color: #fff;
        }

        .skill-card p {
            color: var(--text-secondary);
            font-size: clamp(0.7rem, 2.5vw, 0.8rem);
            line-height: 1.3;
        }

        /* ===== CHANNELS ===== */
        .channels-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 16px;
            max-width: 100%;
            margin: 0 auto;
        }

        .channel-card {
            background: var(--dark-card);
            border-radius: 14px;
            padding: 20px 16px;
            border: 1px solid var(--glass-border);
            backdrop-filter: blur(4px);
            text-align: center;
            transition: all 0.2s ease;
        }

        .channel-card:active {
            transform: scale(0.98);
        }

        .channel-card .ch-icon {
            font-size: 2.2rem;
            margin-bottom: 8px;
            display: inline-block;
        }

        .channel-card.trading .ch-icon {
            color: var(--neon-yellow);
        }
        .channel-card.src .ch-icon {
            color: var(--neon-cyan);
        }
        .channel-card.hacking .ch-icon {
            color: var(--neon-green);
        }
        .channel-card.gaming .ch-icon {
            color: var(--neon-orange);
        }

        .channel-card h3 {
            font-size: clamp(1.1rem, 4.5vw, 1.3rem);
            font-weight: 700;
            margin-bottom: 4px;
            color: #fff;
        }

        .channel-card p {
            color: var(--text-secondary);
            font-size: clamp(0.8rem, 3vw, 0.9rem);
            margin-bottom: 14px;
            line-height: 1.4;
        }

        .channel-card .btn-sm {
            padding: 10px 16px;
            font-size: clamp(0.7rem, 2.5vw, 0.8rem);
            border-radius: 30px;
            font-weight: 600;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            color: #fff;
            min-height: 40px;
            touch-action: manipulation;
            transition: all 0.2s ease;
        }

        .channel-card .btn-sm:active {
            transform: scale(0.95);
        }

        .channel-card.trading .btn-sm {
            background: linear-gradient(135deg, #f7971e, #ffd200);
            box-shadow: 0 0 12px rgba(255, 215, 0, 0.1);
        }
        .channel-card.src .btn-sm {
            background: linear-gradient(135deg, #00b4db, #0083b0);
            box-shadow: 0 0 12px rgba(0, 180, 219, 0.1);
        }
        .channel-card.hacking .btn-sm {
            background: linear-gradient(135deg, #00b09b, #96c93d);
            box-shadow: 0 0 12px rgba(0, 176, 155, 0.1);
        }
        .channel-card.gaming .btn-sm {
            background: linear-gradient(135deg, #ff416c, #ff4b2b);
            box-shadow: 0 0 12px rgba(255, 65, 108, 0.1);
        }

        /* ===== HACK BUY ===== */
        .hack-buy {
            background: linear-gradient(135deg, rgba(255, 0, 110, 0.04), rgba(0, 245, 255, 0.02));
            border: 1px solid var(--glass-border);
            border-radius: 16px;
            padding: 28px 16px;
            text-align: center;
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(4px);
        }

        .hack-buy::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(0, 245, 255, 0.015), transparent, rgba(255, 0, 110, 0.015), transparent);
            animation: spin 20s linear infinite;
            pointer-events: none;
        }

        @keyframes spin {
            to {
                transform: rotate(360deg);
            }
        }

        .hack-buy .content {
            position: relative;
            z-index: 2;
        }

        .hack-buy .badge-icon {
            font-size: 2.2rem;
            display: block;
            margin-bottom: 6px;
        }

        .hack-buy h2 {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(1.2rem, 5.5vw, 1.5rem);
            font-weight: 700;
            margin-bottom: 6px;
            background: linear-gradient(135deg, var(--neon-yellow), var(--neon-orange));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            line-height: 1.2;
        }

        .hack-buy p {
            color: var(--text-secondary);
            font-size: clamp(0.85rem, 3vw, 0.95rem);
            max-width: 100%;
            margin: 0 auto 14px;
            line-height: 1.5;
        }

        .hack-buy .btn-buy {
            background: linear-gradient(135deg, var(--neon-yellow), var(--neon-orange));
            color: #0a0a12;
            font-weight: 800;
            padding: 14px 24px;
            font-size: clamp(0.9rem, 3.5vw, 1rem);
            box-shadow: 0 0 20px rgba(255, 230, 0, 0.08);
            min-height: 48px;
            border: none;
            border-radius: 50px;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            touch-action: manipulation;
        }

        .hack-buy .btn-buy:active {
            transform: scale(0.95);
        }

        .hack-buy .bot-tag {
            margin-top: 12px;
            font-size: clamp(0.75rem, 2.5vw, 0.85rem);
            color: var(--text-secondary);
        }

        .hack-buy .bot-tag strong {
            color: #fff;
            font-weight: 600;
        }

        .hack-buy .bot-tag i {
            color: var(--neon-cyan);
            margin-right: 4px;
        }

        /* ===== CONTACT ===== */
        .contact-wrap {
            display: grid;
            grid-template-columns: 1fr;
            gap: 16px;
            max-width: 100%;
            margin: 0 auto;
        }

        .contact-card {
            background: var(--dark-card);
            border-radius: 14px;
            padding: 24px 16px;
            border: 1px solid var(--glass-border);
            backdrop-filter: blur(4px);
            text-align: center;
        }

        .contact-card:active {
            transform: scale(0.98);
        }

        .contact-card .c-icon {
            font-size: 2rem;
            color: var(--neon-cyan);
            margin-bottom: 8px;
            display: inline-block;
        }

        .contact-card h3 {
            font-size: clamp(1.1rem, 4.5vw, 1.2rem);
            font-weight: 700;
            margin-bottom: 2px;
            color: #fff;
        }

        .contact-card p {
            color: var(--text-secondary);
            font-size: clamp(0.8rem, 3vw, 0.9rem);
            margin-bottom: 4px;
        }

        .contact-card .handle {
            font-size: clamp(0.9rem, 3.5vw, 1rem);
            font-weight: 600;
            color: var(--neon-cyan);
            font-family: 'Orbitron', sans-serif;
            letter-spacing: 0.2px;
            margin: 4px 0 12px;
            display: inline-block;
            padding: 2px 12px;
            border-radius: 30px;
            background: rgba(0, 245, 255, 0.04);
            border: 1px solid rgba(0, 245, 255, 0.06);
            word-break: break-all;
        }

        .contact-card .btn-sm {
            padding: 10px 20px;
            font-size: clamp(0.8rem, 3vw, 0.85rem);
            border-radius: 30px;
            font-weight: 600;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            color: #fff;
            background: linear-gradient(135deg, var(--neon-cyan), #0099ff);
            box-shadow: 0 0 12px rgba(0, 245, 255, 0.08);
            min-height: 42px;
            touch-action: manipulation;
            transition: all 0.2s ease;
        }

        .contact-card .btn-sm:active {
            transform: scale(0.95);
        }

        /* ===== FOOTER ===== */
        footer {
            padding: 24px 0 16px;
            border-top: 1px solid var(--glass-border);
            margin-top: 16px;
            text-align: center;
            background: rgba(10, 10, 18, 0.4);
            backdrop-filter: blur(4px);
        }

        footer .credit {
            font-size: clamp(0.85rem, 3vw, 1rem);
            font-weight: 600;
            color: var(--text-secondary);
            line-height: 1.5;
        }

        footer .credit strong {
            background: linear-gradient(135deg, var(--neon-cyan), var(--neon-pink));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        footer .credit i {
            color: var(--neon-pink);
            margin: 0 2px;
        }

        footer .copy {
            font-size: clamp(0.7rem, 2.5vw, 0.8rem);
            color: var(--text-secondary);
            opacity: 0.5;
            margin-top: 4px;
        }

        /* ============================================================ */
        /* ===== EXTRA SMALL PHONES (<= 360px) ===== */
        /* ============================================================ */
        @media (max-width: 360px) {
            .container {
                padding: 0 8px;
            }
            .hero h1 {
                font-size: 1.7rem;
            }
            .hero-badge {
                font-size: 0.5rem;
                padding: 3px 10px;
            }
            .btn {
                min-height: 40px;
                padding: 8px 14px;
                font-size: 0.75rem;
                min-width: 100px;
            }
            .skill-card {
                padding: 14px 8px;
            }
            .skill-card .icon {
                font-size: 1.5rem;
            }
            .skill-card h3 {
                font-size: 0.75rem;
            }
            .skill-card p {
                font-size: 0.65rem;
            }
            .about-stats {
                grid-template-columns: 1fr;
                gap: 6px;
            }
            .stat-item {
                padding: 8px 6px;
            }
            .channel-card {
                padding: 16px 12px;
            }
            .hack-buy {
                padding: 20px 12px;
            }
            .hack-buy h2 {
                font-size: 1rem;
            }
            .hack-buy .btn-buy {
                padding: 10px 16px;
                font-size: 0.8rem;
                min-height: 40px;
            }
            .contact-card {
                padding: 18px 12px;
            }
            .logo-text {
                font-size: 0.7rem;
            }
            .logo-img {
                width: 28px;
                height: 28px;
            }
            .nav-links a {
                font-size: 1rem;
                padding: 12px 12px;
                min-height: 44px;
            }
        }

        /* ============================================================ */
        /* ===== TABLETS & LARGER (scale up gracefully) ===== */
        /* ============================================================ */
        @media (min-width: 600px) {
            .container {
                padding: 0 24px;
                max-width: 540px;
            }
            .skills-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            .channels-grid {
                grid-template-columns: repeat(2, 1fr);
                max-width: 540px;
            }
            .contact-wrap {
                grid-template-columns: 1fr 1fr;
                max-width: 540px;
            }
            .about-image-wrap {
                max-width: 360px;
            }
            .hero h1 {
                font-size: 3rem;
            }
        }

        @media (min-width: 768px) {
            .container {
                max-width: 720px;
                padding: 0 32px;
            }
            .hero h1 {
                font-size: 3.8rem;
            }
            .section {
                padding: 70px 0;
            }
            .section-title {
                font-size: 2.4rem;
            }
            .skills-grid {
                grid-template-columns: repeat(3, 1fr);
                gap: 18px;
            }
            .channels-grid {
                max-width: 100%;
                grid-template-columns: repeat(2, 1fr);
            }
            .about-grid {
                grid-template-columns: 1fr 1fr;
                gap: 32px;
            }
            .about-text h3 {
                text-align: left;
            }
            .about-text p {
                text-align: left;
            }
            .hamburger {
                display: none;
            }
            .nav-links {
                position: static;
                transform: none;
                height: auto;
                background: transparent;
                backdrop-filter: none;
                padding: 0;
                flex-direction: row;
                gap: 16px;
                overflow: visible;
                width: auto;
            }
            .nav-links a {
                font-size: 0.85rem;
                padding: 6px 0;
                min-height: auto;
                border-bottom: none;
                color: var(--text-secondary);
                background: transparent !important;
                box-shadow: none !important;
            }
            .nav-links a:hover {
                color: #fff;
            }
            .nav-cta {
                padding: 6px 18px !important;
                font-size: 0.75rem !important;
                border-radius: 30px;
            }
            body {
                overflow-x: hidden;
            }
        }

        @media (min-width: 1024px) {
            .container {
                max-width: 960px;
                padding: 0 40px;
            }
            .hero h1 {
                font-size: 4.5rem;
            }
            .channels-grid {
                grid-template-columns: repeat(4, 1fr);
                gap: 24px;
            }
            .contact-wrap {
                max-width: 700px;
            }
        }

        /* ===== SCROLLBAR ===== */
        ::-webkit-scrollbar {
            width: 4px;
        }
        ::-webkit-scrollbar-track {
            background: var(--dark-bg);
        }
        ::-webkit-scrollbar-thumb {
            background: linear-gradient(var(--neon-cyan), var(--neon-pink));
            border-radius: 10px;
        }
    </style>
</head>
<body>

    <!-- ===== ANIMATED BG ===== -->
    <div class="bg-canvas">
        <div class="orb"></div>
        <div class="orb"></div>
        <div class="orb"></div>
    </div>
    <div class="grid-overlay"></div>

    <!-- ===== HEADER ===== -->
    <header id="header">
        <div class="container nav-container">
            <a href="#home" class="logo-wrap">
                <img src="https://www.image2url.com/r2/default/images/1782060674321-f50f86c8-f27d-41cf-b670-8910cd19d5b1.jpg" alt="Tyson_Owner" class="logo-img" loading="lazy" />
                <div class="logo-text">
                    Tyson_Owner Team
                    <span>• Hack</span>
                </div>
            </a>

            <ul class="nav-links" id="navLinks">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#channels">Channels</a></li>
                <li><a href="#contact">Contact</a></li>
                <li><a href="https://tyson-portfolio.github.io/Payment-Getaway/" target="_blank" class="nav-cta"><i class="fas fa-bolt"></i> Buy Hack</a></li>
            </ul>

            <button class="hamburger" id="hamburger" aria-label="Toggle menu">
                <span></span>
                <span></span>
                <span></span>
            </button>
        </div>
    </header>

    <!-- ===== HERO ===== -->
    <section class="hero" id="home">
        <div class="container hero-content">
            <div class="hero-badge"><i class="fas fa-shield-alt"></i> @TYSON_OK_WIN_HACK Specialist</div>
            <h1>TYSON DEVELOPER<br />PORTFOLIO</h1>
            <h2>Full Stack Developer &amp; <strong>Security Specialist</strong></h2>
            <p>Specializing in advanced development, security solutions, and innovative gaming modifications. Pushing the boundaries of technology with cutting-edge expertise.</p>
            <div class="hero-btns">
                <a href="#hack-buy-section" class="btn btn-primary btn-glow"><i class="fas fa-bolt"></i> 🔻 Buy Hack</a>
                <a href="#channels" class="btn btn-cyan"><i class="fab fa-telegram"></i> Explore</a>
                <a href="#about" class="btn btn-outline"><i class="fas fa-user"></i> About</a>
            </div>
        </div>
    </section>

    <!-- ===== ABOUT ===== -->
    <section class="section" id="about">
        <div class="container">
            <h2 class="section-title">About <span class="highlight">Me</span></h2>
            <div class="about-grid">
                <div class="about-image-wrap">
                    <img src="https://images.unsplash.com/photo-1536104968055-4d61aa56f46a?ixlib=rb-4.0.3&auto=format&fit=crop&w=880&q=80" alt="Tyson Developer" loading="lazy" />
                </div>
                <div class="about-text">
                    <h3>Hello, I'm a Tyson Developer</h3>
                    <p>I specialize in creating secure, efficient, and innovative solutions for web applications, Telegram bots, and gaming platforms. With a background in technology and a passion for coding, I constantly explore new horizons in development.</p>
                    <div class="about-stats">
                        <div class="stat-item">
                            <div class="label"><i class="fas fa-map-pin"></i> Country</div>
                            <div class="value">🇮🇳 India</div>
                        </div>
                        <div class="stat-item">
                            <div class="label"><i class="fas fa-calendar"></i> Age</div>
                            <div class="value">26</div>
                        </div>
                        <div class="stat-item">
                            <div class="label"><i class="fas fa-graduation-cap"></i> Education</div>
                            <div class="value">B.Tech</div>
                        </div>
                        <div class="stat-item">
                            <div class="label"><i class="fas fa-heart"></i> Hobbies</div>
                            <div class="value">Coding · Gaming · Designing · Web Dev</div>
                        </div>
                    </div>
                    <a href="#contact" class="btn btn-primary" style="width:100%;"><i class="fas fa-paper-plane"></i> Contact Me</a>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== SKILLS ===== -->
    <section class="section" id="skills">
        <div class="container">
            <h2 class="section-title">My <span class="highlight">Skills</span></h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <div class="icon"><i class="fab fa-php"></i></div>
                    <h3>PHP &amp; Python Bots</h3>
                    <p>Advanced bots for automation, data processing, and interaction.</p>
                </div>
                <div class="skill-card">
                    <div class="icon"><i class="fab fa-html5"></i></div>
                    <h3>HTML, CSS, JS</h3>
                    <p>Expert in responsive, interactive web interfaces.</p>
                </div>
                <div class="skill-card">
                    <div class="icon"><i class="fab fa-telegram"></i></div>
                    <h3>Telegram Bot Dev</h3>
                    <p>Feature-rich bots for automation &amp; notifications.</p>
                </div>
                <div class="skill-card">
                    <div class="icon"><i class="fas fa-paint-brush"></i></div>
                    <h3>Web UI/UX Design</h3>
                    <p>Intuitive interfaces with aesthetic appeal.</p>
                </div>
                <div class="skill-card">
                    <div class="icon"><i class="fas fa-robot"></i></div>
                    <h3>Automation Systems</h3>
                    <p>Complex systems to streamline processes.</p>
                </div>
                <div class="skill-card">
                    <div class="icon"><i class="fas fa-shield-alt"></i></div>
                    <h3>Security Solutions</h3>
                    <p>Secure apps &amp; data protection best practices.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== CHANNELS ===== -->
    <section class="section" id="channels">
        <div class="container">
            <h2 class="section-title">My <span class="highlight">Channels</span></h2>
            <div class="channels-grid">
                <!-- Trading -->
                <div class="channel-card trading">
                    <div class="ch-icon"><i class="fas fa-chart-line"></i></div>
                    <h3>Trading Channel</h3>
                    <p>Advanced strategies, market insights, and financial hacking.</p>
                    <a href="https://t.me/TYSON_OK_WIN_HACK" target="_blank" class="btn-sm"><i class="fab fa-telegram"></i> JOIN COLOR TRADING</a>
                </div>
                <!-- Source Code -->
                <div class="channel-card src">
                    <div class="ch-icon"><i class="fas fa-code"></i></div>
                    <h3>Source Code Channel</h3>
                    <p>Premium source codes, dev resources &amp; programming tools.</p>
                    <a href="https://t.me/nobita_src" target="_blank" class="btn-sm"><i class="fab fa-telegram"></i> JOIN ALL SRC</a>
                </div>
                <!-- Hacking -->
                <div class="channel-card hacking">
                    <div class="ch-icon"><i class="fas fa-shield-alt"></i></div>
                    <h3>Hacking Channel</h3>
                    <p>Ethical hacking, cybersecurity &amp; penetration testing.</p>
                    <a href="https://t.me/+fCz8oujNthtlMzJl" target="_blank" class="btn-sm"><i class="fab fa-telegram"></i> Join Hacking</a>
                </div>
                <!-- Gaming -->
                <div class="channel-card gaming">
                    <div class="ch-icon"><i class="fas fa-gamepad"></i></div>
                    <h3>Gaming Channel</h3>
                    <p>Latest hacks, mods, and cheats for BGMI &amp; PUBG Lite.</p>
                    <a href="https://t.me/+O60hs11qayAwMzFl" target="_blank" class="btn-sm"><i class="fab fa-telegram"></i> Join Gaming</a>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== HACK BUY ===== -->
    <section class="section" id="hack-buy-section">
        <div class="container">
            <div class="hack-buy">
                <div class="content">
                    <span class="badge-icon">🔻</span>
                    <h2>Hack Buy Direct From Developer 🔺</h2>
                    <p><strong>JISKO BUY KERNA 1 LEVEL WIN 🏆🎰</strong> — Premium hacks &amp; tools directly from <strong>@tyson_owner</strong>.</p>
                    <a href="https://tyson-portfolio.github.io/Payment-Getaway/" target="_blank" class="btn-buy"><i class="fas fa-rocket"></i> Buy Now — 1 Level Win</a>
                    <div class="bot-tag">
                        <i class="fab fa-telegram"></i> Telegram Hack Bot: <strong>@tyson_prediction_hack_bot</strong>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== CONTACT ===== -->
    <section class="section" id="contact">
        <div class="container">
            <h2 class="section-title">Contact <span class="highlight">Me</span></h2>
            <div class="contact-wrap">
                <div class="contact-card">
                    <div class="c-icon"><i class="fas fa-user-secret"></i></div>
                    <h3>Project Owner</h3>
                    <p>Business, collabs, or support.</p>
                    <div class="handle">@tyson_owner</div>
                    <a href="https://t.me/tyson_owner" target="_blank" class="btn-sm"><i class="fab fa-telegram"></i> Message on Telegram</a>
                </div>
                <div class="contact-card">
                    <div class="c-icon"><i class="fas fa-robot"></i></div>
                    <h3>Hack Bot</h3>
                    <p>Prediction &amp; hack tools.</p>
                    <div class="handle">@tyson_prediction_hack_bot</div>
                    <a href="https://t.me/tyson_prediction_hack_bot" target="_blank" class="btn-sm"><i class="fab fa-telegram"></i> Try Bot</a>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== FOOTER ===== -->
    <footer>
        <div class="container">
            <p class="credit">
                <i class="fas fa-code"></i> Made with <i class="fas fa-heart"></i> by <strong>@tyson_owner</strong>
            </p>
            <p class="copy">© 2026 Tyson Developer Portfolio. All rights reserved. Specialized in Any solutions.</p>
        </div>
    </footer>

    <!-- ===== SCRIPTS ===== -->
    <script>
        // === Hamburger ===
        const hamburger = document.getElementById('hamburger');
        const navLinks = document.getElementById('navLinks');

        hamburger.addEventListener('click', (e) => {
            e.stopPropagation();
            hamburger.classList.toggle('active');
            navLinks.classList.toggle('open');
            document.body.style.overflow = navLinks.classList.contains('open') ? 'hidden' : '';
        });

        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                hamburger.classList.remove('active');
                navLinks.classList.remove('open');
                document.body.style.overflow = '';
            });
        });

        // Close on outside tap
        document.addEventListener('click', (e) => {
            if (navLinks.classList.contains('open')) {
                const isNav = navLinks.contains(e.target);
                const isHamburger = hamburger.contains(e.target);
                if (!isNav && !isHamburger) {
                    hamburger.classList.remove('active');
                    navLinks.classList.remove('open');
                    document.body.style.overflow = '';
                }
            }
        });

        // === Header scroll ===
        const header = document.getElementById('header');
        window.addEventListener('scroll', () => {
            if (window.pageYOffset > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        }, { passive: true });

        // === Smooth scroll ===
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                const target = document.querySelector(targetId);
                if (target) {
                    e.preventDefault();
                    const offset = 60;
                    const top = target.getBoundingClientRect().top + window.pageYOffset - offset;
                    window.scrollTo({ top, behavior: 'smooth' });
                }
            });
        });

        console.log('📱 Tyson_Owner Team • Hack — Perfectly adjusted for phone screens.');
    </script>

</body>
</html>
