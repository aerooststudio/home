<!DOCTYPE html>
<html>
<head>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }
        
        .github-section {
            max-width: 1200px;
            width: 100%;
            margin: 0 auto;
        }
        
        /* Header Card */
        .header-card {
            background: white;
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 30px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            text-align: center;
            transition: transform 0.3s;
        }
        
        .header-card:hover {
            transform: translateY(-5px);
        }
        
        .studio-name {
            font-size: 48px;
            font-weight: bold;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 10px;
        }
        
        .founder {
            font-size: 20px;
            color: #666;
            margin-bottom: 20px;
        }
        
        .tagline {
            font-size: 18px;
            color: #888;
            margin-bottom: 30px;
        }
        
        .badge-container {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
            margin-top: 20px;
        }
        
        .badge {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 10px 20px;
            border-radius: 25px;
            font-size: 14px;
            font-weight: bold;
        }
        
        /* Skills Section */
        .skills {
            background: white;
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
        }
        
        .skills h2 {
            color: #333;
            margin-bottom: 20px;
            font-size: 28px;
        }
        
        .skill-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
        }
        
        .skill-category {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 15px;
            transition: all 0.3s;
        }
        
        .skill-category:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .skill-category h3 {
            color: #667eea;
            margin-bottom: 15px;
            font-size: 22px;
        }
        
        .skill-category ul {
            list-style: none;
        }
        
        .skill-category li {
            padding: 8px 0;
            color: #555;
            font-size: 16px;
        }
        
        .skill-category li:before {
            content: "▹";
            color: #764ba2;
            margin-right: 10px;
        }
        
        /* Pinned Repositories */
        .pinned-repos {
            background: white;
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
        }
        
        .pinned-repos h2 {
            color: #333;
            margin-bottom: 20px;
            font-size: 28px;
        }
        
        .repo-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .repo-card {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            padding: 20px;
            border-radius: 15px;
            transition: all 0.3s;
            cursor: pointer;
        }
        
        .repo-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }
        
        .repo-name {
            font-size: 20px;
            font-weight: bold;
            color: #667eea;
            margin-bottom: 10px;
        }
        
        .repo-desc {
            color: #666;
            font-size: 14px;
            margin-bottom: 15px;
            line-height: 1.5;
        }
        
        .repo-tags {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }
        
        .repo-tag {
            background: white;
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 12px;
            color: #667eea;
            font-weight: bold;
        }
        
        /* Contact Section */
        .contact {
            background: white;
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
        }
        
        .contact h2 {
            color: #333;
            margin-bottom: 20px;
            font-size: 28px;
        }
        
        .contact-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }
        
        .contact-btn {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 12px 25px;
            border-radius: 10px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s;
            display: inline-block;
        }
        
        .contact-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .email {
            font-size: 16px;
            color: #667eea;
            margin-top: 20px;
            font-weight: bold;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .studio-name {
                font-size: 32px;
            }
            
            .header-card {
                padding: 25px;
            }
            
            .skill-grid, .repo-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="github-section">
        
        <!-- Header Section -->
        <div class="header-card">
            <div class="studio-name">
                🎮 Aeroost Studio
            </div>
            <div class="founder">
                Founded by Mohammad Javad
            </div>
            <div class="tagline">
                Where ideas become apps, games, and digital experiences
            </div>
            <div class="badge-container">
                <span class="badge">📱 App Developer</span>
                <span class="badge">🎮 Game Developer</span>
                <span class="badge">🌐 HTML5 Games</span>
            </div>
        </div>
        
        <!-- Skills Section -->
        <div class="skills">
            <h2>⚡ Tech Stack & Expertise</h2>
            <div class="skill-grid">
                <div class="skill-category">
                    <h3>📱 Mobile Apps</h3>
                    <ul>
                        <li>Flutter</li>
                        <li>Kotlin</li>
                        <li>Swift</li>
                        <li>Firebase</li>
                    </ul>
                </div>
                <div class="skill-category">
                    <h3>🎮 Game Development</h3>
                    <ul>
                        <li>Unity & C#</li>
                        <li>Godot & GDScript</li>
                        <li>Unreal Engine</li>
                        <li>2D & 3D Games</li>
                    </ul>
                </div>
                <div class="skill-category">
                    <h3>🌐 HTML5 Games</h3>
                    <ul>
                        <li>Canvas API</li>
                        <li>JavaScript & CSS</li>
                        <li>WebGL</li>
                        <li>Pure Code (No Plugins)</li>
                    </ul>
                </div>
            </div>
        </div>
        
        <!-- Pinned Repositories Section -->
        <div class="pinned-repos">
            <h2>📌 Pinned Repositories</h2>
            <div class="repo-grid">
                <div class="repo-card">
                    <div class="repo-name">🎮 HTML5 Runner Game</div>
                    <div class="repo-desc">A fast-paced runner game built with pure HTML5 Canvas and JavaScript. No external libraries!</div>
                    <div class="repo-tags">
                        <span class="repo-tag">HTML5</span>
                        <span class="repo-tag">Canvas</span>
                        <span class="repo-tag">JavaScript</span>
                    </div>
                </div>
                
                <div class="repo-card">
                    <div class="repo-name">📱 E-Commerce App</div>
                    <div class="repo-desc">Complete mobile shopping app with Flutter & Firebase. Includes authentication, cart, and payments.</div>
                    <div class="repo-tags">
                        <span class="repo-tag">Flutter</span>
                        <span class="repo-tag">Firebase</span>
                        <span class="repo-tag">Dart</span>
                    </div>
                </div>
                
                <div class="repo-card">
                    <div class="repo-name">🎲 Multiplayer Game</div>
                    <div class="repo-desc">Online multiplayer game built with Unity and Photon. Real-time gameplay and chat system.</div>
                    <div class="repo-tags">
                        <span class="repo-tag">Unity</span>
                        <span class="repo-tag">C#</span>
                        <span class="repo-tag">Photon</span>
                    </div>
                </div>
                
                <div class="repo-card">
                    <div class="repo-name">🧩 Puzzle HTML5 Game</div>
                    <div class="repo-desc">Classic sliding puzzle game with smooth animations. Built with pure CSS Grid and JavaScript.</div>
                    <div class="repo-tags">
                        <span class="repo-tag">HTML5</span>
                        <span class="repo-tag">CSS Grid</span>
                        <span class="repo-tag">JavaScript</span>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Contact Section -->
        <div class="contact">
            <h2>📫 Let's Connect & Collaborate</h2>
            <div class="contact-links">
                <a href="https://github.com/Aeroost-Studio" class="contact-btn">🐙 GitHub</a>
                <a href="mailto:aeroost.dev@gmail.com" class="contact-btn">✉️ Email</a>
                <a href="#" class="contact-btn">💼 LinkedIn</a>
                <a href="#" class="contact-btn">📱 Twitter</a>
            </div>
            <div class="email">
                📧 aeroost.dev@gmail.com
            </div>
        </div>
        
    </div>
</body>
</html>
