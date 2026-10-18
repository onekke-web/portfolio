<!DOCTYPE html>

<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>메모지 MEMOJI | ANIMATION PORTFOLIO</title>

    <!-- Tailwind CSS (CDN) -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Fonts & Icons -->
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
                        frame: '4px 4px 0 #111111',
                        frameHover: '8px 8px 0 #111111'
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
            width: 100%;
        }
        ::selection { background: #FFE500; color: #111; }
        
        /* Custom Cursor */
        .custom-cursor {
            position: fixed;
            width: 16px;
            height: 16px;
            border: 2px solid #111;
            border-radius: 50%;
            pointer-events: none;
            z-index: 9999;
            transform: translate(-50%, -50%);
            transition: width .15s ease, height .15s ease, background-color .15s ease;
        }
        .custom-cursor.hover {
            width: 28px;
            height: 28px;
            background-color: #FFE500;
            opacity: 0.85;
        }
        @media (max-width: 768px) {
            .custom-cursor { display: none; }
        }

        .noise {
            position: fixed;
            inset: 0;
            pointer-events: none;
            opacity: .035;
            z-index: 40;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.8'/%3E%3C/svg%3E");
        }

        .yellow-marker {
            background: linear-gradient(transparent 55%, #FFE500 55%);
        }
        .modal-scroll::-webkit-scrollbar { width: 6px; }
        .modal-scroll::-webkit-scrollbar-thumb { background: #111; }

        
.max-w-7xl {
    width: calc(100% - 64px) !important;
    max-width: 1800px !important;
}

@media (min-width: 1600px) {
    .max-w-7xl {
        width: calc(100% - 96px) !important;
        max-width: 2100px !important;
    }
}

@media (min-width: 1920px) {
    .max-w-7xl {
        width: calc(100% - 120px) !important;
        max-width: 2200px !important;
    }
}

@media (min-width: 2400px) {
    .max-w-7xl {
        width: calc(100% - 160px) !important;
        max-width: 2300px !important;
    }
}    
    </style>

    <style id="memoji-redesign">
        :root {
            --memo-yellow: #ffd928;
            --memo-yellow-soft: #fff0a6;
            --memo-paper: #fffdf4;
            --memo-bg: #fff9e8;
            --memo-ink: #29271f;
            --memo-muted: #777264;
            --memo-line: #29271f;
        }
        body { background: var(--memo-bg); color: var(--memo-ink); }
        ::selection { background: var(--memo-yellow); color: var(--memo-ink); }
        .noise { opacity: .018; }
        header { background: rgba(255,249,232,.94) !important; border-bottom: 1px solid rgba(41,39,31,.22) !important; }
        header > div { min-height: 68px; }
        header a:first-child { letter-spacing: -.06em; font-size: 1.25rem; }
        header nav a { border-radius: 999px; padding: .55rem .8rem !important; transition: background .2s, transform .2s; }
        header nav a:hover { background: var(--memo-yellow) !important; transform: translateY(-2px); }
        #mobileMenu { background: var(--memo-paper) !important; border-color: rgba(41,39,31,.22) !important; }
        main#top > section:first-child { padding-top: 68px; background:
            radial-gradient(ellipse at 85% 18%, rgba(255,217,40,.32), transparent 34%),
            var(--memo-bg); }
        main#top > section:first-child .max-w-7xl { padding-top: clamp(3.5rem, 8vw, 7rem); padding-bottom: clamp(3.5rem, 8vw, 7rem); }
        main#top > section:first-child h1 { line-height: .88; letter-spacing: -.075em; }
        .text-yellowframe-yellow { color: var(--memo-yellow) !important; }
        .bg-yellowframe-yellow { background-color: var(--memo-yellow) !important; }
        .bg-yellowframe-bg { background-color: var(--memo-bg) !important; }
        .bg-yellowframe-card { background-color: var(--memo-paper) !important; }
        .text-yellowframe-muted { color: var(--memo-muted) !important; }
        .border-yellowframe-dark { border-color: var(--memo-line) !important; }
        .shadow-frame { box-shadow: 5px 5px 0 rgba(41,39,31,.14) !important; }
        .shadow-frameHover { box-shadow: 8px 8px 0 rgba(41,39,31,.2) !important; }
        #work, #teamwork, #gallery, #contact { position: relative; }
        #work .grid > div, #teamwork .grid > div, #gallery .grid > div {
            border-radius: 14px; overflow: hidden; box-shadow: 4px 5px 0 rgba(41,39,31,.09);
            transition: transform .22s ease, box-shadow .22s ease;
        }
        #work .grid > div:hover, #teamwork .grid > div:hover, #gallery .grid > div:hover {
            transform: translateY(-4px) rotate(-.25deg); box-shadow: 7px 9px 0 rgba(41,39,31,.12);
        }
        #process { background: #29271f !important; }
        #process .grid > div { border-radius: 12px; min-height: 132px; }
        #process .grid > div:hover { transform: translateY(-3px); }
        #about { background: var(--memo-yellow) !important; }
        #about .max-w-7xl { position: relative; }
        #about .max-w-7xl::after {
            content: "✳"; position: absolute; right: 2rem; top: 1.5rem;
            font-size: clamp(3rem, 7vw, 6rem); line-height: 1; opacity: .16; transform: rotate(12deg);
            pointer-events: none;
        }
        .category-btn { border-radius: 999px; padding: .65rem 1rem !important; }
        #planModal > div { border-radius: 16px; overflow: hidden; box-shadow: 8px 8px 0 rgba(0,0,0,.22); }
        #planModal > div > div:first-child { background: var(--memo-yellow) !important; }
        #imageModal button { border-radius: 999px; }
        footer { background: var(--memo-paper) !important; border-color: rgba(41,39,31,.22) !important; }
        .yellow-marker { background: linear-gradient(transparent 58%, var(--memo-yellow) 58%); }
        /* Paper-note motif */
        .note-chip {
            display: inline-block; background: var(--memo-yellow-soft); padding: .35rem .65rem;
            transform: rotate(-2deg); box-shadow: 2px 3px 0 rgba(41,39,31,.1);
        }
        @media (max-width: 768px) {
            header > div { min-height: 58px; }
            main#top > section:first-child { padding-top: 58px; }
            #about .max-w-7xl::after { right: 1rem; top: 1rem; font-size: 3rem; }
            #process .grid > div { min-height: 112px; }
        }
    </style>

