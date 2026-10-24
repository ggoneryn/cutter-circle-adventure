<!DOCTYPE html>  
<html lang="id">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>CUTTER CIRCLE ADVENTURE - Pizza Math Adventure</title>  
    <!-- Tailwind CSS CDN -->  
    <script src="https://cdn.tailwindcss.com"></script>  
    <!-- Google Fonts -->  
    <link rel="preconnect" href="https://fonts.googleapis.com">  
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>  
    <link href="https://fonts.googleapis.com/css2?family=Fredoka+One&family=Quicksand:wght@500;600;700&display=swap" rel="stylesheet">  
    <!-- FontAwesome Icons -->  
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">  
  
    <script>  
        tailwind.config = {  
            theme: {  
                extend: {  
                    colors: {  
                        'cream-bg': '#FFF9EF',  
                        'pizza-red': '#FF5A5F',  
                        'pizza-yellow': '#FFC107',  
                        'cheese-gold': '#FFA000',  
                        'basil-green': '#4CAF50',  
                        'crust-brown': '#D72638',  
                        'pastel-blue': '#E1F5FE',  
                        'soft-purple': '#9C27B0',  
                        'dark-slate': '#2C3E50',  
                    },  
                    fontFamily: {  
                        'display': ['"Fredoka One"', 'cursive', 'sans-serif'],  
                        'body': ['"Quicksand"', 'sans-serif'],  
                    }  
                }  
            }  
        }  
    </script>  
  
    <style>  
        body {  
            font-family: 'Quicksand', sans-serif;  
            background-color: #FFF8EA;  
            background-image:   
                radial-gradient(#FFD54F 8%, transparent 8%),  
                radial-gradient(#81C784 8%, transparent 8%);  
            background-position: 0 0, 25px 25px;  
            background-size: 50px 50px;  
            user-select: none;  
            overflow-x: hidden;  
        }  
  
        .font-display {  
            font-family: 'Fredoka One', cursive;  
        }  
  
        /* Hand-drawn Sticker Effect */  
        .sticker-card {  
            background: #FFFFFF;  
            border: 4px solid #2C3E50;  
            box-shadow: 6px 6px 0px #2C3E50;  
            border-radius: 24px;  
            transition: all 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275);  
        }  
  
        .sticker-card:hover {  
            transform: translateY(-4px) rotate(-0.5deg);  
            box-shadow: 8px 10px 0px #2C3E50;  
        }  
  
        .btn-cartoon {  
            border: 3.5px solid #2C3E50;  
            box-shadow: 0px 6px 0px #2C3E50;  
            border-radius: 999px;  
            font-family: 'Fredoka One', cursive;  
            transition: all 0.15s ease;  
            position: relative;  
            top: 0;  
        }  
  
        .btn-cartoon:active {  
            top: 5px;  
            box-shadow: 0px 1px 0px #2C3E50;  
        }  
  
        .btn-red { background: #FF5A5F; color: white; }  
        .btn-yellow { background: #FFC107; color: #2C3E50; }  
        .btn-green { background: #4CAF50; color: white; }  
        .btn-blue { background: #29B6F6; color: white; }  
        .btn-purple { background: #AB47BC; color: white; }  
  
        /* Floating Animation */  
        @keyframes float {  
            0%, 100% { transform: translateY(0px) rotate(0deg); }  
            50% { transform: translateY(-10px) rotate(2deg); }  
        }  
        .animate-float {  
            animation: float 4s ease-in-out infinite;  
        }  
  
        @keyframes pulse-slow {  
            0%, 100% { transform: scale(1); }  
            50% { transform: scale(1.04); }  
        }  
        .animate-pulse-slow {  
            animation: pulse-slow 2.5s ease-in-out infinite;  
        }  
  
        /* Custom scrollbar */  
        ::-webkit-scrollbar {  
            width: 10px;  
        }  
        ::-webkit-scrollbar-track {  
            background: #FFE082;  
            border-radius: 10px;  
        }  
        ::-webkit-scrollbar-thumb {  
            background: #FF7043;  
            border-radius: 10px;  
            border: 2px solid #2C3E50;  
        }  
  
        .math-tex {  
            font-family: 'Times New Roman', Times, serif;  
            font-style: italic;  
            font-weight: 600;  
        }  
  
        /* Checkered Kitchen Table pattern */  
        .checkered-table {  
            background-color: #ffffff;  
            background-image: linear-gradient(45deg, #FFE0B2 25%, transparent 25%), linear-gradient(-45deg, #FFE0B2 25%, transparent 25%), linear-gradient(45deg, transparent 75%, #FFE0B2 75%), linear-gradient(-45deg, transparent 75%, #FFE0B2 75%);  
            background-size: 30px 30px;  
            background-position: 0 0, 0 15px, 15px -15px, -15px 0px;  
        }  
    </style>  
</head>  
<body class="min-h-screen text-slate-800 flex flex-col justify-between p-2 md:p-4">  
  
    <!-- Top Header Bar -->  
    <header class="max-w-5xl mx-auto w-full flex justify-between items-center bg-white border-4 border-slate-800 rounded-3xl p-3 px-6 shadow-[4px_4px_0px_#2C3E50] z-20 mb-4">  
        <div class="flex items-center gap-3 cursor-pointer" onclick="showScreen('main-menu')">  
            <div class="w-12 h-12 bg-red-400 border-2 border-slate-800 rounded-full flex items-center justify-center text-2xl shadow-inner">  
                🍕  
            </div>  
            <div>  
                <h1 class="font-display text-xl md:text-2xl text-red-500 tracking-wide leading-none">CUTTER CIRCLE</h1>  
                <p class="text-xs font-bold text-amber-600">PIZZA MATH ADVENTURE</p>  
            </div>  
        </div>  
  
        <div class="flex items-center gap-4">  
            <div class="bg-amber-100 border-2 border-slate-800 px-3 py-1 rounded-full flex items-center gap-2">  
                <span class="text-lg">⭐</span>  
                <span id="global-score-display" class="font-display text-amber-800 text-lg">0 Pts</span>  
            </div>  
            <button id="audio-toggle-btn" onclick="toggleAudio()" class="w-10 h-10 bg-yellow-300 border-2 border-slate-800 rounded-full flex items-center justify-center hover:bg-yellow-400 transition">  
                <i class="fa-solid fa-volume-high text-slate-800"></i>  
            </button>  
        </div>  
    </header>  
  
    <!-- MAIN CONTAINER -->  
    <main class="max-w-5xl mx-auto w-full flex-grow relative flex flex-col justify-center items-center">  
  
        <!-- SCREEN 1: MAIN MENU -->  
        <section id="screen-main-menu" class="w-full flex flex-col items-center py-4">  
            <div class="grid grid-cols-1 md:grid-cols-12 gap-6 w-full items-center">  
                <!-- Left Mascot & Illustration -->  
                <div class="md:col-span-5 flex flex-col items-center text-center">  
                    <div class="relative w-64 h-64 md:w-80 md:h-80 animate-float">  
                        <!-- SVG Mascot Chef Cheesy -->  
                        <svg viewBox="0 0 300 300" class="w-full h-full drop-shadow-xl">  
                            <!-- Pizza Slice Background -->  
                            <path d="M 150 40 L 260 250 A 150 150 0 0 1 40 250 Z" fill="#FFC107" stroke="#2C3E50" stroke-width="8"/>  
                            <path d="M 35 250 A 155 155 0 0 0 265 250" fill="none" stroke="#D72638" stroke-width="18" stroke-linecap="round"/>  
                            <!-- Toppings -->  
                            <circle cx="120" cy="150" r="18" fill="#FF5A5F" stroke="#2C3E50" stroke-width="4"/>  
                            <circle cx="180" cy="180" r="22" fill="#FF5A5F" stroke="#2C3E50" stroke-width="4"/>  
                            <circle cx="150" cy="210" r="15" fill="#FF5A5F" stroke="#2C3E50" stroke-width="4"/>  
                            <path d="M 130 110 Q 140 100 150 110" stroke="#4CAF50" stroke-width="6" fill="none" stroke-linecap="round"/>  
                            <path d="M 170 130 Q 180 120 190 130" stroke="#4CAF50" stroke-width="6" fill="none" stroke-linecap="round"/>  
                            <!-- Chef Hat -->  
                            <path d="M 100 70 C 90 30, 140 20, 150 40 C 160 15, 210 20, 200 70 Z" fill="#FFFFFF" stroke="#2C3E50" stroke-width="6"/>  
                            <rect x="110" y="65" width="80" height="20" rx="5" fill="#FFFFFF" stroke="#2C3E50" stroke-width="5"/>  
                            <!-- Mascot Eyes & Mouth -->  
                            <circle cx="130" cy="115" r="7" fill="#2C3E50"/>  
                            <circle cx="170" cy="115" r="7" fill="#2C3E50"/>  
                            <circle cx="132" cy="113" r="2" fill="#FFFFFF"/>  
                            <circle cx="172" cy="113" r="2" fill="#FFFFFF"/>  
                            <path d="M 135 135 Q 150 150 165 135" stroke="#2C3E50" stroke-width="5" fill="none" stroke-linecap="round"/>  
                            <!-- Cheeks -->  
                            <ellipse cx="118" cy="125" rx="8" ry="5" fill="#FF8A80" opacity="0.7"/>  
                            <ellipse cx="182" cy="125" rx="8" ry="5" fill="#FF8A80" opacity="0.7"/>  
                            <!-- Pizza Cutter Hand -->  
                            <g transform="translate(190, 160) rotate(25)">  
                                <rect x="0" y="0" width="14" height="60" rx="5" fill="#D72638" stroke="#2C3E50" stroke-width="4"/>  
                                <circle cx="7" cy="65" r="22" fill="#CFD8DC" stroke="#2C3E50" stroke-width="5"/>  
                                <circle cx="7" cy="65" r="6" fill="#2C3E50"/>  
                            </g>  
                        </svg>  
                    </div>  
                    <div class="bg-yellow-200 border-2 border-slate-800 rounded-2xl px-4 py-2 mt-2 shadow-[2px_2px_0px_#2C3E50]">  
                        <p class="font-bold text-slate-800 text-sm">Halo! Aku Chef Cheesy 👨‍🍳 Siap belajar matematika lingkaran?</p>  
                    </div>  
                </div>  
  
                <!-- Right Menu Buttons & Player Name -->  
                <div class="md:col-span-7 flex flex-col gap-4">  
                    <div class="sticker-card p-6 bg-amber-50 text-center md:text-left">  
                        <span class="bg-red-100 text-red-600 text-xs font-bold px-3 py-1 rounded-full border border-red-300">SMA Kelas XI - Semester 1</span>  
                        <h2 class="font-display text-3xl md:text-4xl text-slate-800 mt-2">PETUALANGAN MATEMATIKA LINGKARAN</h2>  
                        <p class="text-slate-600 font-medium text-sm mt-1">Taklukkan tantangan formula lingkaran & potong pizzamu dengan presisi!</p>  
  
                        <!-- Player Name Input -->  
                        <div class="mt-4 bg-white p-3 rounded-2xl border-2 border-slate-800 flex items-center gap-3">  
                            <span class="text-2xl">🍕</span>  
                            <input type="text" id="player-name-input" placeholder="Masukkan Nama Koki Cilik..." value="Koki Math" class="w-full bg-transparent font-bold text-slate-800 focus:outline-none text-lg">  
                        </div>  
                    </div>  
  
                    <!-- Navigation Action Buttons -->  
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">  
                        <button onclick="startGame()" class="btn-cartoon btn-red py-4 text-xl flex items-center justify-center gap-2 col-span-1 sm:col-span-2">  
                            <i class="fa-solid fa-play"></i> MULAI BERMAIN  
                        </button>  
                        <button onclick="showScreen('material')" class="btn-cartoon btn-yellow py-3 text-lg flex items-center justify-center gap-2">  
                            <i class="fa-solid fa-book-open"></i> PELAJARI MATERI  
                        </button>  
                        <button onclick="showScreen('instructions')" class="btn-cartoon btn-blue py-3 text-lg flex items-center justify-center gap-2">  
                            <i class="fa-solid fa-circle-info"></i> PETUNJUK  
                        </button>  
                        <button onclick="showScreen('achievements')" class="btn-cartoon btn-purple py-3 text-lg flex items-center justify-center gap-2 col-span-1 sm:col-span-2">  
                            <i class="fa-solid fa-trophy"></i> PENCAPAIAN & SERTIFIKAT  
                        </button>  
                    </div>  
                </div>  
            </div>  
        </section>  
  
        <!-- SCREEN 2: LEVEL MAP -->  
        <section id="screen-level-map" class="w-full hidden py-4">  
            <div class="text-center mb-6">  
                <h2 class="font-display text-3xl text-slate-800">PETA DAPUR PIZZA</h2>  
                <p class="text-slate-600 font-bold">Pilih Oven Level untuk Memulai Tantangan Memasak!</p>  
            </div>  
  
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">  
                <!-- Level 1 Card -->  
                <div class="sticker-card p-5 bg-emerald-50 flex flex-col justify-between relative overflow-hidden">  
                    <div class="absolute -right-4 -top-4 w-20 h-20 bg-emerald-200 rounded-full opacity-50"></div>  
                    <div>  
                        <div class="flex justify-between items-center mb-2">  
                            <span class="bg-emerald-500 text-white font-display px-3 py-1 rounded-full text-xs">LEVEL 1</span>  
                            <span class="text-emerald-700 font-bold text-xs">10 Pts / Soal</span>  
                        </div>  
                        <h3 class="font-display text-2xl text-emerald-900">PIZZA BEGINNER</h3>  
                        <p class="text-xs text-slate-600 mt-1 font-medium">Unsur lingkaran, keliling, luas, & persamaan standar O(0,0).</p>  
                          
                        <!-- Illustration SVG -->  
                        <div class="my-4 h-32 flex items-center justify-center">  
                            <svg viewBox="0 0 100 100" class="w-28 h-28">  
                                <circle cx="50" cy="50" r="40" fill="#FFE082" stroke="#2C3E50" stroke-width="4"/>  
                                <circle cx="50" cy="50" r="32" fill="#FF7043" stroke="#2C3E50" stroke-width="3"/>  
                                <line x1="50" y1="50" x2="82" y2="50" stroke="#FFFFFF" stroke-width="4" stroke-dasharray="3,3"/>  
                                <circle cx="50" cy="50" r="4" fill="#2C3E50"/>  
                                <text x="62" y="45" font-family="Fredoka One" font-size="10" fill="#FFFFFF">r</text>  
                            </svg>  
                        </div>  
                    </div>  
  
                    <button onclick="startLevel(1)" class="btn-cartoon btn-green w-full py-3 text-lg mt-2">  
                        MASUK DAPUR <i class="fa-solid fa-arrow-right"></i>  
                    </button>  
                </div>  
  
                <!-- Level 2 Card -->  
                <div id="level-2-card" class="sticker-card p-5 bg-amber-50 flex flex-col justify-between relative overflow-hidden opacity-90">  
                    <div>  
                        <div class="flex justify-between items-center mb-2">  
                            <span class="bg-amber-500 text-white font-display px-3 py-1 rounded-full text-xs">LEVEL 2</span>  
                            <span class="text-amber-800 font-bold text-xs">20 Pts / Soal</span>  
                        </div>  
                        <h3 class="font-display text-2xl text-amber-900">PIZZA CHEF</h3>  
                        <p class="text-xs text-slate-600 mt-1 font-medium">Persamaan pusat (a,b), kedudukan titik/garis, & garis singgung.</p>  
  
                        <!-- Illustration SVG -->  
                        <div class="my-4 h-32 flex items-center justify-center">  
                            <svg viewBox="0 0 100 100" class="w-28 h-28">  
                                <rect x="10" y="10" width="80" height="80" fill="none" stroke="#B0BEC5" stroke-width="1" stroke-dasharray="2,2"/>  
                                <circle cx="60" cy="40" r="30" fill="#FFD54F" stroke="#2C3E50" stroke-width="4"/>  
                                <line x1="10" y1="70" x2="90" y2="10" stroke="#FF5A5F" stroke-width="4"/>  
                                <circle cx="60" cy="40" r="3" fill="#2C3E50"/>  
                                <text x="40" y="38" font-family="Fredoka One" font-size="8" fill="#2C3E50">P(a,b)</text>  
                            </svg>  
                        </div>  
                    </div>  
  
                    <button id="btn-level-2" onclick="startLevel(2)" class="btn-cartoon btn-yellow w-full py-3 text-lg mt-2">  
                        MASUK DAPUR <i class="fa-solid fa-arrow-right"></i>  
                    </button>  
                </div>  
  
                <!-- Level 3 Card -->  
                <div id="level-3-card" class="sticker-card p-5 bg-purple-50 flex flex-col justify-between relative overflow-hidden opacity-90">  
                    <div>  
                        <div class="flex justify-between items-center mb-2">  
                            <span class="bg-purple-500 text-white font-display px-3 py-1 rounded-full text-xs">LEVEL 3</span>  
                            <span class="text-purple-800 font-bold text-xs">30 Pts / Soal</span>  
                        </div>  
                        <h3 class="font-display text-2xl text-purple-900">PIZZA MASTER</h3>  
                        <p class="text-xs text-slate-600 mt-1 font-medium">Garis singgung gradien m, kedudukan 2 lingkaran & soal HOTS.</p>  
  
                        <!-- Illustration SVG -->  
                        <div class="my-4 h-32 flex items-center justify-center">  
                            <svg viewBox="0 0 100 100" class="w-28 h-28">  
                                <circle cx="35" cy="55" r="25" fill="#FF8A65" stroke="#2C3E50" stroke-width="3"/>  
                                <circle cx="70" cy="45" r="18" fill="#81C784" stroke="#2C3E50" stroke-width="3"/>  
                                <line x1="10" y1="30" x2="90" y2="20" stroke="#29B6F6" stroke-width="4"/>  
                            </svg>  
                        </div>  
                    </div>  
  
                    <button id="btn-level-3" onclick="startLevel(3)" class="btn-cartoon btn-purple w-full py-3 text-lg mt-2">  
                        MASUK DAPUR <i class="fa-solid fa-arrow-right"></i>  
                    </button>  
                </div>  
            </div>  
  
            <div class="mt-6 text-center">  
                <button onclick="showScreen('main-menu')" class="btn-cartoon bg-slate-200 text-slate-800 px-6 py-2 text-md">  
                    <i class="fa-solid fa-house"></i> Kembali ke Menu Utama  
                </button>  
            </div>  
        </section>  
  
        <!-- SCREEN 3: GAMEPLAY (MINI-GAME) -->  
        <section id="screen-gameplay" class="w-full hidden py-2">  
            <!-- Header Status -->  
            <div class="flex flex-wrap justify-between items-center bg-amber-100 border-3 border-slate-800 rounded-2xl p-3 mb-3 shadow-[3px_3px_0px_#2C3E50]">  
                <div class="flex items-center gap-2">  
                    <span id="game-level-badge" class="bg-red-500 text-white font-display px-3 py-1 rounded-full text-xs">LEVEL 1</span>  
                    <span id="question-tracker" class="font-bold text-slate-800 text-sm">Soal 1 dari 5</span>  
                </div>  
  
                <!-- Progress Bar -->  
                <div class="w-32 md:w-48 bg-white border-2 border-slate-800 h-5 rounded-full overflow-hidden p-0.5">  
                    <div id="level-progress-bar" class="bg-amber-400 h-full rounded-full transition-all duration-300" style="width: 20%;"></div>  
                </div>  
  
                <div class="flex items-center gap-2">  
                    <span class="text-sm font-bold text-slate-700">Skor Level:</span>  
                    <span id="level-score-display" class="font-display text-red-600 text-lg">0</span>  
                </div>  
            </div>  
  
            <!-- Question & Diagram Panel -->  
            <div class="grid grid-cols-1 md:grid-cols-12 gap-4 items-start">  
                  
                <!-- Left Column: Dynamic Visualizer / Pizza Math Canvas -->  
                <div class="md:col-span-5 sticker-card p-4 bg-white flex flex-col items-center justify-center min-h-[260px]">  
                    <span class="text-xs font-bold text-slate-500 mb-1 flex items-center gap-1">  
                        <i class="fa-solid fa-compass-drafting"></i> Visualisasi Geometri Pizza  
                    </span>  
                    <div class="w-full h-56 bg-amber-50 rounded-xl border-2 border-slate-700 relative flex items-center justify-center overflow-hidden checkered-table">  
                        <canvas id="math-canvas" width="280" height="220" class="max-w-full h-auto"></canvas>  
                    </div>  
                </div>  
  
                <!-- Right Column: Question & Options -->  
                <div class="md:col-span-7 flex flex-col gap-3">  
                    <div class="sticker-card p-4 bg-amber-50">  
                        <div class="flex items-start gap-3">  
                            <div class="w-10 h-10 bg-red-400 text-white rounded-full flex-shrink-0 flex items-center justify-center font-display text-lg border-2 border-slate-800">  
                                Q  
                            </div>  
                            <div>  
                                <p id="question-text" class="font-bold text-slate-800 text-base md:text-lg leading-snug">  
                                    Loading pertanyaan...  
                                </p>  
                            </div>  
                        </div>  
                    </div>  
  
                    <!-- Multiple Choice Topping Buttons -->  
                    <div id="options-container" class="grid grid-cols-1 gap-2.5">  
                        <!-- Options injected dynamically by JS -->  
                    </div>  
  
                    <!-- Action Buttons -->  
                    <div class="flex gap-3 mt-1">  
                        <button id="btn-submit-answer" onclick="submitAnswer()" disabled class="btn-cartoon btn-green w-full py-3 text-lg opacity-50 cursor-not-allowed">  
                            KONFIRMASI JAWABAN <i class="fa-solid fa-check-circle"></i>  
                        </button>  
                    </div>  
                </div>  
            </div>  
        </section>  
  
        <!-- SCREEN 4: MATERIAL / BELAJAR -->  
        <section id="screen-material" class="w-full hidden py-4 max-w-4xl">  
            <div class="sticker-card p-6 bg-white">  
                <div class="flex justify-between items-center mb-4 border-b-4 border-amber-200 pb-3">  
                    <div class="flex items-center gap-3">  
                        <span class="text-3xl">📚</span>  
                        <div>  
                            <h2 class="font-display text-2xl text-slate-800">MODUL RUMUS PIZZA LINGKARAN</h2>  
                            <p class="text-xs font-bold text-amber-600">Rangkuman Materi Matematika Kelas XI SMA</p>  
                        </div>  
                    </div>  
                    <button onclick="showScreen('main-menu')" class="btn-cartoon bg-slate-200 px-4 py-1 text-sm">  
                        ✕ Tutup  
                    </button>  
                </div>  
  
                <div class="space-y-6 max-h-[60vh] overflow-y-auto pr-2 text-sm text-slate-700">  
                      
                    <!-- Bab 1 -->  
                    <div class="bg-amber-50 p-4 rounded-2xl border-2 border-slate-800">  
                        <h3 class="font-display text-lg text-red-600 mb-2">1. Unsur-Unsur & Luas Lingkaran Pizza</h3>  
                        <ul class="list-disc pl-5 space-y-1">  
                            <li><b>Jari-jari (r):</b> Jarak titik pusat ke tepi lingkaran pizza.</li>  
                            <li><b>Diameter (d):</b> Garis lurus memotong pusat (<span class="math-tex">d = 2r</span>).</li>  
                            <li><b>Keliling Lingkaran:</b> <span class="math-tex">K = 2 \pi r = \pi d</span></li>  
                            <li><b>Luas Lingkaran Pizza:</b> <span class="math-tex">L = \pi r^2</span></li>  
                            <li><b>Luas Juring (Potongan Pizza):</b> <span class="math-tex">L_{juring} = \frac{\theta}{360^\circ} \times \pi r^2</span></li>  
                        </ul>  
                    </div>  
  
                    <!-- Bab 2 -->  
                    <div class="bg-emerald-50 p-4 rounded-2xl border-2 border-slate-800">  
                        <h3 class="font-display text-lg text-emerald-700 mb-2">2. Persamaan Lingkaran</h3>  
                        <div class="space-y-2">  
                            <p><b>A. Berpusat di O(0,0):</b></p>  
                            <p class="bg-white p-2 rounded-lg border border-slate-300 font-mono text-center">x² + y² = r²</p>  
                              
                            <p><b>B. Berpusat di P(a,b):</b></p>  
                            <p class="bg-white p-2 rounded-lg border border-slate-300 font-mono text-center">(x - a)² + (y - b)² = r²</p>  
                              
                            <p><b>C. Bentuk Umum:</b></p>  
                            <p class="bg-white p-2 rounded-lg border border-slate-300 font-mono text-center">x² + y² + Ax + By + C = 0</p>  
                            <p class="text-xs">Dengan Pusat <span class="math-tex">P(-\frac{1}{2}A, -\frac{1}{2}B)</span> dan Jari-jari <span class="math-tex">r = \sqrt{(\frac{1}{2}A)^2 + (\frac{1}{2}B)^2 - C}</span></p>  
                        </div>  
                    </div>  
  
                    <!-- Bab 3 -->  
                    <div class="bg-purple-50 p-4 rounded-2xl border-2 border-slate-800">  
                        <h3 class="font-display text-lg text-purple-700 mb-2">3. Kedudukan Titik & Garis Singgung</h3>  
                        <p><b>Persamaan Garis Singgung di Titik (x₁, y₁) pada Lingkaran:</b></p>  
                        <ul class="list-disc pl-5 space-y-1 mt-1">  
                            <li>Untuk <span class="math-tex">x^2 + y^2 = r^2</span> → <span class="font-mono">x₁x + y₁y = r²</span></li>  
                            <li>Untuk <span class="math-tex">(x-a)^2 + (y-b)^2 = r^2</span> → <span class="font-mono">(x₁-a)(x-a) + (y₁-b)(y-b) = r²</span></li>  
                        </ul>  
                        <p class="mt-2"><b>Garis Singgung dengan Gradien m:</b></p>  
                        <p class="bg-white p-2 rounded-lg border border-slate-300 font-mono text-center">y - b = m(x - a) ± r√(1 + m²)</p>  
                    </div>  
  
                    <!-- Bab 4 -->  
                    <div class="bg-blue-50 p-4 rounded-2xl border-2 border-slate-800">  
                        <h3 class="font-display text-lg text-blue-700 mb-2">4. Kedudukan Dua Lingkaran</h3>  
                        <p>Jika dua lingkaran berjari-jari R dan r dengan jarak antar pusat d:</p>  
                        <ul class="list-disc pl-5 space-y-1">  
                            <li><b>Saling Lepas di Luar:</b> <span class="math-tex">d > R + r</span></li>  
                            <li><b>Bersinggungan di Luar:</b> <span class="math-tex">d = R + r</span></li>  
                            <li><b>Garis Singgung Persekutuan Luar (GSPL):</b> <span class="math-tex">l = \sqrt{d^2 - (R - r)^2}</span></li>  
                        </ul>  
                    </div>  
  
                </div>  
  
                <div class="mt-4 text-center">  
                    <button onclick="startGame()" class="btn-cartoon btn-red px-8 py-3 text-lg">  
                        SIAP MAIN & UJI PEMAHAMAN! 🍕  
                    </button>  
                </div>  
            </div>  
        </section>  
  
        <!-- SCREEN 5: PETUNJUK PERMAINAN -->  
        <section id="screen-instructions" class="w-full hidden py-4 max-w-3xl">  
            <div class="sticker-card p-6 bg-amber-50">  
                <div class="flex justify-between items-center mb-4 border-b-4 border-amber-200 pb-2">  
                    <h2 class="font-display text-2xl text-slate-800">📖 PETUNJUK DAPUR MATEMATIKA</h2>  
                    <button onclick="showScreen('main-menu')" class="btn-cartoon bg-slate-200 px-3 py-1 text-sm">✕</button>  
                </div>  
  
                <div class="space-y-4 text-slate-700 text-sm">  
                    <div class="flex items-start gap-3 bg-white p-3 rounded-xl border border-slate-300">  
                        <span class="text-2xl">👨‍🍳</span>  
                        <div>  
                            <h4 class="font-bold text-slate-800">Tugas Koki</h4>  
                            <p>Selesaikan 15 resep soal matematika lingkaran yang terbagi dalam 3 level kesulitan.</p>  
                        </div>  
                    </div>  
  
                    <div class="flex items-start gap-3 bg-white p-3 rounded-xl border border-slate-300">  
                        <span class="text-2xl">🍕</span>  
                        <div>  
                            <h4 class="font-bold text-slate-800">Poin & Level</h4>  
                            <p>• Level 1 (Beginner): 10 Pts per jawaban benar (Maks 50 Pts)</p>  
                            <p>• Level 2 (Chef): 20 Pts per jawaban benar (Maks 100 Pts)</p>  
                            <p>• Level 3 (Master): 30 Pts per jawaban benar (Maks 150 Pts)</p>  
                            <p class="text-red-600 font-bold mt-1">Total Poin Maksimal: 300 Pts!</p>  
                        </div>  
                    </div>  
  
                    <div class="flex items-start gap-3 bg-white p-3 rounded-xl border border-slate-300">  
                        <span class="text-2xl">💡</span>  
                        <div>  
                            <h4 class="font-bold text-slate-800">Pembahasan Langsung</h4>  
                            <p>Setiap kali selesai menjawab, kamu bisa melihat diagram visual dan pembahasan rumus lengkap secara rinci.</p>  
                        </div>  
                    </div>  
                </div>  
  
                <div class="mt-6 text-center">  
                    <button onclick="showScreen('main-menu')" class="btn-cartoon btn-yellow px-6 py-2 text-md">  
                        Paham, Kembali ke Menu!  
                    </button>  
                </div>  
            </div>  
        </section>  
  
        <!-- SCREEN 6: ACHIEVEMENTS & CERTIFICATE -->  
        <section id="screen-achievements" class="w-full hidden py-4 max-w-3xl">  
            <div class="sticker-card p-6 bg-white text-center relative">  
                <span class="bg-purple-100 text-purple-700 font-bold px-4 py-1 rounded-full text-xs">SERTIFIKAT KOKI MATEMATIKA</span>  
                <h2 class="font-display text-3xl text-slate-800 mt-2">PENCAPAIAN DIPLOMA PIZZA</h2>  
                  
                <div class="my-6 p-6 border-4 border-dashed border-amber-400 bg-amber-50 rounded-2xl relative">  
                    <div class="absolute -top-5 left-1/2 -translate-x-1/2 bg-amber-400 text-slate-900 font-display px-4 py-1 rounded-full text-xs border border-slate-800">  
                        OFFICIAL CERTIFICATE  
                    </div>  
  
                    <p class="text-xs text-slate-500 uppercase tracking-widest mt-2">Diberikan Kepada:</p>  
                    <h3 id="cert-player-name" class="font-display text-3xl text-red-500 my-1">Koki Math</h3>  
                    <p class="text-xs text-slate-600">Telah menyelesaikan tantangan matematika lingkaran pada game</p>  
                    <p class="font-display text-amber-800 text-base">CUTTER CIRCLE ADVENTURE</p>  
  
                    <div class="my-4 flex justify-center items-center gap-6">  
                        <div>  
                            <p class="text-xs text-slate-500">Total Skor</p>  
                            <p id="cert-score" class="font-display text-3xl text-slate-800">0 / 300</p>  
                        </div>  
                        <div class="w-px h-10 bg-amber-300"></div>  
                        <div>  
                            <p class="text-xs text-slate-500">Gelar Koki</p>  
                            <p id="cert-title" class="font-display text-xl text-purple-600">Koki Magang 🍕</p>  
                        </div>  
                    </div>  
  
                    <!-- Badge Icons -->  
                    <div id="badges-container" class="flex justify-center gap-3 mt-4">  
                        <!-- Badges injected by JS -->  
                    </div>  
                </div>  
  
                <div class="flex flex-wrap justify-center gap-3">  
                    <button onclick="showScreen('main-menu')" class="btn-cartoon bg-slate-200 px-6 py-2 text-md">  
                        <i class="fa-solid fa-house"></i> Menu Utama  
                    </button>  
                    <button onclick="startGame()" class="btn-cartoon btn-red px-6 py-2 text-md">  
                        <i class="fa-solid fa-rotate-right"></i> Main Lagi  
                    </button>  
                </div>  
            </div>  
        </section>  
  
    </main>  
  
    <!-- MODAL PEMBAHASAN / EXPLANATION -->  
    <div id="explanation-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">  
        <div class="sticker-card bg-white max-w-lg w-full p-5 max-h-[90vh] overflow-y-auto animate-pulse-slow">  
            <div id="modal-header-badge" class="inline-block px-3 py-1 rounded-full text-xs font-display text-white bg-green-500 mb-2">  
                JAWABAN BENAR! 🎉  
            </div>  
              
            <h3 class="font-display text-2xl text-slate-800 mb-1">PEMBAHASAN RESEP LINGKARAN</h3>  
            <p id="modal-correct-ans-text" class="text-xs font-bold text-slate-600 mb-3"></p>  
  
            <div class="bg-amber-50 p-4 rounded-xl border-2 border-slate-700 text-sm leading-relaxed text-slate-800 font-medium space-y-2" id="modal-explanation-content">  
                <!-- Step by step math explanation injected here -->  
            </div>  
  
            <div class="mt-5 text-right">  
                <button onclick="nextQuestion()" class="btn-cartoon btn-blue px-6 py-2.5 text-base">  
                    LANJUTKAN <i class="fa-solid fa-arrow-right"></i>  
                </button>  
            </div>  
        </div>  
    </div>  
  
    <!-- Footer -->  
    <footer class="max-w-5xl mx-auto w-full text-center py-2 text-xs text-slate-500 font-bold">  
        CUTTER CIRCLE ADVENTURE &copy; 2026 — Game Edukasi Matematika SMA Kelas XI (Lingkaran)  
    </footer>  
  
    <!-- GAME LOGIC JAVASCRIPT -->  
    <script>  
        /* ===================================================  
           1. GAME STATE & QUESTION BANK  
           =================================================== */  
        let gameState = {  
            playerName: 'Koki Math',  
            currentLevel: 1,  
            currentQuestionIdx: 0,  
            score: 0,  
            levelScores: { 1: 0, 2: 0, 3: 0 },  
            selectedOption: null,  
            unlockedLevels: [1],  
            soundEnabled: true  
        };  
  
        // 15 Authentic High School Circle Math Questions  
        const questionsData = {  
            1: [  
                {  
                    q: "Unsur lingkaran berupa garis lurus yang menghubungkan dua titik pada busur tanpa melewati titik pusat dinamakan...",  
                    options: ["A. Jari-jari", "B. Tali Busur", "C. Apotema", "D. Juring"],  
                    answer: 1,  
                    explain: "<b>Tali Busur</b> adalah garis lurus yang menghubungkan dua titik pada keliling lingkaran. Jika melewati titik pusat, maka dinamakan Diameter.",  
                    diagramType: "tali_busur"  
                },  
                {  
                    q: "Persamaan lingkaran yang berpusat di O(0,0) dan memiliki jari-jari r = 7 adalah...",  
                    options: ["A. x² + y² = 14", "B. x² + y² = 49", "C. x² + y² = 7", "D. x² - y² = 49"],  
                    answer: 1,  
                    explain: "Persamaan standar lingkaran pusat O(0,0) adalah <b>x² + y² = r²</b>.<br>Sebab r = 7, maka r² = 7² = 49.<br>Sehingga persamaannya: <b>x² + y² = 49</b>.",  
                    diagramType: "circle_00"  
                },  
                {  
                    q: "Sebuah pizza berbentuk lingkaran dengan persamaan x² + y² = 36. Diameter pizza tersebut adalah...",  
                    options: ["A. 6 unit", "B. 12 unit", "C. 18 unit", "D. 36 unit"],  
                    answer: 1,  
                    explain: "Dari x² + y² = 36, didapatkan r² = 36 ⇒ <b>r = 6</b>.<br>Diameter (d) = 2 × r = 2 × 6 = <b>12 unit</b>.",  
                    diagramType: "circle_diameter"  
                },  
                {  
                    q: "Keliling loyang pizza berbentuk lingkaran dengan jari-jari 14 cm adalah... (π = 22/7)",  
                    options: ["A. 44 cm", "B. 88 cm", "C. 154 cm", "D. 616 cm"],  
                    answer: 1,  
                    explain: "Rumus Keliling Lingkaran: <b>K = 2 × π × r</b><br>K = 2 × (22/7) × 14 = 2 × 22 × 2 = <b>88 cm</b>.",  
                    diagramType: "circle_basic"  
                },  
                {  
                    q: "Luas potongan pizza juring dengan sudut pusat 60° dan jari-jari 21 cm adalah...",  
                    options: ["A. 110 cm²", "B. 231 cm²", "C. 462 cm²", "D. 1386 cm²"],  
                    answer: 1,  
                    explain: "<b>Luas Juring = (θ / 360°) × π × r²</b><br>Luas = (60/360) × (22/7) × 21²<br>= (1/6) × (22/7) × 441 = (1/6) × 1386 = <b>231 cm²</b>.",  
                    diagramType: "juring"  
                }  
            ],  
            2: [  
                {  
                    q: "Persamaan lingkaran yang berpusat di titik P(3, -4) dan berjari-jari 5 adalah...",  
                    options: [  
                        "A. (x - 3)² + (y + 4)² = 25",  
                        "B. (x + 3)² + (y - 4)² = 25",  
                        "C. (x - 3)² + (y - 4)² = 25",  
                        "D. (x + 3)² + (y + 4)² = 5"  
                    ],  
                    answer: 0,  
                    explain: "Persamaan lingkaran pusat P(a,b): <b>(x - a)² + (y - b)² = r²</b>.<br>Dengan a = 3, b = -4, dan r = 5 (r² = 25):<br><b>(x - 3)² + (y - (-4))² = 25 ⇒ (x - 3)² + (y + 4)² = 25</b>.",  
                    diagramType: "circle_ab"  
                },  
                {  
                    q: "Kedudukan titik A(5, 2) terhadap lingkaran L ≡ x² + y² = 25 adalah...",  
                    options: ["A. Berada di dalam lingkaran", "B. Berada pada lingkaran", "C. Berada di luar lingkaran", "D. Berada di pusat lingkaran"],  
                    answer: 2,  
                    explain: "Substitusi (5,2) ke x² + y²:<br>5² + 2² = 25 + 4 = <b>29</b>.<br>Karena 29 > 25 (r²), maka titik A <b>berada di luar lingkaran</b>.",  
                    diagramType: "point_position"  
                },  
                {  
                    q: "Persamaan garis singgung lingkaran x² + y² = 25 yang melalui titik T(3, 4) pada lingkaran adalah...",  
                    options: ["A. 3x + 4y = 25", "B. 4x + 3y = 25", "C. 3x - 4y = 25", "D. 4x - 3y = 25"],  
                    answer: 0,  
                    explain: "Rumus Garis Singgung di T(x₁, y₁): <b>x₁x + y₁y = r²</b>.<br>Dengan x₁ = 3, y₁ = 4, r² = 25:<br><b>3x + 4y = 25</b>.",  
                    diagramType: "tangent_point"  
                },  
                {  
                    q: "Pusat dan jari-jari dari persamaan lingkaran x² + y² - 6x + 8y - 11 = 0 berturut-turut adalah...",  
                    options: [  
                        "A. Pusat (-3, 4) dan r = 6",  
                        "B. Pusat (3, -4) dan r = 6",  
                        "C. Pusat (3, -4) dan r = 36",  
                        "D. Pusat (-6, 8) dan r = 11"  
                    ],  
                    answer: 1,  
                    explain: "Dari bentuk x² + y² + Ax + By + C = 0:<br>A = -6, B = 8, C = -11.<br>Pusat = (-A/2, -B/2) = (3, -4).<br>r = √((-3)² + 4² - (-11)) = √(9 + 16 + 11) = √36 = <b>6</b>.",  
                    diagramType: "circle_general"  
                },  
                {  
                    q: "Garis y = x + c menyinggung lingkaran x² + y² = 8. Nilai c yang memenuhi adalah...",  
                    options: ["A. ± 2", "B. ± 4", "C. ± 8", "D. ± 16"],  
                    answer: 1,  
                    explain: "Rumus garis singgung gradien m: <b>y = mx ± r√(1 + m²)</b>.<br>Garis y = x + c punya gradien m = 1, r = √8.<br>c = ± √8 × √(1 + 1²) = ± √8 × √2 = ± √16 = <b>± 4</b>.",  
                    diagramType: "tangent_m"  
                }  
            ],  
            3: [  
                {  
                    q: "Persamaan garis singgung lingkaran x² + y² = 20 dengan gradien m = 2 adalah...",  
                    options: [  
                        "A. y = 2x ± 10",  
                        "B. y = 2x ± 20",  
                        "C. y = 2x ± 5",  
                        "D. y = 2x ± 100"  
                    ],  
                    answer: 0,  
                    explain: "Rumus: <b>y = mx ± r√(1 + m²)</b>.<br>m = 2, r² = 20 ⇒ r = √20.<br>y = 2x ± √20 × √(1 + 2²) = 2x ± √20 × √5 = 2x ± √100 = <b>y = 2x ± 10</b>.",  
                    diagramType: "tangent_m"  
                },  
                {  
                    q: "Diketahui dua lingkaran L1 ≡ x² + y² = 9 dan L2 ≡ (x - 8)² + y² = 16. Kedudukan kedua lingkaran tersebut adalah...",  
                    options: [  
                        "A. Bersinggungan di dalam",  
                        "B. Bersinggungan di luar",  
                        "C. Saling lepas di luar",  
                        "D. Berpotongan di dua titik"  
                    ],  
                    answer: 2,  
                    explain: "L1: Pusat (0,0), R = 3.<br>L2: Pusat (8,0), r = 4.<br>Jarak pusat (d) = 8.<br>Jumlah jari-jari R + r = 3 + 4 = 7.<br>Karena d (8) > R + r (7), maka kedua lingkaran <b>Saling lepas di luar</b>.",  
                    diagramType: "two_circles"  
                },  
                {  
                    q: "Sebuah pizza cutter memotong pizza sepanjang garis singgung dari titik P(10, 0) ke lingkaran x² + y² = 36. Panjang garis singgung tersebut adalah...",  
                    options: ["A. 6 unit", "B. 8 unit", "C. 10 unit", "D. 64 unit"],  
                    answer: 1,  
                    explain: "Panjang garis singgung (s): <b>s = √(d² - r²)</b>.<br>Jarak P(10,0) ke pusat (0,0) d = 10, r = 6.<br>s = √(10² - 6²) = √(100 - 36) = √64 = <b>8 unit</b>.",  
                    diagramType: "tangent_length"  
                },  
                {  
                    q: "Persamaan lingkaran yang sepusat (konsentris) dengan x² + y² - 4x + 6y - 12 = 0 dan menyinggung garis 3x - 4y + 7 = 0 adalah...",  
                    options: [  
                        "A. (x - 2)² + (y + 3)² = 25",  
                        "B. (x + 2)² + (y - 3)² = 25",  
                        "C. (x - 2)² + (y + 3)² = 16",  
                        "D. (x - 2)² + (y + 3)² = 9"  
                    ],  
                    answer: 0,  
                    explain: "Pusat L1: A = -4, B = 6 ⇒ Pusat (2, -3).<br>Jarak titik (2,-3) ke garis 3x - 4y + 7 = 0 adalah jari-jari r:<br>r = |3(2) - 4(-3) + 7| / √(3² + (-4)²) = |6 + 12 + 7| / 5 = 25 / 5 = 5.<br>Persamaan: <b>(x - 2)² + (y + 3)² = 25</b>.",  
                    diagramType: "circle_concentric"  
                },  
                {  
                    q: "[HOTS] Dua pizza diletakkan berdampingan sehingga lingkarannya saling bersinggungan di luar. Jika R = 9 cm dan r = 4 cm, panjang garis singgung persekutuan luar kedua pizza adalah...",  
                    options: ["A. 12 cm", "B. 13 cm", "C. 15 cm", "D. 36 cm"],  
                    answer: 0,  
                    explain: "Karena bersinggungan di luar, jarak pusat (d) = R + r = 9 + 4 = 13 cm.<br>Panjang Garis Singgung Persekutuan Luar (GSPL):<br>l = √(d² - (R - r)²) = √(13² - (9 - 4)²) = √(169 - 25) = √144 = <b>12 cm</b>.",  
                    diagramType: "gspl"  
                }  
            ]  
        };  
  
        /* ===================================================  
           2. SOUND SYNTHESIZER (WEB AUDIO API)  
           =================================================== */  
        const AudioCtx = window.AudioContext || window.webkitAudioContext;  
        let audioCtx = null;  
  
        function playSound(type) {  
            if (!gameState.soundEnabled) return;  
            try {  
                if (!audioCtx) audioCtx = new AudioCtx();  
                  
                const osc = audioCtx.createOscillator();  
                const gain = audioCtx.createGain();  
                osc.connect(gain);  
                gain.connect(audioCtx.destination);  
  
                const now = audioCtx.currentTime;  
  
                if (type === 'click') {  
                    osc.frequency.setValueAtTime(400, now);  
                    osc.frequency.exponentialRampToValueAtTime(800, now + 0.05);  
                    gain.gain.setValueAtTime(0.3, now);  
                    gain.gain.linearRampToValueAtTime(0.01, now + 0.05);  
                    osc.start(now);  
                    osc.stop(now + 0.05);  
                } else if (type === 'correct') {  
                    osc.type = 'triangle';  
                    osc.frequency.setValueAtTime(523.25, now); // C5  
                    osc.frequency.setValueAtTime(659.25, now + 0.1); // E5  
                    osc.frequency.setValueAtTime(783.99, now + 0.2); // G5  
                    gain.gain.setValueAtTime(0.4, now);  
                    gain.gain.linearRampToValueAtTime(0.01, now + 0.35);  
                    osc.start(now);  
                    osc.stop(now + 0.35);  
                } else if (type === 'wrong') {  
                    osc.type = 'sawtooth';  
                    osc.frequency.setValueAtTime(220, now);  
                    osc.frequency.linearRampToValueAtTime(110, now + 0.2);  
                    gain.gain.setValueAtTime(0.4, now);  
                    gain.gain.linearRampToValueAtTime(0.01, now + 0.25);  
                    osc.start(now);  
                    osc.stop(now + 0.25);  
                }  
            } catch(e) {}  
        }  
  
        function toggleAudio() {  
            gameState.soundEnabled = !gameState.soundEnabled;  
            const btn = document.getElementById('audio-toggle-btn');  
            if (gameState.soundEnabled) {  
                btn.innerHTML = '<i class="fa-solid fa-volume-high text-slate-800"></i>';  
                playSound('click');  
            } else {  
                btn.innerHTML = '<i class="fa-solid fa-volume-xmark text-slate-400"></i>';  
            }  
        }  
  
        /* ===================================================  
           3. UI & SCREEN NAVIGATION  
           =================================================== */  
        function showScreen(screenId) {  
            playSound('click');  
            const screens = ['main-menu', 'level-map', 'gameplay', 'material', 'instructions', 'achievements'];  
            screens.forEach(id => {  
                document.getElementById(`screen-${id}`).classList.add('hidden');  
            });  
            document.getElementById(`screen-${screenId}`).classList.remove('hidden');  
  
            if (screenId === 'achievements') {  
                updateAchievementsUI();  
            }  
        }  
  
        function startGame() {  
            const inputName = document.getElementById('player-name-input').value.trim();  
            if (inputName) gameState.playerName = inputName;  
            showScreen('level-map');  
            updateLevelMapUI();  
        }  
  
        function updateLevelMapUI() {  
            // Level 2 unlock  
            const l2Card = document.getElementById('level-2-card');  
            const l2Btn = document.getElementById('btn-level-2');  
            if (gameState.unlockedLevels.includes(2)) {  
                l2Card.classList.remove('opacity-90');  
                l2Btn.disabled = false;  
            } else {  
                l2Btn.innerHTML = '<i class="fa-solid fa-lock"></i> TERKUNCI';  
                l2Btn.classList.replace('btn-yellow', 'bg-slate-300');  
            }  
  
            // Level 3 unlock  
            const l3Card = document.getElementById('level-3-card');  
            const l3Btn = document.getElementById('btn-level-3');  
            if (gameState.unlockedLevels.includes(3)) {  
                l3Card.classList.remove('opacity-90');  
                l3Btn.disabled = false;  
            } else {  
                l3Btn.innerHTML = '<i class="fa-solid fa-lock"></i> TERKUNCI';  
                l3Btn.classList.replace('btn-purple', 'bg-slate-300');  
            }  
        }  
  
        function startLevel(levelNum) {  
            if (!gameState.unlockedLevels.includes(levelNum)) return;  
            gameState.currentLevel = levelNum;  
            gameState.currentQuestionIdx = 0;  
            gameState.levelScores[levelNum] = 0;  
              
            showScreen('gameplay');  
            loadQuestion();  
        }  
  
        /* ===================================================  
           4. GAMEPLAY CONTROLLER  
           =================================================== */  
        function loadQuestion() {  
            const level = gameState.currentLevel;  
            const qIdx = gameState.currentQuestionIdx;  
            const qData = questionsData[level][qIdx];  
  
            // UI Badges  
            document.getElementById('game-level-badge').innerText = `LEVEL ${level}`;  
            document.getElementById('question-tracker').innerText = `Soal ${qIdx + 1} dari 5`;  
            document.getElementById('level-progress-bar').style.width = `${((qIdx + 1) / 5) * 100}%`;  
            document.getElementById('level-score-display').innerText = gameState.levelScores[level];  
  
            // Text  
            document.getElementById('question-text').innerHTML = qData.q;  
  
            // Render Options (Topping Buttons)  
            const optionsContainer = document.getElementById('options-container');  
            optionsContainer.innerHTML = '';  
            gameState.selectedOption = null;  
  
            const toppingIcons = ['🍕', '🍄', '🫒', '🫑'];  
  
            qData.options.forEach((optText, idx) => {  
                const optBtn = document.createElement('button');  
                optBtn.className = `btn-cartoon bg-white hover:bg-amber-100 text-slate-800 p-3 text-left text-sm font-bold flex items-center gap-3 transition-all border-2 border-slate-700`;  
                optBtn.innerHTML = `  
                    <span class="w-8 h-8 rounded-full bg-amber-200 border border-slate-700 flex items-center justify-center text-base flex-shrink-0">  
                        ${toppingIcons[idx]}  
                    </span>  
                    <span>${optText}</span>  
                `;  
                optBtn.onclick = () => selectOption(idx, optBtn);  
                optionsContainer.appendChild(optBtn);  
            });  
  
            // Disable Submit Button  
            const submitBtn = document.getElementById('btn-submit-answer');  
            submitBtn.disabled = true;  
            submitBtn.classList.add('opacity-50', 'cursor-not-allowed');  
  
            // Draw Geometry Canvas Visualizer  
            drawCanvasDiagram(qData.diagramType);  
        }  
  
        function selectOption(idx, btnElem) {  
            playSound('click');  
            gameState.selectedOption = idx;  
  
            // Highlight UI  
            const allBtns = document.getElementById('options-container').children;  
            for (let btn of allBtns) {  
                btn.classList.remove('bg-amber-300', 'border-red-500', 'ring-2', 'ring-red-400');  
                btn.classList.add('bg-white');  
            }  
            btnElem.classList.remove('bg-white');  
            btnElem.classList.add('bg-amber-300', 'border-red-500', 'ring-2', 'ring-red-400');  
  
            // Enable Submit Button  
            const submitBtn = document.getElementById('btn-submit-answer');  
            submitBtn.disabled = false;  
            submitBtn.classList.remove('opacity-50', 'cursor-not-allowed');  
        }  
  
        function submitAnswer() {  
            if (gameState.selectedOption === null) return;  
  
            const level = gameState.currentLevel;  
            const qIdx = gameState.currentQuestionIdx;  
            const qData = questionsData[level][qIdx];  
  
            const isCorrect = (gameState.selectedOption === qData.answer);  
            const pointsPerQ = level === 1 ? 10 : (level === 2 ? 20 : 30);  
  
            if (isCorrect) {  
                playSound('correct');  
                gameState.levelScores[level] += pointsPerQ;  
                gameState.score += pointsPerQ;  
                document.getElementById('global-score-display').innerText = `${gameState.score} Pts`;  
            } else {  
                playSound('wrong');  
            }  
  
            // Show Modal Explanation  
            showExplanationModal(isCorrect, qData);  
        }  
  
        function showExplanationModal(isCorrect, qData) {  
            const modal = document.getElementById('explanation-modal');  
            const badge = document.getElementById('modal-header-badge');  
            const correctText = document.getElementById('modal-correct-ans-text');  
            const expContent = document.getElementById('modal-explanation-content');  
  
            if (isCorrect) {  
                badge.className = "inline-block px-3 py-1 rounded-full text-xs font-display text-white bg-green-500 mb-2";  
                badge.innerText = "JAWABAN BENAR! 🎉 (+ " + (gameState.currentLevel === 1 ? 10 : (gameState.currentLevel === 2 ? 20 : 30)) + " Pts)";  
            } else {  
                badge.className = "inline-block px-3 py-1 rounded-full text-xs font-display text-white bg-red-500 mb-2";  
                badge.innerText = "KURANG TEPAT! 🍕";  
            }  
  
            correctText.innerHTML = `Jawaban Tepat: <span class="text-emerald-700 font-bold">${qData.options[qData.answer]}</span>`;  
            expContent.innerHTML = qData.explain;  
  
            modal.classList.remove('hidden');  
        }  
  
        function nextQuestion() {  
            playSound('click');  
            document.getElementById('explanation-modal').classList.add('hidden');  
  
            gameState.currentQuestionIdx++;  
  
            if (gameState.currentQuestionIdx < 5) {  
                loadQuestion();  
            } else {  
                // Level Finished  
                if (gameState.currentLevel < 3) {  
                    gameState.unlockedLevels.push(gameState.currentLevel + 1);  
                }  
                showScreen('level-map');  
                updateLevelMapUI();  
            }  
        }  
  
        /* ===================================================  
           5. CANVAS MATH & PIZZA VISUALIZER  
           =================================================== */  
        function drawCanvasDiagram(type) {  
            const canvas = document.getElementById('math-canvas');  
            const ctx = canvas.getContext('2d');  
            const w = canvas.width;  
            const h = canvas.height;  
            const cx = w / 2;  
            const cy = h / 2;  
  
            ctx.clearRect(0, 0, w, h);  
  
            // Draw Cartesian Grid  
            ctx.strokeStyle = '#E0E0E0';  
            ctx.lineWidth = 1;  
            for (let x = 0; x < w; x += 20) {  
                ctx.beginPath(); ctx.moveTo(x, 0); ctx.lineTo(x, h); ctx.stroke();  
            }  
            for (let y = 0; y < h; y += 20) {  
                ctx.beginPath(); ctx.moveTo(0, y); ctx.lineTo(w, y); ctx.stroke();  
            }  
  
            // Draw Axes  
            ctx.strokeStyle = '#9E9E9E';  
            ctx.lineWidth = 1.5;  
            ctx.beginPath(); ctx.moveTo(cx, 0); ctx.lineTo(cx, h); ctx.stroke();  
            ctx.beginPath(); ctx.moveTo(0, cy); ctx.lineTo(w, cy); ctx.stroke();  
  
            // Render Diagram based on Type  
            ctx.lineWidth = 3;  
  
            if (type === 'tali_busur') {  
                // Pizza with chord  
                ctx.fillStyle = '#FFE082'; ctx.strokeStyle = '#D72638';  
                ctx.beginPath(); ctx.arc(cx, cy, 65, 0, Math.PI * 2); ctx.fill(); ctx.stroke();  
  
                // Chord line  
                ctx.strokeStyle = '#29B6F6'; ctx.lineWidth = 4;  
                ctx.beginPath(); ctx.moveTo(cx - 45, cy - 45); ctx.lineTo(cx + 50, cy + 40); ctx.stroke();  
  
                // Center dot  
                ctx.fillStyle = '#2C3E50'; ctx.beginPath(); ctx.arc(cx, cy, 4, 0, Math.PI * 2); ctx.fill();  
            }   
            else if (type === 'circle_00' || type === 'circle_basic') {  
                ctx.fillStyle = '#FFE082'; ctx.strokeStyle = '#D72638';  
                ctx.beginPath(); ctx.arc(cx, cy, 60, 0, Math.PI * 2); ctx.fill(); ctx.stroke();  
                  
                // Radius line  
                ctx.strokeStyle = '#2C3E50'; ctx.lineWidth = 2.5; ctx.setLineDash([4, 4]);  
                ctx.beginPath(); ctx.moveTo(cx, cy); ctx.lineTo(cx + 60, cy); ctx.stroke();  
                ctx.setLineDash([]);  
                  
                ctx.fillStyle = '#2C3E50'; ctx.font = 'bold 12px Fredoka One';  
                ctx.fillText("O(0,0)", cx - 18, cy + 18);  
                ctx.fillText("r", cx + 25, cy - 6);  
            }  
            else if (type === 'juring') {  
                ctx.fillStyle = '#FFE082'; ctx.strokeStyle = '#D72638';  
                ctx.beginPath(); ctx.arc(cx, cy, 65, 0, Math.PI * 2); ctx.fill(); ctx.stroke();  
  
                // Juring Slice  
                ctx.fillStyle = '#FF5A5F';  
                ctx.beginPath(); ctx.moveTo(cx, cy); ctx.arc(cx, cy, 65, -Math.PI / 3, 0); ctx.closePath(); ctx.fill(); ctx.stroke();  
  
                ctx.fillStyle = '#2C3E50'; ctx.font = 'bold 12px Fredoka One';  
                ctx.fillText("60°", cx + 20, cy - 12);  
            }  
            else if (type === 'circle_ab' || type === 'circle_general') {  
                // Shifted Circle  
                const px = cx + 30; const py = cy - 20;  
                ctx.fillStyle = '#FFF176'; ctx.strokeStyle = '#FF7043';  
                ctx.beginPath(); ctx.arc(px, py, 50, 0, Math.PI * 2); ctx.fill(); ctx.stroke();  
  
                ctx.fillStyle = '#2C3E50'; ctx.beginPath(); ctx.arc(px, py, 4, 0, Math.PI * 2); ctx.fill();  
                ctx.font = 'bold 11px Fredoka One';  
                ctx.fillText("P(a,b)", px - 15, py - 8);  
            }  
            else if (type === 'point_position') {  
                ctx.fillStyle = '#FFE082'; ctx.strokeStyle = '#D72638';  
                ctx.beginPath(); ctx.arc(cx, cy, 50, 0, Math.PI * 2); ctx.fill(); ctx.stroke();  
  
                // External Point A  
                ctx.fillStyle = '#E53935'; ctx.beginPath(); ctx.arc(cx + 65, cy - 30, 6, 0, Math.PI * 2); ctx.fill();  
                ctx.fillStyle = '#2C3E50'; ctx.font = 'bold 11px Fredoka One';  
                ctx.fillText("A(5,2)", cx + 55, cy - 40);  
            }  
            else if (type === 'tangent_point' || type === 'tangent_m') {  
                ctx.fillStyle = '#FFE082'; ctx.strokeStyle = '#D72638';  
                ctx.beginPath(); ctx.arc(cx, cy, 50, 0, Math.PI * 2); ctx.fill(); ctx.stroke();  
  
                // Tangent Line  
                ctx.strokeStyle = '#29B6F6'; ctx.lineWidth = 3.5;  
                ctx.beginPath(); ctx.moveTo(cx - 70, cy + 80); ctx.lineTo(cx + 80, cy - 70); ctx.stroke();  
  
                ctx.fillStyle = '#2C3E50'; ctx.beginPath(); ctx.arc(cx + 35, cy - 35, 5, 0, Math.PI * 2); ctx.fill();  
            }  
            else if (type === 'two_circles' || type === 'gspl') {  
                // Two separate circles  
                ctx.fillStyle = '#FFD54F'; ctx.strokeStyle = '#D72638';  
                ctx.beginPath(); ctx.arc(cx - 45, cy, 40, 0, Math.PI * 2); ctx.fill(); ctx.stroke();  
  
                ctx.fillStyle = '#81C784'; ctx.strokeStyle = '#2E7D32';  
                ctx.beginPath(); ctx.arc(cx + 45, cy, 25, 0, Math.PI * 2); ctx.fill(); ctx.stroke();  
  
                // Tangent connecting line  
                ctx.strokeStyle = '#AB47BC'; ctx.lineWidth = 3;  
                ctx.beginPath(); ctx.moveTo(cx - 45, cy - 40); ctx.lineTo(cx + 45, cy - 25); ctx.stroke();  
            }  
            else {  
                // Default Pizza Visual  
                ctx.fillStyle = '#FFE082'; ctx.strokeStyle = '#D72638';  
                ctx.beginPath(); ctx.arc(cx, cy, 60, 0, Math.PI * 2); ctx.fill(); ctx.stroke();  
            }  
        }  
  
        /* ===================================================  
           6. ACHIEVEMENTS & CERTIFICATE LOGIC  
           =================================================== */  
        function updateAchievementsUI() {  
            document.getElementById('cert-player-name').innerText = gameState.playerName;  
            document.getElementById('cert-score').innerText = `${gameState.score} / 300`;  
  
            let title = "Koki Magang 🍕";  
            if (gameState.score >= 250) title = "Master Pizza Math 👑";  
            else if (gameState.score >= 180) title = "Chef Lingkaran Senior 👨‍🍳";  
            else if (gameState.score >= 100) title = "Koki Pizza Bakat 🌟";  
  
            document.getElementById('cert-title').innerText = title;  
  
            // Badges  
            const container = document.getElementById('badges-container');  
            container.innerHTML = `  
                <div class="bg-white border-2 border-slate-800 p-2 rounded-xl text-center w-20 shadow-[2px_2px_0px_#2C3E50]">  
                    <span class="text-2xl">🥇</span>  
                    <p class="text-[10px] font-bold mt-1 text-slate-700">Beginner</p>  
                </div>  
                <div class="bg-white border-2 border-slate-800 p-2 rounded-xl text-center w-20 shadow-[2px_2px_0px_#2C3E50] ${gameState.score >= 100 ? '' : 'opacity-40'}">  
                    <span class="text-2xl">🍕</span>  
                    <p class="text-[10px] font-bold mt-1 text-slate-700">Chef Pro</p>  
                </div>  
                <div class="bg-white border-2 border-slate-800 p-2 rounded-xl text-center w-20 shadow-[2px_2px_0px_#2C3E50] ${gameState.score >= 200 ? '' : 'opacity-40'}">  
                    <span class="text-2xl">🏆</span>  
                    <p class="text-[10px] font-bold mt-1 text-slate-700">Master</p>  
                </div>  
            `;  
        }  
  
        // Initialize App on Window Load  
        window.onload = function() {  
            updateLevelMapUI();  
        };  
    </script>  
</body>  
</html>  
