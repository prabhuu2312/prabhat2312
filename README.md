<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prabhat Kumar Dehariya - Web Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap');

        :root {
            --primary: #3498DB;
            --secondary: #2C3E50;
            --accent: #E74C3C;
            --light: #ECF0F1;
            --text: #2C3E50;
            --text-light: #7F8C8D;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            animation: slideUp 0.8s ease-out;
        }

        /* Cover Banner */
        .cover {
            height: 250px;
            background: linear-gradient(135deg, #3498DB 0%, #2C3E50 100%);
            position: relative;
            overflow: hidden;
        }

        .cover::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(255, 255, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(255, 255, 255, 0.05) 0%, transparent 50%);
            animation: wave 15s ease-in-out infinite;
        }

        .cover-content {
            position: relative;
            z-index: 2;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* Profile Section */
        .profile-section {
            position: relative;
            text-align: center;
            padding: 0 40px -60px 40px;
            margin-top: -80px;
            margin-bottom: 40px;
            animation: fadeIn 1s ease-out 0.3s both;
        }

        .profile-image {
            width: 160px;
            height: 160px;
            border-radius: 50%;
            border: 5px solid white;
            background: linear-gradient(135deg, #667eea, #764ba2);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 80px;
            box-shadow: 0 10px 40px rgba(52, 152, 219, 0.3);
            animation: popIn 0.6s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        .profile-name {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--secondary);
            margin-bottom: 10px;
            animation: slideDown 0.6s ease-out 0.2s both;
        }

        .profile-title {
            font-size: 1.3rem;
            color: var(--primary);
            margin-bottom: 20px;
            animation: slideDown 0.6s ease-out 0.3s both;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 20px;
            animation: slideUp 0.6s ease-out 0.4s both;
        }

        .social-links a {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: var(--primary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            transition: all 0.3s ease;
            font-size: 1.2rem;
        }

        .social-links a:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(52, 152, 219, 0.4);
            background: var(--accent);
        }

        .info-badges {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            animation: fadeIn 1s ease-out 0.5s both;
        }

        .badge {
            background: var(--light);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.9rem;
            color: var(--text-light);
            border: 2px solid var(--primary);
        }

        /* Content */
        .content {
            padding: 40px;
        }

        .section {
            margin-bottom: 50px;
            animation: fadeIn 0.8s ease-out backwards;
        }

        .section:nth-child(1) { animation-delay: 0.6s; }
        .section:nth-child(2) { animation-delay: 0.7s; }
        .section:nth-child(3) { animation-delay: 0.8s; }
        .section:nth-child(4) { animation-delay: 0.9s; }

        .section-title {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 25px;
            padding-bottom: 15px;
            border-bottom: 3px solid var(--primary);
            display: inline-block;
            animation: slideInLeft 0.6s ease-out;
        }

        /* About */
        .about-box {
            background: var(--light);
            padding: 25px;
            border-radius: 12px;
            border-left: 5px solid var(--primary);
            line-height: 1.8;
            color: var(--text-light);
            animation: slideInLeft 0.6s ease-out 0.2s both;
        }

        /* Skills */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            animation: fadeIn 0.8s ease-out;
        }

        .skill-card {
            background: linear-gradient(135deg, var(--primary) 0%, #2980B9 100%);
            color: white;
            padding: 20px;
            border-radius: 12px;
            text-align: center;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            animation: scaleIn 0.5s ease-out backwards;
        }

        .skill-card:nth-child(1) { animation-delay: 0.1s; }
        .skill-card:nth-child(2) { animation-delay: 0.2s; }
        .skill-card:nth-child(3) { animation-delay: 0.3s; }
        .skill-card:nth-child(4) { animation-delay: 0.4s; }
        .skill-card:nth-child(5) { animation-delay: 0.5s; }
        .skill-card:nth-child(6) { animation-delay: 0.6s; }
        .skill-card:nth-child(7) { animation-delay: 0.7s; }
        .skill-card:nth-child(8) { animation-delay: 0.8s; }

        .skill-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 40px rgba(52, 152, 219, 0.3);
        }

        /* Experience */
        .experience-card {
            background: var(--light);
            padding: 30px;
            border-radius: 12px;
            border-left: 5px solid var(--accent);
            margin-bottom: 20px;
            animation: slideInLeft 0.6s ease-out backwards;
            transition: all 0.3s ease;
        }

        .experience-card:nth-child(1) { animation-delay: 0.2s; }
        .experience-card:nth-child(2) { animation-delay: 0.4s; }

        .experience-card:hover {
            transform: translateX(10px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        .job-title {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--secondary);
            margin-bottom: 8px;
        }

        .company {
            color: var(--accent);
            font-weight: 600;
            margin-bottom: 8px;
        }

        .dates {
            color: var(--text-light);
            font-size: 0.9rem;
            margin-bottom: 15px;
            font-style: italic;
        }

        .job-list {
            list-style: none;
            color: var(--text-light);
        }

        .job-list li {
            padding: 8px 0;
            padding-left: 25px;
            position: relative;
        }

        .job-list li::before {
            content: '→';
            position: absolute;
            left: 0;
            color: var(--accent);
            font-weight: bold;
        }

        /* Projects */
        .project-card {
            background: var(--light);
            padding: 30px;
            border-radius: 12px;
            border-top: 5px solid var(--primary);
            margin-bottom: 20px;
            animation: slideInUp 0.6s ease-out backwards;
            transition: all 0.3s ease;
        }

        .project-card:nth-child(1) { animation-delay: 0.2s; }
        .project-card:nth-child(2) { animation-delay: 0.4s; }

        .project-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 40px rgba(52, 152, 219, 0.2);
        }

        .project-name {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--secondary);
            margin-bottom: 10px;
        }

        .project-tech {
            display: flex;
            gap: 10px;
            margin-bottom: 15px;
            flex-wrap: wrap;
        }

        .tech-tag {
            background: var(--primary);
            color: white;
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 0.85rem;
            font-weight: 600;
        }

        .project-features {
            list-style: none;
            color: var(--text-light);
        }

        .project-features li {
            padding: 8px 0;
            padding-left: 25px;
            position: relative;
        }

        .project-features li::before {
            content: '•';
            position: absolute;
            left: 0;
            color: var(--accent);
            font-weight: bold;
        }

        /* Footer */
        .footer {
            background: var(--secondary);
            color: white;
            text-align: center;
            padding: 40px;
            animation: slideUp 0.8s ease-out 1s both;
        }

        .footer-text {
            margin-bottom: 20px;
            font-size: 1.1rem;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: var(--primary);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .footer-links a:hover {
            color: white;
            transform: translateY(-3px);
        }

        /* Animations */
        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(30px);
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

        @keyframes popIn {
            0% {
                opacity: 0;
                transform: scale(0.5);
            }
            50% {
                transform: scale(1.1);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }

        @keyframes scaleIn {
            from {
                opacity: 0;
                transform: scale(0.9);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        @keyframes wave {
            0%, 100% {
                transform: translate(0, 0);
            }
            50% {
                transform: translate(30px, 0);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .profile-name {
                font-size: 1.8rem;
            }

            .profile-title {
                font-size: 1.1rem;
            }

            .profile-image {
                width: 120px;
                height: 120px;
                font-size: 60px;
            }

            .content {
                padding: 30px 20px;
            }

            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            }

            .section-title {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Cover Banner -->
        <div class="cover">
            <div class="cover-content"></div>
        </div>

        <!-- Profile Section -->
        <div class="profile-section">
            <div class="profile-image">👨‍💻</div>
            <h1 class="profile-name">Prabhat Kumar Dehariya</h1>
            <p class="profile-title">Full Stack Web Developer</p>
            
            <div class="social-links">
                <a href="mailto:prabhatkumardehariya786@gmail.com" title="Email">📧</a>
                <a href="tel:+916264413175" title="Phone">📱</a>
                <a href="https://linkedin.com" title="LinkedIn">in</a>
                <a href="https://github.com" title="GitHub">⚙️</a>
            </div>

            <div class="info-badges">
                <span class="badge">📍 Indore, India</span>
                <span class="badge">💼 1+ Years</span>
                <span class="badge">🚀 50+ Projects</span>
            </div>
        </div>

        <!-- Main Content -->
        <div class="content">
            <!-- About -->
            <section class="section">
                <h2 class="section-title">About Me</h2>
                <div class="about-box">
                    Web Developer with 1+ year of professional experience building responsive, secure, and scalable web applications. Delivered 50+ websites and web applications across diverse industries. Strong foundation in HTML, CSS, JavaScript, PHP, Laravel, and MySQL. Specialization in CRUD operations, Authentication Systems, Payment Gateway Integration, and Email Automation.
                </div>
            </section>

            <!-- Skills -->
            <section class="section">
                <h2 class="section-title">Technical Skills</h2>
                <div class="skills-grid">
                    <div class="skill-card">HTML5</div>
                    <div class="skill-card">CSS3</div>
                    <div class="skill-card">JavaScript</div>
                    <div class="skill-card">Bootstrap</div>
                    <div class="skill-card">PHP</div>
                    <div class="skill-card">Laravel</div>
                    <div class="skill-card">MySQL</div>
                    <div class="skill-card">Git & GitHub</div>
                </div>
            </section>

            <!-- Experience -->
            <section class="section">
                <h2 class="section-title">Work Experience</h2>
                
                <div class="experience-card">
                    <div class="job-title">Web Developer</div>
                    <div class="company">India Websoft, Indore</div>
                    <div class="dates">July 2025 - Present</div>
                    <ul class="job-list">
                        <li>Develop responsive web applications using modern tech stack</li>
                        <li>Design and optimize databases with complete CRUD operations</li>
                        <li>Implement secure authentication and authorization systems</li>
                        <li>Integrate payment gateways and email services</li>
                        <li>Delivered 50+ production-ready websites and applications</li>
                    </ul>
                </div>
            </section>

            <!-- Projects -->
            <section class="section">
                <h2 class="section-title">Featured Projects</h2>
                
                <div class="project-card">
                    <div class="project-name">🏨 Triptay – Hotel Booking Platform</div>
                    <div class="project-tech">
                        <span class="tech-tag">PHP</span>
                        <span class="tech-tag">MySQL</span>
                        <span class="tech-tag">Bootstrap</span>
                    </div>
                    <ul class="project-features">
                        <li>Multi-role authentication (User/Vendor/Admin)</li>
                        <li>Role-based access control</li>
                        <li>Complete CRUD operations for booking management</li>
                    </ul>
                </div>

                <div class="project-card">
                    <div class="project-name">📚 KYMS Academy – Educational Portal</div>
                    <div class="project-tech">
                        <span class="tech-tag">Laravel</span>
                        <span class="tech-tag">MySQL</span>
                        <span class="tech-tag">PHP</span>
                    </div>
                    <ul class="project-features">
                        <li>Course management system</li>
                        <li>Question Bank with subject-wise organization</li>
                        <li>Secure admin panel with PDF management</li>
                    </ul>
                </div>
            </section>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p class="footer-text">Let's build something amazing together!</p>
            <div class="footer-links">
                <a href="mailto:prabhatkumardehariya786@gmail.com">Email</a>
                <a href="tel:+916264413175">Phone</a>
                <a href="https://linkedin.com">LinkedIn</a>
                <a href="https://github.com">GitHub</a>
            </div>
        </div>
    </div>
</body>
</html>