</head>

<body>
<div class="noise"></div>
<div id="cursor" class="custom-cursor"></div>

<!-- HEADER -->
<header class="fixed top-0 left-0 right-0 z-50 bg-yellowframe-bg/95 backdrop-blur border-b-2 border-yellowframe-dark">
    <div class="max-w-7xl mx-auto px-5 md:px-8 h-14 flex items-center justify-between">
        <a href="#top" class="font-mono font-black text-lg tracking-tight">MEMOJI<span class="text-yellowframe-dark">.</span></a>

        <nav class="hidden md:flex items-center gap-6 font-mono text-xs font-bold">
            <a href="#work" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">WORK</a>
            <a href="#process" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">PROCESS</a>
            <a href="#gallery" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">GALLERY</a>
            <a href="#about" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">ABOUT</a>
            <a href="#contact" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">CONTACT</a>
        </nav>

        <button id="menuBtn" class="md:hidden text-lg p-1.5" aria-label="메뉴 열기/닫기">
            <i class="fa-solid fa-bars"></i>
        </button>
    </div>

    <!-- MOBILE MENU -->
    <div id="mobileMenu" class="hidden md:hidden border-t-2 border-yellowframe-dark bg-yellowframe-card">
        <nav class="flex flex-col font-mono font-bold text-xs">
            <a href="#work" class="px-5 py-3 border-b border-yellowframe-dark hover:bg-yellowframe-yellow">WORK</a>
            <a href="#process" class="px-5 py-3 border-b border-yellowframe-dark hover:bg-yellowframe-yellow">PROCESS</a>
            <a href="#gallery" class="px-5 py-3 border-b border-yellowframe-dark hover:bg-yellowframe-yellow">GALLERY</a>
            <a href="#about" class="px-5 py-3 border-b border-yellowframe-dark hover:bg-yellowframe-yellow">ABOUT</a>
            <a href="#contact" class="px-5 py-3 hover:bg-yellowframe-yellow">CONTACT</a>
        </nav>
    </div>
</header>

<main id="top" class="w-full">

<!-- HERO -->
<section class="pt-14 border-b-2 border-yellowframe-dark">
    <div class="max-w-7xl mx-auto w-full px-5 md:px-8 py-12 md:py-20">
        <div class="grid md:grid-cols-[1fr_auto] gap-8 md:gap-12 items-end">
            <div>
                <p class="font-mono text-xs font-bold mb-4"><span class="note-chip">✳ MEMOJI'S NOTE</span> &nbsp; 2D ANIMATOR / PORTFOLIO / 2026</p>
                <h1 class="text-[clamp(2.5rem,7vw,6rem)] leading-[0.9] font-black tracking-[-0.05em]">
                    MEMOJI'S<br>
                    <span class="text-yellowframe-yellow" style="-webkit-text-stroke:2px #111;">NOTEBOOK</span>
                </h1>
                <div class="mt-6 max-w-xl">
                    <p class="text-base md:text-lg font-bold leading-relaxed">
                        작은 메모에서 시작해,<br>
                        살아 움직이는 이야기를 그립니다.
                    </p>
                    <div class="mt-4 flex flex-wrap gap-2 font-mono text-xs font-bold">
                        <span class="border-2 border-yellowframe-dark bg-yellowframe-card px-2.5 py-1 shadow-[2px_2px_0_#111]">Character Acting</span>
                        <span class="border-2 border-yellowframe-dark bg-yellowframe-card px-2.5 py-1 shadow-[2px_2px_0_#111]">Key Animation</span>
                        <span class="border-2 border-yellowframe-dark bg-yellowframe-card px-2.5 py-1 shadow-[2px_2px_0_#111]">Storytelling</span>
                    </div>
                </div>
            </div>

            <div class="border-2 border-yellowframe-dark bg-yellowframe-yellow shadow-frame p-4 w-full md:w-64 lg:w-72">
                <div class="font-mono text-[10px] font-bold mb-4">CURRENT STATUS</div>
                <div class="font-mono text-3xl font-black">OPEN</div>
                <div class="font-mono text-xs font-bold mt-1">FOR WORK</div>
                <div class="border-t-2 border-yellowframe-dark mt-4 pt-3 text-xs font-bold">
                    2D ANIMATOR<br>
                    MEMOJI
                </div>
            </div>
        </div>
    </div>
