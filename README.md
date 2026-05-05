<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sahadatur Rahman Anik | README</title>
    <link href="https://cdn.tailwindcss.com" rel="stylesheet">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800;900&family=Space+Grotesk:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        :root {
            --bg: #0a0a0f;
            --bg-secondary: #12121a;
            --fg: #e8e8f0;
            --muted: #6b7280;
            --accent: #00ffaa;
            --accent-secondary: #00d4ff;
            --card: rgba(18, 18, 26, 0.8);
            --border: rgba(0, 255, 170, 0.15);
            --glow: rgba(0, 255, 170, 0.4);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Space Grotesk', sans-serif;
            background: var(--bg);
            color: var(--fg);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .font-display {
            font-family: 'Orbitron', sans-serif;
        }

        /* Animated Grid Background */
        .grid-bg {
            position: fixed;
            inset: 0;
            background-image: 
                linear-gradient(rgba(0, 255, 170, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 255, 170, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: gridMove 20s linear infinite;
            pointer-events: none;
            z-index: 0;
        }

        @keyframes gridMove {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        /* Floating Orbs */
        .orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.5;
            pointer-events: none;
            z-index: 0;
        }

        .orb-1 {
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(0, 255, 170, 0.3), transparent);
            top: -100px;
            right: -100px;
            animation: float1 15s ease-in-out infinite;
        }

        .orb-2 {
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(0, 212, 255, 0.25), transparent);
            bottom: -50px;
            left: -50px;
            animation: float2 18s ease-in-out infinite;
        }

        .orb-3 {
            width: 250px;
            height: 250px;
            background: radial-gradient(circle, rgba(255, 170, 0, 0.2), transparent);
            top: 50%;
            left: 30%;
            animation: float3 20s ease-in-out infinite;
        }

        @keyframes float1 {
            0%, 100% { transform: translate(0, 0) scale(1); }
            33% { transform: translate(-50px, 50px) scale(1.1); }
            66% { transform: translate(30px, -30px) scale(0.95); }
        }

        @keyframes float2 {
            0%, 100% { transform: translate(0, 0) scale(1); }
            50% { transform: translate(60px, -40px) scale(1.15); }
        }

        @keyframes float3 {
            0%, 100% { transform: translate(0, 0); }
            25% { transform: translate(40px, 30px); }
            50% { transform: translate(-30px, 50px); }
            75% { transform: translate(20px, -20px); }
        }

        /* Scanlines */
        .scanlines {
            position: fixed;
            inset: 0;
            background: repeating-linear-gradient(
                0deg,
                transparent,
                transparent 2px,
                rgba(0, 0, 0, 0.1) 2px,
                rgba(0, 0, 0, 0.1) 4px
            );
            pointer-events: none;
            z-index: 100;
            opacity: 0.3;
        }

        /* Main Container */
        .main-container {
            position: relative;
            z-index: 10;
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* Banner */
        .banner {
            position: relative;
            padding: 60px 40px;
            border-radius: 20px;
            background: linear-gradient(135deg, rgba(0, 255, 170, 0.05), rgba(0, 212, 255, 0.05));
            border: 1px solid var(--border);
            overflow: hidden;
            margin-bottom: 40px;
        }

        .banner::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--accent), var(--accent-secondary), transparent);
            animation: shimmer 3s linear infinite;
        }

        @keyframes shimmer {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .banner-glow {
            position: absolute;
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, var(--glow), transparent);
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            opacity: 0.3;
            animation: pulse 4s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: translate(-50%, -50%) scale(1); opacity: 0.3; }
            50% { transform: translate(-50%, -50%) scale(1.2); opacity: 0.5; }
        }

        .name-title {
            font-size: clamp(2rem, 5vw, 3.5rem);
            font-weight: 900;
            letter-spacing: 0.05em;
            background: linear-gradient(135deg, var(--fg), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            position: relative;
            animation: nameReveal 1s ease-out forwards;
            opacity: 0;
        }

        @keyframes nameReveal {
            0% { opacity: 0; transform: translateY(30px); }
            100% { opacity: 1; transform: translateY(0); }
        }

        .tagline {
            font-size: 1.1rem;
            color: var(--accent);
            margin-top: 10px;
            letter-spacing: 0.3em;
            text-transform: uppercase;
            animation: fadeSlide 1s ease-out 0.3s forwards;
            opacity: 0;
        }

        @keyframes fadeSlide {
            0% { opacity: 0; transform: translateX(-20px); }
            100% { opacity: 1; transform: translateX(0); }
        }

        .typing-text {
            font-family: 'Space Grotesk', monospace;
            color: var(--muted);
            margin-top: 20px;
            font-size: 0.95rem;
        }

        .typing-text span {
            color: var(--accent);
        }

        .cursor {
            display: inline-block;
            width: 2px;
            height: 1.2em;
            background: var(--accent);
            margin-left: 2px;
            animation: blink 1s infinite;
            vertical-align: middle;
        }

        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }

        /* Cards */
        .card {
            background: var(--card);
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 30px;
            margin-bottom: 24px;
            backdrop-filter: blur(10px);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }

        .card::after {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(135deg, rgba(0, 255, 170, 0.05), transparent);
            opacity: 0;
            transition: opacity 0.4s;
        }

        .card:hover {
            border-color: rgba(0, 255, 170, 0.4);
            transform: translateY(-4px);
            box-shadow: 0 20px 40px rgba(0, 255, 170, 0.1);
        }

        .card:hover::after {
            opacity: 1;
        }

        .card-title {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--fg);
            margin-bottom: 16px;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .card-title svg {
            color: var(--accent);
        }

        /* Stats */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 16px;
            margin-top: 20px;
        }

        .stat-item {
            text-align: center;
            padding: 20px 10px;
            background: rgba(0, 255, 170, 0.03);
            border-radius: 12px;
            border: 1px solid rgba(0, 255, 170, 0.1);
            transition: all 0.3s;
        }

        .stat-item:hover {
            background: rgba(0, 255, 170, 0.08);
            transform: scale(1.05);
        }

        .stat-number {
            font-size: 2rem;
            font-weight: 900;
            color: var(--accent);
            font-family: 'Orbitron', sans-serif;
        }

        .stat-label {
            font-size: 0.75rem;
            color: var(--muted);
            text-transform: uppercase;
            letter-spacing: 0.1em;
            margin-top: 4px;
        }

        /* Skills */
        .skill-item {
            margin-bottom: 16px;
        }

        .skill-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-size: 0.9rem;
        }

        .skill-name {
            color: var(--fg);
            font-weight: 500;
        }

        .skill-percent {
            color: var(--accent);
            font-family: 'Orbitron', sans-serif;
        }

        .skill-bar {
            height: 6px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 3px;
            overflow: hidden;
            position: relative;
        }

        .skill-progress {
            height: 100%;
            border-radius: 3px;
            background: linear-gradient(90deg, var(--accent), var(--accent-secondary));
            position: relative;
            width: 0;
            transition: width 1.5s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .skill-progress::after {
            content: '';
            position: absolute;
            right: 0;
            top: 0;
            bottom: 0;
            width: 20px;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4));
        }

        /* Social Links */
        .social-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 12px;
        }

        .social-link {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 16px 20px;
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid rgba(255, 255, 255, 0.08);
            border-radius: 12px;
            text-decoration: none;
            color: var(--fg);
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .social-link::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 3px;
            background: var(--accent);
            transform: scaleY(0);
            transition: transform 0.3s;
        }

        .social-link:hover {
            background: rgba(0, 255, 170, 0.08);
            border-color: rgba(0, 255, 170, 0.3);
            transform: translateX(8px);
        }

        .social-link:hover::before {
            transform: scaleY(1);
        }

        .social-link svg {
            color: var(--accent);
            flex-shrink: 0;
        }

        .social-link span {
            font-size: 0.9rem;
            font-weight: 500;
        }

        /* Tech Stack */
        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .tech-badge {
            padding: 8px 16px;
            background: linear-gradient(135deg, rgba(0, 255, 170, 0.1), rgba(0, 212, 255, 0.1));
            border: 1px solid rgba(0, 255, 170, 0.2);
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 500;
            color: var(--fg);
            transition: all 0.3s;
            cursor: default;
        }

        .tech-badge:hover {
            background: linear-gradient(135deg, rgba(0, 255, 170, 0.2), rgba(0, 212, 255, 0.2));
            transform: translateY(-2px);
            box-shadow: 0 5px 20px rgba(0, 255, 170, 0.2);
        }

        /* Terminal */
        .terminal {
            background: rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(0, 255, 170, 0.2);
            border-radius: 12px;
            overflow: hidden;
            font-family: 'Space Grotesk', monospace;
        }

        .terminal-header {
            background: rgba(0, 255, 170, 0.1);
            padding: 12px 16px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .terminal-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .terminal-body {
            padding: 20px;
            font-size: 0.9rem;
            line-height: 1.8;
        }

        .terminal-line {
            margin-bottom: 8px;
        }

        .terminal-prompt {
            color: var(--accent);
        }

        .terminal-command {
            color: var(--fg);
        }

        .terminal-output {
            color: var(--muted);
            padding-left: 20px;
        }

        /* Contact Button */
        .contact-btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 16px 32px;
            background: linear-gradient(135deg, var(--accent), var(--accent-secondary));
            color: var(--bg);
            font-weight: 700;
            font-size: 1rem;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            position: relative;
            overflow: hidden;
        }

        .contact-btn::before {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.2), transparent);
            opacity: 0;
            transition: opacity 0.3s;
        }

        .contact-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0, 255, 170, 0.3);
        }

        .contact-btn:hover::before {
            opacity: 1;
        }

        /* Footer Quote */
        .quote-section {
            text-align: center;
            padding: 40px 20px;
            margin-top: 40px;
            border-top: 1px solid var(--border);
        }

        .quote-text {
            font-size: 1.5rem;
            font-weight: 300;
            font-style: italic;
            color: var(--muted);
        }

        .quote-author {
            margin-top: 16px;
            color: var(--accent);
            font-family: 'Orbitron', sans-serif;
            font-size: 0.9rem;
            letter-spacing: 0.1em;
        }

        /* Reveal Animation */
        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Reduced Motion */
        @media (prefers-reduced-motion: reduce) {
            *, *::before, *::after {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: 0.01ms !important;
            }
        }

        /* Responsive */
        @media (max-width: 640px) {
            .banner {
                padding: 40px 24px;
            }
            
            .card {
                padding: 24px;
            }
            
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .social-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Background Elements -->
    <div class="grid-bg"></div>
    <div class="orb orb-1"></div>
    <div class="orb orb-2"></div>
    <div class="orb orb-3"></div>
    <div class="scanlines"></div>

    <div class="main-container">
        <!-- Banner Section -->
        <div class="banner">
            <div class="banner-glow"></div>
            <h1 class="font-display name-title">Sahadatur Rahman Anik</h1>
            <p class="tagline font-display">Born to make future</p>
            <div class="typing-text">
                <span>const</span> role = "<span id="typing-role"></span><span class="cursor"></span>
            </div>
        </div>

        <!-- About Card -->
        <div class="card reveal">
            <div class="card-title">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path>
                    <circle cx="12" cy="7" r="4"></circle>
                </svg>
                About Me
            </div>
            <p style="color: var(--muted); line-height: 1.8;">
                I am a passionate <strong style="color: var(--fg);">Digital Marketer</strong> and <strong style="color: var(--fg);">Web Developer</strong>, and the founder of <strong style="color: var(--accent);">SRA Digital Labs</strong>. I specialize in providing complete digital solutions including website development, social media marketing, SEO optimization, graphic design, photo editing, and video editing.
            </p>
            <p style="color: var(--muted); line-height: 1.8; margin-top: 12px;">
                With a deep interest in technology and creativity, I continuously improve my skills to deliver high-quality and modern solutions. I believe in <strong style="color: var(--accent);">smart work, consistency</strong>, and creating real value for clients.
            </p>
            <div class="stats-grid">
                <div class="stat-item">
                    <div class="stat-number" data-target="50">0</div>
                    <div class="stat-label">Projects</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number" data-target="35">0</div>
                    <div class="stat-label">Clients</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number" data-target="4">0</div>
                    <div class="stat-label">Years Exp</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number" data-target="100">0</div>
                    <div class="stat-label">Success Rate</div>
                </div>
            </div>
        </div>

        <!-- Skills Card -->
        <div class="card reveal">
            <div class="card-title">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"></polygon>
                </svg>
                Expertise
            </div>
            <div class="skill-item">
                <div class="skill-header">
                    <span class="skill-name">Web Development</span>
                    <span class="skill-percent">95%</span>
                </div>
                <div class="skill-bar">
                    <div class="skill-progress" data-width="95"></div>
                </div>
            </div>
            <div class="skill-item">
                <div class="skill-header">
                    <span class="skill-name">SEO Optimization</span>
                    <span class="skill-percent">92%</span>
                </div>
                <div class="skill-bar">
                    <div class="skill-progress" data-width="92"></div>
                </div>
            </div>
            <div class="skill-item">
                <div class="skill-header">
                    <span class="skill-name">Digital Marketing</span>
                    <span class="skill-percent">90%</span>
                </div>
                <div class="skill-bar">
                    <div class="skill-progress" data-width="90"></div>
                </div>
            </div>
            <div class="skill-item">
                <div class="skill-header">
                    <span class="skill-name">Graphic Design</span>
                    <span class="skill-percent">85%</span>
                </div>
                <div class="skill-bar">
                    <div class="skill-progress" data-width="85"></div>
                </div>
            </div>
            <div class="skill-item">
                <div class="skill-header">
                    <span class="skill-name">Video Editing</span>
                    <span class="skill-percent">88%</span>
                </div>
                <div class="skill-bar">
                    <div class="skill-progress" data-width="88"></div>
                </div>
            </div>
        </div>

        <!-- Tech Stack Card -->
        <div class="card reveal">
            <div class="card-title">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <polyline points="16 18 22 12 16 6"></polyline>
                    <polyline points="8 6 2 12 8 18"></polyline>
                </svg>
                Tech Stack
            </div>
            <div class="tech-stack">
                <span class="tech-badge">HTML5</span>
                <span class="tech-badge">CSS3</span>
                <span class="tech-badge">JavaScript</span>
                <span class="tech-badge">React</span>
                <span class="tech-badge">Node.js</span>
                <span class="tech-badge">WordPress</span>
                <span class="tech-badge">PHP</span>
                <span class="tech-badge">MySQL</span>
                <span class="tech-badge">MongoDB</span>
                <span class="tech-badge">Git</span>
                <span class="tech-badge">Figma</span>
                <span class="tech-badge">Photoshop</span>
                <span class="tech-badge">Premiere Pro</span>
                <span class="tech-badge">After Effects</span>
            </div>
        </div>

        <!-- Terminal Card -->
        <div class="card reveal">
            <div class="card-title">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <polyline points="4 17 10 11 4 5"></polyline>
                    <line x1="12" y1="19" x2="20" y2="19"></line>
                </svg>
                Quick Info
            </div>
            <div class="terminal">
                <div class="terminal-header">
                    <div class="terminal-dot" style="background: #ff5f56;"></div>
                    <div class="terminal-dot" style="background: #ffbd2e;"></div>
                    <div class="terminal-dot" style="background: #27c93f;"></div>
                </div>
                <div class="terminal-body">
                    <div class="terminal-line">
                        <span class="terminal-prompt">$</span> <span class="terminal-command">whoami</span>
                    </div>
                    <div class="terminal-line terminal-output">Sahadatur Rahman Anik | Founder @ SRA Digital Labs</div>
                    <div class="terminal-line">
                        <span class="terminal-prompt">$</span> <span class="terminal-command">cat skills.txt</span>
                    </div>
                    <div class="terminal-line terminal-output">Web Dev, SEO, Digital Marketing, Graphic Design</div>
                    <div class="terminal-line">
                        <span class="terminal-prompt">$</span> <span class="terminal-command">echo $MISSION</span>
                    </div>
                    <div class="terminal-line terminal-output">Building digital excellence, one project at a time</div>
                    <div class="terminal-line">
                        <span class="terminal-prompt">$</span> <span class="terminal-command">contact --email</span>
                    </div>
                    <div class="terminal-line terminal-output">sahadaturrahman2121@gmail.com</div>
                </div>
            </div>
        </div>

        <!-- Contact & Socials Card -->
        <div class="card reveal">
            <div class="card-title">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
                    <polyline points="22,6 12,13 2,6"></polyline>
                </svg>
                Connect With Me
            </div>
            <div class="social-grid">
                <a href="https://www.facebook.com/share/1LD3JLiEFj/" target="_blank" class="social-link">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
                    </svg>
                    <span>Facebook</span>
                </a>
                <a href="https://x.com/SahadaturAnik" target="_blank" class="social-link">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/>
                    </svg>
                    <span>Twitter / X</span>
                </a>
                <a href="https://www.instagram.com/sahadatur_rahman_anik" target="_blank" class="social-link">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
                        <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
                        <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
                    </svg>
                    <span>Instagram</span>
                </a>
                <a href="https://anikboss.rf.gd" target="_blank" class="social-link">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <circle cx="12" cy="12" r="10"></circle>
                        <line x1="2" y1="12" x2="22" y2="12"></line>
                        <path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"></path>
                    </svg>
                    <span>Portfolio</span>
                </a>
                <a href="https://sradigitallabs.rf.gd" target="_blank" class="social-link">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path>
                        <polyline points="9 22 9 12 15 12 15 22"></polyline>
                    </svg>
                    <span>SRA Digital Labs</span>
                </a>
                <a href="mailto:sahadaturrahman2121@gmail.com" class="social-link">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
                        <polyline points="22,6 12,13 2,6"></polyline>
                    </svg>
                    <span>Email Me</span>
                </a>
            </div>
            <div style="margin-top: 24px;">
                <a href="mailto:sahadaturrahman2121@gmail.com" class="contact-btn">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <line x1="22" y1="2" x2="11" y2="13"></line>
                        <polygon points="22 2 15 22 11 13 2 9 22 2"></polygon>
                    </svg>
                    Let's Build Something Amazing
                </a>
            </div>
        </div>

        <!-- Quote Section -->
        <div class="quote-section reveal">
            <p class="quote-text">"Through SRA Digital, I aim to build a trusted brand that offers professional, reliable, and result-driven digital services."</p>
            <p class="quote-author">- Sahadatur Rahman Anik</p>
        </div>

        <!-- Footer -->
        <div style="text-align: center; padding: 20px; color: var(--muted); font-size: 0.85rem;">
            <p>+880 1859-334774 | Dhaka, Bangladesh</p>
            <p style="margin-top: 8px; color: var(--accent);">Crafted with passion and code</p>
        </div>
    </div>

    <script>
        // Initialize all variables first
        const roles = [
            'Professional Web Developer',
            'SEO Expert',
            'Digital Marketer',
            'Founder @ SRA Digital Labs',
            'Creative Problem Solver'
        ];
        
        let roleIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typing-role');

        // Typing Effect
        function typeEffect() {
            if (!typingElement) return;
            
            const currentRole = roles[roleIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentRole.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentRole.substring(0, charIndex + 1);
                charIndex++;
            }

            let typeSpeed = isDeleting ? 50 : 100;

            if (!isDeleting && charIndex === currentRole.length) {
                typeSpeed = 2000;
                isDeleting = true;
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                roleIndex = (roleIndex + 1) % roles.length;
                typeSpeed = 500;
            }

            setTimeout(typeEffect, typeSpeed);
        }

        // Counter Animation
        function animateCounters() {
            const counters = document.querySelectorAll('.stat-number');
            counters.forEach(counter => {
                const target = parseInt(counter.getAttribute('data-target'), 10);
                const duration = 2000;
                const step = target / (duration / 16);
                let current = 0;

                const updateCounter = () => {
                    current += step;
                    if (current < target) {
                        counter.textContent = Math.ceil(current);
                        requestAnimationFrame(updateCounter);
                    } else {
                        counter.textContent = target + (target === 100 ? '%' : '+');
                    }
                };

                updateCounter();
            });
        }

        // Skill Bar Animation
        function animateSkillBars() {
            const skillBars = document.querySelectorAll('.skill-progress');
            skillBars.forEach((bar, index) => {
                const width = bar.getAttribute('data-width');
                setTimeout(() => {
                    bar.style.width = width + '%';
                }, index * 150);
            });
        }

        // Scroll Reveal
        function initScrollReveal() {
            const reveals = document.querySelectorAll('.reveal');
            
            const revealOnScroll = () => {
                reveals.forEach(element => {
                    const windowHeight = window.innerHeight;
                    const elementTop = element.getBoundingClientRect().top;
                    const revealPoint = 150;

                    if (elementTop < windowHeight - revealPoint) {
                        element.classList.add('active');
                        
                        // Trigger animations on first reveal
                        if (element.querySelector('.stat-number')) {
                            animateCounters();
                        }
                        if (element.querySelector('.skill-progress')) {
                            animateSkillBars();
                        }
                    }
                });
            };

            window.addEventListener('scroll', revealOnScroll);
            revealOnScroll(); // Initial check
        }

        // Mouse Trail Effect
        function initMouseTrail() {
            const trail = document.createElement('div');
            trail.style.cssText = `
                position: fixed;
                width: 20px;
                height: 20px;
                border-radius: 50%;
                background: radial-gradient(circle, rgba(0, 255, 170, 0.3), transparent);
                pointer-events: none;
                z-index: 9999;
                transition: transform 0.1s ease-out;
                mix-blend-mode: screen;
            `;
            document.body.appendChild(trail);

            let mouseX = 0, mouseY = 0;
            let trailX = 0, trailY = 0;

            document.addEventListener('mousemove', (e) => {
                mouseX = e.clientX;
                mouseY = e.clientY;
            });

            function animateTrail() {
                trailX += (mouseX - trailX) * 0.15;
                trailY += (mouseY - trailY) * 0.15;
                trail.style.transform = `translate(${trailX - 10}px, ${trailY - 10}px)`;
                requestAnimationFrame(animateTrail);
            }

            animateTrail();
        }

        // Initialize everything after DOM is ready
        document.addEventListener('DOMContentLoaded', () => {
            typeEffect();
            initScrollReveal();
            initMouseTrail();
        });
    </script>
</body>
</html>
