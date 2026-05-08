# Nahaportfolioindex.html
Job portfolios 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HR Operations & HRIS Analyst Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #1e3a5f;
            --secondary: #2d5a87;
            --accent: #e8b339;
            --accent-light: #f5d78e;
            --bg-dark: #0f1c2e;
            --bg-light: #f8fafc;
            --text-dark: #1e293b;
            --text-light: #64748b;
            --white: #ffffff;
            --success: #10b981;
            --gradient: linear-gradient(135deg, #1e3a5f 0%, #2d5a87 50%, #1e3a5f 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--bg-dark);
            color: var(--text-dark);
            overflow: hidden;
            height: 100vh;
        }

        .presentation-container {
            width: 100vw;
            height: 100vh;
            position: relative;
            overflow: hidden;
        }

        .slide {
            position: absolute;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 60px 80px;
            opacity: 0;
            transform: translateX(100%);
            transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
            background: var(--white);
        }

        .slide.active {
            opacity: 1;
            transform: translateX(0);
        }

        .slide.prev {
            transform: translateX(-100%);
        }

        /* Navigation */
        .nav-controls {
            position: fixed;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            align-items: center;
            gap: 20px;
            z-index: 1000;
            background: rgba(15, 28, 46, 0.9);
            padding: 12px 28px;
            border-radius: 50px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.1);
        }

        .nav-btn {
            background: none;
            border: none;
            color: var(--white);
            cursor: pointer;
            font-size: 20px;
            padding: 8px;
            border-radius: 50%;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .nav-btn:hover {
            background: var(--secondary);
        }

        .slide-counter {
            color: var(--white);
            font-size: 14px;
            font-weight: 500;
            min-width: 60px;
            text-align: center;
        }

        .progress-bar {
            position: fixed;
            top: 0;
            left: 0;
            height: 4px;
            background: var(--accent);
            transition: width 0.4s ease;
            z-index: 1001;
        }

        /* Slide 1 - Cover */
        .slide-cover {
            background: var(--gradient);
            color: var(--white);
            text-align: center;
        }

        .slide-cover .badge {
            display: inline-block;
            background: rgba(232, 179, 57, 0.2);
            border: 1px solid var(--accent);
            color: var(--accent-light);
            padding: 8px 24px;
            border-radius: 50px;
            font-size: 14px;
            font-weight: 500;
            letter-spacing: 2px;
            text-transform: uppercase;
            margin-bottom: 30px;
            animation: fadeInDown 0.8s ease;
        }

        .slide-cover h1 {
            font-size: 52px;
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 20px;
            animation: fadeInUp 0.8s ease 0.2s both;
        }

        .slide-cover .subtitle {
            font-size: 22px;
            font-weight: 300;
            opacity: 0.9;
            margin-bottom: 50px;
            animation: fadeInUp 0.8s ease 0.4s both;
        }

        .tools-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 12px;
            max-width: 700px;
            animation: fadeInUp 0.8s ease 0.6s both;
        }

        .tool-tag {
            background: rgba(255,255,255,0.1);
            border: 1px solid rgba(255,255,255,0.2);
            padding: 10px 20px;
            border-radius: 8px;
            font-size: 14px;
            font-weight: 500;
            transition: all 0.3s;
        }

        .tool-tag:hover {
            background: var(--accent);
            color: var(--bg-dark);
            border-color: var(--accent);
            transform: translateY(-2px);
        }

        /* Slide 2 - Profile */
        .slide-profile {
            background: var(--bg-light);
        }

        .slide-header {
            width: 100%;
            max-width: 1000px;
            margin-bottom: 40px;
        }

        .slide-header .label {
            color: var(--accent);
            font-size: 13px;
            font-weight: 700;
            letter-spacing: 3px;
            text-transform: uppercase;
            margin-bottom: 10px;
        }

        .slide-header h2 {
            font-size: 38px;
            font-weight: 700;
            color: var(--primary);
            line-height: 1.2;
        }

        .profile-card {
            background: var(--white);
            border-radius: 20px;
            padding: 50px;
            max-width: 900px;
            width: 100%;
            box-shadow: 0 20px 60px rgba(30, 58, 95, 0.08);
            border: 1px solid rgba(30, 58, 95, 0.06);
            position: relative;
            overflow: hidden;
        }

        .profile-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 5px;
            height: 100%;
            background: var(--accent);
        }

        .profile-text {
            font-size: 19px;
            line-height: 1.8;
            color: var(--text-dark);
        }

        .highlight {
            color: var(--secondary);
            font-weight: 600;
        }

        /* Content Slides */
        .slide-content {
            background: var(--bg-light);
            align-items: flex-start;
            padding-top: 80px;
        }

        .content-wrapper {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            max-width: 1100px;
            width: 100%;
            margin-top: 30px;
        }

        .content-box {
            background: var(--white);
            border-radius: 16px;
            padding: 35px;
            box-shadow: 0 10px 40px rgba(30, 58, 95, 0.06);
            border: 1px solid rgba(30, 58, 95, 0.05);
        }

        .content-box h3 {
            font-size: 18px;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .content-box h3 .icon {
            width: 36px;
            height: 36px;
            background: var(--accent);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
        }

        .content-box ul {
            list-style: none;
        }

        .content-box ul li {
            padding: 10px 0;
            padding-left: 28px;
            position: relative;
            font-size: 15px;
            line-height: 1.6;
            color: var(--text-dark);
            border-bottom: 1px solid rgba(0,0,0,0.04);
        }

        .content-box ul li:last-child {
            border-bottom: none;
        }

        .content-box ul li::before {
            content: '▸';
            position: absolute;
            left: 0;
            color: var(--accent);
            font-weight: bold;
        }

        .impact-box {
            background: var(--primary);
            color: var(--white);
        }

        .impact-box h3 {
            color: var(--accent-light);
        }

        .impact-box ul li {
            color: rgba(255,255,255,0.9);
            border-bottom-color: rgba(255,255,255,0.1);
        }

        .impact-box ul li::before {
            color: var(--accent);
        }

        .metric {
            display: inline-block;
            background: var(--accent);
            color: var(--bg-dark);
            padding: 2px 10px;
            border-radius: 6px;
            font-weight: 700;
            font-size: 14px;
            margin-right: 4px;
        }

        /* Dashboard placeholder */
        .dashboard-placeholder {
            grid-column: 1 / -1;
            background: var(--white);
            border-radius: 16px;
            padding: 40px;
            text-align: center;
            border: 2px dashed var(--accent);
            margin-top: 10px;
        }

        .dashboard-placeholder .placeholder-icon {
            font-size: 48px;
            margin-bottom: 15px;
        }

        .dashboard-placeholder h4 {
            color: var(--primary);
            font-size: 18px;
            margin-bottom: 8px;
        }

        .dashboard-placeholder p {
            color: var(--text-light);
            font-size: 14px;
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

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .animate-in {
            animation: fadeInUp 0.6s ease forwards;
        }

        .delay-1 { animation-delay: 0.1s; opacity: 0; }
        .delay-2 { animation-delay: 0.2s; opacity: 0; }
        .delay-3 { animation-delay: 0.3s; opacity: 0; }
        .delay-4 { animation-delay: 0.4s; opacity: 0; }

        /* Keyboard hint */
        .keyboard-hint {
            position: fixed;
            bottom: 90px;
            left: 50%;
            transform: translateX(-50%);
            color: rgba(255,255,255,0.5);
            font-size: 12px;
            z-index: 1000;
            display: flex;
            gap: 15px;
        }

        .keyboard-hint span {
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .key {
            background: rgba(255,255,255,0.1);
            padding: 2px 8px;
            border-radius: 4px;
            border: 1px solid rgba(255,255,255,0.2);
            font-family: monospace;
        }

        /* Responsive */
        @media (max-width: 900px) {
            .slide {
                padding: 40px 30px;
            }
            .content-wrapper {
                grid-template-columns: 1fr;
                gap: 25px;
            }
            .slide-cover h1 {
                font-size: 32px;
            }
            .slide-header h2 {
                font-size: 28px;
            }
        }
    </style>
</head>
<body>
    <div class="progress-bar" id="progressBar"></div>

    <div class="presentation-container">

        <!-- Slide 1: Cover -->
        <div class="slide slide-cover active" data-index="0">
            <div class="badge">Portfolio</div>
            <h1>HR Operations &<br>HRIS Analyst Portfolio</h1>
            <p class="subtitle">CIPD Level 5 | HRIS | People Analytics</p>
            <div class="tools-grid">
                <span class="tool-tag">Power BI</span>
                <span class="tool-tag">Excel</span>
                <span class="tool-tag">SQL</span>
                <span class="tool-tag">BrightHR</span>
                <span class="tool-tag">PeopleHR</span>
                <span class="tool-tag">BambooHR</span>
                <span class="tool-tag">Workday</span>
            </div>
        </div>

        <!-- Slide 2: Profile Summary -->
        <div class="slide slide-profile" data-index="1">
            <div class="slide-header">
                <div class="label">About Me</div>
                <h2>Profile Summary</h2>
            </div>
            <div class="profile-card">
                <p class="profile-text">
                    HR Operations and HRIS professional with <span class="highlight">3+ years of experience</span> managing employee lifecycle processes, HR systems administration, and workforce analytics across <span class="highlight">multi-site environments</span>. Proven track record of maintaining HR data integrity, optimising workflows, and delivering actionable insights through <span class="highlight">Power BI and Excel</span>. Experienced in HRIS configuration, UAT testing, and employee support, with exposure to <span class="highlight">Workday environments</span>.
                </p>
            </div>
        </div>

        <!-- Slide 3: HRIS Ownership -->
        <div class="slide slide-content" data-index="2">
            <div class="slide-header">
                <div class="label">Core Competency 01</div>
                <h2>HRIS Administration & Data Governance</h2>
            </div>
            <div class="content-wrapper">
                <div class="content-box animate-in delay-1">
                    <h3><span class="icon">⚙️</span> What I Did</h3>
                    <ul>
                        <li>Managed HR systems (BrightHR, PeopleHR) across <strong>200+ employees</strong></li>
                        <li>Maintained data integrity through audits, validation, and cleansing</li>
                        <li>Configured workflows, permissions, and approvals</li>
                        <li>Ensured GDPR-compliant data governance</li>
                    </ul>
                </div>
                <div class="content-box impact-box animate-in delay-2">
                    <h3><span class="icon" style="background: rgba(232,179,57,0.3);">📈</span> Impact</h3>
                    <ul>
                        <li>High data accuracy across HR systems</li>
                        <li>Reliable reporting for leadership decisions</li>
                        <li>Audit-ready HR data environment</li>
                    </ul>
                </div>
            </div>
        </div>

        <!-- Slide 4: HR Data Analytics -->
        <div class="slide slide-content" data-index="3">
            <div class="slide-header">
                <div class="label">Core Competency 02</div>
                <h2>Workforce Analytics & Dashboard Automation</h2>
            </div>
            <div class="content-wrapper">
                <div class="content-box animate-in delay-1">
                    <h3><span class="icon">📊</span> What I Did</h3>
                    <ul>
                        <li>Built Power BI dashboards (headcount, attrition, absence)</li>
                        <li>Automated Excel reports using Power Query</li>
                        <li>Delivered insights for workforce planning</li>
                    </ul>
                </div>
                <div class="content-box impact-box animate-in delay-2">
                    <h3><span class="icon" style="background: rgba(232,179,57,0.3);">🎯</span> Impact</h3>
                    <ul>
                        <li><span class="metric">40%</span> reduction in reporting time</li>
                        <li>Improved decision-making with real-time insights</li>
                        <li>Standardised HR KPI reporting</li>
                    </ul>
                </div>
                <div class="dashboard-placeholder animate-in delay-3">
                    <div class="placeholder-icon">📸</div>
                    <h4>Dashboard Screenshot</h4>
                    <p>Add your Power BI dashboard screenshot here</p>
                </div>
            </div>
        </div>

        <!-- Slide 5: Process Improvement -->
        <div class="slide slide-content" data-index="4">
            <div class="slide-header">
                <div class="label">Core Competency 03</div>
                <h2>Onboarding Process Optimisation</h2>
            </div>
            <div class="content-wrapper">
                <div class="content-box animate-in delay-1">
                    <h3><span class="icon">🔍</span> What I Did</h3>
                    <ul>
                        <li>Analysed onboarding workflow data</li>
                        <li>Identified inefficiencies and bottlenecks</li>
                        <li>Implemented process improvements</li>
                    </ul>
                </div>
                <div class="content-box impact-box animate-in delay-2">
                    <h3><span class="icon" style="background: rgba(232,179,57,0.3);">🚀</span> Impact</h3>
                    <ul>
                        <li><span class="metric">35%</span> improvement in onboarding efficiency</li>
                        <li>Reduced delays and manual admin</li>
                    </ul>
                </div>
            </div>
        </div>

        <!-- Slide 6: Payroll -->
        <div class="slide slide-content" data-index="5">
            <div class="slide-header">
                <div class="label">Core Competency 04</div>
                <h2>Payroll Validation & HR Operations</h2>
            </div>
            <div class="content-wrapper">
                <div class="content-box animate-in delay-1">
                    <h3><span class="icon">💰</span> What I Did</h3>
                    <ul>
                        <li>Validated payroll inputs (joiners, leavers, absence, overtime)</li>
                        <li>Reconciled HR and payroll data</li>
                        <li>Supported monthly payroll cycles</li>
                    </ul>
                </div>
                <div class="content-box impact-box animate-in delay-2">
                    <h3><span class="icon" style="background: rgba(232,179,57,0.3);">✅</span> Impact</h3>
                    <ul>
                        <li>Improved payroll accuracy</li>
                        <li>Reduced compliance risks</li>
                    </ul>
                </div>
            </div>
        </div>

        <!-- Slide 7: HRIS Support -->
        <div class="slide slide-content" data-index="6">
            <div class="slide-header">
                <div class="label">Core Competency 05</div>
                <h2>Employee Support & System Adoption</h2>
            </div>
            <div class="content-wrapper">
                <div class="content-box animate-in delay-1">
                    <h3><span class="icon">🎓</span> What I Did</h3>
                    <ul>
                        <li>Provided first-line HRIS support to employees & managers</li>
                        <li>Troubleshot system issues</li>
                        <li>Delivered training and created user guides</li>
                    </ul>
                </div>
                <div class="content-box impact-box animate-in delay-2">
                    <h3><span class="icon" style="background: rgba(232,179,57,0.3);">📈</span> Impact</h3>
                    <ul>
                        <li>Improved system adoption</li>
                        <li>Reduced user errors and support tickets</li>
                    </ul>
                </div>
            </div>
        </div>

        <!-- Slide 8: Projects -->
        <div class="slide slide-content" data-index="7">
            <div class="slide-header">
                <div class="label">Core Competency 06</div>
                <h2>System Enhancement & UAT Testing</h2>
            </div>
            <div class="content-wrapper">
                <div class="content-box animate-in delay-1">
                    <h3><span class="icon">🧪</span> What I Did</h3>
                    <ul>
                        <li>Led UAT testing for HRIS updates</li>
                        <li>Supported configuration (workflows, permissions)</li>
                        <li>Managed data migration and validation</li>
                    </ul>
                </div>
                <div class="content-box impact-box animate-in delay-2">
                    <h3><span class="icon" style="background: rgba(232,179,57,0.3);">🏆</span> Impact</h3>
                    <ul>
                        <li>Smooth system updates</li>
                        <li><strong>Zero data loss</strong> during migration</li>
                        <li>Improved system usability</li>
                    </ul>
                </div>
            </div>
        </div>

    </div>

    <!-- Navigation -->
    <div class="nav-controls">
        <button class="nav-btn" onclick="prevSlide()" title="Previous">◀</button>
        <span class="slide-counter"><span id="currentSlide">1</span> / <span id="totalSlides">8</span></span>
        <button class="nav-btn" onclick="nextSlide()" title="Next">▶</button>
    </div>

    <div class="keyboard-hint">
        <span><span class="key">←</span> Prev</span>
        <span><span class="key">→</span> Next</span>
        <span><span class="key">Space</span> Next</span>
    </div>

    <script>
        let currentSlide = 0;
        const slides = document.querySelectorAll('.slide');
        const totalSlides = slides.length;

        document.getElementById('totalSlides').textContent = totalSlides;

        function updateSlide() {
            slides.forEach((slide, index) => {
                slide.classList.remove('active', 'prev');
                if (index === currentSlide) {
                    slide.classList.add('active');
                } else if (index < currentSlide) {
                    slide.classList.add('prev');
                }
            });

            document.getElementById('currentSlide').textContent = currentSlide + 1;

            const progress = ((currentSlide + 1) / totalSlides) * 100;
            document.getElementById('progressBar').style.width = progress + '%';
        }

        function nextSlide() {
            if (currentSlide < totalSlides - 1) {
                currentSlide++;
                updateSlide();
            }
        }

        function prevSlide() {
            if (currentSlide > 0) {
                currentSlide--;
                updateSlide();
            }
        }

        // Keyboard navigation
        document.addEventListener('keydown', (e) => {
            if (e.key === 'ArrowRight' || e.key === ' ' || e.key === 'PageDown') {
                e.preventDefault();
                nextSlide();
            } else if (e.key === 'ArrowLeft' || e.key === 'PageUp') {
                e.preventDefault();
                prevSlide();
            }
        });

        // Touch/swipe support
        let touchStartX = 0;
        let touchEndX = 0;

        document.addEventListener('touchstart', (e) => {
            touchStartX = e.changedTouches[0].screenX;
        });

        document.addEventListener('touchend', (e) => {
            touchEndX = e.changedTouches[0].screenX;
            if (touchStartX - touchEndX > 50) {
                nextSlide();
            } else if (touchEndX - touchStartX > 50) {
                prevSlide();
            }
        });

        updateSlide();
    </script>
</body>
</html>
