<!DOCTYPE html>
<html lang="am">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>I am Ak | Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=Noto+Sans+Ethiopic:wght@300;400;700&display=swap');
        
        :root {
            --bg-color: #050505;
            --gold-primary: #fbbf24;
            --gold-glow: rgba(251, 191, 36, 0.4);
        }

        body {
            font-family: 'Inter', 'Noto Sans Ethiopic', sans-serif;
            background-color: var(--bg-color);
            color: #fef3c7;
            scroll-behavior: smooth;
            overflow-x: hidden;
        }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
            100% { transform: translateY(0px); }
        }

        @keyframes shimmer {
            0% { background-position: -200% 0; }
            100% { background-position: 200% 0; }
        }

        @keyframes pulse-glow {
            0% { box-shadow: 0 0 5px var(--gold-glow); }
            50% { box-shadow: 0 0 25px var(--gold-glow); }
            100% { box-shadow: 0 0 5px var(--gold-glow); }
        }

        .animate-float { animation: float 4s ease-in-out infinite; }
        
        .gold-shimmer {
            background: linear-gradient(90deg, #fbbf24, #fef3c7, #fbbf24);
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: shimmer 3s linear infinite;
        }

        .vibe-badge { animation: pulse-glow 3s infinite; }

        .glass-card {
            background: rgba(15, 15, 15, 0.7);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(251, 191, 36, 0.1);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .glass-card:hover {
            border-color: var(--gold-primary);
            transform: scale(1.02);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }

        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin: auto;
            height: 350px;
        }

        .nav-link:hover {
            color: var(--gold-primary);
            text-shadow: 0 0 10px var(--gold-glow);
        }

        .lang-active {
            background-color: var(--gold-primary);
            color: black;
            box-shadow: 0 0 15px var(--gold-glow);
        }

        section {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease-out;
        }

        section.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>

    <nav class="fixed w-full z-50 bg-black/80 backdrop-blur-md border-b border-amber-500/10">
        <div class="max-w-6xl mx-auto px-4 h-20 flex items-center justify-between">
            <div class="font-black text-3xl tracking-tighter gold-shimmer uppercase">AK</div>
            
            <div class="hidden md:flex space-x-8 font-bold text-sm">
                <a href="#home" class="nav-link text-amber-100/70 transition-all" data-i18n="nav_home">መነሻ</a>
                <a href="#about" class="nav-link text-amber-100/70 transition-all" data-i18n="nav_about">ስለ እኔ</a>
                <a href="#skills" class="nav-link text-amber-100/70 transition-all" data-i18n="nav_skills">ክህሎቶች</a>
                <a href="#work" class="nav-link text-amber-100/70 transition-all" data-i18n="nav_work">ስራዎች</a>
            </div>

            <div class="flex items-center space-x-4">
                <div class="flex bg-zinc-900 rounded-lg p-1 text-xs font-bold border border-amber-500/20">
                    <button onclick="setLanguage('en')" id="lang-en" class="px-3 py-1.5 rounded-md lang-active transition-all">EN</button>
                    <button onclick="setLanguage('am')" id="lang-am" class="px-3 py-1.5 rounded-md transition-all text-amber-400/60">AM</button>
                </div>
                <!-- Updated Contact Button with links -->
                <div class="relative group hidden sm:block">
                    <button class="px-5 py-2 bg-amber-500 text-black rounded-lg hover:bg-amber-400 transition-all text-sm font-black" data-i18n="cta_contact">Contact</button>
                    <div class="absolute right-0 top-full mt-2 w-48 bg-zinc-900 border border-amber-500/20 rounded-xl overflow-hidden shadow-2xl opacity-0 group-hover:opacity-100 transition-opacity pointer-events-none group-hover:pointer-events-auto">
                        <a href="https://twitter.com/AkeEtn" target="_blank" class="block px-4 py-3 hover:bg-amber-500/10 text-amber-100 text-sm">Twitter</a>
                        <a href="mailto:akeberegn@gmail.com" class="block px-4 py-3 hover:bg-amber-500/10 text-amber-100 text-sm">Gmail</a>
                        <a href="https://t.me/Aki_GD" target="_blank" class="block px-4 py-3 hover:bg-amber-500/10 text-amber-100 text-sm">Telegram</a>
                        <a href="https://github.com/akeberegn" target="_blank" class="block px-4 py-3 hover:bg-amber-500/10 text-amber-100 text-sm">GitHub</a>
                    </div>
                </div>
            </div>
        </div>
    </nav>

    <section id="home" class="visible relative pt-48 pb-32 px-4 overflow-hidden flex flex-col items-center text-center">
        <div class="absolute top-20 left-1/2 -translate-x-1/2 w-[500px] h-[500px] bg-amber-500/5 rounded-full blur-[120px] -z-10"></div>
        
        <div class="vibe-badge inline-flex items-center px-6 py-2 bg-amber-500/10 border border-amber-500/30 text-amber-400 rounded-full text-xs font-black mb-8 uppercase tracking-widest animate-pulse" data-i18n="hero_badge">
            Vibe Coding & Trading
        </div>
        
        <h1 class="text-7xl md:text-9xl font-black mb-8 text-white leading-tight animate-float">
            <span data-i18n="hero_greet">I am</span> <span class="gold-shimmer">Ak.</span>
        </h1>
        
        <p class="text-xl md:text-3xl text-amber-100/60 mb-12 max-w-2xl leading-relaxed italic" data-i18n="hero_desc">
            "Code with Vibe. Trade with Mind."
        </p>
        
        <div class="flex flex-wrap justify-center gap-6">
            <a href="#work" class="px-12 py-5 bg-amber-500 text-black font-black rounded-2xl shadow-xl shadow-amber-500/20 hover:bg-amber-400 hover:-translate-y-1 transition-all uppercase tracking-wider" data-i18n="hero_btn_work">ፕሮጀክቶችን እይ</a>
            <a href="https://t.me/Aki_GD" target="_blank" class="px-12 py-5 bg-zinc-900 border border-amber-500/20 text-amber-400 font-black rounded-2xl hover:bg-zinc-800 transition-all uppercase tracking-wider" data-i18n="hero_btn_tele">Telegram</a>
        </div>
    </section>

    <section id="about" class="py-24">
        <div class="max-w-6xl mx-auto px-4">
            <div class="grid lg:grid-cols-2 gap-20 items-center">
                <div class="space-y-10">
                    <h2 class="text-5xl font-black text-white" data-i18n="about_title">እኔ Ak ነኝ</h2>
                    <p class="text-xl text-amber-100/60 leading-relaxed" data-i18n="about_text">
                        ዋናው አላማዬ ቴክኖሎጂን በቀላል እና በሚያዝናና መንገድ (Vibe Coding) ማስተማር ነው። የሙሉ-ስቴኩ (Full-Stack) የዌብ እና የሞባይል አፕሊኬሽን ልማት ልምዴን ተጠቅሜ የሰዎችን ችግር የሚፈቱ ዲጂታል ውጤቶችን እገነባለሁ።
                    </p>
                    <div class="p-10 glass-card border-l-8 border-amber-500 rounded-3xl animate-float">
                        <p class="italic text-amber-200 text-xl leading-relaxed font-semibold" data-i18n="about_quote">
                            "ትሬዲንግ ከቴክኒክ ትንታኔ በላይ የስነ-ልቦና ጨዋታ ነው። ለዛም ነው ትክክለኛውን የአስተሳሰብ ዘይቤ (Mindset) የማስተምረው።"
                        </p>
                    </div>
                </div>
                <div class="grid grid-cols-2 gap-8">
                    <div class="p-10 glass-card text-center">
                        <div class="text-5xl font-black text-amber-500 mb-2">Web</div>
                        <div class="text-xs text-zinc-500 uppercase font-black tracking-widest">Full Stack</div>
                    </div>
                    <div class="p-10 glass-card text-center">
                        <div class="text-5xl font-black text-amber-500 mb-2">App</div>
                        <div class="text-xs text-zinc-500 uppercase font-black tracking-widest">Mobile Dev</div>
                    </div>
                    <div class="p-10 glass-card text-center">
                        <div class="text-5xl font-black text-amber-500 mb-2">AI</div>
                        <div class="text-xs text-zinc-500 uppercase font-black tracking-widest">Python</div>
                    </div>
                    <div class="p-10 glass-card text-center">
                        <div class="text-5xl font-black text-amber-500 mb-2">Trade</div>
                        <div class="text-xs text-zinc-500 uppercase font-black tracking-widest" data-i18n="stat_psych">Psychology</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="skills" class="py-24 bg-zinc-950/40">
        <div class="max-w-4xl mx-auto px-4 text-center">
            <h2 class="text-5xl font-black mb-6 text-white" data-i18n="skills_title">የክህሎት ዳሽቦርድ</h2>
            <p class="text-amber-100/60 mb-16 text-xl" data-i18n="skills_desc">በተለያዩ የሙያ ዘርፎች ያለኝን ብቃት በዚህ ግራፍ መመልከት ይችላሉ።</p>
            <div class="chart-container glass-card p-10 rounded-[3rem] shadow-2xl">
                <canvas id="skillsChart"></canvas>
            </div>
        </div>
    </section>

    <section id="work" class="py-24">
        <div class="max-w-6xl mx-auto px-4">
            <div class="flex flex-col md:flex-row justify-between items-center mb-12 gap-8">
                <div class="text-center md:text-left">
                    <h2 class="text-5xl font-black mb-4 text-white" data-i18n="work_title">የምሰራቸው ስራዎች</h2>
                    <p class="text-amber-100/60 text-xl" data-i18n="work_desc">በአሁኑ ሰዓት ትኩረት አድርጌ እየሰራሁባቸው ያሉ ዋና ዋና ፕሮጀክቶች።</p>
                </div>
            </div>

            <!-- New Featured Projects Table -->
            <div class="glass-card p-6 md:p-8 rounded-[2rem] overflow-x-auto mb-20 border border-amber-500/20">
                <table class="w-full text-left border-collapse">
                    <thead>
                        <tr class="border-b border-amber-500/20 text-amber-500 font-black uppercase text-sm">
                            <th class="py-4 px-2">Project</th>
                            <th class="py-4 px-2">Description</th>
                            <th class="py-4 px-2">Tech</th>
                        </tr>
                    </thead>
                    <tbody class="text-amber-100/80">
                        <tr class="border-b border-amber-500/10">
                            <td class="py-4 px-2 font-bold">📱 Vibe Coding App</td>
                            <td class="py-4 px-2">Android & iOS ላይ የሚሰራ ኮዲንግ ትምህርት አፕ። Interactive lessons + AI quiz</td>
                            <td class="py-4 px-2 text-xs text-amber-500/80 font-bold">Android, iOS, AI</td>
                        </tr>
                        <tr class="border-b border-amber-500/10">
                            <td class="py-4 px-2 font-bold">🌐 Vibe Portfolio Builder</td>
                            <td class="py-4 px-2">Modern responsive website builder for Ethiopian developers</td>
                            <td class="py-4 px-2 text-xs text-amber-500/80 font-bold">React, JS</td>
                        </tr>
                        <tr class="border-b border-amber-500/10">
                            <td class="py-4 px-2 font-bold">🧠 AI Trading Mindset Assistant</td>
                            <td class="py-4 px-2">Traders ለሚጠቀሙ AI chatbot። Psychology tips, journal & emotional control</td>
                            <td class="py-4 px-2 text-xs text-amber-500/80 font-bold">Python, AI</td>
                        </tr>
                        <tr class="border-b border-amber-500/10">
                            <td class="py-4 px-2 font-bold">📊 Ak Trades Dashboard</td>
                            <td class="py-4 px-2">Trading journal + psychology tracker with daily insights</td>
                            <td class="py-4 px-2 text-xs text-amber-500/80 font-bold">Web, Firebase</td>
                        </tr>
                        <tr>
                            <td class="py-4 px-2 font-bold">📚 Vibe Coding Hub</td>
                            <td class="py-4 px-2">Interactive tutorial platform for beginners (HTML, Web Design & more)</td>
                            <td class="py-4 px-2 text-xs text-amber-500/80 font-bold">HTML, CSS, JS</td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <div id="project-grid" class="grid md:grid-cols-2 gap-12">
                <div class="project-card group glass-card p-12 rounded-[3rem]" data-type="coding">
                    <div class="w-16 h-16 bg-amber-500/10 border border-amber-500/30 rounded-2xl flex items-center justify-center mb-10 text-amber-500 font-black text-2xl group-hover:scale-110 transition-transform">VC</div>
                    <h3 class="text-3xl font-black mb-5 text-white" data-i18n="proj1_title">Vibe Coding Tutorials</h3>
                    <p class="text-amber-100/60 mb-10 text-xl leading-relaxed" data-i18n="proj1_desc">ለኢትዮጵያውያን ዲቨሎፐሮች የቀለለ እና ተግባራዊ የኮዲንግ ትምህርቶች ማዘጋጀት።</p>
                    <div class="flex space-x-4">
                        <span class="text-xs px-5 py-2 bg-amber-500/10 border border-amber-500/20 rounded-full font-black text-amber-500">YouTube</span>
                        <span class="text-xs px-5 py-2 bg-amber-500/10 border border-amber-500/20 rounded-full font-black text-amber-500" data-i18n="tag_edu">Education</span>
                    </div>
                </div>
                <div class="project-card group glass-card p-12 rounded-[3rem]" data-type="trading">
                    <div class="w-16 h-16 bg-amber-500/10 border border-amber-500/30 rounded-2xl flex items-center justify-center mb-10 text-amber-500 font-black text-2xl group-hover:scale-110 transition-transform">TP</div>
                    <h3 class="text-3xl font-black mb-5 text-white" data-i18n="proj2_title">Trading Psychology</h3>
                    <p class="text-amber-100/60 mb-10 text-xl leading-relaxed" data-i18n="proj2_desc">በ Ak_Trades_Oficial ቻናል በኩል የትሬደሮችን አስተሳሰብ እና የገበያ ስነ-ልቦና ማሻሻል።</p>
                    <div class="flex space-x-4">
                        <span class="text-xs px-5 py-2 bg-amber-500/10 border border-amber-500/20 rounded-full font-black text-amber-500">Telegram</span>
                        <span class="text-xs px-5 py-2 bg-amber-500/10 border border-amber-500/20 rounded-full font-black text-amber-500" data-i18n="tag_mind">Mindset</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer class="py-24 border-t border-amber-500/10 bg-black">
        <div class="max-w-6xl mx-auto px-4 text-center">
            <h2 class="text-5xl font-black mb-10 gold-shimmer uppercase">I am Ak</h2>
            <p class="text-amber-100/40 text-xl mb-12" data-i18n="footer_desc">"Code with Vibe. Trade with Mind." አብረን እንስራ።</p>
            <div class="flex justify-center space-x-8 mb-16">
                <a href="https://t.me/Aki_GD" class="w-14 h-14 flex items-center justify-center bg-zinc-900 border border-amber-500/20 rounded-2xl hover:bg-amber-500 hover:text-black transition-all font-black">T</a>
                <a href="https://twitter.com/AkeEtn" class="w-14 h-14 flex items-center justify-center bg-zinc-900 border border-amber-500/20 rounded-2xl hover:bg-amber-500 hover:text-black transition-all font-black">X</a>
                <a href="https://github.com/akeberegn" class="w-14 h-14 flex items-center justify-center bg-zinc-900 border border-amber-500/20 rounded-2xl hover:bg-amber-500 hover:text-black transition-all font-black">G</a>
            </div>
            <div class="text-amber-500/20 text-sm font-bold uppercase tracking-widest">
                &copy; 2024 I AM AK. VIBE CODING & TRADING.
            </div>
        </div>
    </footer>

    <script>
        const langData = {
            am: {
                nav_home: "መነሻ", nav_about: "ስለ እኔ", nav_skills: "ክህሎቶች", nav_work: "ስራዎች", cta_contact: "አግኘኝ",
                hero_greet: "እኔ", hero_badge: "Vibe Coding & Trading", hero_desc: '"Code with Vibe. Trade with Mind."',
                hero_btn_work: "ፕሮጀክቶችን እይ", hero_btn_tele: "Telegram", about_title: "እኔ Ak ነኝ",
                about_text: "ዋናው አላማዬ ቴክኖሎጂን በቀላል እና በሚያዝናና መንገድ (Vibe Coding) ማስተማር ነው። የሙሉ-ስቴኩ (Full-Stack) የዌብ እና የሞባይል አፕሊኬሽን ልማት ልምዴን ተጠቅሜ የሰዎችን ችግር የሚፈቱ ዲጂታል ውጤቶችን እገነባለሁ።",
                about_quote: '"ትሬዲንግ ከቴክኒክ ትንታኔ በላይ የስነ-ልቦና ጨዋታ ነው። ለዛም ነው ትክክለኛውን የአስተሳሰብ ዘይቤ (Mindset) የማስተምረው።"',
                stat_psych: "ስነ-ልቦና", skills_title: "የክህሎት ዳሽቦርድ", skills_desc: "በተለያዩ የሙያ ዘርፎች ያለኝን ብቃት በዚህ ግራፍ መመልከት ይችላሉ።",
                work_title: "የምሰራቸው ስራዎች", work_desc: "በአሁኑ ሰዓት ትኩረት አድርጌ እየሰራሁባቸው ያሉ ዋና ዋና ፕሮጀክቶች።",
                filter_all: "ሁሉንም", filter_coding: "ኮዲንግ", filter_trading: "ትሬዲንግ", proj1_title: "Vibe Coding Tutorials",
                proj1_desc: "ለኢትዮጵያውያን ዲቨሎፐሮች የቀለለ እና ተግባራዊ የኮዲንግ ትምህርቶች ማዘጋጀት።", proj2_title: "Trading Psychology",
                proj2_desc: "በ Ak_Trades_Oficial ቻናል በኩል የትሬደሮችን አስተሳሰብ እና የገበያ ስነ-ልቦና ማሻሻል።", tag_edu: "ትምህርት", tag_mind: "አስተሳሰብ",
                footer_desc: '"Code with Vibe. Trade with Mind." አብረን እንስራ።', chart_labels: ['ፍሮንት-እንድ', 'ባክ-እንድ', 'ሞባይል', 'AI መሳሪያዎች', 'ትሬዲንግ ስነ-ልቦና', 'ዲዛይን']
            },
            en: {
                nav_home: "Home", nav_about: "About", nav_skills: "Skills", nav_work: "Work", cta_contact: "Contact",
                hero_greet: "I am", hero_badge: "Vibe Coding & Trading", hero_desc: '"Code with Vibe. Trade with Mind."',
                hero_btn_work: "View Projects", hero_btn_tele: "Telegram", about_title: "I am Ak",
                about_text: "My mission is to teach technology through simplicity and fun (Vibe Coding). As a Full-Stack developer, I build digital products that solve human problems.",
                about_quote: '"Trading is a mental game beyond technical analysis. That is why I focus on teaching the right mindset."',
                stat_psych: "Psychology", skills_title: "Skill Dashboard", skills_desc: "Overview of my professional expertise across key domains.",
                work_title: "Featured Projects", work_desc: "Major projects I am currently developing and scaling.",
                filter_all: "All", filter_coding: "Coding", filter_trading: "Trading", proj1_title: "Vibe Coding Tutorials",
                proj1_desc: "Practical coding tutorials specifically designed for the Ethiopian developer community.",
                proj2_title: "Trading Psychology", proj2_desc: "Mastering market mindset and psychology through Ak_Trades_Oficial.",
                tag_edu: "Education", tag_mind: "Mindset", footer_desc: '"Code with Vibe. Trade with Mind." Let\'s connect.',
                chart_labels: ['Frontend', 'Backend', 'Mobile', 'AI Tools', 'Trading Psych', 'Design']
            }
        };

        let currentLang = 'en';
        let skillsChart;

        function setLanguage(lang) {
            currentLang = lang;
            document.getElementById('lang-am').classList.toggle('lang-active', lang === 'am');
            document.getElementById('lang-en').classList.toggle('lang-active', lang === 'en');
            document.querySelectorAll('[data-i18n]').forEach(el => {
                const key = el.getAttribute('data-i18n');
                if (langData[lang][key]) el.innerText = langData[lang][key];
            });
            updateChart();
        }

        function initChart() {
            const ctx = document.getElementById('skillsChart').getContext('2d');
            skillsChart = new Chart(ctx, {
                type: 'radar',
                data: {
                    labels: langData[currentLang].chart_labels,
                    datasets: [{
                        label: 'Skill Level',
                        data: [95, 82, 88, 75, 94, 85],
                        backgroundColor: 'rgba(251, 191, 36, 0.2)',
                        borderColor: '#fbbf24', borderWidth: 3,
                        pointBackgroundColor: '#fbbf24', pointBorderColor: '#000', pointHoverRadius: 8
                    }]
                },
                options: {
                    maintainAspectRatio: false,
                    scales: { r: { angleLines: { color: 'rgba(251, 191, 36, 0.1)' }, grid: { color: 'rgba(251, 191, 36, 0.1)' }, pointLabels: { color: '#fbbf24', font: { size: 14, weight: 'bold' } }, ticks: { display: false }, suggestedMin: 0, suggestedMax: 100 } },
                    plugins: { legend: { display: false } }
                }
            });
        }

        function updateChart() {
            if (skillsChart) {
                skillsChart.data.labels = langData[currentLang].chart_labels;
                skillsChart.update();
            }
        }

        function filterProjects(type) {
            const cards = document.querySelectorAll('.project-card');
            const buttons = document.querySelectorAll('.filter-btn');
            buttons.forEach(btn => {
                const key = btn.getAttribute('data-i18n');
                const btnType = key === 'filter_all' ? 'all' : key.split('_')[1];
                btn.classList.toggle('bg-amber-500', btnType === type);
                btn.classList.toggle('text-black', btnType === type);
                btn.classList.toggle('text-amber-100/40', btnType !== type);
            });
            cards.forEach(card => {
                if (type === 'all' || card.getAttribute('data-type') === type) {
                    card.style.display = 'block';
                    card.style.opacity = '1';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => { if (entry.isIntersecting) entry.target.classList.add('visible'); });
        }, { threshold: 0.1 });

        window.onload = () => {
            initChart();
            setLanguage('en');
            document.querySelectorAll('section').forEach(section => observer.observe(section));
        };
    </script>
</body>
</html>