</section>

<!-- PERSONAL PROJECTS -->
<section id="work" class="py-12 md:py-20">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <div class="flex items-end justify-between mb-8 md:mb-12">
            <div>
                <p class="font-mono text-xs font-bold mb-2">01 / PERSONAL PROJECTS</p>
                <h2 class="text-4xl md:text-6xl font-black tracking-tight">PERSONAL WORK<span class="text-yellowframe-yellow">.</span></h2>
            </div>
            <span class="hidden md:block font-mono text-xs font-bold">PERSONAL WORK (2025 — 2026)</span>
        </div>

        <div class="grid md:grid-cols-2 gap-6 md:gap-8">
            <!-- PERSONAL PROJECT 01 -->
            <div class="border-2 border-yellowframe-dark bg-yellowframe-card shadow-frame flex flex-col justify-between">
                <div>
                    <a href="https://youtu.be/quQ9GGipFd8?si=HsrWw-7NemKNSwds" target="_blank" rel="noopener noreferrer"
                       class="group block border-b-2 border-yellowframe-dark overflow-hidden relative">
                        <div class="aspect-video bg-yellowframe-dark relative w-full">
                            <img src="https://img.youtube.com/vi/quQ9GGipFd8/hqdefault.jpg"
                                 alt="개인 프로젝트 01 썸네일" loading="lazy" referrerpolicy="no-referrer"
                                 class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-12 h-12 rounded-full bg-yellowframe-yellow border-2 border-yellowframe-dark flex items-center justify-center shadow-frame group-hover:scale-110 transition-transform">
                                    <i class="fa-solid fa-play text-sm"></i>
                                </div>
                            </div>
                        </div>
                    </a>
                    <div class="p-5 md:p-6">
                        <div class="flex justify-between items-start gap-4">
                            <div>
                                <p class="font-mono text-xs font-bold">PERSONAL PROJECT 01</p>
                                <h3 class="text-xl md:text-2xl font-black mt-1">개인 프로젝트 01</h3>
                            </div>
                            <span class="font-mono text-[11px] border-2 border-yellowframe-dark px-2 py-0.5 bg-yellowframe-yellow font-bold">PERSONAL</span>
                        </div>
                        <p class="text-xs md:text-sm text-yellowframe-muted mt-3 leading-relaxed">개인 역량 강화를 위해 기획부터 제작까지 독자적으로 진행한 애니메이션 프로젝트 작업물입니다.</p>
                        
                        <div class="mt-4 pt-4 border-t-2 border-yellowframe-dark/20 grid grid-cols-3 gap-2 font-mono text-[11px]">
                            <div>
                                <span class="block text-yellowframe-muted font-bold">MY ROLE</span>
                                <span class="font-bold">전체 제작</span>
                            </div>
                            <div>
                                <span class="block text-yellowframe-muted font-bold">FORMAT</span>
                                <span class="font-bold">단편</span>
                            </div>
                            <div>
                                <span class="block text-yellowframe-muted font-bold">GENRE</span>
                                <span class="font-bold">애니메이션</span>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="p-5 md:p-6 pt-0">
                    <a href="https://youtu.be/quQ9GGipFd8?si=HsrWw-7NemKNSwds" target="_blank" rel="noopener noreferrer" class="block w-full text-center border-2 border-yellowframe-dark py-2.5 font-mono text-xs font-bold bg-yellowframe-bg hover:bg-yellowframe-yellow transition-colors">
                        WATCH VIDEO ON YOUTUBE →
                    </a>
                </div>
            </div>

            <!-- PERSONAL PROJECT 02 -->
            <div class="border-2 border-yellowframe-dark bg-yellowframe-card shadow-frame flex flex-col justify-between">
                <div>
                    <a href="https://youtu.be/ozSqsGvsF5I?si=my8Y81qXT9lfqCfQ" target="_blank" rel="noopener noreferrer"
                       class="group block border-b-2 border-yellowframe-dark overflow-hidden relative">
                        <div class="aspect-video bg-yellowframe-dark relative w-full">
                            <img src="https://img.youtube.com/vi/ozSqsGvsF5I/hqdefault.jpg"
                                 alt="개인 프로젝트 02 썸네일" loading="lazy" referrerpolicy="no-referrer"
                                 class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-12 h-12 rounded-full bg-yellowframe-yellow border-2 border-yellowframe-dark flex items-center justify-center shadow-frame group-hover:scale-110 transition-transform">
                                    <i class="fa-solid fa-play text-sm"></i>
                                </div>
                            </div>
                        </div>
                    </a>
                    <div class="p-5 md:p-6">
                        <div class="flex justify-between items-start gap-4">
                            <div>
                                <p class="font-mono text-xs font-bold">PERSONAL PROJECT 02</p>
                                <h3 class="text-xl md:text-2xl font-black mt-1">개인 프로젝트 02</h3>
                            </div>
                            <span class="font-mono text-[11px] border-2 border-yellowframe-dark px-2 py-0.5 bg-yellowframe-yellow font-bold">PERSONAL</span>
                        </div>
                        <p class="text-xs md:text-sm text-yellowframe-muted mt-3 leading-relaxed">독창적인 세계관과 캐릭터 액팅을 담아낸 개인 제작 애니메이션 포트폴리오입니다.</p>
                        
                        <div class="mt-4 pt-4 border-t-2 border-yellowframe-dark/20 grid grid-cols-3 gap-2 font-mono text-[11px]">
                            <div>
                                <span class="block text-yellowframe-muted font-bold">MY ROLE</span>
                                <span class="font-bold">전체 제작</span>
                            </div>
                            <div>
                                <span class="block text-yellowframe-muted font-bold">FORMAT</span>
                                <span class="font-bold">단편</span>
                            </div>
                            <div>
                                <span class="block text-yellowframe-muted font-bold">GENRE</span>
                                <span class="font-bold">애니메이션</span>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="p-5 md:p-6 pt-0">
                    <a href="https://youtu.be/ozSqsGvsF5I?si=my8Y81qXT9lfqCfQ" target="_blank" rel="noopener noreferrer" class="block w-full text-center border-2 border-yellowframe-dark py-2.5 font-mono text-xs font-bold bg-yellowframe-bg hover:bg-yellowframe-yellow transition-colors">
                        WATCH VIDEO ON YOUTUBE →
                    </a>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- TEAM PROJECTS -->
