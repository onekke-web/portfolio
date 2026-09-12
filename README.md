<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>김고은 | ANIMATION PORTFOLIO</title>

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
            z-index: 9998;
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
</head>

<body>
<div class="noise"></div>
<div id="cursor" class="custom-cursor"></div>

<header class="fixed top-0 left-0 right-0 z-50 bg-yellowframe-bg/95 backdrop-blur border-b-2 border-yellowframe-dark">
    <div class="max-w-7xl mx-auto px-5 md:px-8 h-14 flex items-center justify-between">
        <a href="#top" class="font-mono font-black text-lg tracking-tight">GKEUN<span class="text-yellowframe-dark">.</span></a>

        <nav class="hidden md:flex items-center gap-6 font-mono text-xs font-bold">
            <a href="#work" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">WORK</a>
            <a href="#process" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">PROCESS</a>
            <a href="#gallery" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">GALLERY</a>
            <a href="#about" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">ABOUT</a>
            <a href="#contact" class="hover:bg-yellowframe-yellow px-2 py-1 transition-colors">CONTACT</a>
        </nav>

        <button id="menuBtn" class="md:hidden text-lg p-1.5 focus:outline-none" aria-label="메뉴 열기/닫기">
            <i class="fa-solid fa-bars"></i>
        </button>
    </div>

    <div id="mobileMenu" class="hidden md:hidden border-t-2 border-yellowframe-dark bg-yellowframe-card">
        <nav class="flex flex-col font-mono font-bold text-xs">
            <a href="#work" class="mobile-link px-5 py-3 border-b border-yellowframe-dark hover:bg-yellowframe-yellow">WORK</a>
            <a href="#process" class="mobile-link px-5 py-3 border-b border-yellowframe-dark hover:bg-yellowframe-yellow">PROCESS</a>
            <a href="#gallery" class="mobile-link px-5 py-3 border-b border-yellowframe-dark hover:bg-yellowframe-yellow">GALLERY</a>
            <a href="#about" class="mobile-link px-5 py-3 border-b border-yellowframe-dark hover:bg-yellowframe-yellow">ABOUT</a>
            <a href="#contact" class="mobile-link px-5 py-3 hover:bg-yellowframe-yellow">CONTACT</a>
        </nav>
    </div>
</header>

<main id="top" class="w-full">

<section class="pt-14 border-b-2 border-yellowframe-dark">
    <div class="max-w-7xl mx-auto w-full px-5 md:px-8 py-12 md:py-20">
        <div class="grid md:grid-cols-[1fr_auto] gap-8 md:gap-12 items-end">
            <div>
                <p class="font-mono text-xs font-bold mb-4">2D ANIMATOR / PORTFOLIO / 2026</p>
                <h1 class="text-[clamp(2.5rem,7vw,6rem)] leading-[0.9] font-black tracking-[-0.05em]">
                    FRAME BY<br>
                    <span class="text-yellowframe-yellow" style="-webkit-text-stroke:2px #111;">FRAME</span>
                </h1>
                <div class="mt-6 max-w-xl">
                    <p class="text-base md:text-lg font-bold leading-relaxed">
                        움직임을 그리고,<br>
                        이야기를 프레임 안에 담습니다.
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
                    KIM GOEUN
                </div>
            </div>
        </div>
    </div>
</section>

