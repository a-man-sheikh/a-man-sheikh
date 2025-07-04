<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aman Sheikh - Full Stack Developer</title>
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
        }

        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: #fff;
            border-radius: 50%;
            animation: twinkle 3s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 1; }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            text-align: center;
            padding: 60px 0;
            position: relative;
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 5px solid #fff;
            margin: 0 auto 20px;
            display: block;
            background: linear-gradient(45deg, #22c55e, #84cc16);
            animation: float 3s ease-in-out infinite;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .profile-img:hover {
            transform: scale(1.1) rotate(5deg);
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .name {
            font-size: 3.5em;
            font-weight: bold;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #22c55e, #84cc16, #fff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { text-shadow: 0 0 20px #22c55e; }
            to { text-shadow: 0 0 30px #84cc16; }
        }

        .title {
            font-size: 1.8em;
            margin-bottom: 20px;
            opacity: 0.9;
        }

        .typing-text {
            font-size: 1.2em;
            border-right: 2px solid #22c55e;
            white-space: nowrap;
            overflow: hidden;
            animation: typing 3s steps(30, end), blink 1s infinite;
        }

        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }

        @keyframes blink {
            0%, 50% { border-color: transparent; }
            51%, 100% { border-color: #22c55e; }
        }

        .game-section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            margin: 40px 0;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        }

        .snake-game {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }

        .game-canvas {
            border: 3px solid #22c55e;
            border-radius: 10px;
            background: #000;
        }

        .game-controls {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .btn {
            padding: 12px 24px;
            background: linear-gradient(45deg, #22c55e, #84cc16);
            border: none;
            border-radius: 25px;
            color: #000;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(34, 197, 94, 0.4);
        }

        .skills-section {
            margin: 40px 0;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .skill-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .skill-card:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .skill-card:hover::before {
            left: 100%;
        }

        .skill-icon {
            font-size: 2.5em;
            margin-bottom: 10px;
            display: block;
        }

        .contact-section {
            text-align: center;
            margin: 40px 0;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .contact-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 25px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .contact-card:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.2);
        }

        .section-title {
            font-size: 2.5em;
            text-align: center;
            margin-bottom: 30px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(45deg, #22c55e, #84cc16);
            border-radius: 2px;
        }

        .stats-section {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat-number {
            font-size: 3em;
            font-weight: bold;
            color: #22c55e;
            display: block;
            margin-bottom: 10px;
        }

        .quiz-section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            margin: 40px 0;
        }

        .quiz-question {
            font-size: 1.3em;
            margin-bottom: 20px;
        }

        .quiz-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-bottom: 20px;
        }

        .quiz-option {
            padding: 15px;
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid transparent;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
        }

        .quiz-option:hover {
            border-color: #22c55e;
            background: rgba(34, 197, 94, 0.2);
        }

        .quiz-option.correct {
            background: rgba(34, 197, 94, 0.5);
            border-color: #22c55e;
        }

        .quiz-option.wrong {
            background: rgba(239, 68, 68, 0.5);
            border-color: #ef4444;
        }

        .footer {
            text-align: center;
            padding: 40px 0;
            background: rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(10px);
            margin-top: 60px;
        }

        .floating-shapes {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .shape {
            position: absolute;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            animation: float-shapes 6s infinite ease-in-out;
        }

        @keyframes float-shapes {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .score {
            font-size: 1.5em;
            font-weight: bold;
            color: #22c55e;
            margin: 20px 0;
        }

        @media (max-width: 768px) {
            .name { font-size: 2.5em; }
            .title { font-size: 1.4em; }
            .skills-grid { grid-template-columns: repeat(auto-fit, minmax(100px, 1fr)); }
            .game-canvas { width: 280px; height: 280px; }
        }
    </style>
</head>
<body>
    <div class="stars"></div>
    <div class="floating-shapes"></div>
    
    <div class="container">
        <header class="header">
            <div class="profile-img" onclick="profileClick()"></div>
            <h1 class="name">Aman Sheikh</h1>
            <h2 class="title">Full Stack Web Developer</h2>
            <p class="typing-text">I love to code and design!!!</p>
        </header>

        <section class="game-section">
            <h2 class="section-title">🎮 Snake Game Challenge</h2>
            <div class="snake-game">
                <canvas class="game-canvas" id="gameCanvas" width="400" height="400"></canvas>
                <div class="game-controls">
                    <button class="btn" onclick="startGame()">Start Game</button>
                    <button class="btn" onclick="pauseGame()">Pause</button>
                    <button class="btn" onclick="resetGame()">Reset</button>
                </div>
                <div class="score">Score: <span id="score">0</span></div>
            </div>
        </section>

        <section class="skills-section">
            <h2 class="section-title">🚀 Technical Skills</h2>
            <div class="skills-grid">
                <div class="skill-card" onclick="animateSkill(this)">
                    <span class="skill-icon">🔥</span>
                    <h3>JavaScript</h3>
                </div>
                <div class="skill-card" onclick="animateSkill(this)">
                    <span class="skill-icon">⚛️</span>
                    <h3>React</h3>
                </div>
                <div class="skill-card" onclick="animateSkill(this)">
                    <span class="skill-icon">🟢</span>
                    <h3>Node.js</h3>
                </div>
                <div class="skill-card" onclick="animateSkill(this)">
                    <span class="skill-icon">☕</span>
                    <h3>Java</h3>
                </div>
                <div class="skill-card" onclick="animateSkill(this)">
                    <span class="skill-icon">🍃</span>
                    <h3>Spring Boot</h3>
                </div>
                <div class="skill-card" onclick="animateSkill(this)">
                    <span class="skill-icon">🍃</span>
                    <h3>MongoDB</h3>
                </div>
                <div class="skill-card" onclick="animateSkill(this)">
                    <span class="skill-icon">🐬</span>
                    <h3>MySQL</h3>
                </div>
                <div class="skill-card" onclick="animateSkill(this)">
                    <span class="skill-icon">🎨</span>
                    <h3>CSS3</h3>
                </div>
                <div class="skill-card" onclick="animateSkill(this)">
                    <span class="skill-icon">🌐</span>
                    <h3>HTML5</h3>
                </div>
                <div class="skill-card" onclick="animateSkill(this)">
                    <span class="skill-icon">🔧</span>
                    <h3>Git</h3>
                </div>
                <div class="skill-card" onclick="animateSkill(this)">
                    <span class="skill-icon">🐧</span>
                    <h3>Linux</h3>
                </div>
                <div class="skill-card" onclick="animateSkill(this)">
                    <span class="skill-icon">⚡</span>
                    <h3>Next.js</h3>
                </div>
            </div>
        </section>

        <section class="quiz-section">
            <h2 class="section-title">🧠 Developer Quiz</h2>
            <div id="quiz-container">
                <div class="quiz-question" id="question">What is React?</div>
                <div class="quiz-options">
                    <div class="quiz-option" onclick="selectAnswer(this, false)">A database</div>
                    <div class="quiz-option" onclick="selectAnswer(this, true)">A JavaScript library</div>
                    <div class="quiz-option" onclick="selectAnswer(this, false)">A CSS framework</div>
                    <div class="quiz-option" onclick="selectAnswer(this, false)">A web server</div>
                </div>
                <div class="score">Quiz Score: <span id="quizScore">0</span></div>
            </div>
        </section>

        <section class="stats-section">
            <div class="stat-card">
                <span class="stat-number" id="projects">25+</span>
                <h3>Projects Completed</h3>
            </div>
            <div class="stat-card">
                <span class="stat-number" id="experience">3+</span>
                <h3>Years Experience</h3>
            </div>
            <div class="stat-card">
                <span class="stat-number" id="technologies">15+</span>
                <h3>Technologies</h3>
            </div>
            <div class="stat-card">
                <span class="stat-number" id="coffee">∞</span>
                <h3>Cups of Coffee</h3>
            </div>
        </section>

        <section class="contact-section">
            <h2 class="section-title">📫 Get In Touch</h2>
            <div class="contact-grid">
                <div class="contact-card" onclick="openContact('email')">
                    <h3>📧 Email</h3>
                    <p>sheikhaman0321@gmail.com</p>
                </div>
                <div class="contact-card" onclick="openContact('github')">
                    <h3>🐙 GitHub</h3>
                    <p>@a-man-sheikh</p>
                </div>
                <div class="contact-card" onclick="openContact('linkedin')">
                    <h3>💼 LinkedIn</h3>
                    <p>@a-mansheikh</p>
                </div>
                <div class="contact-card" onclick="openContact('twitter')">
                    <h3>🐦 Twitter</h3>
                    <p>@a_man_sheikh</p>
                </div>
                <div class="contact-card" onclick="openContact('medium')">
                    <h3>📝 Medium</h3>
                    <p>@a_man_sheikh</p>
                </div>
                <div class="contact-card">
                    <h3>🌍 Location</h3>
                    <p>Ujjain, India</p>
                </div>
            </div>
        </section>
    </div>

    <footer class="footer">
        <p>✨ Made with love by Aman Sheikh | Currently learning React & Spring Boot ✨</p>
        <p>🎬 Movies & 📚 Books enthusiast | 🤝 Open to collaboration</p>
    </footer>

    <script>
        // Initialize stars
        function createStars() {
            const starsContainer = document.querySelector('.stars');
            for (let i = 0; i < 100; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.animationDelay = Math.random() * 3 + 's';
                starsContainer.appendChild(star);
            }
        }

        // Initialize floating shapes
        function createShapes() {
            const shapesContainer = document.querySelector('.floating-shapes');
            for (let i = 0; i < 10; i++) {
                const shape = document.createElement('div');
                shape.className = 'shape';
                shape.style.left = Math.random() * 100 + '%';
                shape.style.top = Math.random() * 100 + '%';
                shape.style.width = Math.random() * 20 + 10 + 'px';
                shape.style.height = shape.style.width;
                shape.style.animationDelay = Math.random() * 6 + 's';
                shapesContainer.appendChild(shape);
            }
        }

        // Profile click animation
        function profileClick() {
            const profile = document.querySelector('.profile-img');
            profile.style.animation = 'none';
            setTimeout(() => {
                profile.style.animation = 'float 3s ease-in-out infinite';
            }, 100);
            
            // Create celebration particles
            for (let i = 0; i < 20; i++) {
                const particle = document.createElement('div');
                particle.style.position = 'fixed';
                particle.style.left = '50%';
                particle.style.top = '200px';
                particle.style.width = '4px';
                particle.style.height = '4px';
                particle.style.background = '#22c55e';
                particle.style.borderRadius = '50%';
                particle.style.pointerEvents = 'none';
                particle.style.zIndex = '1000';
                document.body.appendChild(particle);
                
                const angle = (i / 20) * Math.PI * 2;
                const velocity = 100 + Math.random() * 50;
                const vx = Math.cos(angle) * velocity;
                const vy = Math.sin(angle) * velocity;
                
                particle.animate([
                    { transform: 'translate(0, 0)', opacity: 1 },
                    { transform: `translate(${vx}px, ${vy}px)`, opacity: 0 }
                ], {
                    duration: 1000,
                    easing: 'ease-out'
                }).onfinish = () => particle.remove();
            }
        }

        // Snake Game
        let game = {
            canvas: null,
            ctx: null,
            snake: [{x: 200, y: 200}],
            food: {x: 100, y: 100},
            direction: {x: 0, y: 0},
            score: 0,
            gameRunning: false,
            gameLoop: null
        };

        function initGame() {
            game.canvas = document.getElementById('gameCanvas');
            game.ctx = game.canvas.getContext('2d');
            generateFood();
        }

        function startGame() {
            if (!game.gameRunning) {
                game.gameRunning = true;
                game.gameLoop = setInterval(updateGame, 150);
            }
        }

        function pauseGame() {
            game.gameRunning = false;
            clearInterval(game.gameLoop);
        }

        function resetGame() {
            pauseGame();
            game.snake = [{x: 200, y: 200}];
            game.direction = {x: 0, y: 0};
            game.score = 0;
            document.getElementById('score').textContent = game.score;
            generateFood();
            drawGame();
        }

        function generateFood() {
            game.food = {
                x: Math.floor(Math.random() * 20) * 20,
                y: Math.floor(Math.random() * 20) * 20
            };
        }

        function updateGame() {
            if (!game.gameRunning) return;

            const head = {x: game.snake[0].x + game.direction.x, y: game.snake[0].y + game.direction.y};

            // Check wall collision
            if (head.x < 0 || head.x >= 400 || head.y < 0 || head.y >= 400) {
                gameOver();
                return;
            }

            // Check self collision
            if (game.snake.some(segment => segment.x === head.x && segment.y === head.y)) {
                gameOver();
                return;
            }

            game.snake.unshift(head);

            // Check food collision
            if (head.x === game.food.x && head.y === game.food.y) {
                game.score++;
                document.getElementById('score').textContent = game.score;
                generateFood();
            } else {
                game.snake.pop();
            }

            drawGame();
        }

        function drawGame() {
            game.ctx.fillStyle = '#000';
            game.ctx.fillRect(0, 0, 400, 400);

            // Draw snake
            game.ctx.fillStyle = '#22c55e';
            game.snake.forEach(segment => {
                game.ctx.fillRect(segment.x, segment.y, 18, 18);
            });

            // Draw food
            game.ctx.fillStyle = '#ef4444';
            game.ctx.fillRect(game.food.x, game.food.y, 18, 18);
        }

        function gameOver() {
            pauseGame();
            alert(`Game Over! Your score: ${game.score}`);
        }

        // Game controls
        document.addEventListener('keydown', (e) => {
            if (!game.gameRunning) return;
            
            switch(e.key) {
                case 'ArrowUp':
                    if (game.direction.y === 0) game.direction = {x: 0, y: -20};
                    break;
                case 'ArrowDown':
                    if (game.direction.y === 0) game.direction = {x: 0, y: 20};
                    break;
                case 'ArrowLeft':
                    if (game.direction.x === 0) game.direction = {x: -20, y: 0};
                    break;
                case 'ArrowRight':
                    if (game.direction.x === 0) game.direction = {x: 20, y: 0};
                    break;
            }
        });

        // Skill animation
        function animateSkill(element) {
            element.style.transform = 'scale(1.2) rotate(360deg)';
            setTimeout(() => {
                element.style.transform = '';
            }, 600);
        }

        // Quiz functionality
        const quizQuestions = [
            {
                question: "What is React?",
                options: ["A database", "A JavaScript library", "A CSS framework", "A web server"],
                correct: 1
            },
            {
                question: "What does HTML stand for?",
                options: ["Hypertext Markup Language", "High-level Programming Language", "Home Tool Markup Language", "Hyperlink and Text Markup Language"],
                correct: 0
            },
            {
                question: "Which company developed Spring Boot?",
                options: ["Google", "Microsoft", "Pivotal", "Oracle"],
                correct: 2
            },
            {
                question: "What is Node.js?",
                options: ["A web browser", "A JavaScript runtime", "A CSS preprocessor", "A database"],
                correct: 1
            }
        ];

        let currentQuiz = 0;
        let quizScore = 0;

        function selectAnswer(element, isCorrect) {
            const options = document.querySelectorAll('.quiz-option');
            options.forEach(option => {
                option.style.pointerEvents = 'none';
                if (option === element) {
                    option.classList.add(isCorrect ? 'correct' : 'wrong');
                }
            });

            if (isCorrect) {
                quizScore++;
                document.getElementById('quizScore').textContent = quizScore;
            }

            setTimeout(() => {
                loadNextQuestion();
            }, 1500);
        }

        function loadNextQuestion() {
            currentQuiz = (currentQuiz + 1) % quizQuestions.length;
            const question = quizQuestions[currentQuiz];
            
            document.getElementById('question').textContent = question.question;
            
            const options = document.querySelectorAll('.quiz-option');
            options.forEach((option, index) => {
                option.textContent = question.options[index];
                option.className = 'quiz-option';
                option.style.pointerEvents = 'auto';
                option.onclick = () => selectAnswer(option, index === question.correct);
            });
        }

        // Contact functions
        function openContact(type) {
            const links = {
                email: 'mailto:sheikhaman0321@gmail.com',
                github: 'https://github.com/a-man-sheikh',
                linkedin: 'https://linkedin.com/in/a-mansheikh',
                twitter: 'https://x.com/a_man_sheikh',
                medium: 'https://medium.com/@a_man_sheikh'
            };
            
            if (links[type]) {
                window.open(links[type], '_blank');
            }
        }

        // Counter animation
        function animateCounters() {
            const counters = document.querySelectorAll('.stat-number');
            counters.forEach(counter => {
                const target = counter.textContent;
                if (target.includes('+')) {
                    const num = parseInt(target);
                    let current = 0;
                    const increment = num / 20;
                    const timer = setInterval(() => {
                        current += increment;
                        if (current >= num) {
                            counter.textContent = target;
                            clearInterval(timer);
                        } else {
                            counter.textContent = Math.floor(current) + '+';
                        }
                    }, 50);
                }
            });
        }

        // Initialize everything
        document.addEventListener('DOMContentLoaded', () => {
            createStars();
            createShapes();
            initGame();
            drawGame();
            animateCounters();
        });
    </script>
</body>
</html>
