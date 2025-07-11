<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ritesh Kumar - Animated Profile</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'JetBrains Mono', monospace;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: #ffffff;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        
        .header {
            text-align: center;
            margin-bottom: 3rem;
            animation: fadeInUp 1s ease-out;
        }
        
        .header h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            background-size: 200% 200%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 3s ease-in-out infinite;
        }
        
        .header h3 {
            font-size: 1.5rem;
            font-weight: 400;
            opacity: 0.9;
            margin-bottom: 2rem;
            animation: typewriter 2s steps(40) 1s both;
        }
        
        .profile-image {
            width: 300px;
            height: 200px;
            margin: 0 auto 2rem;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            animation: float 3s ease-in-out infinite;
        }
        
        .profile-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }
        
        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 15px;
            padding: 2rem;
            text-align: center;
            transition: all 0.3s ease;
            animation: slideInUp 0.6s ease-out forwards;
            opacity: 0;
            transform: translateY(50px);
        }
        
        .stat-card:nth-child(1) { animation-delay: 0.1s; }
        .stat-card:nth-child(2) { animation-delay: 0.2s; }
        .stat-card:nth-child(3) { animation-delay: 0.3s; }
        .stat-card:nth-child(4) { animation-delay: 0.4s; }
        
        .stat-card:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 30px 60px rgba(0,0,0,0.3);
            background: rgba(255, 255, 255, 0.2);
        }
        
        .stat-card h3 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: #4ecdc4;
        }
        
        .stat-card p {
            font-size: 0.9rem;
            line-height: 1.6;
            opacity: 0.9;
        }
        
        .tech-stack {
            margin-bottom: 3rem;
        }
        
        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 2rem;
            position: relative;
            animation: fadeInUp 1s ease-out;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            border-radius: 2px;
        }
        
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1.5rem;
        }
        
        .tech-item {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            padding: 1.5rem;
            text-align: center;
            transition: all 0.3s ease;
            animation: scaleIn 0.5s ease-out forwards;
            opacity: 0;
            transform: scale(0.8);
        }
        
        .tech-item:nth-child(1) { animation-delay: 0.1s; }
        .tech-item:nth-child(2) { animation-delay: 0.2s; }
        .tech-item:nth-child(3) { animation-delay: 0.3s; }
        .tech-item:nth-child(4) { animation-delay: 0.4s; }
        .tech-item:nth-child(5) { animation-delay: 0.5s; }
        .tech-item:nth-child(6) { animation-delay: 0.6s; }
        .tech-item:nth-child(7) { animation-delay: 0.7s; }
        .tech-item:nth-child(8) { animation-delay: 0.8s; }
        
        .tech-item:hover {
            transform: scale(1.1) rotate(5deg);
            background: rgba(255, 255, 255, 0.2);
            box-shadow: 0 15px 30px rgba(0,0,0,0.3);
        }
        
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }
        
        .project-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 15px;
            padding: 2rem;
            transition: all 0.3s ease;
            animation: slideInLeft 0.8s ease-out forwards;
            opacity: 0;
            transform: translateX(-100px);
        }
        
        .project-card:nth-child(1) { animation-delay: 0.2s; }
        .project-card:nth-child(2) { animation-delay: 0.4s; }
        .project-card:nth-child(3) { animation-delay: 0.6s; }
        
        .project-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 25px 50px rgba(0,0,0,0.3);
            background: rgba(255, 255, 255, 0.2);
        }
        
        .project-card h3 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: #ff6b6b;
        }
        
        .project-card p {
            font-size: 0.9rem;
            line-height: 1.6;
            opacity: 0.9;
        }
        
        .connect-section {
            text-align: center;
            margin-top: 3rem;
        }
        
        .connect-buttons {
            display: flex;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
            margin-top: 2rem;
        }
        
        .connect-btn {
            display: inline-block;
            padding: 1rem 2rem;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            text-decoration: none;
            color: white;
            border-radius: 25px;
            font-weight: 500;
            transition: all 0.3s ease;
            animation: bounceIn 0.8s ease-out forwards;
            opacity: 0;
            transform: scale(0.3);
        }
        
        .connect-btn:nth-child(1) { animation-delay: 0.1s; }
        .connect-btn:nth-child(2) { animation-delay: 0.2s; }
        .connect-btn:nth-child(3) { animation-delay: 0.3s; }
        
        .connect-btn:hover {
            transform: scale(1.1);
            box-shadow: 0 10px 20px rgba(0,0,0,0.3);
            background: linear-gradient(45deg, #4ecdc4, #ff6b6b);
        }
        
        .floating-particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .particle {
            position: absolute;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            animation: float-particle 15s infinite linear;
        }
        
        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }
        
        @keyframes typewriter {
            0% { width: 0; }
            100% { width: 100%; }
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }
        
        @keyframes fadeInUp {
            0% {
                opacity: 0;
                transform: translateY(30px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes slideInUp {
            0% {
                opacity: 0;
                transform: translateY(50px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes slideInLeft {
            0% {
                opacity: 0;
                transform: translateX(-100px);
            }
            100% {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        @keyframes scaleIn {
            0% {
                opacity: 0;
                transform: scale(0.8);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }
        
        @keyframes bounceIn {
            0% {
                opacity: 0;
                transform: scale(0.3);
            }
            50% {
                transform: scale(1.05);
            }
            70% {
                transform: scale(0.9);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }
        
        @keyframes float-particle {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }
        
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5rem;
            }
            
            .header h3 {
                font-size: 1.2rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
            
            .connect-buttons {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <div class="floating-particles"></div>
    
    <div class="container">
        <div class="header">
            <h1>Hi 👋, I'm Ritesh Kumar</h1>
            <h3>An aspiring Software Engineer from India</h3>
            <div class="profile-image">
                <img src="https://cdn.dribbble.com/users/1162077/screenshots/3848914/programmer.gif" alt="Programming Animation">
            </div>
        </div>
        
        <div class="stats-grid">
            <div class="stat-card">
                <h3>🔭 Currently Working On</h3>
                <p>Machine Learning projects exploring deep learning and computer vision</p>
            </div>
            <div class="stat-card">
                <h3>🌱 Currently Learning</h3>
                <p>SpringBoot, TensorFlow, and Keras for full-stack ML development</p>
            </div>
            <div class="stat-card">
                <h3>💬 Ask Me About</h3>
                <p>Python, Machine Learning, SpringBoot, and SQL optimization</p>
            </div>
            <div class="stat-card">
                <h3>📫 Contact Me</h3>
                <p>riteshkumar90359@gmail.com</p>
            </div>
        </div>
        
        <div class="tech-stack">
            <h2 class="section-title">🛠️ Tech Stack</h2>
            <div class="tech-grid">
                <div class="tech-item">Python</div>
                <div class="tech-item">C/C++</div>
                <div class="tech-item">JavaScript</div>
                <div class="tech-item">SpringBoot</div>
                <div class="tech-item">TensorFlow</div>
                <div class="tech-item">OpenCV</div>
                <div class="tech-item">MySQL</div>
                <div class="tech-item">Git</div>
            </div>
        </div>
        
        <div class="projects-section">
            <h2 class="section-title">🚀 Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3>🧠 Age Gender Prediction</h3>
                    <p>Built a sophisticated face detection and classification model using deep learning techniques with TensorFlow and OpenCV.</p>
                </div>
                <div class="project-card">
                    <h3>🍔 Food & Recipe API App</h3>
                    <p>Created a responsive food recipe search application using MealDB API with modern JavaScript and CSS animations.</p>
                </div>
                <div class="project-card">
                    <h3>💉 Blood Donation Forecast</h3>
                    <p>Developed a machine learning model to predict blood donations using Random Forest and GridSearchCV optimization.</p>
                </div>
            </div>
        </div>
        
        <div class="connect-section">
            <h2 class="section-title">📫 Let's Connect</h2>
            <div class="connect-buttons">
                <a href="https://www.linkedin.com/in/ritesh-kumar-b3a654253" class="connect-btn">LinkedIn</a>
                <a href="https://github.com/RiteshKumar2e" class="connect-btn">GitHub</a>
                <a href="https://riteshkumar2e.github.io/Portfolio/" class="connect-btn">Portfolio</a>
            </div>
        </div>
    </div>
    
    <script>
        // Create floating particles
        function createParticles() {
            const container = document.querySelector('.floating-particles');
            const particleCount = 50;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                
                // Random size between 2-6px
                const size = Math.random() * 4 + 2;
                particle.style.width = size + 'px';
                particle.style.height = size + 'px';
                
                // Random horizontal position
                particle.style.left = Math.random() * 100 + '%';
                
                // Random animation duration
                particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
                
                // Random delay
                particle.style.animationDelay = Math.random() * 15 + 's';
                
                container.appendChild(particle);
            }
        }
        
        // Initialize particles when page loads
        window.addEventListener('load', createParticles);
        
        // Add typing effect for skills
        const techItems = document.querySelectorAll('.tech-item');
        techItems.forEach((item, index) => {
            item.addEventListener('mouseenter', () => {
                item.style.animation = 'none';
                item.offsetHeight; // Trigger reflow
                item.style.animation = `scaleIn 0.3s ease-out forwards`;
            });
        });
        
        // Add parallax effect to cards
        document.addEventListener('mousemove', (e) => {
            const cards = document.querySelectorAll('.stat-card, .project-card');
            const mouseX = e.clientX / window.innerWidth;
            const mouseY = e.clientY / window.innerHeight;
            
            cards.forEach((card, index) => {
                const speed = (index % 2 === 0) ? 2 : -2;
                const x = (mouseX - 0.5) * speed;
                const y = (mouseY - 0.5) * speed;
                
                card.style.transform = `translateX(${x}px) translateY(${y}px)`;
            });
        });
        
        // Add smooth scrolling for internal links
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