<section id="work" class="py-12 md:py-20">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <div class="flex items-end justify-between mb-8 md:mb-12">
            <div>
                <p class="font-mono text-xs font-bold mb-2">01 / TEAM PROJECTS</p>
                <h2 class="text-4xl md:text-6xl font-black tracking-tight">SELECTED WORK<span class="text-yellowframe-yellow">.</span></h2>
            </div>
            <span class="hidden md:block font-mono text-xs font-bold">TEAM WORK (2025 — 2026)</span>
        </div>

        <div class="grid md:grid-cols-2 gap-6 md:gap-8">
            <div class="border-2 border-yellowframe-dark bg-yellowframe-card shadow-frame flex flex-col justify-between">
                <div>
                    <a href="https://youtu.be/imD6U6dVes8?si=6TZcW1DbJxwKmnde" target="_blank" rel="noopener noreferrer"
                       class="group block border-b-2 border-yellowframe-dark overflow-hidden relative">
                        <div class="aspect-video bg-yellowframe-dark relative w-full">
                            <img src="https://cdn.phototourl.com/free/2026-09-10-b8988685-e6b7-4222-815c-c153b166a66a.png"
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
                                <p class="font-mono text-xs font-bold">TEAM PROJECT 01</p>
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

            <div class="border-2 border-yellowframe-dark bg-yellowframe-card shadow-frame flex flex-col justify-between">
                <div>
                    <a href="https://youtu.be/494-k5M4vuY?si=MIRqNVYPDjmymfpr" target="_blank" rel="noopener noreferrer"
                       class="group block border-b-2 border-yellowframe-dark overflow-hidden relative">
                        <div class="aspect-video bg-yellowframe-dark relative w-full">
                            <img src="https://cdn.phototourl.com/free/2026-09-10-1016abe6-3ec4-4246-b20f-bf31a2160e09.jpg"
                                 alt="괴짜과학자 비키 썸네일" loading="lazy" referrerpolicy="no-referrer"
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
                                <p class="font-mono text-xs font-bold">TEAM PROJECT 02</p>
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

<section id="process" class="py-12 md:py-20 bg-yellowframe-dark text-yellowframe-bg">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <div class="mb-8 md:mb-12">
            <p class="font-mono text-xs font-bold mb-2 text-yellowframe-yellow">02 / PERSONAL WORKFLOW</p>
            <h2 class="text-4xl md:text-6xl font-black tracking-tight">PROCESS<span class="text-yellowframe-yellow">.</span></h2>
            <p class="mt-3 text-xs md:text-sm text-yellowframe-bg/70 max-w-2xl font-mono">
                개인 프로젝트 구상 시 아이디어 스케치부터 최종 프레임 완성까지 전 과정을 자체 수립한 6단계 파이프라인입니다.
            </p>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-6 gap-3 font-mono">
            <div class="border-2 border-yellowframe-bg p-4 flex flex-col justify-between bg-yellowframe-dark hover:bg-yellowframe-yellow hover:text-yellowframe-dark transition-colors group">
                <span class="text-[10px] font-bold text-yellowframe-yellow group-hover:text-yellowframe-dark">STEP 01</span>
                <div>
                    <span class="text-lg font-black block">개인 기획</span>
                    <span class="text-[10px] opacity-75 font-normal">컨셉 & 콘티</span>
                </div>
            </div>
            <div class="border-2 border-yellowframe-bg p-4 flex flex-col justify-between bg-yellowframe-dark hover:bg-yellowframe-yellow hover:text-yellowframe-dark transition-colors group">
                <span class="text-[10px] font-bold text-yellowframe-yellow group-hover:text-yellowframe-dark">STEP 02</span>
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

