<!DOCTYPE html>
<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 40px 20px;
        }
        
        .github-profile {
            max-width: 1300px;
            width: 100%;
            margin: 0 auto;
        }
        
        /* Hero Section with Glassmorphism */
        .hero {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 40px;
            padding: 60px 40px;
            margin-bottom: 40px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 25px 45px rgba(0, 0, 0, 0.3);
            animation: fadeInUp 0.8s ease;
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .studio-badge {
            display: inline-block;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 8px 20px;
            border-radius: 50px;
            font-size: 14px;
            font-weight: 600;
            letter-spacing: 2px;
            margin-bottom: 20px;
            color: white;
        }
        
        .hero h1 {
            font-size: 70px;
            font-weight: 800;
            background: linear-gradient(135deg, #fff 0%, #a8c0ff 50%, #3f2b6d 100%);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 15px;
        }
        
        .hero h3 {
            font-size: 28px;
            color: rgba(255, 255, 255, 0.8);
            font-weight: 500;
            margin-bottom: 10px;
        }
        
        .hero p {
            font-size: 18px;
            color: rgba(255, 255, 255, 0.6);
            margin-top: 20px;
        }
        
        /* Stats Section */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 25px;
            margin-bottom: 50px;
        }
        
        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 25px;
            padding: 30px 20px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }
        
        .stat-card:hover {
            transform: translateY(-10px);
            background: rgba(255, 255, 255, 0.1);
        }
        
        .stat-number {
            font-size: 45px;
            font-weight: 800;
            background: linear-gradient(135deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .stat-label {
            font-size: 16px;
            color: rgba(255, 255, 255, 0.7);
            margin-top: 10px;
            font-weight: 500;
        }
        
        /* Section Titles */
        .section-title {
            font-size: 42px;
            font-weight: 700;
            text-align: center;
            margin-bottom: 40px;
            background: linear-gradient(135deg, #fff, #a8c0ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        /* Skills Grid */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }
        
        .skill-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 30px;
            padding: 35px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s;
        }
        
        .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }
        
        .skill-icon {
            font-size: 50px;
            margin-bottom: 20px;
        }
        
        .skill-card h3 {
            font-size: 28px;
            color: white;
            margin-bottom: 20px;
        }
        
        .skill-items {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }
        
        .skill-tag {
            background: linear-gradient(135deg, #667eea, #764ba2);
            padding: 8px 18px;
            border-radius: 50px;
            font-size: 14px;
            font-weight: 500;
            color: white;
        }
        
        /* Pinned Projects */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }
        
        .project-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 30px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s;
        }
        
        .project-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 30px 50px rgba(0, 0, 0, 0.4);
        }
        
        .project-header {
            background: linear-gradient(135deg, #667eea, #764ba2);
            padding: 25px;
            text-align: center;
        }
        
        .project-icon {
            font-size: 60px;
        }
        
        .project-title {
            font-size: 24px;
            font-weight: 700;
            color: white;
            margin-top: 10px;
        }
        
        .project-body {
            padding: 25px;
        }
        
        .project-desc {
            color: rgba(255, 255, 255, 0.7);
            line-height: 1.6;
            margin-bottom: 20px;
            font-size: 14px;
        }
        
        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 20px;
        }
        
        .tech-badge {
            background: rgba(255, 255, 255, 0.1);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 12px;
            color: #a8c0ff;
        }
        
        .project-link {
            display: inline-block;
            color: #a8c0ff;
            text-decoration: none;
            font-weight: 600;
            transition: 0.3s;
        }
        
        .project-link:hover {
            color: white;
            padding-left: 5px;
        }
        
        /* Contact Section */
        .contact-section {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 40px;
            padding: 50px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .contact-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin: 30px 0;
        }
        
        .contact-btn {
            background: linear-gradient(135deg, #667eea, #764ba2);
            padding: 14px 35px;
            border-radius: 50px;
            color: white;
            text-decoration: none;
            font-weight: 600;
            transition: 0.3s;
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }
        
        .contact-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
        }
        
        .email {
            font-size: 18px;
            color: #a8c0ff;
            margin-top: 20px;
        }
        
        /* Footer */
        .footer {
            text-align: center;
            margin-top: 40px;
            padding: 30px;
            color: rgba(255, 255, 255, 0.5);
            font-size: 14px;
        }
        
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 40px;
            }
            
            .hero h3 {
                font-size: 20px;
            }
            
            .section-title {
                font-size: 30px;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="github-profile">
        
        <!-- Hero Section -->
        <div class="hero">
            <div class="studio-badge">✦ PREMIUM STUDIO ✦</div>
            <h1>Aeroost Studio</h1>
            <h3>Founded by <span style="color:#a8c0ff">Mohammad Javad</span></h3>
            <p>🎮 Where ideas transform into stunning apps, immersive games & web experiences</p>
        </div>
        
        <!-- Stats -->
        <div class="stats">
            <div class="stat-card">
                <div class="stat-number">15+</div>
                <div class="stat-label">Projects Completed</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">4+</div>
                <div class="stat-label">Years Experience</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">100%</div>
                <div class="stat-label">Client Satisfaction</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">24/7</div>
                <div class="stat-label">Support</div>
            </div>
        </div>
        
        <!-- Skills -->
        <div class="section-title">⚡ Core Expertise</div>
        <div class="skills-container">
            <div class="skill-card">
                <div class="skill-icon">📱</div>
                <h3>Mobile Apps</h3>
                <div class="skill-items">
                    <span class="skill-tag">Flutter</span>
                    <span class="skill-tag">Kotlin</span>
                    <span class="skill-tag">Swift</span>
                    <span class="skill-tag">Firebase</span>
                    <span class="skill-tag">REST API</span>
                </div>
            </div>
            
            <div class="skill-card">
                <div class="skill-icon">🎮</div>
                <h3>Game Dev</h3>
                <div class="skill-items">
                    <span class="skill-tag">Unity</span>
                    <span class="skill-tag">C#</span>
                    <span class="skill-tag">Godot</span>
                    <span class="skill-tag">Unreal</span>
                    <span class="skill-tag">2D/3D</span>
                </div>
            </div>
            
            <div class="skill-card">
                <div class="skill-icon">🌐</div>
                <h3>HTML5 Games</h3>
                <div class="skill-items">
                    <span class="skill-tag">Canvas API</span>
                    <span class="skill-tag">JavaScript</span>
                    <span class="skill-tag">CSS3</span>
                    <span class="skill-tag">WebGL</span>
                    <span class="skill-tag">Pure Code</span>
                </div>
            </div>
        </div>
        
        <!-- Pinned Projects (GitHub Pinned Section) -->
        <div class="section-title">📌 Pinned Projects</div>
        <div class="projects-grid">
            <div class="project-card">
                <div class="project-header">
                    <div class="project-icon">🎮</div>
                    <div class="project-title">Speed Runner</div>
                </div>
                <div class="project-body">
                    <div class="project-desc">
                        An addictive HTML5 endless runner game with smooth animations, particle effects, and leaderboard system. Pure JavaScript & Canvas.
                    </div>
                    <div class="project-tech">
                        <span class="tech-badge">HTML5</span>
                        <span class="tech-badge">Canvas</span>
                        <span class="tech-badge">JavaScript</span>
                    </div>
                    <a href="#" class="project-link">🔗 View Project →</a>
                </div>
            </div>
            
            <div class="project-card">
                <div class="project-header">
                    <div class="project-icon">📱</div>
                    <div class="project-title">ShopWave</div>
                </div>
                <div class="project-body">
                    <div class="project-desc">
                        Complete e-commerce mobile app with user auth, product listing, cart, payments, and real-time order tracking. Flutter + Firebase.
                    </div>
                    <div class="project-tech">
                        <span class="tech-badge">Flutter</span>
                        <span class="tech-badge">Firebase</span>
                        <span class="tech-badge">Dart</span>
                    </div>
                    <a href="#" class="project-link">🔗 View Project →</a>
                </div>
            </div>
            
            <div class="project-card">
                <div class="project-header">
                    <div class="project-icon">🎲</div>
                    <div class="project-title">Arena Battle</div>
                </div>
                <div class="project-body">
                    <div class="project-desc">
                        Real-time multiplayer battle arena game with matchmaking, chat, and ranked system. Built with Unity and Photon.
                    </div>
                    <div class="project-tech">
                        <span class="tech-badge">Unity</span>
                        <span class="tech-badge">C#</span>
                        <span class="tech-badge">Photon</span>
                    </div>
                    <a href="#" class="project-link">🔗 View Project →</a>
                </div>
            </div>
            
            <div class="project-card">
                <div class="project-header">
                    <div class="project-icon">🧩</div>
                    <div class="project-title">Puzzle Master</div>
                </div>
                <div class="project-body">
                    <div class="project-desc">
                        Classic sliding puzzle game with 3 difficulty levels, timer, move counter, and beautiful animations. HTML5/CSS3/JavaScript.
                    </div>
                    <div class="project-tech">
                        <span class="tech-badge">HTML5</span>
                        <span class="tech-badge">CSS Grid</span>
                        <span class="tech-badge">JavaScript</span>
                    </div>
                    <a href="#" class="project-link">🔗 View Project →</a>
                </div>
            </div>
        </div>
        
        <!-- Contact Section -->
        <div class="contact-section">
            <div class="section-title" style="font-size: 32px; margin-bottom: 20px;">🤝 Let's Create Something Amazing</div>
            <div class="contact-buttons">
                <a href="#" class="contact-btn">🐙 GitHub</a>
                <a href="mailto:aeroost.dev@gmail.com" class="contact-btn">✉️ Email Me</a>
                <a href="#" class="contact-btn">💼 LinkedIn</a>
                <a href="#" class="contact-btn">🎮 Itch.io</a>
            </div>
            <div class="email">
                📧 aeroost.dev@gmail.com
            </div>
        </div>
        
        <!-- Footer -->
        <div class="footer">
            <p>🚀 Open for collaboration | 💡 Turning ideas into reality | 🎮 Code. Create. Play. Repeat.</p>
            <p style="margin-top: 10px;">© 2024 Aeroost Studio — Premium App & Game Development</p>
        </div>
        
    </div>
</body>
</html>
