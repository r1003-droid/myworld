# myworld
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Blog - Thoughts & Stories</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            line-height: 1.7;
            color: #1a1a1a;
            background: #0a0a0a;
            overflow-x: hidden;
        }

        /* Animated background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(45deg, #0a0a0a, #1a1a2e, #16213e);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Floating particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            width: 3px;
            height: 3px;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            animation: float 20s infinite;
        }

        .particle:nth-child(1) { left: 10%; animation-delay: 0s; }
        .particle:nth-child(2) { left: 20%; animation-delay: 2s; }
        .particle:nth-child(3) { left: 30%; animation-delay: 4s; }
        .particle:nth-child(4) { left: 40%; animation-delay: 6s; }
        .particle:nth-child(5) { left: 50%; animation-delay: 8s; }
        .particle:nth-child(6) { left: 60%; animation-delay: 10s; }
        .particle:nth-child(7) { left: 70%; animation-delay: 12s; }
        .particle:nth-child(8) { left: 80%; animation-delay: 14s; }
        .particle:nth-child(9) { left: 90%; animation-delay: 16s; }

        @keyframes float {
            0%, 100% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10%, 90% { opacity: 1; }
            50% { transform: translateY(-100vh) rotate(360deg); }
        }

        header {
            background: transparent;
            color: white;
            padding: 8rem 0 4rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(102, 126, 234, 0.1) 0%, transparent 70%);
            animation: pulse 8s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.2); opacity: 0.8; }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
            position: relative;
            z-index: 1;
        }

        header h1 {
            font-size: 4.5rem;
            margin-bottom: 1rem;
            font-weight: 700;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: shimmer 3s ease-in-out infinite;
            letter-spacing: -2px;
        }

        @keyframes shimmer {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        header p {
            font-size: 1.3rem;
            opacity: 0.8;
            font-style: italic;
            font-family: 'Georgia', serif;
        }

        nav {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            padding: 1rem 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 3rem;
            justify-content: center;
        }

        nav a {
            text-decoration: none;
            color: #fff;
            font-weight: 500;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            transition: all 0.3s;
            position: relative;
            padding: 0.5rem 0;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, #667eea, #764ba2);
            transition: width 0.3s;
        }

        nav a:hover::after {
            width: 100%;
        }

        nav a:hover {
            color: #667eea;
        }

        main {
            padding: 4rem 0;
        }

        .featured-post {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            margin-bottom: 4rem;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.5s;
            position: relative;
        }

        .featured-post::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.7s;
        }

        .featured-post:hover::before {
            left: 100%;
        }

        .featured-post:hover {
            transform: translateY(-10px);
            box-shadow: 0 12px 48px rgba(102, 126, 234, 0.3);
        }

        .featured-image {
            width: 100%;
            height: 500px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 5rem;
            position: relative;
            overflow: hidden;
        }

        .featured-image::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.2) 0%, transparent 70%);
            animation: rotate 10s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .featured-content {
            padding: 3rem;
        }

        .featured-content h2 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
            color: #fff;
            font-weight: 700;
        }

        .post-meta {
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.95rem;
            margin-bottom: 1.5rem;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
        }

        .featured-content p {
            color: rgba(255, 255, 255, 0.8);
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
        }

        .post-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(380px, 1fr));
            gap: 2.5rem;
            margin-top: 2rem;
        }

        .post-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
        }

        .post-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1), rgba(118, 75, 162, 0.1));
            opacity: 0;
            transition: opacity 0.4s;
        }

        .post-card:hover::before {
            opacity: 1;
        }

        .post-card:hover {
            transform: translateY(-12px) scale(1.02);
            box-shadow: 0 12px 40px rgba(102, 126, 234, 0.4);
        }

        .post-thumbnail {
            width: 100%;
            height: 250px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            position: relative;
            overflow: hidden;
        }

        .post-thumbnail::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.2);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .post-card:hover .post-thumbnail::after {
            width: 500px;
            height: 500px;
        }

        .post-card:nth-child(1) .post-thumbnail {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .post-card:nth-child(2) .post-thumbnail {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .post-card:nth-child(3) .post-thumbnail {
            background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
        }

        .post-card:nth-child(4) .post-thumbnail {
            background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
        }

        .post-card:nth-child(5) .post-thumbnail {
            background: linear-gradient(135deg, #fa709a 0%, #fee140 100%);
        }

        .post-card:nth-child(6) .post-thumbnail {
            background: linear-gradient(135deg, #30cfd0 0%, #330867 100%);
        }

        .post-body {
            padding: 2rem;
            position: relative;
            z-index: 1;
        }

        .post-body h3 {
            margin-bottom: 0.8rem;
            color: #fff;
            font-size: 1.5rem;
            font-weight: 600;
        }

        .post-body p {
            color: rgba(255, 255, 255, 0.7);
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }

        .read-more {
            color: #667eea;
            text-decoration: none;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            transition: all 0.3s;
        }

        .read-more:hover {
            gap: 1rem;
            color: #764ba2;
        }

        .category {
            display: inline-block;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 0.4rem 1rem;
            border-radius: 25px;
            font-size: 0.75rem;
            margin-bottom: 1rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
        }

        footer {
            background: rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(10px);
            color: white;
            text-align: center;
            padding: 3rem 0;
            margin-top: 6rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            color: #fff;
            font-weight: 700;
            position: relative;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 60px;
            height: 4px;
            background: linear-gradient(90deg, #667eea, #764ba2);
            border-radius: 2px;
        }

        /* Scroll reveal animation */
        .reveal {
            opacity: 0;
            transform: translateY(50px);
            animation: reveal 0.8s ease forwards;
        }

        @keyframes reveal {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .post-card:nth-child(1) { animation-delay: 0.1s; }
        .post-card:nth-child(2) { animation-delay: 0.2s; }
        .post-card:nth-child(3) { animation-delay: 0.3s; }
        .post-card:nth-child(4) { animation-delay: 0.4s; }
        .post-card:nth-child(5) { animation-delay: 0.5s; }
        .post-card:nth-child(6) { animation-delay: 0.6s; }

        @media (max-width: 768px) {
            header h1 {
                font-size: 2.5rem;
            }

            .post-grid {
                grid-template-columns: 1fr;
            }

            nav ul {
                gap: 1.5rem;
            }

            .featured-image {
                height: 300px;
            }

            .featured-content {
                padding: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Animated background -->
    <div class="bg-animation"></div>
    
    <!-- Floating particles -->
    <div class="particles">
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>
    </div>

    <header>
        <div class="container">
            <h1>My Blog</h1>
            <p>Where thoughts become stories and ideas take flight</p>
        </div>
    </header>

    <nav>
        <div class="container">
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#archive">Archive</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <main>
        <div class="container">
            <article class="featured-post reveal">
                <div class="featured-image">✨</div>
                <div class="featured-content">
                    <span class="category">Featured</span>
                    <h2>Welcome to My Blog: A New Beginning</h2>
                    <div class="post-meta">Published on February 9, 2026 • 5 min read</div>
                    <p>Starting a blog has been on my mind for a while now. There's something special about creating a space where thoughts can flow freely, where stories can be shared, and where connections can be made with people from all walks of life. This is that space.</p>
                    <p>In this blog, I'll be sharing my experiences, insights, and musings on topics that matter to me. Whether it's technology, creativity, personal growth, or just everyday observations, you'll find it here. I believe that everyone has a unique perspective worth sharing, and I'm excited to share mine with you.</p>
                    <a href="#" class="read-more">Read full article →</a>
                </div>
            </article>

            <h2 class="section-title">Recent Posts</h2>
            
            <div class="post-grid">
                <article class="post-card reveal">
                    <div class="post-thumbnail">💡</div>
                    <div class="post-body">
                        <span class="category">Technology</span>
                        <h3>The Future of Web Development</h3>
                        <div class="post-meta">February 7, 2026 • 4 min read</div>
                        <p>Exploring the latest trends and technologies shaping how we build for the web in 2026 and beyond.</p>
                        <a href="#" class="read-more">Read more →</a>
                    </div>
                </article>

                <article class="post-card reveal">
                    <div class="post-thumbnail">🎨</div>
                    <div class="post-body">
                        <span class="category">Design</span>
                        <h3>Finding Inspiration in Everyday Life</h3>
                        <div class="post-meta">February 5, 2026 • 3 min read</div>
                        <p>How paying attention to the small details around us can fuel creativity and innovation.</p>
                        <a href="#" class="read-more">Read more →</a>
                    </div>
                </article>

                <article class="post-card reveal">
                    <div class="post-thumbnail">🚀</div>
                    <div class="post-body">
                        <span class="category">Productivity</span>
                        <h3>Building Better Habits</h3>
                        <div class="post-meta">February 3, 2026 • 6 min read</div>
                        <p>A practical guide to creating sustainable habits that actually stick and improve your daily life.</p>
                        <a href="#" class="read-more">Read more →</a>
                    </div>
                </article>

                <article class="post-card reveal">
                    <div class="post-thumbnail">🌍</div>
                    <div class="post-body">
                        <span class="category">Travel</span>
                        <h3>Adventures in Remote Work</h3>
                        <div class="post-meta">January 30, 2026 • 5 min read</div>
                        <p>Stories and lessons learned from working remotely while exploring different corners of the world.</p>
                        <a href="#" class="read-more">Read more →</a>
                    </div>
                </article>

                <article class="post-card reveal">
                    <div class="post-thumbnail">📚</div>
                    <div class="post-body">
                        <span class="category">Learning</span>
                        <h3>Books That Changed My Perspective</h3>
                        <div class="post-meta">January 28, 2026 • 4 min read</div>
                        <p>A curated list of books that challenged my thinking and opened new doors of understanding.</p>
                        <a href="#" class="read-more">Read more →</a>
                    </div>
                </article>

                <article class="post-card reveal">
                    <div class="post-thumbnail">🎯</div>
                    <div class="post-body">
                        <span class="category">Personal Growth</span>
                        <h3>Setting Goals That Matter</h3>
                        <div class="post-meta">January 25, 2026 • 7 min read</div>
                        <p>Moving beyond generic resolutions to create meaningful objectives aligned with your values.</p>
                        <a href="#" class="read-more">Read more →</a>
                    </div>
                </article>
            </div>
        </div>
    </main>

    <footer>
        <div class="container">
            <p>&copy; 2026 My Blog. All rights reserved.</p>
            <p style="margin-top: 0.5rem; opacity: 0.8;">Made with passion and purpose ✨</p>
        </div>
    </footer>
</body>
</html>