<section id="teamwork" class="py-12 md:py-20 bg-yellowframe-card/50 border-t-2 border-yellowframe-dark">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <div class="flex items-end justify-between mb-8 md:mb-12">
            <div>
                <p class="font-mono text-xs font-bold mb-2">02 / TEAM PROJECTS</p>
                <h2 class="text-4xl md:text-6xl font-black tracking-tight">TEAM WORK<span class="text-yellowframe-yellow">.</span></h2>
            </div>
            <span class="hidden md:block font-mono text-xs font-bold">TEAM COLLABORATION (2025 — 2026)</span>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6 md:gap-8">
            <!-- TEAM PROJECT 01 (Love ya!) -->
            <div class="border-2 border-yellowframe-dark bg-yellowframe-card shadow-frame flex flex-col justify-between">
                <div>
                    <a href="https://youtu.be/cjik4BfnpvI?si=9kz1EA25mTu78wGV" target="_blank" rel="noopener noreferrer"
                       class="group block border-b-2 border-yellowframe-dark overflow-hidden relative">
                        <div class="aspect-video bg-yellowframe-dark relative w-full">
                            <img src="https://img.youtube.com/vi/cjik4BfnpvI/hqdefault.jpg"
                                 alt="2학년 1학기 콘텐츠 프로젝트 썸네일" loading="lazy" referrerpolicy="no-referrer"
                                 class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-12 h-12 rounded-full bg-yellowframe-yellow border-2 border-yellowframe-dark flex items-center justify-center shadow-frame group-hover:scale-110 transition-transform">
                                    <i class="fa-solid fa-play text-sm"></i>
                                </div>
                            </div>
                        </div>
                    </a>
                    <div class="p-5 md:p-6">
                        <div class="flex justify-between items-start gap-4">
                            <div>
                                <p class="font-mono text-xs font-bold">2학년 1학기 콘텐츠 프로젝트</p>
                                <h3 class="text-xl md:text-2xl font-black mt-1">Love ya!</h3>
                            </div>
                            <span class="font-mono text-[11px] border-2 border-yellowframe-dark px-2 py-0.5 bg-yellowframe-yellow font-bold">TEAM</span>
                        </div>
                        <p class="text-xs md:text-sm text-yellowframe-muted mt-3 leading-relaxed">평행 우주 속 다양한 사랑 이야기. 총 다섯 파트로 구성되며, 여러 그림체의 주인공들이 지나가는 연출로 다중 우주를 표현했습니다.</p>
                        
                        <div class="mt-4 pt-4 border-t-2 border-yellowframe-dark/20 grid grid-cols-3 gap-2 font-mono text-[11px]">
                            <div>
                                <span class="block text-yellowframe-muted font-bold">MY ROLE</span>
                                <span class="font-bold">기획 및 제작</span>
                            </div>
                            <div>
                                <span class="block text-yellowframe-muted font-bold">FORMAT</span>
                                <span class="font-bold">단편 애니메이션</span>
                            </div>
                            <div>
                                <span class="block text-yellowframe-muted font-bold">GENRE</span>
                                <span class="font-bold">로맨스, 판타지</span>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="p-5 md:p-6 pt-0">
                    <button onclick="openPlanModal('contentProject')" class="w-full text-center border-2 border-yellowframe-dark py-2.5 font-mono text-xs font-bold bg-yellowframe-bg hover:bg-yellowframe-yellow transition-colors">
                        VIEW TEAM PITCH DECK →
                    </button>
                </div>
            </div>

            <!-- TEAM PROJECT 02 (천재? 탐정 새롬) -->
            <div class="border-2 border-yellowframe-dark bg-yellowframe-card shadow-frame flex flex-col justify-between">
                <div>
                    <a href="https://youtu.be/imD6U6dVes8?si=6TZcW1DbJxwKmnde" target="_blank" rel="noopener noreferrer"
                       class="group block border-b-2 border-yellowframe-dark overflow-hidden relative">
                        <div class="aspect-video bg-yellowframe-dark relative w-full">
                            <img src="https://img.youtube.com/vi/imD6U6dVes8/hqdefault.jpg"
                                 alt="천재? 탐정 새롬 썸네일" loading="lazy" referrerpolicy="no-referrer"
                                 class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-12 h-12 rounded-full bg-yellowframe-yellow border-2 border-yellowframe-dark flex items-center justify-center shadow-frame group-hover:scale-110 transition-transform">
                                    <i class="fa-solid fa-play text-sm"></i>
                                </div>
                            </div>
                        </div>
                    </a>
                    <div class="p-5 md:p-6">
                        <div class="flex justify-between items-start gap-4">
                            <div>
                                <p class="font-mono text-xs font-bold">TEAM PROJECT</p>
                                <h3 class="text-xl md:text-2xl font-black mt-1">천재? 탐정 새롬</h3>
                            </div>
                            <span class="font-mono text-[11px] border-2 border-yellowframe-dark px-2 py-0.5 bg-yellowframe-yellow font-bold">TEAM</span>
                        </div>
                        <p class="text-xs md:text-sm text-yellowframe-muted mt-3 leading-relaxed">팀 협업 기반의 단편 애니메이션. 자칭 천재 탐정 새롬이가 산장에서 일어난 수상한 사건을 수사하며 벌어지는 코미디 추리물입니다.</p>
                        
                        <div class="mt-4 pt-4 border-t-2 border-yellowframe-dark/20 grid grid-cols-3 gap-2 font-mono text-[11px]">
                            <div>
                                <span class="block text-yellowframe-muted font-bold">MY ROLE</span>
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
                <div class="p-5 md:p-6 pt-0">
                    <button onclick="openPlanModal('saerom')" class="w-full text-center border-2 border-yellowframe-dark py-2.5 font-mono text-xs font-bold bg-yellowframe-bg hover:bg-yellowframe-yellow transition-colors">
                        VIEW TEAM PITCH DECK →
                    </button>
                </div>
            </div>

            <!-- TEAM PROJECT 03 (happy family) - 새로 추가된 칸 -->
            <div class="border-2 border-yellowframe-dark bg-yellowframe-card shadow-frame flex flex-col justify-between">
                <div>
                    <a href="https://youtu.be/IGrS1fc0sq8?si=S0pVyoD9yZpM-QAh" target="_blank" rel="noopener noreferrer"
                       class="group block border-b-2 border-yellowframe-dark overflow-hidden relative">
                        <div class="aspect-video bg-yellowframe-dark relative w-full">
                            <img src="https://img.youtube.com/vi/IGrS1fc0sq8/hqdefault.jpg"
                                 alt="happy family 썸네일" loading="lazy" referrerpolicy="no-referrer"
                                 class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-12 h-12 rounded-full bg-yellowframe-yellow border-2 border-yellowframe-dark flex items-center justify-center shadow-frame group-hover:scale-110 transition-transform">
                                    <i class="fa-solid fa-play text-sm"></i>
                                </div>
                            </div>
                        </div>
                    </a>
                    <div class="p-5 md:p-6">
                        <div class="flex justify-between items-start gap-4">
                            <div>
                                <p class="font-mono text-xs font-bold">TEAM PROJECT</p>
                                <h3 class="text-xl md:text-2xl font-black mt-1">happy family (행복한 가족)</h3>
                            </div>
                            <span class="font-mono text-[11px] border-2 border-yellowframe-dark px-2 py-0.5 bg-yellowframe-yellow font-bold">TEAM</span>
                        </div>
                        <p class="text-xs md:text-sm text-yellowframe-muted mt-3 leading-relaxed">알 수 없는 현상으로 달이 커지며 미쳐가는 사람들 속에서 정신병원을 찾게 되는 심리 공포 게임 프로젝트입니다.</p>
                        
                        <div class="mt-4 pt-4 border-t-2 border-yellowframe-dark/20 grid grid-cols-3 gap-2 font-mono text-[11px]">
                            <div>
                                <span class="block text-yellowframe-muted font-bold">ENGINE</span>
                                <span class="font-bold">유니티</span>
                            </div>
                            <div>
                                <span class="block text-yellowframe-muted font-bold">FORMAT</span>
                                <span class="font-bold">PC 게임</span>
                            </div>
                            <div>
                                <span class="block text-yellowframe-muted font-bold">GENRE</span>
                                <span class="font-bold">심리, 공포</span>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="p-5 md:p-6 pt-0">
                    <button onclick="openPlanModal('happyFamily')" class="w-full text-center border-2 border-yellowframe-dark py-2.5 font-mono text-xs font-bold bg-yellowframe-bg hover:bg-yellowframe-yellow transition-colors">
                        VIEW TEAM PITCH DECK →
                    </button>
                </div>
            </div>

            <!-- TEAM PROJECT 04 (괴짜과학자 비키) - 아래쪽으로 이동 -->
            <div class="border-2 border-yellowframe-dark bg-yellowframe-card shadow-frame flex flex-col justify-between">
                <div>
                    <a href="https://youtu.be/494-k5M4vuY?si=MIRqNVYPDjmymfpr" target="_blank" rel="noopener noreferrer"
                       class="group block border-b-2 border-yellowframe-dark overflow-hidden relative">
                        <div class="aspect-video bg-yellowframe-dark relative w-full">
                            <img src="https://lh3.googleusercontent.com/d/1m__l6P90ifoH0b1IDoFtEL8qNTmgx-yY=w1600"
                                 alt="괴짜과학자 비키 썸네일" loading="lazy" referrerpolicy="no-referrer"
                                 class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1m__l6P90ifoH0b1IDoFtEL8qNTmgx-yY';this.onerror=function(){this.style.display='none'}">
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-12 h-12 rounded-full bg-yellowframe-yellow border-2 border-yellowframe-dark flex items-center justify-center shadow-frame group-hover:scale-110 transition-transform">
                                    <i class="fa-solid fa-play text-sm"></i>
                                </div>
                            </div>
                        </div>
                    </a>
                    <div class="p-5 md:p-6">
                        <div class="flex justify-between items-start gap-4">
                            <div>
                                <p class="font-mono text-xs font-bold">TEAM PROJECT</p>
                                <h3 class="text-xl md:text-2xl font-black mt-1">괴짜과학자 비키</h3>
                            </div>
                            <span class="font-mono text-[11px] border-2 border-yellowframe-dark px-2 py-0.5 bg-yellowframe-yellow font-bold">TEAM</span>
                        </div>
                        <p class="text-xs md:text-sm text-yellowframe-muted mt-3 leading-relaxed">팀 파이프라인으로 제작된 TV 시리즈 프로젝트. 괴짜 과학자 ‘비키’가 음모론을 증명해 나가는 코믹 SF 애니메이션입니다.</p>
                        
                        <div class="mt-4 pt-4 border-t-2 border-yellowframe-dark/20 grid grid-cols-3 gap-2 font-mono text-[11px]">
                            <div>
                                <span class="block text-yellowframe-muted font-bold">MY ROLE</span>
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
                <div class="p-5 md:p-6 pt-0">
                    <button onclick="openPlanModal('vicky')" class="w-full text-center border-2 border-yellowframe-dark py-2.5 font-mono text-xs font-bold bg-yellowframe-bg hover:bg-yellowframe-yellow transition-colors">
                        VIEW TEAM PITCH DECK →
                    </button>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- PROCESS -->
