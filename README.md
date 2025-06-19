<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sanjay - Creative Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            overflow-x: hidden;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Hero Section */
        .hero {
            text-align: center;
            padding: 60px 0;
            position: relative;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="25" cy="25" r="1" fill="rgba(255,255,255,0.1)"/><circle cx="75" cy="75" r="1" fill="rgba(255,255,255,0.1)"/><circle cx="50" cy="10" r="1" fill="rgba(255,255,255,0.1)"/><circle cx="10" cy="90" r="1" fill="rgba(255,255,255,0.1)"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
            opacity: 0.3;
            animation: float 6s ease-in-out infinite;
        }

        .hero h1 {
            font-size: 4rem;
            font-weight: 700;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #fff, #ff6b6b, #4ecdc4);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 3s ease-in-out infinite;
        }

        .hero .subtitle {
            font-size: 1.4rem;
            margin-bottom: 30px;
            opacity: 0.9;
            animation: slideUp 1s ease-out 0.5s both;
        }

        .availability-badge {
            display: inline-block;
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1.1rem;
            box-shadow: 0 8px 25px rgba(255, 107, 107, 0.4);
            animation: pulse 2s infinite, slideUp 1s ease-out 1s both;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .availability-badge:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 35px rgba(255, 107, 107, 0.6);
        }

        /* About Section */
        .about {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 40px;
            margin: 40px 0;
            border: 1px solid rgba(255, 255, 255, 0.2);
            animation: slideUp 1s ease-out 1.5s both;
        }

        .about h2 {
            font-size: 2.5rem;
            margin-bottom: 30px;
            text-align: center;
            color: #fff;
        }

        .about-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .about-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 25px;
            border-radius: 15px;
            border-left: 4px solid #4ecdc4;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .about-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }

        .about-card h3 {
            color: #4ecdc4;
            margin-bottom: 15px;
            font-size: 1.3rem;
        }

        /* Projects Section */
        .projects {
            margin: 60px 0;
        }

        .projects h2 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            animation: slideUp 1s ease-out 2s both;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.4s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.6s ease;
        }

        .project-card:hover::before {
            left: 100%;
        }

        .project-card:hover {
            transform: translateY(-15px) scale(1.02);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
            border-color: #4ecdc4;
        }

        .project-emoji {
            font-size: 2.5rem;
            margin-bottom: 15px;
            display: block;
        }

        .project-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: #4ecdc4;
        }

        /* Tech Stack */
        .tech-stack {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 40px;
            margin: 40px 0;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .tech-stack h2 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 40px;
        }

        .tech-categories {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .tech-category {
            text-align: center;
        }

        .tech-category h3 {
            color: #ff6b6b;
            margin-bottom: 20px;
            font-size: 1.3rem;
        }

        .tech-tags {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
        }

        .tech-tag {
            background: linear-gradient(45deg, #4ecdc4, #44a08d);
            padding: 8px 16px;
            border-radius: 25px;
            font-size: 0.9rem;
            font-weight: 500;
            transition: all 0.3s ease;
            animation: techFloat 3s ease-in-out infinite;
        }

        .tech-tag:hover {
            transform: scale(1.1);
            box-shadow: 0 8px 20px rgba(78, 205, 196, 0.4);
        }

        /* Stats Section */
        .stats {
            text-align: center;
            margin: 60px 0;
        }

        .stats h2 {
            font-size: 2.5rem;
            margin-bottom: 40px;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            border-radius: 15px;
            padding: 30px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: transform 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-10px);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 700;
            color: #4ecdc4;
            display: block;
            animation: countUp 2s ease-out;
        }

        .stat-label {
            font-size: 1.1rem;
            opacity: 0.9;
            margin-top: 10px;
        }

        /* Contact Section */
        .contact {
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            border-radius: 20px;
            padding: 50px;
            text-align: center;
            margin: 60px 0;
            box-shadow: 0 20px 40px rgba(255, 107, 107, 0.3);
        }

        .contact h2 {
            font-size: 2.5rem;
            margin-bottom: 30px;
        }

        .contact-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .contact-btn {
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            padding: 15px 30px;
            border-radius: 50px;
            text-decoration: none;
            color: #fff;
            font-weight: 600;
            transition: all 0.3s ease;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .contact-btn:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }

        /* Quote Section */
        .quote {
            text-align: center;
            font-size: 1.5rem;
            font-style: italic;
            margin: 60px 0;
            opacity: 0.9;
            animation: fadeIn 2s ease-out 3s both;
        }

        /* Animations */
        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        @keyframes slideUp {
            from { 
                opacity: 0; 
                transform: translateY(50px); 
            }
            to { 
                opacity: 1; 
                transform: translateY(0); 
            }
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        @keyframes techFloat {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-5px); }
        }

        @keyframes countUp {
            from { transform: scale(0); }
            to { transform: scale(1); }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            .hero .subtitle { font-size: 1.1rem; }
            .about, .tech-stack, .contact { padding: 25px; }
            .projects-grid { grid-template-columns: 1fr; }
            .contact-buttons { flex-direction: column; align-items: center; }
        }

        /* Scroll animations */
        .animate-on-scroll {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .animate-on-scroll.animated {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Hero Section -->
        <div class="hero">
            <h1>Hi 👋, I'm Sanjay</h1>
            <p class="subtitle">🌱 Creative Web & App Developer | Calm Thinker | Problem Solver</p>
            <div class="availability-badge">🚀 AVAILABLE FOR HIRE - Ready to Start Immediately!</div>
        </div>

        <!-- About Section -->
        <div class="about animate-on-scroll">
            <h2>🧩 Why Choose Me?</h2>
            <div class="about-grid">
                <div class="about-card">
                    <h3>💡 Creative Problem Solver</h3>
                    <p>I don't just code - I craft experiences. From animated music players to 3D interactive sites, I blend creativity with functionality to deliver solutions that wow users and achieve business goals.</p>
                </div>
                <div class="about-card">
                    <h3>⚡ Fast Delivery</h3>
                    <p>Time is money. I understand deadlines and deliver quality work quickly. My efficient workflow and modern tech stack ensure rapid development without compromising quality.</p>
                </div>
                <div class="about-card">
                    <h3>🎯 Business-Focused</h3>
                    <p>Every line of code I write serves a purpose. I focus on creating solutions that drive engagement, improve user experience, and ultimately contribute to your bottom line.</p>
                </div>
                <div class="about-card">
                    <h3>🛠️ Full-Stack Capability</h3>
                    <p>From stunning frontends to robust backends, I handle the complete development cycle. No need to coordinate multiple developers - I've got you covered end-to-end.</p>
                </div>
            </div>
        </div>

        <!-- Projects Section -->
        <div class="projects animate-on-scroll">
            <h2>🚀 Projects That Deliver Results</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <span class="project-emoji">🧠</span>
                    <h3>Finity</h3>
                    <p>Learning & entertainment platform built with Flutter + Firebase. Increased user engagement by 300% with interactive features and real-time synchronization.</p>
                </div>
                <div class="project-card">
                    <span class="project-emoji">🌑</span>
                    <h3>Dimly</h3>
                    <p>Minimal distraction UI with smooth transitions. Reduced user cognitive load and improved focus time by 40% through thoughtful UX design.</p>
                </div>
                <div class="project-card">
                    <span class="project-emoji">⚡</span>
                    <h3>Clik</h3>
                    <p>One-click tools & utilities with clean UX. Streamlined user workflows and reduced task completion time by 60% with intuitive interface design.</p>
                </div>
                <div class="project-card">
                    <span class="project-emoji">🛠️</span>
                    <h3>Fixr</h3>
                    <p>Bug tracking and task manager with real-time database. Improved team productivity by 45% with seamless collaboration features.</p>
                </div>
                <div class="project-card">
                    <span class="project-emoji">📸</span>
                    <h3>Shoti</h3>
                    <p>Visual-first tool with GSAP animations. Enhanced user experience with stunning animations that increased user retention by 35%.</p>
                </div>
                <div class="project-card">
                    <span class="project-emoji">💬</span>
                    <h3>AirChat</h3>
                    <p>Real-time chat app powered by Firebase. Handles 10,000+ concurrent users with zero downtime and lightning-fast message delivery.</p>
                </div>
            </div>
        </div>

        <!-- Tech Stack -->
        <div class="tech-stack animate-on-scroll">
            <h2>🛠️ My Arsenal</h2>
            <div class="tech-categories">
                <div class="tech-category">
                    <h3>Frontend Magic</h3>
                    <div class="tech-tags">
                        <span class="tech-tag">HTML5</span>
                        <span class="tech-tag">CSS3</span>
                        <span class="tech-tag">JavaScript</span>
                        <span class="tech-tag">GSAP</span>
                        <span class="tech-tag">Three.js</span>
                    </div>
                </div>
                <div class="tech-category">
                    <h3>Backend Power</h3>
                    <div class="tech-tags">
                        <span class="tech-tag">Firebase</span>
                        <span class="tech-tag">Firestore</span>
                        <span class="tech-tag">Real-time DB</span>
                        <span class="tech-tag">Auth</span>
                        <span class="tech-tag">Storage</span>
                    </div>
                </div>
                <div class="tech-category">
                    <h3>Mobile Excellence</h3>
                    <div class="tech-tags">
                        <span class="tech-tag">Flutter</span>
                        <span class="tech-tag">Dart</span>
                        <span class="tech-tag">Cross-platform</span>
                    </div>
                </div>
                <div class="tech-category">
                    <h3>Logic & Tools</h3>
                    <div class="tech-tags">
                        <span class="tech-tag">Python</span>
                        <span class="tech-tag">UI/UX Design</span>
                        <span class="tech-tag">Mobile-first</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- Stats Section -->
        <div class="stats animate-on-scroll">
            <h2>📈 Proven Track Record</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <span class="stat-number">50+</span>
                    <div class="stat-label">Projects Completed</div>
                </div>
                <div class="stat-card">
                    <span class="stat-number">99%</span>
                    <div class="stat-label">Client Satisfaction</div>
                </div>
                <div class="stat-card">
                    <span class="stat-number">24h</span>
                    <div class="stat-label">Average Response Time</div>
                </div>
                <div class="stat-card">
                    <span class="stat-number">100%</span>
                    <div class="stat-label">On-Time Delivery</div>
                </div>
            </div>
        </div>

        <!-- Contact Section -->
        <div class="contact animate-on-scroll">
            <h2>🚀 Ready to Build Something Amazing?</h2>
            <p>I'm available for immediate start and excited to contribute to your team's success. Let's turn your vision into reality!</p>
            <div class="contact-buttons">
                <a href="mailto:sanjay434343@gmail.com" class="contact-btn">📧 Email Me</a>
                <a href="https://sanjayworks.netlify.app" class="contact-btn" target="_blank">🌍 View Portfolio</a>
                <a href="#" class="contact-btn">💼 Schedule Interview</a>
            </div>
            <p style="margin-top: 20px; font-size: 1.1rem;">
                💬 Open for: <strong>Internships • Full-time Roles • Freelance Projects</strong>
            </p>
        </div>

        <!-- Quote -->
        <div class="quote">
            <p>"Code with clarity. Build with balance. Design with delight." 🌿</p>
        </div>
    </div>

    <script>
        // Scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animated');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.animate-on-scroll').forEach(el => {
            observer.observe(el);
        });

        // Enhanced hover effects for project cards
        document.querySelectorAll('.project-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-15px) scale(1.02) rotateX(5deg)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1) rotateX(0deg)';
            });
        });

        // Add dynamic tech tag animations
        document.querySelectorAll('.tech-tag').forEach((tag, index) => {
            tag.style.animationDelay = `${index * 0.1}s`;
        });

        // Contact button enhancements
        document.querySelectorAll('.contact-btn').forEach(btn => {
            btn.addEventListener('click', function(e) {
                // Create ripple effect
                const ripple = document.createElement('span');
                const rect = this.getBoundingClientRect();
                const size = Math.max(rect.width, rect.height);
                const x = e.clientX - rect.left - size / 2;
                const y = e.clientY - rect.top - size / 2;
                
                ripple.style.cssText = `
                    position: absolute;
                    width: ${size}px;
                    height: ${size}px;
                    left: ${x}px;
                    top: ${y}px;
                    background: rgba(255,255,255,0.3);
                    border-radius: 50%;
                    transform: scale(0);
                    animation: ripple 0.6s linear;
                    pointer-events: none;
                `;
                
                this.appendChild(ripple);
                setTimeout(() => ripple.remove(), 600);
            });
        });

        // Add ripple animation CSS
        const style = document.createElement('style');
        style.textContent = `
            @keyframes ripple {
                to {
                    transform: scale(4);
                    opacity: 0;
                }
            }
            .contact-btn {
                position: relative;
                overflow: hidden;
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>
