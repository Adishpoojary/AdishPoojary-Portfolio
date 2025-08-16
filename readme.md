<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Adish Poojary - Frontend Developer</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            color: #ffffff;
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Animated background particles */
        .particles {
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
            width: 2px;
            height: 2px;
            background: #6366f1;
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 0.7; }
            50% { transform: translateY(-20px) rotate(180deg); opacity: 1; }
        }

        /* Navigation */
            nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(10, 10, 10, 0.9);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
            border-bottom: 1px solid rgba(99, 102, 241, 0.1);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #6366f1;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: #ffffff;
            text-decoration: none;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #6366f1;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #6366f1;
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            max-width: 800px;
            padding: 2rem;
            animation: fadeInUp 1s ease-out;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 2rem;
        }

        .hero-profile {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            border: 4px solid #6366f1;
            object-fit: cover;
            animation: fadeInUp 1s ease-out 0.3s both;
            box-shadow: 0 0 30px rgba(99, 102, 241, 0.3);
        }

        .hero-text {
            animation: fadeInUp 1s ease-out 0.6s both;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #6366f1, #ffffff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero .subtitle {
            font-size: 1.5rem;
            color: #a0a0a0;
            margin-bottom: 2rem;
        }

        .hero .description {
            font-size: 1.1rem;
            color: #cccccc;
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2rem;
            background: linear-gradient(45deg, #6366f1, #8b5cf6);
            color: #fff;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            margin: 0 1rem;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(99, 102, 241, 0.3);
        }

        .cta-button.secondary {
            background: transparent;
            color: #6366f1;
            border: 2px solid #6366f1;
        }

        /* Sections */
        section {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 3rem;
            color: #6366f1;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 50px;
            height: 3px;
            background: linear-gradient(45deg, #6366f1, #8b5cf6);
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
            color: #cccccc;
        }

        .about-text h3 {
            color: #6366f1;
            margin-bottom: 1rem;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 1rem;
        }

        .skill-item {
            background: rgba(99, 102, 241, 0.1);
            padding: 1rem;
            border-radius: 10px;
            text-align: center;
            border: 1px solid rgba(99, 102, 241, 0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .skill-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(99, 102, 241, 0.2);
        }

        .skill-item i {
            font-size: 2rem;
            color: #6366f1;
            margin-bottom: 0.5rem;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .project-card {
            background: rgba(26, 26, 46, 0.8);
            border-radius: 15px;
            padding: 2rem;
            border: 1px solid rgba(99, 102, 241, 0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, rgba(99, 102, 241, 0.05), rgba(139, 92, 246, 0.05));
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .project-card:hover::before {
            opacity: 1;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(99, 102, 241, 0.2);
        }

        .project-card h3 {
            color: #6366f1;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .project-card p {
            color: #cccccc;
            margin-bottom: 1.5rem;
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .tech-tag {
            background: rgba(99, 102, 241, 0.2);
            color: #6366f1;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            border: 1px solid rgba(99, 102, 241, 0.3);
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        .project-links a {
            color: #6366f1;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            transition: color 0.3s ease;
        }

        .project-links a:hover {
            color: #ffffff;
        }

        /* Experience Section */
        .timeline {
            position: relative;
            padding-left: 2rem;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            height: 100%;
            width: 2px;
            background: linear-gradient(to bottom, #6366f1, #8b5cf6);
        }

        .timeline-item {
            position: relative;
            margin-bottom: 2rem;
            background: rgba(26, 26, 46, 0.8);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid rgba(99, 102, 241, 0.2);
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -2.5rem;
            top: 2rem;
            width: 12px;
            height: 12px;
            background: #6366f1;
            border-radius: 50%;
            border: 3px solid #0a0a0a;
        }

        .timeline-item h3 {
            color: #6366f1;
            margin-bottom: 0.5rem;
        }

        .timeline-item .date {
            color: #a0a0a0;
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        /* Contact Section */
        .contact-content {
            text-align: center;
        }

        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .contact-item {
            background: rgba(26, 26, 46, 0.8);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid rgba(99, 102, 241, 0.2);
            transition: transform 0.3s ease;
        }

        .contact-item:hover {
            transform: translateY(-5px);
        }

        .contact-item i {
            font-size: 2rem;
            color: #6366f1;
            margin-bottom: 1rem;
        }

        .contact-item h3 {
            color: #ffffff;
            margin-bottom: 0.5rem;
        }

        .contact-item a {
            color: #cccccc;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .contact-item a:hover {
            color: #6366f1;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 2rem;
            background: rgba(10, 10, 10, 0.9);
            border-top: 1px solid rgba(99, 102, 241, 0.2);
        }

        /* Animations */
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

        .fade-in {
            animation: fadeInUp 1s ease-out;
        }

        /* Mobile Responsiveness */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .contact-info {
                grid-template-columns: 1fr;
            }

            .timeline {
                padding-left: 1rem;
            }

            .timeline-item::before {
                left: -1.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- Animated Background Particles -->
    <div class="particles" id="particles"></div>

    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <a href="#" class="logo">AP</a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <!-- Profile Photo Placeholder - Replace src with your actual photo URL -->
            <img src="AdishPoojary.jpeg" 
                 alt="Adish Poojary" 
                 class="hero-profile">
            
            <div class="hero-text">
                <h1>Adish Poojary</h1>
                <p class="subtitle">Frontend Developer & AI Enthusiast</p>
                <p class="description">
                    Passionate Computer Science student crafting innovative web applications with modern technologies. 
                    Specializing in React, Next.js, and AI-powered solutions with a keen eye for user experience.
                </p>
                <div>
                    <a href="#projects" class="cta-button">View My Work</a>
                    <a href="#contact" class="cta-button secondary">Get In Touch</a>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <h2 class="section-title">About Me</h2>
        <div class="about-content">
            <div class="about-text">
                <h3>Hello! I'm Adish</h3>
                <p>
                    I'm a Computer Science Engineering student at SMVITM, Udupi, with a passion for creating 
                    exceptional digital experiences. My journey in tech spans across frontend development, 
                    AI/ML projects, and full-stack applications.
                </p>
                <p>
                    I enjoy turning complex problems into simple, beautiful, and intuitive solutions. When I'm 
                    not coding, you'll find me exploring new technologies, participating in hackathons, or 
                    contributing to open-source projects.
                </p>
                <p>
                    Currently pursuing my Bachelor's degree and actively seeking opportunities to apply my 
                    skills in real-world projects and internships.
                </p>
            </div>
            <div class="skills-grid">
                <div class="skill-item">
                    <i class="fab fa-react"></i>
                    <p>React</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-js"></i>
                    <p>JavaScript</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-python"></i>
                    <p>Python</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-node-js"></i>
                    <p>Node.js</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-html5"></i>
                    <p>HTML5</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-css3-alt"></i>
                    <p>CSS3</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-git-alt"></i>
                    <p>Git</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-docker"></i>
                    <p>Docker</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects">
        <h2 class="section-title">Featured Projects</h2>
        <div class="projects-grid">
            <div class="project-card">
                <h3>NOVA - AI Voice Assistant</h3>
                <p>
                    Developed a Python-based AI voice assistant with GUI, capable of executing system commands, 
                    fetching information, and automating tasks via voice recognition.
                </p>
                <div class="tech-stack">
                    <span class="tech-tag">Python</span>
                    <span class="tech-tag">PyQt5</span>
                    <span class="tech-tag">Deepgram</span>
                    <span class="tech-tag">OpenCV</span>
                </div>
                <div class="project-links">
                    <a href="#"><i class="fab fa-github"></i> GitHub</a>
                    <a href="#"><i class="fas fa-external-link-alt"></i> Live Demo</a>
                </div>
            </div>

            <div class="project-card">
                <h3>Healthcare Patient Management System</h3>
                <p>
                    Built a responsive healthcare platform for patient registration, doctor appointments, and 
                    admin scheduling with real-time SMS notifications.
                </p>
                <div class="tech-stack">
                    <span class="tech-tag">Next.js</span>
                    <span class="tech-tag">TypeScript</span>
                    <span class="tech-tag">Appwrite</span>
                    <span class="tech-tag">Twilio</span>
                </div>
                <div class="project-links">
                    <a href="#"><i class="fab fa-github"></i> GitHub</a>
                    <a href="#"><i class="fas fa-external-link-alt"></i> Live Demo</a>
                </div>
            </div>

            <div class="project-card">
                <h3>AI Powered Code Reviewer</h3>
                <p>
                    Developed an AI-based code review platform with real-time feedback and improvement suggestions 
                    using Google Gemini API for intelligent code analysis.
                </p>
                <div class="tech-stack">
                    <span class="tech-tag">MERN Stack</span>
                    <span class="tech-tag">Google Gemini</span>
                    <span class="tech-tag">API Integration</span>
                </div>
                <div class="project-links">
                    <a href="#"><i class="fab fa-github"></i> GitHub</a>
                    <a href="#"><i class="fas fa-external-link-alt"></i> Live Demo</a>
                </div>
            </div>

            <div class="project-card">
                <h3>Blood Group Detection using Fingerprints</h3>
                <p>
                    Innovative non-invasive blood group detection system leveraging fingerprint image analysis 
                    using Convolutional Neural Networks with high accuracy classification.
                </p>
                <div class="tech-stack">
                    <span class="tech-tag">PyTorch</span>
                    <span class="tech-tag">TensorFlow</span>
                    <span class="tech-tag">Flask</span>
                    <span class="tech-tag">CNN</span>
                </div>
                <div class="project-links">
                    <a href="#"><i class="fab fa-github"></i> GitHub</a>
                    <a href="#"><i class="fas fa-external-link-alt"></i> Research Paper</a>
                </div>
            </div>
        </div>
    </section>

     <title>Technical Skills Section</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            color: #ffffff;
            min-height: 100vh;
            padding: 2rem;
        }

        .skills-section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 5rem 2rem;
        }

        .section-title {
            font-size: 2.8rem;
            text-align: center;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #6366f1, #8b5cf6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            position: relative;
        }

        .section-subtitle {
            text-align: center;
            color: #a0a0a0;
            font-size: 1.1rem;
            margin-bottom: 4rem;
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .skill-category {
            background: rgba(26, 26, 46, 0.8);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid rgba(99, 102, 241, 0.2);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .skill-category::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, rgba(99, 102, 241, 0.05), rgba(139, 92, 246, 0.05));
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .skill-category:hover::before {
            opacity: 1;
        }

        .skill-category:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(99, 102, 241, 0.3);
            border-color: rgba(99, 102, 241, 0.4);
        }

        .category-header {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1.5rem;
            position: relative;
            z-index: 1;
        }

        .category-icon {
            font-size: 1.8rem;
            color: #6366f1;
            background: rgba(99, 102, 241, 0.1);
            padding: 0.8rem;
            border-radius: 12px;
            border: 1px solid rgba(99, 102, 241, 0.2);
        }

        .category-title {
            font-size: 1.3rem;
            color: #ffffff;
            font-weight: 600;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            gap: 1rem;
            position: relative;
            z-index: 1;
        }

        .skill-item {
            background: rgba(99, 102, 241, 0.08);
            border: 1px solid rgba(99, 102, 241, 0.15);
            border-radius: 12px;
            padding: 1rem 0.8rem;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .skill-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(99, 102, 241, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .skill-item:hover::before {
            left: 100%;
        }

        .skill-item:hover {
            transform: scale(1.05);
            background: rgba(99, 102, 241, 0.15);
            border-color: rgba(99, 102, 241, 0.3);
            box-shadow: 0 8px 25px rgba(99, 102, 241, 0.2);
        }

        .skill-icon {
            font-size: 1.8rem;
            margin-bottom: 0.5rem;
            color: #6366f1;
            transition: color 0.3s ease;
        }

        .skill-name {
            font-size: 0.9rem;
            color: #cccccc;
            font-weight: 500;
            position: relative;
            z-index: 1;
        }

        .skill-item:hover .skill-name {
            color: #ffffff;
        }

        /* Custom icons for specific technologies */
        .python-icon { color: #3776ab; }
        .java-icon { color: #f89820; }
        .js-icon { color: #f7df1e; }
        .react-icon { color: #61dafb; }
        .node-icon { color: #339933; }
        .next-icon { color: #ffffff; }
        .docker-icon { color: #2496ed; }
        .git-icon { color: #f05032; }

        .skill-item:hover .python-icon,
        .skill-item:hover .java-icon,
        .skill-item:hover .js-icon,
        .skill-item:hover .react-icon,
        .skill-item:hover .node-icon,
        .skill-item:hover .next-icon,
        .skill-item:hover .docker-icon,
        .skill-item:hover .git-icon {
            color: #6366f1;
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

        .animate-in {
            animation: fadeInUp 0.8s ease-out forwards;
        }

        @media (max-width: 768px) {
            .skills-container {
                grid-template-columns: 1fr;
                gap: 1.5rem;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
                gap: 0.8rem;
            }
            
            .section-title {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>
    <section class="skills-section">
        <h2 class="section-title">Technical Skills</h2>
        <p class="section-subtitle">Technologies I work with to bring ideas to life</p>
        
        <div class="skills-container">
            <!-- Programming Languages -->
            <div class="skill-category">
                <div class="category-header">
                    <div class="category-icon">
                        <i class="fas fa-code"></i>
                    </div>
                    <h3 class="category-title">Languages</h3>
                </div>
                <div class="skills-grid">
                    <div class="skill-item">
                        <i class="fab fa-python skill-icon python-icon"></i>
                        <p class="skill-name">Python</p>
                    </div>
                    <div class="skill-item">
                        <i class="fab fa-java skill-icon java-icon"></i>
                        <p class="skill-name">Java</p>
                    </div>
                    <div class="skill-item">
                        <i class="fas fa-code skill-icon"></i>
                        <p class="skill-name">C</p>
                    </div>
                    <div class="skill-item">
                        <i class="fas fa-database skill-icon"></i>
                        <p class="skill-name">SQL</p>
                    </div>
                    <div class="skill-item">
                        <i class="fab fa-js skill-icon js-icon"></i>
                        <p class="skill-name">JavaScript</p>
                    </div>
                    <div class="skill-item">
                        <i class="fab fa-js skill-icon"></i>
                        <p class="skill-name">TypeScript</p>
                    </div>
                    <div class="skill-item">
                        <i class="fab fa-html5 skill-icon"></i>
                        <p class="skill-name">HTML</p>
                    </div>
                    <div class="skill-item">
                        <i class="fab fa-css3-alt skill-icon"></i>
                        <p class="skill-name">CSS</p>
                    </div>
                </div>
            </div>

            <!-- Frameworks & Platforms -->
            <div class="skill-category">
                <div class="category-header">
                    <div class="category-icon">
                        <i class="fas fa-layer-group"></i>
                    </div>
                    <h3 class="category-title">Frameworks</h3>
                </div>
                <div class="skills-grid">
                    <div class="skill-item">
                        <i class="fas fa-flask skill-icon"></i>
                        <p class="skill-name">Flask</p>
                    </div>
                    <div class="skill-item">
                        <i class="fab fa-react skill-icon react-icon"></i>
                        <p class="skill-name">React</p>
                    </div>
                    <div class="skill-item">
                        <i class="fab fa-node-js skill-icon node-icon"></i>
                        <p class="skill-name">Node.js</p>
                    </div>
                    <div class="skill-item">
                        <i class="fas fa-rocket skill-icon next-icon"></i>
                        <p class="skill-name">Next.js</p>
                    </div>
                    <div class="skill-item">
                        <i class="fas fa-desktop skill-icon"></i>
                        <p class="skill-name">PyQt5</p>
                    </div>
                </div>
            </div>

            <!-- Developer Tools -->
            <div class="skill-category">
                <div class="category-header">
                    <div class="category-icon">
                        <i class="fas fa-tools"></i>
                    </div>
                    <h3 class="category-title">Developer Tools</h3>
                </div>
                <div class="skills-grid">
                    <div class="skill-item">
                        <i class="fab fa-git-alt skill-icon git-icon"></i>
                        <p class="skill-name">Git</p>
                    </div>
                    <div class="skill-item">
                        <i class="fab fa-docker skill-icon docker-icon"></i>
                        <p class="skill-name">Docker</p>
                    </div>
                    <div class="skill-item">
                        <i class="fas fa-bug skill-icon"></i>
                        <p class="skill-name">Postman</p>
                    </div>
                    <div class="skill-item">
                        <i class="fas fa-database skill-icon"></i>
                        <p class="skill-name">Appwrite</p>
                    </div>
                    <div class="skill-item">
                        <i class="fas fa-sms skill-icon"></i>
                        <p class="skill-name">Twilio</p>
                    </div>
                    <div class="skill-item">
                        <i class="fas fa-microphone skill-icon"></i>
                        <p class="skill-name">Deepgram</p>
                    </div>
                </div>
            </div>

            <!-- Libraries & Frameworks -->
            <div class="skill-category">
                <div class="category-header">
                    <div class="category-icon">
                        <i class="fas fa-brain"></i>
                    </div>
                    <h3 class="category-title">AI & Data</h3>
                </div>
                <div class="skills-grid">
                    <div class="skill-item">
                        <i class="fas fa-robot skill-icon"></i>
                        <p class="skill-name">TensorFlow</p>
                    </div>
                    <div class="skill-item">
                        <i class="fas fa-fire skill-icon"></i>
                        <p class="skill-name">PyTorch</p>
                    </div>
                    <div class="skill-item">
                        <i class="fas fa-table skill-icon"></i>
                        <p class="skill-name">Pandas</p>
                    </div>
                    <div class="skill-item">
                        <i class="fas fa-calculator skill-icon"></i>
                        <p class="skill-name">NumPy</p>
                    </div>
                    <div class="skill-item">
                        <i class="fas fa-chart-line skill-icon"></i>
                        <p class="skill-name">Matplotlib</p>
                    </div>
                    <div class="skill-item">
                        <i class="fas fa-eye skill-icon"></i>
                        <p class="skill-name">OpenCV</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <script>
        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animate-in');
                }
            });
        }, observerOptions);

        // Observe all skill categories
        document.querySelectorAll('.skill-category').forEach((category, index) => {
            category.style.opacity = '0';
            category.style.transform = 'translateY(30px)';
            category.style.transition = `opacity 0.8s ease ${index * 0.1}s, transform 0.8s ease ${index * 0.1}s`;
            observer.observe(category);
        });

        // Add click effect to skill items
        document.querySelectorAll('.skill-item').forEach(item => {
            item.addEventListener('click', function() {
                this.style.transform = 'scale(0.95)';
                setTimeout(() => {
                    this.style.transform = '';
                }, 150);
            });
        });
    </script>

    <!-- Experience Section -->
    <section id="experience">
        <h2 class="section-title">Experience & Activities</h2>
        <div class="timeline">
            <div class="timeline-item">
                <h3>IEEE Member</h3>
                <div class="date">June 2024 - Present</div>
                <p>
                    Active member of IEEE at SMVITM, participating in tech talks, events, and collaborative 
                    student-led sessions focused on emerging technologies and professional development.
                </p>
            </div>

            <div class="timeline-item">
                <h3>Docker Workshops</h3>
                <div class="date">2023 - 2024</div>
                <p>
                    Attended comprehensive Docker workshops through UniCourt Offline to master containerization 
                    and deployment practices, gaining deep understanding of cloud computing and CI/CD pipelines.
                </p>
            </div>

            <div class="timeline-item">
                <h3>Hackathon Participant</h3>
                <div class="date">2022</div>
                <p>
                    Participated in college-level and national-level hackathons, securing top 10 position in 
                    national competition. Contributed to innovative solutions under time constraints.
                </p>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <h2 class="section-title">Get In Touch</h2>
        <div class="contact-content">
            <p>I'm always interested in new opportunities and exciting projects. Let's connect!</p>
            <div class="contact-info">
                <div class="contact-item">
                    <i class="fas fa-envelope"></i>
                    <h3>Email</h3>
                    <a href="mailto:adishpoojary24@gmail.com">adishpoojary24@gmail.com</a>
                </div>
                <div class="contact-item">
                    <i class="fas fa-phone"></i>
                    <h3>Phone</h3>
                    <a href="tel:+918431571020">+91-8431571020</a>
                </div>
                <div class="contact-item">
                    <i class="fab fa-linkedin"></i>
                    <h3>LinkedIn</h3>
                    <a href="https://linkedin.com/in/adishpoojary" target="_blank">linkedin.com/in/adishpoojary</a>
                </div>
                <div class="contact-item">
                    <i class="fab fa-github"></i>
                    <h3>GitHub</h3>
                    <a href="https://github.com/adishpoojary" target="_blank">github.com/adishpoojary</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2025 Adish Poojary. Built with passion and code.</p>
    </footer>

    <script>
        // Create animated particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 50;

            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Intersection Observer for fade-in animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe all sections
        document.querySelectorAll('section').forEach(section => {
            section.style.opacity = '0';
            section.style.transform = 'translateY(30px)';
            section.style.transition = 'opacity 0.8s ease, transform 0.8s ease';
            observer.observe(section);
        });

        // Initialize particles when page loads
        window.addEventListener('load', createParticles);

        // Add typing effect to hero subtitle
        function typeWriter(text, element, speed = 100) {
            let i = 0;
            element.innerHTML = '';
            function type() {
                if (i < text.length) {
                    element.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                }
            }
            type();
        }

        // Start typing effect after page loads
        window.addEventListener('load', () => {
            const subtitle = document.querySelector('.hero .subtitle');
            const originalText = subtitle.textContent;
            setTimeout(() => {
                typeWriter(originalText, subtitle, 80);
            }, 1000);
        });
    </script>
</body>
</html>