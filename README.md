<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zachary Henley - Data-Driven Professional</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;900&display=swap" rel="stylesheet">
    <style>
        html {
            scroll-behavior: smooth;
        }
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0d1117;
            color: #f1f5f9;
            overflow-x: hidden;
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: radial-gradient(circle at 15% 25%, rgba(255, 166, 0, 0.2) 0%, transparent 25%),
                        radial-gradient(circle at 85% 75%, rgba(239, 86, 117, 0.2) 0%, transparent 25%);
            z-index: -1;
            animation: move-aurora 15s infinite alternate;
        }

        @keyframes move-aurora {
            from {
                transform: rotate(0deg);
            }
            to {
                transform: rotate(360deg);
            }
        }

        .chart-container {
            position: relative;
            width: 100%;
            max-width: 400px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 350px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 350px;
            }
        }

        .stat-card {
            background-color: rgba(28, 28, 30, 0.5);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-radius: 1rem;
            padding: 1.5rem;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 10px 30px -5px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
            display: flex;
            flex-direction: column;
        }

        .stat-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 40px -10px rgba(0, 0, 0, 0.3);
            border-color: rgba(255, 166, 0, 0.5);
        }
        
        .interactive-card {
            cursor: pointer;
        }

        .gradient-text {
            background: linear-gradient(90deg, #ffa600, #ff764a);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-fill-color: transparent;
        }
        
        .flow-step {
            border-left: 4px solid #ffa600;
        }

        .flow-arrow {
            color: #ffa600;
            font-weight: bold;
            font-size: 2rem;
            text-align: center;
            margin: 0.5rem 0;
            animation: pulse-arrow 2s infinite;
        }

        @keyframes pulse-arrow {
            0%, 100% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.1); opacity: 0.7; }
        }
        
        .bg-custom-grey {
            background-color: rgba(42, 42, 45, 0.6);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .toolkit-link {
            text-decoration: none;
            color: #f1f5f9;
            position: relative;
            transition: color 0.3s ease;
        }
        .toolkit-link::after {
            content: '';
            position: absolute;
            width: 100%;
            transform: scaleX(0);
            height: 2px;
            bottom: -4px;
            left: 0;
            background-color: #ffa600;
            transform-origin: bottom right;
            transition: transform 0.3s ease-out;
        }
        .toolkit-link:hover {
            color: #ffa600;
        }
        .toolkit-link:hover::after {
            transform: scaleX(1);
            transform-origin: bottom left;
        }
        
        #subtitle-cursor {
            animation: blink 1s step-end infinite;
        }

        @keyframes blink {
            from, to { color: transparent; }
            50% { color: #ffa600; }
        }

        .fade-in-up {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }
        .fade-in-up.is-visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body class="antialiased">

    <div class="container mx-auto p-4 md:p-8">

        <header class="text-center mb-16">
            <h1 class="text-5xl md:text-7xl font-black mb-2 gradient-text">Zachary Henley</h1>
            <p id="animated-subtitle" class="text-xl md:text-2xl font-semibold text-slate-300 min-h-[32px]"></p>
            <div class="flex justify-center items-center gap-4 mt-6">
                <a href="mailto:zacharybhenley@gmail.com" class="text-slate-400 hover:text-amber-400 transition-colors" title="Email">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" /></svg>
                </a>
                <a href="https://www.linkedin.com/in/zachary-henley" target="_blank" rel="noopener noreferrer" class="text-slate-400 hover:text-amber-400 transition-colors" title="LinkedIn">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" viewBox="0 0 24 24" fill="currentColor"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
                </a>
                <a href="https://www.kaggle.com/zacharyhenley" target="_blank" rel="noopener noreferrer" class="text-slate-400 hover:text-amber-400 transition-colors" title="Kaggle">
                     <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" viewBox="0 0 24 24" fill="currentColor"><path d="M12.2,16.2l-3.8-3.8l3.8-3.8l1.2,1.2l-2.6,2.6l2.6,2.6L12.2,16.2z M18,12l-6,6l-1.2-1.2l4.8-4.8l-4.8-4.8L12,6L18,12z"/></svg>
                </a>
            </div>
        </header>

        <main class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            
            <div class="stat-card md:col-span-2 lg:col-span-3 fade-in-up">
                <h2 class="text-2xl font-bold text-white mb-4">Professional Summary</h2>
                <p class="text-slate-300 leading-relaxed">Driven and results-oriented professional with a proven record of exceeding sales targets by up to 150%. My experience in consultative sales and strategic prospecting has honed my ability to identify needs, build strong client relationships, and generate significant revenue. I leverage a unique analytical perspective, using data to inform outreach strategies and unlock strategic opportunities. I am eager to apply my skills in exceeding quotas and fostering client retention to a dynamic recruiting or sales role.</p>
            </div>

            <div class="stat-card lg:col-span-1 md:col-span-1 fade-in-up">
                <h2 class="text-2xl font-bold text-white mb-1">Strategic Revenue Generation</h2>
                <p class="text-slate-300 mb-4">At Green Solar Technologies, an analytical approach to sales led to exceptional performance.</p>
                <div class="chart-container mt-auto">
                    <canvas id="revenueBarChart"></canvas>
                </div>
            </div>

            <div class="stat-card lg:col-span-1 md:col-span-1 fade-in-up interactive-card" style="transition-delay: 150ms;" onclick="document.getElementById('case-study-dasalla').scrollIntoView();">
                <h2 class="text-2xl font-bold text-white mb-4">High-Impact Results</h2>
                <p class="text-slate-300 mb-6">Driving tangible financial outcomes through data-informed strategies. Click a card to learn more.</p>
                <div class="space-y-4 mt-auto">
                    <div class="bg-custom-grey p-4 rounded-lg text-center hover:bg-amber-800/50 transition-colors">
                        <p class="text-lg font-semibold text-slate-300">Revenue Generated</p>
                        <p class="text-5xl font-extrabold" style="color: #ffa600;">$720,000</p>
                        <p class="text-slate-400 mt-1">at Green Solar</p>
                    </div>
                    <div class="bg-custom-grey p-4 rounded-lg text-center hover:bg-amber-800/50 transition-colors">
                        <p class="text-lg font-semibold text-slate-300">Product Line Analyzed</p>
                        <p class="text-5xl font-extrabold" style="color: #ff764a;">$2,000,000</p>
                        <p class="text-slate-400 mt-1">as Product Manager</p>
                    </div>
                    <div class="bg-custom-grey p-4 rounded-lg text-center hover:bg-amber-800/50 transition-colors">
                        <p class="text-lg font-semibold text-slate-300">Inventory Return Authorized</p>
                        <p class="text-5xl font-extrabold" style="color: #ef5675;">$300,000</p>
                        <p class="text-slate-400 mt-1">to improve cash flow</p>
                    </div>
                </div>
            </div>

            <div class="stat-card lg:col-span-1 md:col-span-2 fade-in-up" style="transition-delay: 300ms;">
                <h2 class="text-2xl font-bold text-white mb-1">Consistent Over-Performance</h2>
                <p class="text-slate-300 mb-4">A track record of exceeding targets across different roles and companies.</p>
                <div class="chart-container mt-auto">
                    <canvas id="performanceBarChart"></canvas>
                </div>
            </div>

            <div id="case-study-gst" class="stat-card md:col-span-2 lg:col-span-3 fade-in-up">
                <h2 class="text-2xl font-bold text-white mb-1">Case Study: Driving Growth at Green Solar Technologies</h2>
                <p class="text-slate-300 mb-6">As a Sales Development Representative, I utilized CRM data to create highly effective, targeted sales campaigns.</p>
                <div class="grid grid-cols-1 md:grid-cols-3 items-center gap-4 text-center md:text-left">
                    <div class="flow-step pl-4">
                        <h3 class="text-xl font-bold text-white flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-amber-400" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" /></svg>1. Analysis</h3>
                        <p class="text-slate-300">Leveraged Velocify CRM to analyze lead data and identify high-potential prospects for targeted energy solution consulting.</p>
                    </div>
                    <div class="flow-arrow hidden md:block">&#10230;</div>
                    <div class="flow-arrow md:hidden">&#11167;</div>
                    <div class="flow-step pl-4">
                        <h3 class="text-xl font-bold text-white flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-amber-400" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" /></svg>2. Action</h3>
                        <p class="text-slate-300">Executed strategic email and phone campaigns, focusing on a consultative sales approach to address specific client needs.</p>
                    </div>
                    <div class="flow-arrow hidden md:block">&#10230;</div>
                    <div class="flow-arrow md:hidden">&#11167;</div>
                    <div class="flow-step pl-4">
                        <h3 class="text-xl font-bold text-white flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-amber-400" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6" /></svg>3. Outcome</h3>
                        <p class="text-slate-300">Generated <strong class="text-amber-400">$720,000 in revenue</strong> and consistently exceeded monthly quotas by <strong class="text-amber-400">150%</strong>, demonstrating significant ROI.</p>
                    </div>
                </div>
            </div>

            <div id="case-study-spectrum" class="stat-card md:col-span-2 lg:col-span-3 fade-in-up">
                <h2 class="text-2xl font-bold text-white mb-1">Case Study: Maximizing Sales at Spectrum</h2>
                <p class="text-slate-300 mb-6">As a Customer Sales Representative, I focused on data analysis to refine sales strategies and boost performance.</p>
                <div class="grid grid-cols-1 md:grid-cols-3 items-center gap-4 text-center md:text-left">
                    <div class="flow-step pl-4">
                        <h3 class="text-xl font-bold text-white flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-amber-400" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" /></svg>1. Analysis</h3>
                        <p class="text-slate-300">Performed analysis of customer needs and historical buying patterns to identify upselling opportunities and refine sales tactics.</p>
                    </div>
                    <div class="flow-arrow hidden md:block">&#10230;</div>
                    <div class="flow-arrow md:hidden">&#11167;</div>
                    <div class="flow-step pl-4">
                        <h3 class="text-xl font-bold text-white flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-amber-400" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" /></svg>2. Action</h3>
                        <p class="text-slate-300">Employed a consultative selling process to acquire over <strong class="text-amber-400">60 new accounts monthly</strong>, tailoring solutions to individual customer requirements.</p>
                    </div>
                    <div class="flow-arrow hidden md:block">&#10230;</div>
                    <div class="flow-arrow md:hidden">&#11167;</div>
                    <div class="flow-step pl-4">
                        <h3 class="text-xl font-bold text-white flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-amber-400" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6" /></svg>3. Outcome</h3>
                        <p class="text-slate-300">Sustained a <strong class="text-amber-400">120% quota achievement rate</strong> and increased customer satisfaction and retention through strong relationship building.</p>
                    </div>
                </div>
            </div>
            
            <div id="case-study-dasalla" class="stat-card md:col-span-2 lg:col-span-3 fade-in-up">
                <h2 class="text-2xl font-bold text-white mb-1">Case Study: Product Management at Dasalla Trading</h2>
                <p class="text-slate-300 mb-6">As a Product Manager, I applied a data-driven process to enhance operational and financial efficiency.</p>
                <div class="grid grid-cols-1 md:grid-cols-3 items-center gap-4 text-center md:text-left">
                    <div class="flow-step pl-4">
                        <h3 class="text-xl font-bold text-white flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-amber-400" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" /></svg>1. Analysis</h3>
                        <p class="text-slate-300">Conducted granular analysis of inventory data for a <strong class="text-amber-400">$2M product line</strong> across multiple E-Commerce platforms.</p>
                    </div>
                    <div class="flow-arrow hidden md:block">&#10230;</div>
                    <div class="flow-arrow md:hidden">&#11167;</div>
                    <div class="flow-step pl-4">
                        <h3 class="text-xl font-bold text-white flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-amber-400" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" /></svg>2. Action</h3>
                        <p class="text-slate-300">Pinpointed key inefficiencies, leading to a strategic decision to authorize a <strong class="text-amber-400">$300,000 inventory return</strong>.</p>
                    </div>
                    <div class="flow-arrow hidden md:block">&#10230;</div>
                    <div class="flow-arrow md:hidden">&#11167;</div>
                    <div class="flow-step pl-4">
                        <h3 class="text-xl font-bold text-white flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-amber-400" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6" /></svg>3. Outcome</h3>
                        <p class="text-slate-300">Streamlined operations, boosted sales performance, and significantly <strong class="text-amber-400">improved cash flow</strong> for the business.</p>
                    </div>
                </div>
            </div>

            <div class="stat-card lg:col-span-3 fade-in-up">
                <h2 class="text-2xl font-bold text-white mb-4 text-center">Technical Toolkit</h2>
                <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
                    <div class="bg-custom-grey p-6 rounded-lg">
                        <h3 class="text-xl font-bold text-white mb-3 text-center flex items-center justify-center gap-2">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z" /></svg>
                            Visualization
                        </h3>
                        <ul class="space-y-2 text-slate-300 text-center">
                            <li><a href="https://www.tableau.com/" target="_blank" rel="noopener noreferrer" class="toolkit-link">Tableau</a></li>
                            <li><a href="https://powerbi.microsoft.com/" target="_blank" rel="noopener noreferrer" class="toolkit-link">Power BI</a></li>
                            <li><a href="https://looker.google.com/" target="_blank" rel="noopener noreferrer" class="toolkit-link">Looker</a></li>
                        </ul>
                    </div>
                    <div class="bg-custom-grey p-6 rounded-lg">
                        <h3 class="text-xl font-bold text-white mb-3 text-center flex items-center justify-center gap-2">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4" /></svg>
                            Languages
                        </h3>
                        <ul class="space-y-2 text-slate-300 text-center">
                            <li><a href="https://www.python.org/" target="_blank" rel="noopener noreferrer" class="toolkit-link">Python</a></li>
                            <li><a href="https://www.r-project.org/" target="_blank" rel="noopener noreferrer" class="toolkit-link">R</a></li>
                            <li><a href="https://en.wikipedia.org/wiki/SQL" target="_blank" rel="noopener noreferrer" class="toolkit-link">SQL</a></li>
                        </ul>
                    </div>
                    <div class="bg-custom-grey p-6 rounded-lg">
                        <h3 class="text-xl font-bold text-white mb-3 text-center flex items-center justify-center gap-2">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 7v10c0 2.21 3.582 4 8 4s8-1.79 8-4V7M4 7c0-2.21 3.582-4 8-4s8 1.79 8 4M4 7v10" /></svg>
                            Databases
                        </h3>
                        <ul class="space-y-2 text-slate-300 text-center">
                            <li><a href="https://www.postgresql.org/" target="_blank" rel="noopener noreferrer" class="toolkit-link">PostgreSQL</a></li>
                            <li><a href="https://www.mysql.com/" target="_blank" rel="noopener noreferrer" class="toolkit-link">MySQL</a></li>
                            <li><a href="https://cloud.google.com/bigquery" target="_blank" rel="noopener noreferrer" class="toolkit-link">BigQuery</a></li>
                        </ul>
                    </div>
                </div>
            </div>
            
            <div class="stat-card md:col-span-2 lg:col-span-3 fade-in-up text-center">
                <h2 class="text-2xl font-bold text-white mb-4">Let's Connect</h2>
                <p class="text-slate-300 mb-6 max-w-2xl mx-auto">I'm excited to apply my skills to new challenges. If you're looking for a data-driven professional who consistently exceeds expectations, I'd love to hear from you.</p>
                 <div class="flex justify-center items-center gap-4 mt-4">
                    <a href="mailto:zacharybhenley@gmail.com" class="text-slate-400 hover:text-amber-400 transition-colors" title="Email">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" /></svg>
                    </a>
                    <a href="https://www.linkedin.com/in/zachary-henley" target="_blank" rel="noopener noreferrer" class="text-slate-400 hover:text-amber-400 transition-colors" title="LinkedIn">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" viewBox="0 0 24 24" fill="currentColor"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
                    </a>
                    <a href="https://www.kaggle.com/zacharyhenley" target="_blank" rel="noopener noreferrer" class="text-slate-400 hover:text-amber-400 transition-colors" title="Kaggle">
                         <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" viewBox="0 0 24 24" fill="currentColor"><path d="M12.2,16.2l-3.8-3.8l3.8-3.8l1.2,1.2l-2.6,2.6l2.6,2.6L12.2,16.2z M18,12l-6,6l-1.2-1.2l4.8-4.8l-4.8-4.8L12,6L18,12z"/></svg>
                    </a>
                </div>
            </div>

        </main>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('is-visible');
                    }
                });
            }, { threshold: 0.1 });

            const fadeUpElements = document.querySelectorAll('.fade-in-up');
            fadeUpElements.forEach(el => observer.observe(el));
            
            const subtitle = "From Business Strategy to Data-Driven Success";
            const subtitleElement = document.getElementById('animated-subtitle');
            let i = 0;
            function typeWriter() {
                if (i < subtitle.length) {
                    subtitleElement.innerHTML = subtitle.substring(0, i + 1) + '<span id="subtitle-cursor">|</span>';
                    i++;
                    setTimeout(typeWriter, 50);
                } else {
                     subtitleElement.innerHTML = subtitle;
                }
            }
            typeWriter();

            const revenueBarCtx = document.getElementById('revenueBarChart').getContext('2d');
            new Chart(revenueBarCtx, {
                type: 'bar',
                data: {
                    labels: ['Q3 2019', 'Q4 2019', 'Q1 2020'],
                    datasets: [{
                        label: 'Quarterly Revenue ($)',
                        data: [170000, 280000, 270000],
                        backgroundColor: 'rgba(255, 166, 0, 0.6)',
                        borderColor: 'rgba(255, 166, 0, 1)',
                        borderWidth: 1,
                        borderRadius: 4
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    scales: {
                        y: {
                            beginAtZero: true,
                            ticks: {
                                color: '#f1f5f9',
                                callback: (value) => '$' + value / 1000 + 'k'
                            },
                            grid: { color: 'rgba(255, 255, 255, 0.1)' }
                        },
                        x: {
                            ticks: { color: '#f1f5f9', font: { size: 14, weight: '600' } },
                            grid: { display: false }
                        }
                    },
                    plugins: {
                        legend: { display: false },
                        title: { display: true, text: 'Quarterly Revenue Generation ($720k Total)', color: '#ffffff', font: { size: 18, weight: 'bold' }, padding: { top: 10, bottom: 20 } },
                        tooltip: { 
                            callbacks: { 
                                label: (context) => new Intl.NumberFormat('en-US', { style: 'currency', currency: 'USD' }).format(context.parsed.y)
                             } 
                        }
                    }
                }
            });

            const performanceBarCtx = document.getElementById('performanceBarChart').getContext('2d');
            new Chart(performanceBarCtx, {
                type: 'bar',
                data: {
                    labels: ['Green Solar Tech', 'Charter Comms'],
                    datasets: [{
                        label: 'Quota Exceeded By (%)',
                        data: [150, 120],
                        backgroundColor: ['rgba(239, 86, 117, 0.7)', 'rgba(188, 80, 144, 0.7)'],
                        borderColor: ['rgba(239, 86, 117, 1)', 'rgba(188, 80, 144, 1)'],
                        borderWidth: 1,
                        borderRadius: 6,
                        barThickness: 50
                    }]
                },
                options: {
                    indexAxis: 'y',
                    responsive: true,
                    maintainAspectRatio: false,
                    scales: {
                        x: { beginAtZero: true, grid: { color: 'rgba(255, 255, 255, 0.1)' }, ticks: { color: '#f1f5f9', font: { size: 14 } } },
                        y: { grid: { display: false }, ticks: { color: '#f1f5f9', font: { size: 14, weight: '600' } } }
                    },
                    plugins: {
                        legend: { display: false },
                        title: { display: true, text: 'Monthly Quota Performance', color: '#ffffff', font: { size: 18, weight: 'bold' }, padding: { top: 10, bottom: 20 } },
                    }
                }
            });
        });
    </script>

</body>
</html>