<section id="gallery" class="py-12 md:py-20">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <div class="mb-8 md:mb-10">
            <p class="font-mono text-xs font-bold mb-2">03 / GALLERY</p>
            <h2 class="text-4xl md:text-6xl font-black tracking-tight">GALLERY<span class="text-yellowframe-yellow">.</span></h2>
        </div>

        <div class="flex flex-wrap gap-2 mb-8">
            <button onclick="switchCategory('character')" class="category-btn active font-mono text-xs font-bold border-2 border-yellowframe-dark px-3 py-1.5 bg-yellowframe-yellow" data-category="character">CHARACTER DESIGN</button>
            <button onclick="switchCategory('animating')" class="category-btn font-mono text-xs font-bold border-2 border-yellowframe-dark px-3 py-1.5 bg-yellowframe-card" data-category="animating">ANIMATION</button>
            <button onclick="switchCategory('croquis')" class="category-btn font-mono text-xs font-bold border-2 border-yellowframe-dark px-3 py-1.5 bg-yellowframe-card" data-category="croquis">CROQUIS / DRAWING</button>
        </div>

        <div id="cat-character" class="category-content">
            <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4 md:gap-6">
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 0)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-dcce84bb-b990-4b63-87ca-85afbc07950f.png" alt="캐릭터 일러스트 1" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CHARACTER #01</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 1)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-8a31e455-5394-4f6a-8adf-9bb88c520208.png" alt="캐릭터 일러스트 2" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CHARACTER #02</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 2)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-806e145f-eab8-40b9-8bc3-01bcec55aecd.png" alt="캐릭터 일러스트 3" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CHARACTER #03</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 3)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-b8988685-e6b7-4222-815c-c153b166a66a.png" alt="캐릭터 일러스트 4" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CHARACTER #04</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('character', 4)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-1016abe6-3ec4-4246-b20f-bf31a2160e09.jpg" alt="캐릭터 일러스트 5" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CHARACTER #05</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
            </div>
        </div>

        <div id="cat-animating" class="category-content hidden">
            <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4 md:gap-6">
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 0)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-8a31e455-5394-4f6a-8adf-9bb88c520208.png" alt="애니메이션 1" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>ANIMATION #01</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 1)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-dcce84bb-b990-4b63-87ca-85afbc07950f.png" alt="애니메이션 2" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>ANIMATION #02</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 2)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-806e145f-eab8-40b9-8bc3-01bcec55aecd.png" alt="애니메이션 3" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>ANIMATION #03</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 3)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-b8988685-e6b7-4222-815c-c153b166a66a.png" alt="애니메이션 4" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>ANIMATION #04</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 4)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-1016abe6-3ec4-4246-b20f-bf31a2160e09.jpg" alt="애니메이션 5" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>ANIMATION #05</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('animating', 5)">
                    <div class="aspect-square bg-yellowframe-bg overflow-hidden border-b-2 border-yellowframe-dark relative flex items-center justify-center">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-dcce84bb-b990-4b63-87ca-85afbc07950f.png" alt="애니메이션 6" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 bg-yellowframe-card font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>ANIMATION #06</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
            </div>
        </div>

        <div id="cat-croquis" class="category-content hidden">
            <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4 md:gap-6">
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('croquis', 0)">
                    <div class="aspect-square overflow-hidden border-b-2 border-yellowframe-dark">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-dcce84bb-b990-4b63-87ca-85afbc07950f.png" alt="Croquis 1" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CROQUIS #01</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('croquis', 1)">
                    <div class="aspect-square overflow-hidden border-b-2 border-yellowframe-dark">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-8a31e455-5394-4f6a-8adf-9bb88c520208.png" alt="Croquis 2" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CROQUIS #02</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
                <div class="bg-yellowframe-card border-2 border-yellowframe-dark shadow-frame hover:shadow-frameHover transition-all overflow-hidden group cursor-pointer" onclick="openGalleryModal('croquis', 2)">
                    <div class="aspect-square overflow-hidden border-b-2 border-yellowframe-dark">
                        <img src="https://cdn.phototourl.com/free/2026-09-10-806e145f-eab8-40b9-8bc3-01bcec55aecd.png" alt="Croquis 3" loading="lazy" referrerpolicy="no-referrer" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-2.5 font-mono text-[11px] font-bold flex items-center justify-between">
                        <span>CROQUIS #03</span>
                        <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<section id="about" class="py-12 md:py-20 bg-yellowframe-yellow border-y-2 border-yellowframe-dark">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <p class="font-mono text-xs font-bold mb-2">04 / ABOUT ME</p>
        <h2 class="text-4xl md:text-6xl font-black tracking-tight mb-8 md:mb-10">ABOUT<span class="text-yellowframe-dark">.</span></h2>
        <div class="grid md:grid-cols-[1fr_2fr] gap-8 md:gap-12">
            <div>
                <p class="text-lg md:text-xl font-black leading-snug">
                    안녕하세요, 프레임마다 생동감을 불어넣는 2D 애니메이터 김고은입니다.
                </p>
            </div>
            <div class="space-y-4 text-sm md:text-base leading-relaxed font-medium">
                <p>
                    캐릭터의 개성과 감정을 섬세하게 포착하여 가시적인 움직임으로 구현하는 것에 깊은 흥미를 느낍니다. 
                    단순히 그림을 그리는 것에 그치지 않고, 서사에 생명력을 부여하는 '액팅(Acting)' 중심의 작화를 지향합니다.
                </p>
                <p>
                    기획 단계부터 캐릭터 디자인, 원동화 작업에 이르기까지 애니메이션 제작 전반에 높은 이해도를 갖추고 있으며, 동료들과의 활발한 소통을 통해 최고의 결과물을 완성합니다.
                </p>
            </div>
        </div>
    </div>