<section id="process" class="py-12 md:py-20 bg-yellowframe-dark text-yellowframe-bg">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <div class="mb-8 md:mb-12">
            <p class="font-mono text-xs font-bold mb-2 text-yellowframe-yellow">03 / PERSONAL WORKFLOW</p>
            <h2 class="text-4xl md:text-6xl font-black tracking-tight">PROCESS<span class="text-yellowframe-yellow">.</span></h2>
            <p class="mt-3 text-xs md:text-sm text-yellowframe-bg/70 max-w-2xl font-mono">
                개인 프로젝트 구상 시 아이디어 스케치부터 최종 프레임 완성까지 전 과정을 자체 수립한 6단계 파이프라인입니다. (STEP 클릭 시 상세 기획서 확인 가능)
            </p>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-6 gap-3 font-mono">
            <!-- STEP 01 -->
            <div onclick="openPlanModal('hero')" class="border-2 border-yellowframe-bg p-4 flex flex-col justify-between bg-yellowframe-dark hover:bg-yellowframe-yellow hover:text-yellowframe-dark transition-colors group cursor-pointer shadow-[2px_2px_0_#FFE500]">
                <span class="text-[10px] font-bold text-yellowframe-yellow group-hover:text-yellowframe-dark">STEP 01 (CLICK)</span>
                <div>
                    <span class="text-lg font-black block">개인 기획</span>
                    <span class="text-[10px] opacity-75 font-normal">컨셉 & 콘티</span>
                </div>
            </div>
            <div onclick="openPlanModal('character')" class="border-2 border-yellowframe-bg p-4 flex flex-col justify-between bg-yellowframe-dark hover:bg-yellowframe-yellow hover:text-yellowframe-dark transition-colors group cursor-pointer shadow-[2px_2px_0_#FFE500]">
                <span class="text-[10px] font-bold text-yellowframe-yellow group-hover:text-yellowframe-dark">STEP 02 (CLICK)</span>
                <div>
                    <span class="text-lg font-black block">캐릭터</span>
                    <span class="text-[10px] opacity-75 font-normal">디자인 & 턴어라운드</span>
                </div>
            </div>
            <div class="border-2 border-yellowframe-bg p-4 flex flex-col justify-between bg-yellowframe-dark hover:bg-yellowframe-yellow hover:text-yellowframe-dark transition-colors group">
                <span class="text-[10px] font-bold text-yellowframe-yellow group-hover:text-yellowframe-dark">STEP 03</span>
                <div>
                    <span class="text-lg font-black block">원화 작화</span>
                    <span class="text-[10px] opacity-75 font-normal">키 포즈 & 타이밍</span>
                </div>
            </div>
            <div class="border-2 border-yellowframe-bg p-4 flex flex-col justify-between bg-yellowframe-dark hover:bg-yellowframe-yellow hover:text-yellowframe-dark transition-colors group">
                <span class="text-[10px] font-bold text-yellowframe-yellow group-hover:text-yellowframe-dark">STEP 04</span>
                <div>
                    <span class="text-lg font-black block">동화 보정</span>
                    <span class="text-[10px] opacity-75 font-normal">인비트윈 & 클린업</span>
                </div>
            </div>
            <div class="border-2 border-yellowframe-bg p-4 flex flex-col justify-between bg-yellowframe-dark hover:bg-yellowframe-yellow hover:text-yellowframe-dark transition-colors group">
                <span class="text-[10px] font-bold text-yellowframe-yellow group-hover:text-yellowframe-dark">STEP 05</span>
                <div>
                    <span class="text-lg font-black block">움직임 검증</span>
                    <span class="text-[10px] opacity-75 font-normal">모션 체크 & 튜닝</span>
                </div>
            </div>
            <div class="border-2 border-yellowframe-yellow bg-yellowframe-yellow text-yellowframe-dark p-4 flex flex-col justify-between">
                <span class="text-[10px] font-bold">STEP 06</span>
                <div>
                    <span class="text-lg font-black block">최종 완성</span>
                    <span class="text-[10px] opacity-75 font-normal">컴포지팅 & 마스터링</span>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- GALLERY -->
