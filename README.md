<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>김고은 | ANIMATION PORTFOLIO</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700;800&family=Noto+Sans+KR:wght@400;500;700;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css">

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        yellowframe: {
                            yellow: '#FFE500',
                            dark: '#111111',
                            bg: '#F5F1E8',
                            card: '#FFFDF5',
                            muted: '#77736B'
                        }
                    },
                    boxShadow: {
                        frame: '6px 6px 0 #111111',
                        frameHover: '10px 10px 0 #111111'
                    },
                    fontFamily: {
                        sans: ['Noto Sans KR', 'sans-serif'],
                        mono: ['JetBrains Mono', 'monospace']
                    }
                }
            }
        }
    </script>

    <style>
        * { box-sizing: border-box; }
        html { scroll-behavior: smooth; }
        body {
            margin: 0;
            background: #F5F1E8;
            color: #111;
            font-family: 'Noto Sans KR', sans-serif;
            overflow-x: hidden;
        }
        ::selection { background: #FFE500; color: #111; }
        
        .custom-cursor {
            position: fixed;
            width: 18px;
            height: 18px;
            border: 2px solid #111;
            border-radius: 50%;
            pointer-events: none;
            z-index: 9999;
            transform: translate(-50%, -50%);
            transition: width .15s ease, height .15s ease, background-color .15s ease;
        }
        .custom-cursor.hover {
            width: 32px;
            height: 32px;
            background-color: #FFE500;
            opacity: 0.8;
        }
        @media (max-width: 768px) {
            .custom-cursor { display: none; }
        }

        .noise {
            position: fixed;
            inset: 0;
            pointer-events: none;
            opacity: .035;
            z-index: 9998;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.8'/%3E%3C/svg%3E");
        }

        .yellow-marker {
            background: linear-gradient(transparent 55%, #FFE500 55%);
        }
        .modal-scroll::-webkit-scrollbar { width: 8px; }
        .modal-scroll::-webkit-scrollbar-thumb { background: #111; }
    </style>
</head>

<body>
<div class="noise"></div>
<div id="cursor" class="custom-cursor"></div>

<!-- HEADER -->
<header class="fixed top-0 left-0 right-0 z-50 bg-yellowframe-bg/95 backdrop-blur border-b-2 border-yellowframe-dark">
    <div class="max-w-7xl mx-auto px-5 md:px-8 h-20 flex items-center justify-between">
        <a href="#top" class="font-mono font-black text-xl tracking-tight">GKEUN<span class="text-yellowframe-dark">.</span></a>

        <nav class="hidden md:flex items-center gap-8 font-mono text-xs font-bold">
            <a href="#work" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">WORK</a>
            <a href="#process" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">PROCESS</a>
            <a href="#gallery" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">GALLERY</a>
            <a href="#about" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">ABOUT</a>
            <a href="#contact" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">CONTACT</a>
        </nav>

        <button id="menuBtn" class="md:hidden text-xl p-2" aria-label="메뉴 열기/닫기">
            <i class="fa-solid fa-bars"></i>
        </button>
    </div>

    <!-- MOBILE MENU -->
    <div id="mobileMenu" class="hidden md:hidden border-t-2 border-yellowframe-dark bg-yellowframe-card">
        <nav class="flex flex-col font-mono font-bold text-sm">
            <a href="#work" class="px-5 py-4 border-b border-yellowframe-dark hover:bg-yellowframe-yellow">WORK</a>
            <a href="#process" class="px-5 py-4 border-b border-yellowframe-dark hover:bg-yellowframe-yellow">PROCESS</a>
            <a href="#gallery" class="px-5 py-4 border-b border-yellowframe-dark hover:bg-yellowframe-yellow">GALLERY</a>
            <a href="#about" class="px-5 py-4 border-b border-yellowframe-dark hover:bg-yellowframe-yellow">ABOUT</a>
            <a href="#contact" class="px-5 py-4 hover:bg-yellowframe-yellow">CONTACT</a>
        </nav>
    </div>
</header>

<main id="top">

<!-- HERO -->
<section class="min-h-screen pt-20 flex items-center border-b-2 border-yellowframe-dark">
    <div class="max-w-7xl mx-auto w-full px-5 md:px-8 py-20">
        <div class="grid md:grid-cols-[1fr_auto] gap-12 items-end">
            <div>
                <p class="font-mono text-xs font-bold mb-7">2D ANIMATOR / PORTFOLIO / 2026</p>
                <h1 class="text-[clamp(3.5rem,11vw,9.5rem)] leading-[.85] font-black tracking-[-.08em]">
                    FRAME BY<br>
                    <span class="text-yellowframe-yellow" style="-webkit-text-stroke:3px #111;">FRAME</span>
                </h1>
                <div class="mt-10 max-w-xl">
                    <p class="text-lg md:text-xl font-bold leading-relaxed">
                        움직임을 그리고,<br>
                        이야기를 프레임 안에 담습니다.
                    </p>
                    <!-- KEY SKILLS -->
                    <div class="mt-6 flex flex-wrap gap-2 font-mono text-xs font-bold">
                        <span class="border-2 border-yellowframe-dark bg-yellowframe-card px-3 py-1.5 shadow-[2px_2px_0_#111]">Character Acting</span>
                        <span class="border-2 border-yellowframe-dark bg-yellowframe-card px-3 py-1.5 shadow-[2px_2px_0_#111]">Key Animation</span>
                        <span class="border-2 border-yellowframe-dark bg-yellowframe-card px-3 py-1.5 shadow-[2px_2px_0_#111]">Storytelling</span>
                    </div>
                </div>
            </div>

            <div class="border-2 border-yellowframe-dark bg-yellowframe-yellow shadow-frame p-5 w-full md:w-64">
                <div class="font-mono text-[10px] font-bold mb-8">CURRENT STATUS</div>
                <div class="font-mono text-4xl font-black">OPEN</div>
                <div class="font-mono text-xs font-bold mt-2">FOR WORK</div>
                <div class="border-t-2 border-yellowframe-dark mt-8 pt-4 text-xs font-bold">
                    2D ANIMATOR<br>
                    KIM GOEUN
                </div>
            </div>
        </div>
    </div>
</section>

<!-- SELECTED WORK -->
<section id="work" class="py-24 md:py-32">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <div class="flex items-end justify-between mb-14">
            <div>
                <p class="font-mono text-xs font-bold mb-3">01 / SELECTED WORK</p>
                <h2 class="text-5xl md:text-7xl font-black tracking-tight">SELECTED WORK<span class="text-yellowframe-yellow">.</span></h2>
            </div>
            <span class="hidden md:block font-mono text-xs font-bold">2025 — 2026</span>
        </div>

        <div class="grid md:grid-cols-2 gap-8">
            <!-- PROJECT 01: 천재? 탐정 새롬 -->
            <div class="border-2 border-yellowframe-dark bg-yellowframe-card shadow-frame flex flex-col justify-between">
                <div>
                    <a href="https://youtu.be/imD6U6dVes8?si=6TZcW1DbJxwKmnde" target="_blank" rel="noopener noreferrer"
                       class="group block border-b-2 border-yellowframe-dark overflow-hidden relative">
                        <div class="aspect-video bg-yellowframe-dark relative">
                            <img src="https://cdn.phototourl.com/free/2026-09-10-b8988685-e6b7-4222-815c-c153b166a66a.png"
                                 alt="천재? 탐정 새롬 썸네일" loading="lazy"
                                 class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-16 h-16 rounded-full bg-yellowframe-yellow border-2 border-yellowframe-dark flex items-center justify-center shadow-frame group-hover:scale-110 transition-transform">
                                    <i class="fa-solid fa-play"></i>
                                </div>
                            </div>
                        </div>
                    </a>
                    <div class="p-6">
                        <div class="flex justify-between items-start gap-4">
                            <div>
                                <p class="font-mono text-xs font-bold">PROJECT 01</p>
                                <h3 class="text-2xl font-black mt-2">천재? 탐정 새롬</h3>
                            </div>
                            <span class="font-mono text-xs border-2 border-yellowframe-dark px-2 py-1 bg-yellowframe-yellow">ANIMATION</span>
                        </div>
                        <p class="text-sm text-yellowframe-muted mt-4 leading-6">자칭 천재 탐정 새롬이가 산장에서 일어난 수상한 살인사건을 수사하며 벌어지는 코미디 추리 단편 애니메이션.</p>
                        
                        <!-- ROLE / FORMAT / GENRE -->
                        <div class="mt-6 pt-6 border-t-2 border-yellowframe-dark/20 grid grid-cols-3 gap-2 font-mono text-[11px]">
                            <div>
                                <span class="block text-yellowframe-muted font-bold">ROLE</span>
                                <span class="font-bold">원동화, 캐릭터</span>
                            </div>
                            <div>
                                <span class="block text-yellowframe-muted font-bold">FORMAT</span>
                                <span class="font-bold">단편 (5분)</span>
                            </div>
                            <div>
                                <span class="block text-yellowframe-muted font-bold">GENRE</span>
                                <span class="font-bold">코미디, 추리</span>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="p-6 pt-0">
                    <button onclick="openPlanModal('saerom')" class="w-full text-center border-2 border-yellowframe-dark py-3 font-mono text-xs font-bold bg-yellowframe-bg hover:bg-yellowframe-yellow transition-colors">
                        VIEW PITCH DECK →
                    </button>
                </div>
            </div>

            <!-- PROJECT 02: 괴짜과학자 비키 -->
            <div class="border-2 border-yellowframe-dark bg-yellowframe-card shadow-frame flex flex-col justify-between">
                <div>
                    <a href="https://youtu.be/494-k5M4vuY?si=MIRqNVYPDjmymfpr" target="_blank" rel="noopener noreferrer"
                       class="group block border-b-2 border-yellowframe-dark overflow-hidden relative">
                        <div class="aspect-video bg-yellowframe-dark relative">
                            <img src="https://cdn.phototourl.com/free/2026-09-10-1016abe6-3ec4-4246-b20f-bf31a2160e09.jpg"
                                 alt="괴짜과학자 비키 썸네일" loading="lazy"
                                 class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-16 h-16 rounded-full bg-yellowframe-yellow border-2 border-yellowframe-dark flex items-center justify-center shadow-frame group-hover:scale-110 transition-transform">
                                    <i class="fa-solid fa-play"></i>
                                </div>
                            </div>
                        </div>
                    </a>
                    <div class="p-6">
                        <div class="flex justify-between items-start gap-4">
                            <div>
                                <p class="font-mono text-xs font-bold">PROJECT 02</p>
                                <h3 class="text-2xl font-black mt-2">괴짜과학자 비키</h3>
                            </div>
                            <span class="font-mono text-xs border-2 border-yellowframe-dark px-2 py-1 bg-yellowframe-yellow">ANIMATION</span>
                        </div>
                        <p class="text-sm text-yellowframe-muted mt-4 leading-6">음모론으로 뒤덮인 현대 사회에서 괴짜 과학자 ‘비키’는 지구 음모론을 증명할 수 있을 것인가?</p>
                        
                        <!-- ROLE / FORMAT / GENRE -->
                        <div class="mt-6 pt-6 border-t-2 border-yellowframe-dark/20 grid grid-cols-3 gap-2 font-mono text-[11px]">
                            <div>
                                <span class="block text-yellowframe-muted font-bold">ROLE</span>
                                <span class="font-bold">원동화 작화</span>
                            </div>
                            <div>
                                <span class="block text-yellowframe-muted font-bold">FORMAT</span>
                                <span class="font-bold">TV 시리즈</span>
                            </div>
                            <div>
                                <span class="block text-yellowframe-muted font-bold">GENRE</span>
                                <span class="font-bold">SF, 코미디</span>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="p-6 pt-0">
                    <button onclick="openPlanModal('vicky')" class="w-full text-center border-2 border-yellowframe-dark py-3 font-mono text-xs font-bold bg-yellowframe-bg hover:bg-yellowframe-yellow transition-colors">
                        VIEW PITCH DECK →
                    </button>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- PROCESS -->
<section id="process" class="py-24 md:py-32 bg-yellowframe-dark text-yellowframe-bg">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <div class="mb-14">
            <p class="font-mono text-xs font-bold mb-3 text-yellowframe-yellow">02 / WORKFLOW</p>
            <h2 class="text-5xl md:text-7xl font-black tracking-tight">PROCESS<span class="text-yellowframe-yellow">.</span></h2>
        </div>

        <!-- PIPELINE FLOW -->
        <div class="grid grid-cols-2 md:grid-cols-6 gap-3 font-mono">
            <div class="border-2 border-yellowframe-bg p-5 flex flex-col justify-between bg-yellowframe-dark hover:bg-yellowframe-yellow hover:text-yellowframe-dark transition-colors group">
                <span class="text-xs font-bold text-yellowframe-yellow group-hover:text-yellowframe-dark">STEP 01</span>
                <span class="text-xl font-black mt-6">기획</span>
            </div>
            <div class="border-2 border-yellowframe-bg p-5 flex flex-col justify-between bg-yellowframe-dark hover:bg-yellowframe-yellow hover:text-yellowframe-dark transition-colors group">
                <span class="text-xs font-bold text-yellowframe-yellow group-hover:text-yellowframe-dark">STEP 02</span>
                <span class="text-xl font-black mt-6">캐릭터</span>
            </div>
            <div class="border-2 border-yellowframe-bg p-5 flex flex-col justify-between bg-yellowframe-dark hover:bg-yellowframe-yellow hover:text-yellowframe-dark transition-colors group">
                <span class="text-xs font-bold text-yellowframe-yellow group-hover:text-yellowframe-dark">STEP 03</span>
                <span class="text-xl font-black mt-6">원동화</span>
            </div>
            <div class="border-2 border-yellowframe-bg p-5 flex flex-col justify-between bg-yellowframe-dark hover:bg-yellowframe-yellow hover:text-yellowframe-dark transition-colors group">
                <span class="text-xs font-bold text-yellowframe-yellow group-hover:text-yellowframe-dark">STEP 04</span>
                <span class="text-xl font-black mt-6">동화</span>
            </div>
            <div class="border-2 border-yellowframe-bg p-5 flex flex-col justify-between bg-yellowframe-dark hover:bg-yellowframe-yellow hover:text-yellowframe-dark transition-colors group">
                <span class="text-xs font-bold text-yellowframe-yellow group-hover:text-yellowframe-dark">STEP 05</span>
                <span class="text-xl font-black mt-6">움직임</span>
            </div>
            <div class="border-2 border-yellowframe-yellow bg-yellowframe-yellow text-yellowframe-dark p-5 flex flex-col justify-between">
                <span class="text-xs font-bold">STEP 06</span>
                <span class="text-xl font-black mt-6">완성</span>
            </div>
        </div>
    </div>
</section>

<!-- GALLERY -->
<section id="gallery" class="py-24 md:py-32">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <div class="mb-12">
            <p class="font-mono text-xs font-bold mb-3">03 / GALLERY</p>
            <h2 class="text-5xl md:text-7xl font-black tracking-tight">GALLERY<span class="text-yellowframe-yellow">.</span></h2>
        </div>

        <div class="flex flex-wrap gap-2 mb-10">
            <button onclick="switchCategory('character')" class="category-btn active font-mono text-xs font-bold border-2 border-yellowframe-dark px-4 py-2 bg-yellowframe-yellow" data-category="character">CHARACTER DESIGN</button>
            <button onclick="switchCategory('animating')" class="category-btn font-mono text-xs font-bold border-2 border-yellowframe-dark px-4 py-2 bg-yellowframe-card" data-category="animating">ANIMATION</button>
            <button onclick="switchCategory('croquis')" class="category-btn font-mono text-xs font-bold border-2 border-yellowframe-dark px-4 py-2 bg-yellowframe-card" data-category="croquis">CROQUIS / DRAWING</button>
        </div>

        <!-- CHARACTER DESIGN -->
        <div id="cat-character" class="category-content">
            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 0)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/13qbdDvmqw4yxpk42hn9zEjYbGpdqoAov" alt="캐릭터 일러스트 1" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 bg-yellowframe-card font-mono text-xs font-bold flex items-center justify-between">
                        <span>CHARACTER #01</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 1)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1c8Cu2MGmm0bohhzw_W5jn1aeKxk7mBPU" alt="캐릭터 일러스트 2" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 bg-yellowframe-card font-mono text-xs font-bold flex items-center justify-between">
                        <span>CHARACTER #02</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 2)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1TCKegKyIa-fQWd4-uoIGjmqFduLzFhnD" alt="캐릭터 일러스트 3" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 bg-yellowframe-card font-mono text-xs font-bold flex items-center justify-between">
                        <span>CHARACTER #03</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 3)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1UDPoCEa3Dt4CywGTbHxZI9GZTNSDLqBg" alt="캐릭터 일러스트 4" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 bg-yellowframe-card font-mono text-xs font-bold flex items-center justify-between">
                        <span>CHARACTER #04</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 4)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/15JbarnOmtB6w2A9s1-EQ4ldRXq6deH98" alt="캐릭터 일러스트 5" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 bg-yellowframe-card font-mono text-xs font-bold flex items-center justify-between">
                        <span>CHARACTER #05</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- ANIMATION -->
        <div id="cat-animating" class="category-content hidden">
            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 0)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1QBDVOqRDhdWscY-9V1Qr09OETVv6w3dc" alt="애니메이션 1" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 bg-yellowframe-card font-mono text-xs font-bold flex items-center justify-between">
                        <span>ANIMATION #01</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 1)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1RRU-LhcxPEWFOwaHwVI_XUXcBeTXTuUY" alt="애니메이션 2" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 bg-yellowframe-card font-mono text-xs font-bold flex items-center justify-between">
                        <span>ANIMATION #02</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 2)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1mUnVyLHkuivFQUZTVELW_3oIw4tmULdl" alt="애니메이션 3" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 bg-yellowframe-card font-mono text-xs font-bold flex items-center justify-between">
                        <span>ANIMATION #03</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 3)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1YQ9-GKC2bv_YnVMY9tPTJihENRykU6zE" alt="애니메이션 4" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 bg-yellowframe-card font-mono text-xs font-bold flex items-center justify-between">
                        <span>ANIMATION #04</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 4)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1tJJJiFmCo9kRZWDCdJ1K8L4XVZV2Ak-e" alt="애니메이션 5" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 bg-yellowframe-card font-mono text-xs font-bold flex items-center justify-between">
                        <span>ANIMATION #05</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 5)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1rsqfTtiPjN34ftUIRJMXHcwfAfDOrxwO" alt="애니메이션 6" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 bg-yellowframe-card font-mono text-xs font-bold flex items-center justify-between">
                        <span>ANIMATION #06</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- CROQUIS / DRAWING -->
        <div id="cat-croquis" class="category-content hidden">
            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('croquis', 0)">
                    <div class="aspect-square overflow-hidden border-b-2 border-yellowframe-dark">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-dcce84bb-b990-4b63-87ca-85afbc07950f.png" alt="Croquis 1" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 font-mono text-xs font-bold flex items-center justify-between">
                        <span>CROQUIS #01</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('croquis', 1)">
                    <div class="aspect-square overflow-hidden border-b-2 border-yellowframe-dark">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-8a31e455-5394-4f6a-8adf-9bb88c520208.png" alt="Croquis 2" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 font-mono text-xs font-bold flex items-center justify-between">
                        <span>CROQUIS #02</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('croquis', 2)">
                    <div class="aspect-square overflow-hidden border-b-2 border-yellowframe-dark">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-806e145f-eab8-40b9-8bc3-01bcec55aecd.png" alt="Croquis 3" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-3 font-mono text-xs font-bold flex items-center justify-between">
                        <span>CROQUIS #03</span>
                        <span class="text-[10px] text-yellowframe-muted">ENLARGE</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ABOUT -->
<section id="about" class="py-24 md:py-32 bg-yellowframe-yellow border-y-2 border-yellowframe-dark">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <p class="font-mono text-xs font-bold mb-3">04 / ABOUT ME</p>
        <h2 class="text-5xl md:text-7xl font-black tracking-tight mb-12">ABOUT<span class="text-yellowframe-dark">.</span></h2>

        <div class="grid md:grid-cols-[1fr_2fr] gap-12">
            <div>
                <p class="text-xl md:text-2xl font-black leading-snug">
                    안녕하세요, 프레임마다 생동감을 불어넣는 2D 애니메이터 김고은입니다.
                </p>
            </div>
            <div class="space-y-6 text-sm md:text-base leading-relaxed font-medium">
                <p>
                    캐릭터의 개성과 감정을 섬세하게 포착하여 가시적인 움직임으로 구현하는 것에 깊은 흥미를 느낍니다. 
                    단순히 그림을 그리는 것에 그치지 않고, 서사에 생명력을 부여하는 '액팅(Acting)' 중심의 작화를 지향합니다.
                </p>
                <p>
                    기획 단계부터 캐릭터 디자인, 원동화 작업에 이르기까지 애니메이션 제작 전반에 높은 이해도를 갖추고 있으며, 
                    동료들과의 활발한 소통을 통해 최고의 결과물을 완성해내는 리듬감을 중시합니다.
                </p>
            </div>
        </div>
    </div>
</section>

<!-- CONTACT -->
<section id="contact" class="py-24 md:py-32">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <p class="font-mono text-xs font-bold mb-3">05 / CONTACT</p>
        <div class="grid md:grid-cols-[1fr_auto] gap-12 items-end">
            <div>
                <h2 class="text-5xl md:text-8xl font-black tracking-tight">LET'S<br><span class="yellow-marker">WORK TOGETHER.</span></h2>
                <p class="mt-8 text-sm leading-7 text-yellowframe-muted">작업 문의 및 포트폴리오 관련 연락은 아래 메일로 부탁드립니다.</p>
            </div>
            <div class="font-mono font-bold text-sm space-y-4 md:text-right">
                <a href="mailto:onekke@gmail.com" class="block hover:bg-yellowframe-yellow px-2 py-1 transition-colors">EMAIL: onekke@gmail.com</a>
                <a href="https://twitter.com/memo__paper_" target="_blank" rel="noopener noreferrer" class="block hover:bg-yellowframe-yellow px-2 py-1 transition-colors">TWITTER: @memo__paper_ →</a>
            </div>
        </div>
    </div>
</section>

</main>

<footer class="border-t-2 border-yellowframe-dark bg-yellowframe-card">
    <div class="max-w-7xl mx-auto px-5 md:px-8 py-6 flex flex-col md:flex-row justify-between gap-3 font-mono text-[10px] font-bold">
        <span>© 2026 KIM GOEUN</span>
        <span>ANIMATION PORTFOLIO / FRAME BY FRAME</span>
    </div>
</footer>

<!-- PLAN MODAL -->
<div id="planModal" class="fixed inset-0 z-[100] hidden bg-black/70 p-4 md:p-10 flex items-center justify-center">
    <div class="max-w-4xl w-full max-h-[90vh] overflow-y-auto modal-scroll bg-yellowframe-bg border-2 border-yellowframe-dark shadow-frame">
        <div class="sticky top-0 z-10 flex justify-between items-center bg-yellowframe-yellow border-b-2 border-yellowframe-dark p-4">
            <span id="planModalTitle" class="font-mono font-black text-sm">PITCH DECK</span>
            <button onclick="closePlanModal()" aria-label="닫기" class="w-9 h-9 border-2 border-yellowframe-dark bg-yellowframe-card hover:bg-yellowframe-dark hover:text-white transition-colors flex items-center justify-center">
                <i class="fa-solid fa-xmark"></i>
            </button>
        </div>
        <div id="planModalBody" class="p-6 md:p-10"></div>
    </div>
</div>

<!-- IMAGE MODAL -->
<div id="imageModal" class="fixed inset-0 z-[110] hidden bg-black/90 p-4 md:p-8 flex items-center justify-center">
    <button onclick="closeImageModal()" aria-label="닫기" class="absolute top-5 right-5 z-20 w-12 h-12 border-2 border-white text-white hover:bg-yellowframe-yellow hover:text-black hover:border-black transition-colors">
        <i class="fa-solid fa-xmark text-xl"></i>
    </button>

    <button onclick="prevImage()" aria-label="이전 이미지" class="absolute left-3 md:left-6 top-1/2 -translate-y-1/2 z-20 w-12 h-12 border-2 border-white text-white hover:bg-yellowframe-yellow hover:text-black hover:border-black transition-colors">
        <i class="fa-solid fa-chevron-left"></i>
    </button>

    <button onclick="nextImage()" aria-label="다음 이미지" class="absolute right-3 md:right-6 top-1/2 -translate-y-1/2 z-20 w-12 h-12 border-2 border-white text-white hover:bg-yellowframe-yellow hover:text-black hover:border-black transition-colors">
        <i class="fa-solid fa-chevron-right"></i>
    </button>

    <div class="w-full h-full flex items-center justify-center">
        <div class="max-w-6xl max-h-full flex flex-col items-center">
            <img id="modalImage" src="" alt="" class="max-w-full max-h-[80vh] object-contain border-2 border-white">
            <div id="modalCaption" class="mt-4 bg-yellowframe-yellow border-2 border-yellowframe-dark px-4 py-2 font-mono text-xs font-black"></div>
        </div>
    </div>
</div>

<script>
    // 모바일 메뉴 토글
    const menuBtn = document.getElementById('menuBtn');
    const mobileMenu = document.getElementById('mobileMenu');

    menuBtn.addEventListener('click', () => {
        mobileMenu.classList.toggle('hidden');
    });

    mobileMenu.querySelectorAll('a').forEach(link => {
        link.addEventListener('click', () => mobileMenu.classList.add('hidden'));
    });

    // 커스텀 커서
    const cursor = document.getElementById('cursor');
    document.addEventListener('mousemove', e => {
        cursor.style.left = e.clientX + 'px';
        cursor.style.top = e.clientY + 'px';
    });

    document.querySelectorAll('a, button, [onclick]').forEach(el => {
        el.addEventListener('mouseenter', () => cursor.classList.add('hover'));
        el.addEventListener('mouseleave', () => cursor.classList.remove('hover'));
    });

    // 갤러리 데이터
    const galleryData = {
        character: [
            { src: 'https://lh3.googleusercontent.com/d/13qbdDvmqw4yxpk42hn9zEjYbGpdqoAov', title: 'CHARACTER #01' },
            { src: 'https://lh3.googleusercontent.com/d/1c8Cu2MGmm0bohhzw_W5jn1aeKxk7mBPU', title: 'CHARACTER #02' },
            { src: 'https://lh3.googleusercontent.com/d/1TCKegKyIa-fQWd4-uoIGjmqFduLzFhnD', title: 'CHARACTER #03' },
            { src: 'https://lh3.googleusercontent.com/d/1UDPoCEa3Dt4CywGTbHxZI9GZTNSDLqBg', title: 'CHARACTER #04' },
            { src: 'https://lh3.googleusercontent.com/d/15JbarnOmtB6w2A9s1-EQ4ldRXq6deH98', title: 'CHARACTER #05' }
        ],
        animating: [
            { src: 'https://lh3.googleusercontent.com/d/1QBDVOqRDhdWscY-9V1Qr09OETVv6w3dc', title: 'ANIMATION #01' },
            { src: 'https://lh3.googleusercontent.com/d/1RRU-LhcxPEWFOwaHwVI_XUXcBeTXTuUY', title: 'ANIMATION #02' },
            { src: 'https://lh3.googleusercontent.com/d/1mUnVyLHkuivFQUZTVELW_3oIw4tmULdl', title: 'ANIMATION #03' },
            { src: 'https://lh3.googleusercontent.com/d/1YQ9-GKC2bv_YnVMY9tPTJihENRykU6zE', title: 'ANIMATION #04' },
            { src: 'https://lh3.googleusercontent.com/d/1tJJJiFmCo9kRZWDCdJ1K8L4XVZV2Ak-e', title: 'ANIMATION #05' },
            { src: 'https://lh3.googleusercontent.com/d/1rsqfTtiPjN34ftUIRJMXHcwfAfDOrxwO', title: 'ANIMATION #06' }
        ],
        croquis: [
            { src: 'https://cdn.phototourl.com/free/2026-09-10-dcce84bb-b990-4b63-87ca-85afbc07950f.png', title: 'CROQUIS #01' },
            { src: 'https://cdn.phototourl.com/free/2026-09-10-8a31e455-5394-4f6a-8adf-9bb88c520208.png', title: 'CROQUIS #02' },
            { src: 'https://cdn.phototourl.com/free/2026-09-10-806e145f-eab8-40b9-8bc3-01bcec55aecd.png', title: 'CROQUIS #03' }
        ]
    };

    function switchCategory(category) {
        document.querySelectorAll('.category-content').forEach(el => el.classList.add('hidden'));
        document.getElementById('cat-' + category).classList.remove('hidden');

        document.querySelectorAll('.category-btn').forEach(btn => {
            if (btn.dataset.category === category) {
                btn.classList.remove('bg-yellowframe-card');
                btn.classList.add('bg-yellowframe-yellow');
            } else {
                btn.classList.remove('bg-yellowframe-yellow');
                btn.classList.add('bg-yellowframe-card');
            }
        });
    }

    let currentGallery = '';
    let currentIndex = 0;

    function openGalleryModal(category, index) {
        currentGallery = category;
        currentIndex = index;
        updateModalImage();
        document.getElementById('imageModal').classList.remove('hidden');
        document.body.style.overflow = 'hidden';
    }

    function updateModalImage() {
        const item = galleryData[currentGallery][currentIndex];
        document.getElementById('modalImage').src = item.src;
        document.getElementById('modalImage').alt = item.title;
        document.getElementById('modalCaption').textContent =
            `${item.title}   (${currentIndex + 1} / ${galleryData[currentGallery].length})`;
    }

    function nextImage() {
        currentIndex = (currentIndex + 1) % galleryData[currentGallery].length;
        updateModalImage();
    }

    function prevImage() {
        currentIndex = (currentIndex - 1 + galleryData[currentGallery].length) % galleryData[currentGallery].length;
        updateModalImage();
    }

    function closeImageModal() {
        document.getElementById('imageModal').classList.add('hidden');
        document.body.style.overflow = '';
    }

    const planData = {
        saerom: {
            title: 'PITCH DECK / 천재? 탐정 새롬',
            body: `
                <div class="space-y-8">
                    <div>
                        <p class="font-mono text-xs font-bold text-yellowframe-muted">01 / CONCEPT</p>
                        <h3 class="text-3xl md:text-4xl font-black mt-2">천재? 탐정 새롬</h3>
                        <p class="mt-4 leading-7">자칭 천재 탐정 새롬이가 산장에서 일어난 수상한 살인사건을 수사한다. 하지만 연이은 잘못된 추리에 용의자가 하나, 둘씩 죽어 나가며 수사는 미궁에 빠진다. 과연 새롬이는 범인을 잡을 수 있을까?</p>
                    </div>

                    <!-- BACKGROUND ART SECTION -->
                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-5 shadow-[4px_4px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-4">BACKGROUND ART (배경 이미지 5종)</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden md:col-span-2">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1LXumIbeHjTUz8aAS6bjZh3v52RWOoEMW" alt="배경 아트 #01" loading="lazy" class="w-full h-full object-cover">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">BACKGROUND #01</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1-ubKYR5xMFeHbg_6Y7gddcka5jLWEM9q" alt="배경 아트 #02" loading="lazy" class="w-full h-full object-cover">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">BACKGROUND #02</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/10mmvwCc_74_-p8z9xKCySAU3_JH7pjdO" alt="배경 아트 #03" loading="lazy" class="w-full h-full object-cover">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">BACKGROUND #03</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1YY2UZUxPaLMkFIcJlpzsltrRzqnw7R69" alt="배경 아트 #04" loading="lazy" class="w-full h-full object-cover">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">BACKGROUND #04</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/13Dc7NsLSV36nrh6JIwwbgEzuoD_hMs1a" alt="배경 아트 #05" loading="lazy" class="w-full h-full object-cover">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">BACKGROUND #05</div>
                            </div>
                        </div>
                    </div>

                    <!-- ANIMATION IN-BETWEEN CUTS -->
                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-5 shadow-[4px_4px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-4">ANIMATION / IN-BETWEEN CUTS (동화 움짤 5종)</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1CYIklhtcfj2EoGbcEZ1waY8ijcxf0IcA" alt="동화 움짤 #01" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">CUT #01</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1x41DDfgXecIDOK6X0P0e-tmHzQWHjYFq" alt="동화 움짤 #02" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">CUT #02</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1ecpLwwo0lZZajYKKdxHoTIiAH1KGpLXJ" alt="동화 움짤 #03" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">CUT #03</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1Ie4RV-lnIk12t1h2AsOR7tSpvFWGr3Ro" alt="동화 움짤 #04" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">CUT #04</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/16QYsW3Ugi2SiW900ZPqbKiR2K1IB5An0" alt="동화 움짤 #05" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">CUT #05</div>
                            </div>
                        </div>
                    </div>

                    <div class="grid md:grid-cols-2 gap-5">
                        <div class="border-2 border-yellowframe-dark p-5 bg-yellowframe-card">
                            <p class="font-mono text-xs font-bold text-yellowframe-muted">GENRE</p>
                            <p class="mt-2 text-sm font-bold">코미디 · 스릴러 · 공포 · 추리</p>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-5 bg-yellowframe-card">
                            <p class="font-mono text-xs font-bold text-yellowframe-muted">FORMAT</p>
                            <p class="mt-2 text-sm font-bold">단편 애니메이션 (상영시간 5분)</p>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-5 bg-yellowframe-card md:col-span-2">
                            <p class="font-mono text-xs font-bold text-yellowframe-muted">ROLE</p>
                            <p class="mt-2 text-sm font-bold">원동화 작화 · 배경 · 캐릭터 디자인 · 기획</p>
                        </div>
                    </div>
                </div>
            `
        },
        vicky: {
            title: 'PITCH DECK / 괴짜과학자 비키',
            body: `
                <div class="space-y-8">
                    <div>
                        <p class="font-mono text-xs font-bold text-yellowframe-muted">01 / LOGLINE</p>
                        <h3 class="text-3xl md:text-4xl font-black mt-2">괴짜과학자 비키</h3>
                        <p class="mt-4 leading-7 text-lg font-medium">음모론으로 뒤덮인 현대 사회에서 괴짜 과학자 ‘비키’는 지구 음모론을 증명할 수 있을 것인가?</p>
                    </div>

                    <!-- LIP-SYNC SECTION -->
                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-5 shadow-[4px_4px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-4">LIP-SYNC / 립싱크 (5종)</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1dYrvTygXIBc5PNWlceu0Rd7a2eXotvVe" alt="립싱크 움짤 #01" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">LIP-SYNC #01</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1FlLRTI3FEBk4RPc48OI5dTRBGtYO_Nwg" alt="립싱크 움짤 #02" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">LIP-SYNC #02</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1k32aVMMIg9y27nH4CggydZL1DYjcFYyf" alt="립싱크 움짤 #03" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">LIP-SYNC #03</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1jqtDmOPNxWycaHrTvuQUJC2Q2R8my4Kj" alt="립싱크 움짤 #04" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">LIP-SYNC #04</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1O3AIMtevQF_GH6qVqcMvn_w3GLQuypPF" alt="립싱크 움짤 #05" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">LIP-SYNC #05</div>
                            </div>
                        </div>
                    </div>

                    <!-- ANIMATION IN-BETWEEN CUTS SECTION -->
                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-5 shadow-[4px_4px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-4">ANIMATION / IN-BETWEEN CUTS (동화 움짤 8종)</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1T5oJ9b5pOL-sbcYyIdVmUqM5tc2kiVN7" alt="동화 움짤 #01" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">CUT #01</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1OK4tGmJL3Dok8BU7cPAMp7Y1oCNiEFEd" alt="동화 움짤 #02" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">CUT #02</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1AN4VS31l08W4dENZjZP51svneu8yre6B" alt="동화 움짤 #03" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">CUT #03</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1M72tG7KZgiWVzntbpnihrIJ7bl2BWBYf" alt="동화 움짤 #04" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">CUT #04</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1L6XQ0qA39Sj6Jy_Cf5rbyE1uTjnY-UM-" alt="동화 움짤 #05" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">CUT #05</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1xTv6nrZgM5xbzyTniKXAdxMEhupeqlI1" alt="동화 움짤 #06" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">CUT #06</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1ZE06yY3FhJi2nEtu_MNyCRHrTrTnxBAw" alt="동화 움짤 #07" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">CUT #07</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="aspect-video flex items-center justify-center bg-black/5">
                                    <img src="https://lh3.googleusercontent.com/d/1ylLc9s-tjJIF_YbTX1qdK8UqPmZjacBA" alt="동화 움짤 #08" loading="lazy" class="w-full h-full object-contain">
                                </div>
                                <div class="p-2 border-t-2 border-yellowframe-dark font-mono text-[11px] font-bold bg-yellowframe-card">CUT #08</div>
                            </div>
                        </div>
                    </div>

                    <div class="grid md:grid-cols-2 gap-5">
                        <div class="border-2 border-yellowframe-dark p-5 bg-yellowframe-card">
                            <p class="font-mono text-xs font-bold text-yellowframe-muted">GENRE</p>
                            <p class="mt-2 text-sm font-bold">SF, 코미디</p>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-5 bg-yellowframe-card">
                            <p class="font-mono text-xs font-bold text-yellowframe-muted">TARGET</p>
                            <p class="mt-2 text-sm font-bold">전연령</p>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-5 bg-yellowframe-card">
                            <p class="font-mono text-xs font-bold text-yellowframe-muted">RUNNING TIME / CATEGORY</p>
                            <p class="mt-2 text-sm font-bold">10분 이내 / TV 애니메이션 시리즈 에피소드</p>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-5 bg-yellowframe-card">
                            <p class="font-mono text-xs font-bold text-yellowframe-muted">ROLE</p>
                            <p class="mt-2 text-sm font-bold">원동화 작화</p>
                        </div>
                    </div>
                </div>
            `
        }
    };

    function openPlanModal(type) {
        const data = planData[type];
        document.getElementById('planModalTitle').textContent = data.title;
        document.getElementById('planModalBody').innerHTML = data.body;
        document.getElementById('planModal').classList.remove('hidden');
        document.body.style.overflow = 'hidden';
    }

    function closePlanModal() {
        document.getElementById('planModal').classList.add('hidden');
        document.body.style.overflow = '';
    }

    document.addEventListener('keydown', e => {
        if (!document.getElementById('imageModal').classList.contains('hidden')) {
            if (e.key === 'Escape') closeImageModal();
            if (e.key === 'ArrowRight') nextImage();
            if (e.key === 'ArrowLeft') prevImage();
        }

        if (!document.getElementById('planModal').classList.contains('hidden')) {
            if (e.key === 'Escape') closePlanModal();
        }
    });

    document.getElementById('imageModal').addEventListener('click', e => {
        if (e.target === e.currentTarget) closeImageModal();
    });

    document.getElementById('planModal').addEventListener('click', e => {
        if (e.target === e.currentTarget) closePlanModal();
    });
</script>

</body>
</html>