</section>

<section id="contact" class="py-12 md:py-20">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <p class="font-mono text-xs font-bold mb-2">05 / CONTACT</p>
        <div class="grid md:grid-cols-[1fr_auto] gap-8 items-end">
            <div>
                <h2 class="text-4xl md:text-7xl font-black tracking-tight">LET'S<br><span class="yellow-marker">WORK TOGETHER.</span></h2>
                <p class="mt-4 text-xs md:text-sm leading-6 text-yellowframe-muted">작업 문의 및 포트폴리오 관련 연락은 아래 메일로 부탁드립니다.</p>
            </div>
            <div class="font-mono font-bold text-xs md:text-sm space-y-2 md:text-right">
                <a href="mailto:onekke@gmail.com" class="block hover:bg-yellowframe-yellow px-2 py-1 transition-colors">EMAIL: onekke@gmail.com</a>
                <a href="https://x.com/memo__paper_" target="_blank" rel="noopener noreferrer" class="block hover:bg-yellowframe-yellow px-2 py-1 transition-colors">TWITTER: @memo__paper_ →</a>
            </div>
        </div>
    </div>
</section>
</main>

<footer class="border-t-2 border-yellowframe-dark bg-yellowframe-card">
    <div class="max-w-7xl mx-auto px-5 md:px-8 py-5 flex flex-col md:flex-row justify-between gap-2 font-mono text-[10px] font-bold">
        <span>© 2026 KIM GOEUN</span>
        <span>ANIMATION PORTFOLIO / FRAME BY FRAME</span>
    </div>
</footer>

<div id="planModal" class="fixed inset-0 z-[100] hidden bg-black/70 p-4 md:p-6 flex items-center justify-center">
    <div class="max-w-3xl w-full max-h-[85vh] flex flex-col bg-yellowframe-bg border-2 border-yellowframe-dark shadow-frame">
        <div class="flex-none flex justify-between items-center bg-yellowframe-yellow border-b-2 border-yellowframe-dark p-3 md:p-4">
            <span id="planModalTitle" class="font-mono font-black text-xs md:text-sm">PITCH DECK</span>
            <button onclick="closePlanModal()" aria-label="닫기" class="w-7 h-7 md:w-8 md:h-8 border-2 border-yellowframe-dark bg-yellowframe-card hover:bg-yellowframe-dark hover:text-white transition-colors flex items-center justify-center">
                <i class="fa-solid fa-xmark text-sm"></i>
            </button>
        </div>
        <div id="planModalBody" class="p-4 md:p-8 overflow-y-auto modal-scroll"></div>
    </div>
</div>

<div id="imageModal" class="fixed inset-0 z-[110] hidden bg-black/90 p-4 flex items-center justify-center">
    <button onclick="closeImageModal()" aria-label="닫기" class="absolute top-4 right-4 z-20 w-10 h-10 border-2 border-white text-white hover:bg-yellowframe-yellow hover:text-black hover:border-black transition-colors flex items-center justify-center">
        <i class="fa-solid fa-xmark text-lg"></i>
    </button>
    <button onclick="prevImage()" aria-label="이전 이미지" class="absolute left-2 md:left-6 top-1/2 -translate-y-1/2 z-20 w-10 h-10 border-2 border-white text-white hover:bg-yellowframe-yellow hover:text-black hover:border-black transition-colors flex items-center justify-center">
        <i class="fa-solid fa-chevron-left"></i>
    </button>
    <button onclick="nextImage()" aria-label="다음 이미지" class="absolute right-2 md:right-6 top-1/2 -translate-y-1/2 z-20 w-10 h-10 border-2 border-white text-white hover:bg-yellowframe-yellow hover:text-black hover:border-black transition-colors flex items-center justify-center">
        <i class="fa-solid fa-chevron-right"></i>
    </button>
    <div class="w-full h-full flex items-center justify-center p-2">
        <div class="max-w-5xl max-h-[90vh] flex flex-col items-center justify-center">
            <img id="modalImage" src="" alt="" class="max-w-full max-h-[80vh] object-contain border-2 border-white">
            <p id="modalCaption" class="text-white font-mono text-xs mt-3"></p>
        </div>
    </div>