<section id="gallery" class="py-12 md:py-20">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <div class="mb-8 md:mb-10">
            <p class="font-mono text-xs font-bold mb-2">04 / GALLERY</p>
            <h2 class="text-4xl md:text-6xl font-black tracking-tight">GALLERY<span class="text-yellowframe-yellow">.</span></h2>
        </div>

        <div class="flex flex-wrap gap-2 mb-8">
            <button onclick="switchCategory('character')" class="category-btn active font-mono text-xs font-bold border-2 border-yellowframe-dark px-3 py-1.5 bg-yellowframe-yellow" data-category="character">CHARACTER DESIGN</button>
            <button onclick="switchCategory('animating')" class="category-btn font-mono text-xs font-bold border-2 border-yellowframe-dark px-3 py-1.5 bg-yellowframe-card" data-category="animating">ANIMATION</button>
            <button onclick="switchCategory('croquis')" class="category-btn font-mono text-xs font-bold border-2 border-yellowframe-dark px-3 py-1.5 bg-yellowframe-card" data-category="croquis">CROQUIS / DRAWING</button>
        </div>

        <!-- CHARACTER DESIGN -->
        <div id="cat-character" class="category-content">
            <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4 md:gap-6">
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 0)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/13qbdDvmqw4yxpk42hn9zEjYbGpdqoAov=w1600" alt="캐릭터 일러스트 1" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=13qbdDvmqw4yxpk42hn9zEjYbGpdqoAov';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CHARACTER #01</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 1)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1c8Cu2MGmm0bohhzw_W5jn1aeKxk7mBPU=w1600" alt="캐릭터 일러스트 2" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1c8Cu2MGmm0bohhzw_W5jn1aeKxk7mBPU';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CHARACTER #02</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 2)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1TCKegKyIa-fQWd4-uoIGjmqFduLzFhnD=w1600" alt="캐릭터 일러스트 3" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1TCKegKyIa-fQWd4-uoIGjmqFduLzFhnD';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CHARACTER #03</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 3)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1UDPoCEa3Dt4CywGTbHxZI9GZTNSDLqBg=w1600" alt="캐릭터 일러스트 4" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1UDPoCEa3Dt4CywGTbHxZI9GZTNSDLqBg';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CHARACTER #04</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 4)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/15JbarnOmtB6w2A9s1-EQ4ldRXq6deH98=w1600" alt="캐릭터 일러스트 5" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=15JbarnOmtB6w2A9s1-EQ4ldRXq6deH98';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CHARACTER #05</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- ANIMATION -->
        <div id="cat-animating" class="category-content hidden">
            <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4 md:gap-6">
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 0)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1QBDVOqRDhdWscY-9V1Qr09OETVv6w3dc=w1600" alt="애니메이션 1" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1QBDVOqRDhdWscY-9V1Qr09OETVv6w3dc';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>ANIMATION #01</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 1)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1RRU-LhcxPEWFOwaHwVI_XUXcBeTXTuUY=w1600" alt="애니메이션 2" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1RRU-LhcxPEWFOwaHwVI_XUXcBeTXTuUY';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>ANIMATION #02</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 2)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1mUnVyLHkuivFQUZTVELW_3oIw4tmULdl=w1600" alt="애니메이션 3" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1mUnVyLHkuivFQUZTVELW_3oIw4tmULdl';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>ANIMATION #03</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 3)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1YQ9-GKC2bv_YnVMY9tPTJihENRykU6zE=w1600" alt="애니메이션 4" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1YQ9-GKC2bv_YnVMY9tPTJihENRykU6zE';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>ANIMATION #04</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 4)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1tJJJiFmCo9kRZWDCdJ1K8L4XVZV2Ak-e=w1600" alt="애니메이션 5" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1tJJJiFmCo9kRZWDCdJ1K8L4XVZV2Ak-e';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>ANIMATION #05</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 5)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://lh3.googleusercontent.com/d/1rsqfTtiPjN34ftUIRJMXHcwfAfDOrxwO=w1600" alt="애니메이션 6" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1rsqfTtiPjN34ftUIRJMXHcwfAfDOrxwO';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>ANIMATION #06</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- CROQUIS / DRAWING -->
        <div id="cat-croquis" class="category-content hidden">
            <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4 md:gap-6">
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('croquis', 0)">
                    <div class="aspect-square overflow-hidden border-b-2 border-yellowframe-dark">
                        <img src="https://lh3.googleusercontent.com/d/19Rxn6CBx42FHnHLxeIXBGxKVfVg7sHl5=w1600" alt="Croquis 1" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=19Rxn6CBx42FHnHLxeIXBGxKVfVg7sHl5';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CROQUIS #01</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('croquis', 1)">
                    <div class="aspect-square overflow-hidden border-b-2 border-yellowframe-dark">
                        <img src="https://lh3.googleusercontent.com/d/1j_pvHD2dAmLXyaDzeRL6eOOKJA0zmJS-=w1600" alt="Croquis 2" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1j_pvHD2dAmLXyaDzeRL6eOOKJA0zmJS-';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CROQUIS #02</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('croquis', 2)">
                    <div class="aspect-square overflow-hidden border-b-2 border-yellowframe-dark">
                        <img src="https://lh3.googleusercontent.com/d/1IXmwSbR9auNd5e6_4JvQtG3RlDOwf9JQ=w1600" alt="Croquis 3" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1IXmwSbR9auNd5e6_4JvQtG3RlDOwf9JQ';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CROQUIS #03</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('croquis', 3)">
                    <div class="aspect-square overflow-hidden border-b-2 border-yellowframe-dark">
                        <img src="https://lh3.googleusercontent.com/d/1uY9ME5MW2rB322OLegcmODWwMHgUq_L_=w1600" alt="Croquis 4" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1uY9ME5MW2rB322OLegcmODWwMHgUq_L_';this.onerror=function(){this.style.display='none'}">
                    </div>
                    <div class="p-2.5 font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CROQUIS #04</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ABOUT -->
<section id="about" class="py-12 md:py-20 bg-yellowframe-yellow border-y-2 border-yellowframe-dark">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <p class="font-mono text-xs font-bold mb-2">05 / ABOUT ME</p>
        <h2 class="text-4xl md:text-6xl font-black tracking-tight mb-8 md:mb-10">ABOUT<span class="text-yellowframe-dark">.</span></h2>

        <div class="grid md:grid-cols-[1fr_2fr] gap-8 md:gap-12">
            <div>
                <p class="text