</div>

<script>
    // Custom Cursor
    const cursor = document.getElementById('cursor');
    window.addEventListener('mousemove', e => {
        cursor.style.left = e.clientX + 'px';
        cursor.style.top = e.clientY + 'px';
    });

    document.querySelectorAll('a, button, input, textarea').forEach(el => {
        el.addEventListener('mouseenter', () => cursor.classList.add('hover'));
        el.addEventListener('mouseleave', () => cursor.classList.remove('hover'));
    });

    // Mobile Menu Toggle Fix
    const menuBtn = document.getElementById('menuBtn');
    const mobileMenu = document.getElementById('mobileMenu');
    menuBtn.addEventListener('click', () => {
        mobileMenu.classList.toggle('hidden');
    });

    document.querySelectorAll('.mobile-link').forEach(link => {
        link.addEventListener('click', () => {
            mobileMenu.classList.add('hidden');
        });
    });

    // Gallery Category Switcher
    function switchCategory(category) {
        document.querySelectorAll('.category-content').forEach(el => el.classList.add('hidden'));
        document.getElementById('cat-' + category).classList.remove('hidden');

        document.querySelectorAll('.category-btn').forEach(btn => {
            btn.classList.remove('bg-yellowframe-yellow', 'active');
            btn.classList.add('bg-yellowframe-card');
            if(btn.dataset.category === category) {
                btn.classList.add('bg-yellowframe-yellow', 'active');
                btn.classList.remove('bg-yellowframe-card');
            }
        });
    }

    // Gallery Images Data Store
    const galleryData = {
        character: [
            { src: 'https://cdn.phototourl.com/free/2026-09-10-dcce84bb-b990-4b63-87ca-85afbc07950f.png', title: 'CHARACTER DESIGN #01' },
            { src: 'https://cdn.phototourl.com/free/2026-09-10-8a31e455-5394-4f6a-8adf-9bb88c520208.png', title: 'CHARACTER DESIGN #02' },
            { src: 'https://cdn.phototourl.com/free/2026-09-10-806e145f-eab8-40b9-8bc3-01bcec55aecd.png', title: 'CHARACTER DESIGN #03' },
            { src: 'https://cdn.phototourl.com/free/2026-09-10-b8988685-e6b7-4222-815c-c153b166a66a.png', title: 'CHARACTER DESIGN #04' },
            { src: 'https://cdn.phototourl.com/free/2026-09-10-1016abe6-3ec4-4246-b20f-bf31a2160e09.jpg', title: 'CHARACTER DESIGN #05' }
        ],
        animating: [
            { src: 'https://cdn.phototourl.com/free/2026-09-10-8a31e455-5394-4f6a-8adf-9bb88c520208.png', title: 'ANIMATION #01' },
            { src: 'https://cdn.phototourl.com/free/2026-09-10-dcce84bb-b990-4b63-87ca-85afbc07950f.png', title: 'ANIMATION #02' },
            { src: 'https://cdn.phototourl.com/free/2026-09-10-806e145f-eab8-40b9-8bc3-01bcec55aecd.png', title: 'ANIMATION #03' },
            { src: 'https://cdn.phototourl.com/free/2026-09-10-b8988685-e6b7-4222-815c-c153b166a66a.png', title: 'ANIMATION #04' },
            { src: 'https://cdn.phototourl.com/free/2026-09-10-1016abe6-3ec4-4246-b20f-bf31a2160e09.jpg', title: 'ANIMATION #05' },
            { src: 'https://cdn.phototourl.com/free/2026-09-10-dcce84bb-b990-4b63-87ca-85afbc07950f.png', title: 'ANIMATION #06' }
        ],
        croquis: [
            { src: 'https://cdn.phototourl.com/free/2026-09-10-dcce84bb-b990-4b63-87ca-85afbc07950f.png', title: 'CROQUIS #01' },
            { src: 'https://cdn.phototourl.com/free/2026-09-10-8a31e455-5394-4f6a-8adf-9bb88c520208.png', title: 'CROQUIS #02' },
            { src: 'https://cdn.phototourl.com/free/2026-09-10-806e145f-eab8-40b9-8bc3-01bcec55aecd.png', title: 'CROQUIS #03' }
        ]
    };

    let currentCategory = 'character';
    let currentIndex = 0;

    function openGalleryModal(category, index) {
        currentCategory = category;
        currentIndex = index;
        updateModalImage();
        document.getElementById('imageModal').classList.remove('hidden');
        document.body.style.overflow = 'hidden';
    }

    function closeImageModal() {
        document.getElementById('imageModal').classList.add('hidden');
        document.body.style.overflow = '';
    }

    function updateModalImage() {
        const item = galleryData[currentCategory][currentIndex];
        document.getElementById('modalImage').src = item.src;
        document.getElementById('modalCaption').textContent = item.title;
    }

    function nextImage() {
        const list = galleryData[currentCategory];
        currentIndex = (currentIndex + 1) % list.length;
        updateModalImage();
    }

    function prevImage() {
        const list = galleryData[currentCategory];
        currentIndex = (currentIndex - 1 + list.length) % list.length;
        updateModalImage();
    }

    // Pitch Deck Modal Data
    const planData = {
        saerom: {
            title: '천재? 탐정 새롬 - PITCH DECK & PRODUCTION NOTES',
            body: `
                <div class="space-y-6 font-mono text-xs md:text-sm">
                    <div class="border-2 border-yellowframe-dark p-4 bg-yellowframe-card shadow-frame">
                        <h4 class="font-black text-base mb-2">1. 프로젝트 개요</h4>
                        <p class="leading-relaxed text-yellowframe-muted">설산 속 고립된 산장에서 벌어지는 밀실 추리극을 코믹하게 풀어낸 단편 애니메이션입니다. 주인공 새롬의 허당미 넘치는 액팅과 빠른 템포의 연출이 특징입니다.</p>
                    </div>
                    <div class="border-2 border-yellowframe-dark p-4 bg-yellowframe-card shadow-frame">
                        <h4 class="font-black text-base mb-2">2. 담당 역할 (My Role)</h4>
                        <p class="leading-relaxed text-yellowframe-muted">메인 캐릭터 턴어라운드 및 주요 시퀀스 원·동화 작화 담당. 코믹한 표정 변화와 과장된 바디 액팅의 타이밍 조율에 집중했습니다.</p>
                    </div>
                </div>
            `
        },
        vicky: {
            title: '괴짜과학자 비키 - PITCH DECK & PRODUCTION NOTES',
            body: `
                <div class="space-y-6 font-mono text-xs md:text-sm">
                    <div class="border-2 border-yellowframe-dark p-4 bg-yellowframe-card shadow-frame">
                        <h4 class="font-black text-base mb-2">1. 프로젝트 개요</h4>
                        <p class="leading-relaxed text-yellowframe-muted">엉뚱한 발명품으로 음모론을 증명하려는 과학자 비키의 일상을 다룬 TV 시리즈 애니메이션 포맷입니다.</p>
                    </div>
                    <div class="border-2 border-yellowframe-dark p-4 bg-yellowframe-card shadow-frame">
                        <h4 class="font-black text-base mb-2">2. 담당 역할 (My Role)</h4>
                        <p class="leading-relaxed text-yellowframe-muted">시리즈 전반의 원동화 작화 파트 담당으로, 메카닉 요소와 캐릭터 간의 자연스러운 상호작용 움직임을 연구하여 작업했습니다.</p>
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
