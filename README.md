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

    <style id="memoji-ui-unification">
        :root {
            --ui-radius: 14px;
            --ui-border: 1.5px solid rgba(41,39,31,.78);
            --ui-shadow: 4px 4px 0 rgba(41,39,31,.12);
            --ui-shadow-hover: 7px 8px 0 rgba(41,39,31,.16);
            --ui-section-space: clamp(3.5rem, 7vw, 6.5rem);
        }

        body { line-height: 1.65; }
        .max-w-7xl {
            width: 100% !important;
            max-width: 1280px !important;
            margin-left: auto !important;
            margin-right: auto !important;
        }
        section[id] { scroll-margin-top: 84px; }
        #work, #teamwork, #process, #gallery, #about, #contact {
            padding-top: var(--ui-section-space);
            padding-bottom: var(--ui-section-space);
        }

        section[id] h2 {
            line-height: 1.05;
            letter-spacing: -.055em;
            overflow-wrap: anywhere;
        }
        section[id] > .max-w-7xl > div:first-child,
        #work .max-w-7xl > div:first-child,
        #teamwork .max-w-7xl > div:first-child {
            min-width: 0;
        }

        #work .grid > div,
        #teamwork .grid > div {
            min-width: 0;
            height: 100%;
            border: var(--ui-border);
            border-radius: var(--ui-radius);
            box-shadow: var(--ui-shadow);
            overflow: hidden;
            transition: transform .22s ease, box-shadow .22s ease;
        }
        #work .grid > div:hover,
        #teamwork .grid > div:hover {
            transform: translateY(-3px);
            box-shadow: var(--ui-shadow-hover);
        }
        #work .grid > div > div:first-child,
        #teamwork .grid > div > div:first-child {
            min-width: 0;
        }
        #work .grid > div p,
        #teamwork .grid > div p {
            overflow-wrap: anywhere;
        }
        #work .grid > div a.group,
        #teamwork .grid > div a.group {
            border-bottom-width: 1.5px;
        }

        button, a, [onclick] { -webkit-tap-highlight-color: transparent; }
        button:not(#menuBtn),
        #gallery .category-btn,
        #work a[href*="youtu"],
        #teamwork button,
        #contact a {
            border-radius: 8px;
        }
        #work .grid > div a.block.w-full,
        #teamwork .grid > div button {
            min-height: 44px;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: .75rem 1rem;
            line-height: 1.4;
        }
        #gallery .category-btn {
            border-width: 1.5px;
            transition: background-color .2s ease, transform .2s ease;
        }
        #gallery .category-btn:hover { transform: translateY(-1px); }
        #gallery .category-btn.active {
            background: var(--memo-yellow) !important;
        }

        #process .grid > div {
            min-width: 0;
            min-height: 140px;
            padding: clamp(.8rem, 1.5vw, 1.2rem);
            border: 1.5px solid rgba(255,253,244,.85);
            border-radius: 12px;
            box-shadow: 3px 3px 0 rgba(255,217,40,.65);
            transition: transform .2s ease, background-color .2s ease, color .2s ease;
        }
        #process .grid > div:last-child {
            border-color: var(--memo-yellow);
            box-shadow: 3px 3px 0 rgba(255,217,40,.35);
        }
        #process .grid > div span { overflow-wrap: anywhere; }

        #gallery .category-content .grid > div {
            min-width: 0;
            border: var(--ui-border);
            border-radius: 12px;
            box-shadow: var(--ui-shadow);
            transition: transform .2s ease, box-shadow .2s ease;
        }
        #gallery .category-content .grid > div:hover {
            transform: translateY(-3px);
            box-shadow: var(--ui-shadow-hover);
        }
        #gallery .category-content .grid > div > div:last-child {
            min-height: 40px;
        }

        #about { border-width: 1.5px; }
        #about .max-w-7xl > div { min-width: 0; }
        #contact { padding-top: clamp(3rem, 6vw, 5rem); padding-bottom: clamp(3rem, 6vw, 5rem); }
        footer { border-top-width: 1.5px !important; }
        footer .max-w-7xl { row-gap: .65rem; }

        #planModal { backdrop-filter: blur(5px); }
        #planModal > div {
            width: min(100%, 900px);
            max-height: min(88vh, 900px);
            border-radius: 16px;
            border-width: 1.5px;
            box-shadow: 8px 8px 0 rgba(0,0,0,.2);
        }
        #planModal > div > div:first-child {
            min-height: 58px;
            padding: .85rem 1.1rem;
        }
        #planModalBody {
            line-height: 1.8;
            overflow-wrap: anywhere;
        }
        #planModalBody h3,
        #planModalBody h4 { line-height: 1.3; }
        #planModalBody img { max-width: 100%; }
        #imageModal { backdrop-filter: blur(4px); }
        #imageModal #modalCaption { text-align: center; }

        a:focus-visible, button:focus-visible, [onclick]:focus-visible {
            outline: 3px solid var(--memo-yellow);
            outline-offset: 3px;
        }

        @media (min-width: 769px) {
            #work .grid > div,
            #teamwork .grid > div { display: flex; flex-direction: column; }
            #work .grid > div > div:last-child,
            #teamwork .grid > div > div:last-child { margin-top: auto; }
        }
        @media (max-width: 768px) {
            .max-w-7xl { width: 100% !important; }
            #work, #teamwork, #process, #gallery, #about, #contact {
                padding-top: 3.25rem;
                padding-bottom: 3.25rem;
            }
            section[id] { scroll-margin-top: 68px; }
            #work .grid, #teamwork .grid { gap: 1.1rem; }
            #process .grid > div { min-height: 112px; }
            #planModal { padding: .75rem; }
            #planModal > div { max-height: 90vh; }
            #planModalBody { padding: 1rem; }
            #about .max-w-7xl::after { opacity: .1; }
        }
        @media (prefers-reduced-motion: reduce) {
            html { scroll-behavior: auto; }
            *, *::before, *::after {
                animation-duration: .01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: .01ms !important;
            }
        }
    </style>

    <style id="teamwork-layout-unification">
        #teamwork .grid {
            align-items: stretch;
            grid-auto-rows: 1fr;
        }
        #teamwork .grid > div {
            display: flex;
            flex-direction: column;
            height: 100%;
            min-width: 0;
        }
        #teamwork .grid > div > div:first-child {
            display: flex;
            flex: 1 1 auto;
            flex-direction: column;
            min-width: 0;
        }
        #teamwork .grid > div > div:first-child > a {
            display: block;
            flex: 0 0 auto;
            width: 100%;
            aspect-ratio: 16 / 9;
        }
        #teamwork .grid > div > div:first-child > a > div {
            width: 100%;
            height: 100%;
            aspect-ratio: 16 / 9;
        }
        #teamwork .grid > div > div:first-child > a img {
            display: block;
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        #teamwork .grid > div > div:first-child > div:last-child {
            display: flex;
            flex: 1 1 auto;
            flex-direction: column;
        }
        #teamwork .grid > div > div:first-child > div:last-child > p:first-of-type + h3 {
            min-height: 2.6em;
            overflow-wrap: anywhere;
        }
        #teamwork .grid > div > div:first-child > div:last-child > p:nth-of-type(2) {
            flex: 1 0 auto;
        }
        #teamwork .grid > div > div:first-child > div:last-child > div:last-child {
            margin-top: auto;
            align-items: start;
        }
        #teamwork .grid > div > div:last-child {
            margin-top: auto;
            padding-top: .75rem;
        }
        #teamwork .grid > div > div:last-child button {
            min-height: 46px;
            border-width: 1.5px;
            font-size: .72rem;
            letter-spacing: .025em;
        }

        #planModalBody {
            width: 100%;
            max-width: 100%;
        }
        #planModalBody > div {
            width: 100%;
            max-width: 100%;
        }
        #planModalBody > div > div:first-child {
            padding-bottom: 1.25rem;
            border-bottom: 1px solid rgba(41,39,31,.18);
        }
        #planModalBody > div > div:first-child h3 {
            font-size: clamp(1.55rem, 3vw, 2.15rem);
            letter-spacing: -.04em;
        }
        #planModalBody > div > div:not(:first-child) {
            border-radius: 10px;
            border-width: 1.5px;
            box-shadow: 3px 3px 0 rgba(41,39,31,.10);
        }
        #planModalBody img {
            display: block;
            width: 100%;
            height: clamp(210px, 30vw, 340px);
            object-fit: contain;
            object-position: center;
            background: rgba(41,39,31,.035);
        }
        #planModalBody .grid > div {
            min-width: 0;
            border-radius: 8px;
            overflow: hidden;
        }
        #planModalBody .grid > div > div:first-child:has(img) {
            display: flex;
            align-items: center;
            justify-content: center;
            min-height: 210px;
            overflow: hidden;
            background: rgba(41,39,31,.035);
        }
        #planModalBody .grid > div > div:first-child:has(img) img {
            flex: 0 0 auto;
        }
        #planModalBody .grid > div > div:last-child:not(:first-child) {
            min-height: 34px;
        }
        #planModalBody p,
        #planModalBody li,
        #planModalBody span { overflow-wrap: anywhere; }
        #planModalBody .grid { align-items: stretch; }
        #planModalBody .grid > div:has(> span:first-child) {
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        @media (max-width: 767px) {
            #teamwork .grid { grid-auto-rows: auto; }
            #teamwork .grid > div > div:first-child > div:last-child > p:first-of-type + h3 {
                min-height: 0;
            }
            #planModalBody img { height: clamp(190px, 58vw, 280px); }
            #planModalBody > div { gap: 1rem; }
            #planModalBody > div > div:not(:first-child) { padding: .9rem; }
        }
        @media (prefers-reduced-motion: reduce) {
            #teamwork .grid > div,
            #teamwork .grid > div img { transition: none !important; }
        }
    </style>


<style id="memoji-notebook-redesign">
:root{
 --memo-yellow:#F2DA88; --memo-yellow-soft:#f8edc6;
 --memo-paper:#fffdf8; --memo-bg:#f7f5ef; --memo-ink:#184c45;
 --memo-muted:#647873; --memo-line:#184c45;
 --memo-lilac:#C9B8E9; --memo-green:#184c45;
 --ui-radius:5px; --ui-border:1px solid rgba(24,76,69,.22);
 --ui-shadow:0 8px 24px rgba(24,76,69,.08);
 --ui-shadow-hover:0 14px 32px rgba(24,76,69,.15);
 --ui-section-space:clamp(4rem,8vw,7rem);
}
html{scroll-padding-top:88px}
body{background:var(--memo-bg)!important;color:var(--memo-green)!important;font-family:'Noto Sans KR',sans-serif;line-height:1.7}
::selection{background:var(--memo-yellow);color:var(--memo-green)}
.noise{opacity:.012}
.custom-cursor{border-color:var(--memo-green)}
.custom-cursor.hover{background:var(--memo-yellow)}
.max-w-7xl{width:min(100% - 64px,1320px)!important;max-width:1320px!important;margin-inline:auto!important}
header{background:rgba(247,245,239,.92)!important;border:0!important;border-bottom:1px solid rgba(24,76,69,.15)!important;box-shadow:0 4px 18px rgba(24,76,69,.04);backdrop-filter:blur(16px)}
header>div{min-height:76px!important}
header a:first-child{color:var(--memo-green)!important;font-size:1.35rem;letter-spacing:-.07em}
header a:first-child span{color:var(--memo-lilac)!important}
header nav a{color:var(--memo-green)!important;border-radius:3px;padding:.55rem .85rem!important;letter-spacing:.08em;font-size:.7rem;transition:all .2s}
header nav a:hover{background:var(--memo-lilac)!important;transform:translateY(-2px)}
#mobileMenu{background:var(--memo-paper)!important;border-color:#d8dfd9!important}
#mobileMenu a:hover{background:var(--memo-lilac)!important}
main#top>section:first-child{padding-top:76px;background:var(--memo-green)!important;color:var(--memo-paper)!important;border:0!important;position:relative;overflow:hidden}
main#top>section:first-child:before{content:"";position:absolute;inset:0;opacity:.1;background-image:radial-gradient(var(--memo-yellow) .7px,transparent .7px);background-size:17px 17px;pointer-events:none}
main#top>section:first-child .max-w-7xl{position:relative;padding-top:clamp(5rem,10vw,9rem)!important;padding-bottom:clamp(5rem,10vw,9rem)!important}
main#top>section:first-child h1{line-height:.92;letter-spacing:-.075em;color:var(--memo-paper)}
main#top>section:first-child h1 span{color:var(--memo-yellow)!important;-webkit-text-stroke:0!important}
main#top>section:first-child p{color:inherit}
.note-chip{background:var(--memo-yellow-soft);color:var(--memo-green);border:1px solid rgba(24,76,69,.12);box-shadow:3px 4px 0 rgba(0,0,0,.12);padding:.45rem .75rem;transform:rotate(-2deg);display:inline-block}
main#top>section:first-child .grid>div:last-child{background:var(--memo-lilac)!important;color:var(--memo-green)!important;border:0!important;border-radius:3px!important;box-shadow:8px 8px 0 var(--memo-yellow)!important;transform:rotate(2deg);padding:1.5rem!important}
main#top>section:first-child .grid>div:last-child *{color:var(--memo-green)!important}
section[id]{scroll-margin-top:90px}
#work,#teamwork,#process,#gallery,#about,#contact{padding-top:var(--ui-section-space)!important;padding-bottom:var(--ui-section-space)!important}
section[id] h2{color:var(--memo-green);letter-spacing:-.065em;line-height:1}
.text-yellowframe-yellow{color:var(--memo-lilac)!important}
.bg-yellowframe-yellow{background-color:var(--memo-yellow)!important}
.bg-yellowframe-bg{background-color:#f7f5ef!important}
.bg-yellowframe-card{background-color:var(--memo-paper)!important}
.text-yellowframe-muted{color:var(--memo-muted)!important}
.border-yellowframe-dark{border-color:rgba(24,76,69,.28)!important}
.bg-yellowframe-dark{background-color:var(--memo-green)!important}
.text-yellowframe-dark{color:var(--memo-green)!important}
.text-yellowframe-bg{color:var(--memo-paper)!important}
.border-yellowframe-bg{border-color:rgba(255,253,248,.75)!important}
.shadow-frame{box-shadow:4px 5px 0 rgba(201,184,233,.75)!important}
.shadow-frameHover{box-shadow:7px 9px 0 rgba(201,184,233,.85)!important}
#work,#gallery{background:var(--memo-bg)}
#teamwork{background:#eeece5!important;border:0!important}
#work .grid>div,#teamwork .grid>div,#gallery .category-content .grid>div{
 border:1px solid rgba(24,76,69,.18)!important;border-radius:5px!important;
 background:var(--memo-paper)!important;box-shadow:5px 6px 0 rgba(201,184,233,.62)!important;
 transition:transform .24s ease,box-shadow .24s ease;
}
#work .grid>div:hover,#teamwork .grid>div:hover,#gallery .category-content .grid>div:hover{transform:translateY(-5px) rotate(-.2deg);box-shadow:8px 10px 0 rgba(201,184,233,.75)!important}
#work .grid>div img,#teamwork .grid>div img{filter:saturate(.96)}
#work .grid>div>div:first-child>a,#teamwork .grid>div>div:first-child>a{border-color:rgba(24,76,69,.16)!important}
#work .grid>div a.block.w-full,#teamwork .grid>div button{border:1px solid var(--memo-green)!important;border-radius:3px!important;background:transparent!important;color:var(--memo-green)!important;font-size:.72rem;letter-spacing:.03em;transition:all .2s}
#work .grid>div a.block.w-full:hover,#teamwork .grid>div button:hover{background:var(--memo-yellow)!important}
#process{background:var(--memo-green)!important;color:var(--memo-paper)!important;position:relative;overflow:hidden}
#process:after{content:"MEMO / 01";position:absolute;right:4vw;top:2rem;color:rgba(242,218,136,.12);font:800 clamp(2rem,6vw,5rem) 'JetBrains Mono',monospace;letter-spacing:-.08em;pointer-events:none}
#process h2{color:var(--memo-paper)!important}
#process .grid>div{border:1px solid rgba(255,253,248,.4)!important;border-radius:4px!important;box-shadow:4px 4px 0 rgba(201,184,233,.55)!important;min-height:150px!important;padding:1.2rem!important;background:rgba(255,255,255,.025)!important;transition:all .2s}
#process .grid>div:hover{background:var(--memo-lilac)!important;color:var(--memo-green)!important;transform:translateY(-4px)}
#process .grid>div:hover span{color:var(--memo-green)!important}
#process .grid>div:last-child{background:var(--memo-yellow)!important;color:var(--memo-green)!important;border-color:var(--memo-yellow)!important;box-shadow:4px 4px 0 rgba(255,253,248,.4)!important}
#process .grid>div:last-child span{color:var(--memo-green)!important}
#gallery .category-btn{border:1px solid rgba(24,76,69,.35)!important;border-radius:3px!important;padding:.7rem 1rem!important;background:var(--memo-paper)!important;color:var(--memo-green)!important}
#gallery .category-btn.active,#gallery .category-btn:hover{background:var(--memo-lilac)!important;color:var(--memo-green)!important}
#gallery .category-content .grid>div{overflow:hidden}
#gallery .category-content .grid>div>div:last-child{background:var(--memo-paper)!important;color:var(--memo-green)!important;border-color:rgba(24,76,69,.15)!important}
#about{background:var(--memo-yellow)!important;color:var(--memo-green)!important;border:0!important;position:relative}
#about h2,#about h3,#about p,#about span{color:var(--memo-green)!important}
#about .max-w-7xl:after{content:"✳";color:var(--memo-green);opacity:.12}
#contact{background:var(--memo-lilac)!important;color:var(--memo-green)!important}
#contact h2,#contact p,#contact a{color:var(--memo-green)!important}
#contact a{border:1px solid rgba(24,76,69,.35)!important;background:rgba(255,253,248,.35);padding:.75rem 1rem;border-radius:3px!important;transition:background .2s}
#contact a:hover{background:var(--memo-yellow)!important}
footer{background:var(--memo-paper)!important;color:var(--memo-green)!important;border-color:rgba(24,76,69,.2)!important}
footer *{color:var(--memo-green)!important}
#planModal{backdrop-filter:blur(8px)}
#planModal>div{border:1px solid rgba(24,76,69,.2)!important;border-radius:5px!important;box-shadow:8px 8px 0 rgba(201,184,233,.8)!important}
#planModal>div>div:first-child{background:var(--memo-green)!important;color:var(--memo-paper)!important}
#planModal button{border-radius:3px}
#imageModal{backdrop-filter:blur(8px)}
#imageModal button{border-radius:3px}
a:focus-visible,button:focus-visible,[onclick]:focus-visible{outline:3px solid var(--memo-lilac)!important;outline-offset:3px}
@media(max-width:768px){
 .max-w-7xl{width:calc(100% - 32px)!important}
 header>div{min-height:62px!important}
 main#top>section:first-child{padding-top:62px}
 main#top>section:first-child .max-w-7xl{padding-top:4.5rem!important;padding-bottom:4.5rem!important}
 main#top>section:first-child .grid>div:last-child{max-width:240px}
 #work,#teamwork,#process,#gallery,#about,#contact{padding-top:3.75rem!important;padding-bottom:3.75rem!important}
 #process .grid>div{min-height:115px!important}
 #process:after{top:1rem;right:1rem;font-size:2rem}
}
@media(prefers-reduced-motion:reduce){*,*:before,*:after{scroll-behavior:auto!important;transition:none!important;animation:none!important}}
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
                                <span class="font-bold">3파트(인어공주) 제작</span>
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

            <!-- TEAM PROJECT 03 (happy family) -->
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

            <!-- TEAM PROJECT 04 (괴짜과학자 비키) -->
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
                <p class="text-lg md:text-xl font-black leading-snug">
                    안녕하세요, 작은 아이디어를 움직임으로 기록하는 2D 애니메이터 메모지입니다.
                </p>
            </div>
            <div class="space-y-4 text-sm md:text-base leading-relaxed font-medium">
                <p>
                    캐릭터의 개성과 감정을 섬세하게 포착하여 가시적인 움직임으로 구현하는 것에 깊은 흥미를 느낍니다. 
                    단순히 그림을 그리는 것에 그치지 않고, 서사에 생명력을 부여하는 '액팅(Acting)' 중심의 작화를 지향합니다.
                </p>
                <p>
                    기획 단계부터 캐릭터 디자인, 원동화 작업에 이르기까지 애니메이션 제작 전반에 높은 이해도를 갖추고 있으며, 
                    동료들과의 활발한 소통을 통해 최고의 결과물을 완성합니다.
                </p>
            </div>
        </div>
    </div>
</section>

<!-- CONTACT -->
<section id="contact" class="py-12 md:py-20">
    <div class="max-w-7xl mx-auto px-5 md:px-8">
        <p class="font-mono text-xs font-bold mb-2">06 / CONTACT</p>
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
        <span>© 2026 MEMOJI</span>
        <span>ANIMATION PORTFOLIO / NOTES IN MOTION</span>
    </div>
</footer>

<!-- PLAN MODAL -->
<div id="planModal" role="dialog" aria-modal="true" aria-labelledby="planModalTitle" class="fixed inset-0 z-[10000] hidden bg-black/70 p-4 md:p-6 flex items-center justify-center">
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

<!-- IMAGE MODAL -->
<div id="imageModal" role="dialog" aria-modal="true" aria-labelledby="modalCaption" class="fixed inset-0 z-[10001] hidden bg-black/90 p-4 flex items-center justify-center">
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
            <img id="modalImage" src="" alt="" class="max-w-full max-h-[82vh] object-contain border-2 border-white">
            <div id="modalCaption" class="mt-3 bg-yellowframe-yellow border-2 border-yellowframe-dark px-3 py-1 font-mono text-xs font-black"></div>
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
            { src: 'https://lh3.googleusercontent.com/d/13qbdDvmqw4yxpk42hn9zEjYbGpdqoAov=w1600', title: 'CHARACTER #01' },
            { src: 'https://lh3.googleusercontent.com/d/1c8Cu2MGmm0bohhzw_W5jn1aeKxk7mBPU=w1600', title: 'CHARACTER #02' },
            { src: 'https://lh3.googleusercontent.com/d/1TCKegKyIa-fQWd4-uoIGjmqFduLzFhnD=w1600', title: 'CHARACTER #03' },
            { src: 'https://lh3.googleusercontent.com/d/1UDPoCEa3Dt4CywGTbHxZI9GZTNSDLqBg=w1600', title: 'CHARACTER #04' },
            { src: 'https://lh3.googleusercontent.com/d/15JbarnOmtB6w2A9s1-EQ4ldRXq6deH98=w1600', title: 'CHARACTER #05' }
        ],
        animating: [
            { src: 'https://lh3.googleusercontent.com/d/1QBDVOqRDhdWscY-9V1Qr09OETVv6w3dc=w1600', title: 'ANIMATION #01' },
            { src: 'https://lh3.googleusercontent.com/d/1RRU-LhcxPEWFOwaHwVI_XUXcBeTXTuUY=w1600', title: 'ANIMATION #02' },
            { src: 'https://lh3.googleusercontent.com/d/1mUnVyLHkuivFQUZTVELW_3oIw4tmULdl=w1600', title: 'ANIMATION #03' },
            { src: 'https://lh3.googleusercontent.com/d/1YQ9-GKC2bv_YnVMY9tPTJihENRykU6zE=w1600', title: 'ANIMATION #04' },
            { src: 'https://lh3.googleusercontent.com/d/1tJJJiFmCo9kRZWDCdJ1K8L4XVZV2Ak-e=w1600', title: 'ANIMATION #05' },
            { src: 'https://lh3.googleusercontent.com/d/1rsqfTtiPjN34ftUIRJMXHcwfAfDOrxwO=w1600', title: 'ANIMATION #06' }
        ],
        croquis: [
            { src: 'https://lh3.googleusercontent.com/d/19Rxn6CBx42FHnHLxeIXBGxKVfVg7sHl5=w1600', title: 'CROQUIS #01' },
            { src: 'https://lh3.googleusercontent.com/d/1j_pvHD2dAmLXyaDzeRL6eOOKJA0zmJS-=w1600', title: 'CROQUIS #02' },
            { src: 'https://lh3.googleusercontent.com/d/1IXmwSbR9auNd5e6_4JvQtG3RlDOwf9JQ=w1600', title: 'CROQUIS #03' },
            { src: 'https://lh3.googleusercontent.com/d/1uY9ME5MW2rB322OLegcmODWwMHgUq_L_=w1600', title: 'CROQUIS #04' }
        ]
    };

    function switchCategory(category) {
        const target = document.getElementById('cat-' + category);
        if (!target) return;

        document.querySelectorAll('.category-content').forEach(el => el.classList.add('hidden'));
        target.classList.remove('hidden');

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
        const gallery = galleryData[currentGallery];
        if (!gallery || !gallery.length) return;

        currentIndex = Math.max(0, Math.min(currentIndex, gallery.length - 1));
        const item = gallery[currentIndex];
        const modalImg = document.getElementById('modalImage');
        modalImg.src = item.src;
        modalImg.alt = item.title;
        modalImg.setAttribute('referrerpolicy', 'no-referrer');
        document.getElementById('modalCaption').textContent =
            `${item.title}   (${currentIndex + 1} / ${gallery.length})`;
    }

    function nextImage() {
        const gallery = galleryData[currentGallery];
        if (!gallery || !gallery.length) return;
        currentIndex = (currentIndex + 1) % gallery.length;
        updateModalImage();
    }

    function prevImage() {
        const gallery = galleryData[currentGallery];
        if (!gallery || !gallery.length) return;
        currentIndex = (currentIndex - 1 + gallery.length) % gallery.length;
        updateModalImage();
    }

    function closeImageModal() {
        document.getElementById('imageModal').classList.add('hidden');
        document.body.style.overflow = '';
    }

    document.addEventListener('click', function (event) {
        const img = event.target.closest('img');
        if (!img || img.id === 'modalImage' || img.closest('#imageModal')) return;
        if (img.closest('a[href]')) return;
        const galleryCard = img.closest('[onclick*="openGalleryModal"]');
        if (galleryCard) return;

        const container = img.closest('.grid, #planModalBody') || document.body;
        const imgs = Array.from(container.querySelectorAll('img')).filter(i => {
            return i.id !== 'modalImage' && !i.closest('a[href]') && !i.closest('[onclick*="openGalleryModal"]');
        });

        const index = imgs.indexOf(img);
        if (index !== -1) {
            currentGallery = '__dynamic_group__';
            galleryData.__dynamic_group__ = imgs.map(i => ({
                src: i.currentSrc || i.src,
                title: i.alt || 'PREVIEW IMAGE'
            }));
            currentIndex = index;
            updateModalImage();
            document.getElementById('imageModal').classList.remove('hidden');
            document.body.style.overflow = 'hidden';
            event.preventDefault();
        }
    });

    document.addEventListener('keydown', function (event) {
        const modal = document.getElementById('imageModal');
        if (!modal || modal.classList.contains('hidden')) return;
        if (event.key === 'Escape') closeImageModal();
        if (event.key === 'ArrowRight') nextImage();
        if (event.key === 'ArrowLeft') prevImage();
    });

    const planData = {
        hero: {
            title: '개인 기획 / 길 잃은 용사 (가제) & 스토리보드',
            body: `
                <div class="space-y-6 text-xs md:text-sm leading-relaxed">
                    <div>
                        <p class="font-mono text-xs font-bold text-yellowframe-muted">03 / PERSONAL PROJECT CONCEPT</p>
                        <h3 class="text-2xl md:text-3xl font-black mt-1">길 잃은 용사 (가제)</h3>
                        <div class="mt-3 grid grid-cols-1 md:grid-cols-2 gap-3 font-mono">
                            <div class="border-2 border-yellowframe-dark p-3 bg-yellowframe-card">
                                <span class="block text-yellowframe-muted font-bold text-[11px]">장르</span>
                                <span class="font-bold">판타지, 일상 / 2D 단편 애니메이션</span>
                            </div>
                            <div class="border-2 border-yellowframe-dark p-3 bg-yellowframe-card">
                                <span class="block text-yellowframe-muted font-bold text-[11px]">타깃</span>
                                <span class="font-bold">20~30대 직장인 및 보편적 성인 관객</span>
                            </div>
                        </div>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-2 text-yellowframe-muted">로그라인 (한 줄 요약)</p>
                        <p class="font-bold text-base">던전(회사) 보스를 해치운 후 복귀하는 길 잃은 용사(가장)의 이야기</p>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3 text-yellowframe-muted">STORYBOARD / 스토리보드 (기)</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1JRBSqxnvxs-k-yiSz2IrvrRNZ4zlAZjb=w1600" alt="스토리보드 기 01" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1JRBSqxnvxs-k-yiSz2IrvrRNZ4zlAZjb';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">STORYBOARD - PART 01</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1O5kj7xwOhXbTiNAUsJfNptc6_WmAHEBh=w1600" alt="스토리보드 기 02" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1O5kj7xwOhXbTiNAUsJfNptc6_WmAHEBh';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">STORYBOARD - PART 02</div>
                            </div>
                        </div>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3 text-yellowframe-muted">주요 캐릭터</p>
                        <div class="space-y-3">
                            <div class="border-l-4 border-yellowframe-dark pl-3">
                                <p class="font-black text-sm">용사 (남 / 30대 후반, 회사원)</p>
                                <p class="mt-1 text-xs text-yellowframe-muted">어둠이 지배하는 거대한 요새와 미궁 속을 헤쳐 나가는 베테랑 용사이자, 현실에서는 가족의 평화를 지키기 위해 매일 야근과 사투를 벌이는 10년 차 가장. "가족이 웃는 세상"을 만들기 위해 열심히 일을 한다. 오늘도 완벽한 퇴근을 위해 노력한다.</p>
                            </div>
                        </div>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3 text-yellowframe-muted">줄거리 요약 (Synopsis)</p>
                        <div class="space-y-4 font-medium">
                            <div>
                                <span class="font-black block text-xs font-mono mb-1 text-yellowframe-dark">[발단]</span>
                                <p>어둠이 지배하는 거대한 요새 타르타로스. 대마왕의 옥좌 앞에서 온몸이 짓무른 갑옷을 입은 용사는 마법의 힘으로 빛나는 서류 봉인 검을 쥐고 숨을 몰아쉰다. 마침내 최후의 일격을 날려 마왕을 쓰러뜨린다. 사방으로 흩어지는 마력의 파편 속에서 승리의 포효를 내지른다.</p>
                            </div>
                            <div>
                                <span class="font-black block text-xs font-mono mb-1 text-yellowframe-dark">[전개]</span>
                                <p>마왕을 무찔렀다는 해방감도 잠시, 요새의 구조가 요동치며 무너져 내리기 시작한다. 용사는 성채를 빠져나가기 위해 탈출로를 찾지만, 눈앞에는 끝없이 이어지는 미로 같은 회랑과 수백 개의 비상계단뿐이다. 지옥의 미궁이 형태를 바꾸는 동안 손에 든 ‘마법 나침반(스마트폰 GPS)’은 차가운 자줏빛 오류 신호만 내뿜으며 사방으로 핑글핑글 돌다.</p>
                            </div>
                            <div>
                                <span class="font-black block text-xs font-mono mb-1 text-yellowframe-dark">[위기 및 절정]</span>
                                <p>탈출구는 보이지 않고 체력은 바닥을 친다. 이때 어둠 속에서 ‘막차의 시간’, ‘끝나지 않는 내일의 업무’, ‘차가운 야간의 찬 바람’이라는 수많은 망령과 마물들이 사방에서 몰려와 용사를 짓누른다. 결국 무릎을 꿇고 만 용사의 손에서 검이 떨어지고, 성채의 차가운 바닥 위로 축 늘어져 쓰러진다.</p>
                            </div>
                            <div>
                                <span class="font-black block text-xs font-mono mb-1 text-yellowframe-dark">[결말]</span>
                                <p>바로 그 순간, 어둡고 차가운 미궁의 석벽이 허물어지며 따뜻하고 주황빛 노을이 쏟아진다. 차가운 갑옷과 투구인 줄 알았던 것은 구겨진 정장 코트와 넥타이였고, 거대한 성채와 미궁은 수많은 빌딩 숲과 지하철역이 얽힌 ‘회사와 퇴근길’이었다. 바닥에 엎드려 있던 주인공(가장)의 품으로 아빠의 퇴근을 기다리던 아이의 작은 두 팔이 달려와 안긴다. 아이가 아빠의 헝클어진 머리에 삐뚤빼뚤한 종이 왕관을 씌워주자, 지친 용사의 얼굴에 진정한 평화의 미소가 번지며 화면이 암전된다.</p>
                            </div>
                        </div>
                    </div>
                </div>
            `
        },
        character: {
            title: 'STEP 03 / 캐릭터 디자인, 무드보드 & 턴어라운드',
            body: `
                <div class="space-y-6 text-xs md:text-sm leading-relaxed">
                    <div>
                        <p class="font-mono text-xs font-bold text-yellowframe-muted">03 / PERSONAL WORKFLOW</p>
                        <h3 class="text-2xl md:text-3xl font-black mt-1">캐릭터 디자인, 무드보드 & 턴어라운드</h3>
                        <p class="mt-3 text-yellowframe-muted">주인공의 무드보드, 초기 디자인 스케치부터 최종 캐릭터 디자인까지의 작업 과정입니다.</p>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3">MOOD BOARD / 무드보드</p>
                        <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                            <img src="https://lh3.googleusercontent.com/d/13hKSqal381cEjd8z2UUZRYETMMI6mpi0=w1600" alt="캐릭터 무드보드" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=13hKSqal381cEjd8z2UUZRYETMMI6mpi0';this.onerror=function(){this.style.display='none'}">
                        </div>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3">CHARACTER DESIGN / 주인공 디자인 스케치</p>
                        <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                            <img src="https://lh3.googleusercontent.com/d/1MvNbCfFRRC27t2J2RG9tFMP3yoiqPyKR=w1600" alt="주인공 디자인 스케치" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1MvNbCfFRRC27t2J2RG9tFMP3yoiqPyKR';this.onerror=function(){this.style.display='none'}">
                        </div>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3">CHARACTER TURNAROUND / 주인공 완성</p>
                        <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                            <img src="https://lh3.googleusercontent.com/d/1OEPlrtVFspo8AfhT13xMuqbAiHwTYdOD=w1600" alt="주인공 완성 캐릭터 디자인" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1OEPlrtVFspo8AfhT13xMuqbAiHwTYdOD';this.onerror=function(){this.style.display='none'}">
                        </div>
                        <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden mt-4">
                            <img src="https://lh3.googleusercontent.com/d/1ghXJsg-nvttxgVkPyT0XSIiqR1Aj9_Nt=w1600" alt="주인공 완성 캐릭터 디자인 추가 이미지" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1ghXJsg-nvttxgVkPyT0XSIiqR1Aj9_Nt';this.onerror=function(){this.style.display='none'}">
                        </div>
                    </div>
                </div>
            `
        },
        contentProject: {
            title: 'TEAM PITCH DECK / Love ya!',
            body: `
                <div class="space-y-6">
                    <div>
                        <p class="font-mono text-xs font-bold text-yellowframe-muted">02 / TEAM PROJECT PITCH DECK</p>
                        <h3 class="text-2xl md:text-3xl font-black mt-1">Love ya!</h3>
                        <p class="mt-3 leading-relaxed text-xs md:text-sm font-bold text-yellowframe-dark">평행 우주 속 다양한 사랑 이야기</p>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-2 text-yellowframe-muted">작품 소개 (Synopsis & Direction)</p>
                        <p class="text-xs md:text-sm leading-relaxed font-medium">
                            총 다섯 파트로 구성되어 있으며, 마지막 파트에서 일러스트를 삽입하여 모든 사랑이 이루어지는 것으로 연출하였습니다. 특히 여러 그림체의 주인공들이 지나가는 것으로 다중 우주를 효과적으로 표현하였습니다.
                        </p>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3 text-yellowframe-muted">PROJECT IMAGES (일러스트 이미지)</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden cursor-pointer group">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1wl_XqWht2laZQAwLFpK2vkmJkpUNSUqr=w1600" alt="콘텐츠 프로젝트 이미지 #01" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1wl_XqWht2laZQAwLFpK2vkmJkpUNSUqr';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card flex justify-between items-center">
                                    <span>PROJECT IMAGE #01</span>
                                    <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                                </div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden cursor-pointer group">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1vV9Wfv3JWX4i1UVNNSQyk2XgPjdpJ4AA=w1600" alt="콘텐츠 프로젝트 이미지 #02" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain group-hover:scale-105 transition-transform duration-500" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1vV9Wfv3JWX4i1UVNNSQyk2XgPjdpJ4AA';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card flex justify-between items-center">
                                    <span>PROJECT IMAGE #02</span>
                                    <span class="text-[9px] text-yellowframe-muted">VIEW</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="grid md:grid-cols-2 gap-4">
                        <div class="border-2 border-yellowframe-dark p-4 bg-yellowframe-card">
                            <p class="font-mono text-[11px] font-bold text-yellowframe-muted">PROJECT</p>
                            <p class="mt-1 text-xs md:text-sm font-bold">2학년 1학기 콘텐츠 프로젝트</p>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-4 bg-yellowframe-card">
                            <p class="font-mono text-[11px] font-bold text-yellowframe-muted">STRUCTURE</p>
                            <p class="mt-1 text-xs md:text-sm font-bold">총 5개 파트 구성</p>
                        </div>
                    </div>
                </div>
            `
        },
        saerom: {
            title: 'TEAM PITCH DECK / 천재? 탐정 새롬',
            body: `
                <div class="space-y-6">
                    <div>
                        <p class="font-mono text-xs font-bold text-yellowframe-muted">02 / CONCEPT (TEAM PROJECT)</p>
                        <h3 class="text-2xl md:text-3xl font-black mt-1">천재? 탐정 새롬</h3>
                        <p class="mt-3 leading-relaxed text-xs md:text-sm">팀 협업 단편 애니메이션. 자칭 천재 탐정 새롬이가 산장에서 일어난 수상한 살인사건을 수사한다. 연이은 잘못된 추리에 용의자가 하나둘씩 죽어가며 수사는 미궁에 빠진다.</p>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3">BACKGROUND ART (배경 이미지 5종)</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1LXumIbeHjTUz8aAS6bjZh3v52RWOoEMW=w1600" alt="배경 아트 #01" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1LXumIbeHjTUz8aAS6bjZh3v52RWOoEMW';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">BACKGROUND #01</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1-ubKYR5xMFeHbg_6Y7gddcka5jLWEM9q=w1600" alt="배경 아트 #02" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1-ubKYR5xMFeHbg_6Y7gddcka5jLWEM9q';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">BACKGROUND #02</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/10mmvwCc_74_-p8z9xKCySAU3_JH7pjdO=w1600" alt="배경 아트 #03" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=10mmvwCc_74_-p8z9xKCySAU3_JH7pjdO';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">BACKGROUND #03</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1YY2UZUxPaLMkFIcJlpzsltrRzqnw7R69=w1600" alt="배경 아트 #04" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1YY2UZUxPaLMkFIcJlpzsltrRzqnw7R69';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">BACKGROUND #04</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/13Dc7NsLSV36nrh6JIwwbgEzuoD_hMs1a=w1600" alt="배경 아트 #05" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=13Dc7NsLSV36nrh6JIwwbgEzuoD_hMs1a';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">BACKGROUND #05</div>
                            </div>
                        </div>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3">ANIMATION / IN-BETWEEN CUTS (동화 움짤 5종)</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1CYIklhtcfj2EoGbcEZ1waY8ijcxf0IcA=w1600" alt="동화 움짤 #01" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1CYIklhtcfj2EoGbcEZ1waY8ijcxf0IcA';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CUT #01</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1x41DDfgXecIDOK6X0P0e-tmHzQWHjYFq=w1600" alt="동화 움짤 #02" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1x41DDfgXecIDOK6X0P0e-tmHzQWHjYFq';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CUT #02</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1ecpLwwo0lZZajYKKdxHoTIiAH1KGpLXJ=w1600" alt="동화 움짤 #03" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1ecpLwwo0lZZajYKKdxHoTIiAH1KGpLXJ';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CUT #03</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1Ie4RV-lnIk12t1h2AsOR7tSpvFWGr3Ro=w1600" alt="동화 움짤 #04" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1Ie4RV-lnIk12t1h2AsOR7tSpvFWGr3Ro';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CUT #04</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/16QYsW3Ugi2SiW900ZPqbKiR2K1IB5An0=w1600" alt="동화 움짤 #05" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=16QYsW3Ugi2SiW900ZPqbKiR2K1IB5An0';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CUT #05</div>
                            </div>
                        </div>
                    </div>

                    <div class="grid md:grid-cols-2 gap-4">
                        <div class="border-2 border-yellowframe-dark p-4 bg-yellowframe-card">
                            <p class="font-mono text-[11px] font-bold text-yellowframe-muted">GENRE</p>
                            <p class="mt-1 text-xs md:text-sm font-bold">코미디 · 스릴러 · 공포 · 추리</p>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-4 bg-yellowframe-card">
                            <p class="font-mono text-[11px] font-bold text-yellowframe-muted">FORMAT</p>
                            <p class="mt-1 text-xs md:text-sm font-bold">팀 단편 애니메이션 (5분)</p>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-4 bg-yellowframe-card md:col-span-2">
                            <p class="font-mono text-[11px] font-bold text-yellowframe-muted">MY ROLE IN TEAM</p>
                            <p class="mt-1 text-xs md:text-sm font-bold">원동화 작화 · 배경 아트 · 캐릭터 디자인 참여</p>
                        </div>
                    </div>
                </div>
            `
        },
        happyFamily: {
            title: 'TEAM PITCH DECK / happy family (행복한 가족)',
            body: `
                <div class="space-y-6 text-xs md:text-sm leading-relaxed">
                    <div>
                        <p class="font-mono text-xs font-bold text-yellowframe-muted">02 / GAME OVERVIEW & SYNOPSIS</p>
                        <h3 class="text-2xl md:text-3xl font-black mt-1">happy family (행복한 가족)</h3>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3 text-yellowframe-muted">시놉시스 (Synopsis)</p>
                        <p class="font-medium leading-relaxed">
                          환각과 헛소리에 시달리던 이들이 점차 난폭해져 살인을 저지르기 시작하고, 사태는 손쓸 수 없이 악화된다. 정확한 원인을 모르는 정부는 그저 "야간 외출을 금지하라"는 무력한 경고만 되풀이할 뿐이다. 평화롭던 이웃이 언제 연쇄 살인마로 바뀔지 모르는 극한의 기강 속에서, 사람들은 자기 자신마저 광기에 물들지 모른다는 공포에 떨며 정신병원을 찾고 있다.
                        </p>
                    </div>

                    <!-- 캐릭터 도트 -->
                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3 text-yellowframe-muted">캐릭터 도트</p>
                        <div class="grid grid-cols-1 gap-3">
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1Li_dH7K3eUBMLkiOKqGES3laZxCHZV3w=w1600" alt="캐릭터 도트 1" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1Li_dH7K3eUBMLkiOKqGES3laZxCHZV3w';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CHARACTER DOT #01</div>
                            </div>
                        </div>
                    </div>

                    <!-- 애니메이팅 -->
                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3 text-yellowframe-muted">애니메이팅</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1t5WY2ehmJwydgZcZzncQu2eIdkzLPw2c=w1600" alt="애니메이팅 1" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1t5WY2ehmJwydgZcZzncQu2eIdkzLPw2c';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">ANIMATING #01</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1aZFfzu1b2tmoxLjRqE-PTMZ_GrVXbHBu=w1600" alt="애니메이팅 2" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1aZFfzu1b2tmoxLjRqE-PTMZ_GrVXbHBu';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">ANIMATING #02</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1phxDUD0Qt76_-XShlEFx1z607od6Wo2V=w1600" alt="애니메이팅 3" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1phxDUD0Qt76_-XShlEFx1z607od6Wo2V';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">ANIMATING #03</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1EpkBOnOb527XedbXWrDAEO7qKOz9KGx9=w1600" alt="애니메이팅 4" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1EpkBOnOb527XedbXWrDAEO7qKOz9KGx9';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">ANIMATING #04</div>
                            </div>
                        </div>
                    </div>

                    <!-- 배경 -->
                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3 text-yellowframe-muted">배경</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/16gvxIfocvzGdun6xMO8XGnze5BnbIcdX=w1600" alt="배경 1" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=16gvxIfocvzGdun6xMO8XGnze5BnbIcdX';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">BACKGROUND #01</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/16OESb5KSvK59NsvOWKD7-YhhX-ZxIW6X=w1600" alt="배경 2" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=16OESb5KSvK59NsvOWKD7-YhhX-ZxIW6X';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">BACKGROUND #02</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden md:col-span-2">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1K6cj7ueAjJSotNNStc2ep1WvVUjGHOAy=w1600" alt="배경 3" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1K6cj7ueAjJSotNNStc2ep1WvVUjGHOAy';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">BACKGROUND #03</div>
                            </div>
                        </div>
                    </div>

                    <div class="mt-3 grid grid-cols-1 md:grid-cols-2 gap-3 font-mono">
                        <div class="border-2 border-yellowframe-dark p-3 bg-yellowframe-card">
                            <span class="block text-yellowframe-muted font-bold text-[11px]">장르</span>
                            <span class="font-bold">심리, 공포</span>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-3 bg-yellowframe-card">
                            <span class="block text-yellowframe-muted font-bold text-[11px]">플랫폼 / 엔진</span>
                            <span class="font-bold">PC / 유니티</span>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-3 bg-yellowframe-card">
                            <span class="block text-yellowframe-muted font-bold text-[11px]">주요 연령 / 등급</span>
                            <span class="font-bold">10대 중후반 ~ 30대 초 / 15세 이용가</span>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-3 bg-yellowframe-card">
                            <span class="block text-yellowframe-muted font-bold text-[11px]">조작 방식</span>
                            <span class="font-bold">키보드, 마우스</span>
                        </div>
                    </div>
                </div>
            `
        },
        vicky: {
            title: 'TEAM PITCH DECK / 괴짜과학자 비키',
            body: `
                <div class="space-y-6">
                    <div>
                        <p class="font-mono text-xs font-bold text-yellowframe-muted">02 / LOGLINE (TEAM PROJECT)</p>
                        <h3 class="text-2xl md:text-3xl font-black mt-1">괴짜과학자 비키</h3>
                        <p class="mt-3 text-xs md:text-sm leading-relaxed font-medium">음모론으로 뒤덮인 현대 사회에서 괴짜 과학자 ‘비키’는 지구 음모론을 증명할 수 있을 것인가?</p>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3">CHARACTER DESIGN / 캐릭터 디자인</p>
                        <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                            <div class="bg-black/5 w-full">
                                <img src="https://lh3.googleusercontent.com/d/15rJi9s9pAi5RsarHC9DIulZW8iTVd4hz=w1600"
                                     alt="괴짜과학자 비키 캐릭터 디자인" loading="lazy" referrerpolicy="no-referrer"
                                     class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=15rJi9s9pAi5RsarHC9DIulZW8iTVd4hz';this.onerror=function(){this.style.display='none'}">
                            </div>
                            <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">VICKY / CHARACTER DESIGN</div>
                        </div>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3">LIP-SYNC / 립싱크 (5종)</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1dYrvTygXIBc5PNWlceu0Rd7a2eXotvVe=w1600" alt="립싱크 움짤 #01" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1dYrvTygXIBc5PNWlceu0Rd7a2eXotvVe';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">LIP-SYNC #01</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1FlLRTI3FEBk4RPc48OI5dTRBGtYO_Nwg=w1600" alt="립싱크 움짤 #02" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1FlLRTI3FEBk4RPc48OI5dTRBGtYO_Nwg';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">LIP-SYNC #02</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1k32aVMMIg9y27nH4CggydZL1DYjcFYyf=w1600" alt="립싱크 움짤 #03" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1k32aVMMIg9y27nH4CggydZL1DYjcFYyf';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">LIP-SYNC #03</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1jqtDmOPNxWycaHrTvuQUJC2Q2R8my4Kj=w1600" alt="립싱크 움짤 #04" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1jqtDmOPNxWycaHrTvuQUJC2Q2R8my4Kj';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">LIP-SYNC #04</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1O3AIMtevQF_GH6qVqcMvn_w3GLQuypPF=w1600" alt="립싱크 움짤 #05" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1O3AIMtevQF_GH6qVqcMvn_w3GLQuypPF';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">LIP-SYNC #05</div>
                            </div>
                        </div>
                    </div>

                    <div class="border-2 border-yellowframe-dark bg-yellowframe-card p-4 shadow-[3px_3px_0_#111]">
                        <p class="font-mono text-xs font-bold mb-3">ANIMATION / IN-BETWEEN CUTS (동화 움짤 8종)</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1T5oJ9b5pOL-sbcYyIdVmUqM5tc2kiVN7=w1600" alt="동화 움짤 #01" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1T5oJ9b5pOL-sbcYyIdVmUqM5tc2kiVN7';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CUT #01</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1OK4tGmJL3Dok8BU7cPAMp7Y1oCNiEFEd=w1600" alt="동화 움짤 #02" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1OK4tGmJL3Dok8BU7cPAMp7Y1oCNiEFEd';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CUT #02</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1AN4VS31l08W4dENZjZP51svneu8yre6B=w1600" alt="동화 움짤 #03" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1AN4VS31l08W4dENZjZP51svneu8yre6B';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CUT #03</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1M72tG7KZgiWVzntbpnihrIJ7bl2BWBYf=w1600" alt="동화 움짤 #04" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1M72tG7KZgiWVzntbpnihrIJ7bl2BWBYf';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CUT #04</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1L6XQ0qA39Sj6Jy_Cf5rbyE1uTjnY-UM-=w1600" alt="동화 움짤 #05" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1L6XQ0qA39Sj6Jy_Cf5rbyE1uTjnY-UM-';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CUT #05</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1xTv6nrZgM5xbzyTniKXAdxMEhupeqlI1=w1600" alt="동화 움짤 #06" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1xTv6nrZgM5xbzyTniKXAdxMEhupeqlI1';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CUT #06</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1ZE06yY3FhJi2nEtu_MNyCRHrTrTnxBAw=w1600" alt="동화 움짤 #07" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1ZE06yY3FhJi2nEtu_MNyCRHrTrTnxBAw';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CUT #07</div>
                            </div>
                            <div class="border-2 border-yellowframe-dark bg-yellowframe-bg overflow-hidden">
                                <div class="bg-black/5 w-full">
                                    <img src="https://lh3.googleusercontent.com/d/1ylLc9s-tjJIF_YbTX1qdK8UqPmZjacBA=w1600" alt="동화 움짤 #08" loading="lazy" referrerpolicy="no-referrer" class="w-full h-auto object-contain" onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&id=1ylLc9s-tjJIF_YbTX1qdK8UqPmZjacBA';this.onerror=function(){this.style.display='none'}">
                                </div>
                                <div class="p-1.5 border-t-2 border-yellowframe-dark font-mono text-[10px] font-bold bg-yellowframe-card">CUT #08</div>
                            </div>
                        </div>
                    </div>

                    <div class="grid md:grid-cols-2 gap-4">
                        <div class="border-2 border-yellowframe-dark p-4 bg-yellowframe-card">
                            <p class="font-mono text-[11px] font-bold text-yellowframe-muted">GENRE</p>
                            <p class="mt-1 text-xs md:text-sm font-bold">SF, 코미디</p>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-4 bg-yellowframe-card">
                            <p class="font-mono text-[11px] font-bold text-yellowframe-muted">TARGET</p>
                            <p class="mt-1 text-xs md:text-sm font-bold">전연령</p>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-4 bg-yellowframe-card">
                            <p class="font-mono text-[11px] font-bold text-yellowframe-muted">RUNNING TIME / CATEGORY</p>
                            <p class="mt-1 text-xs md:text-sm font-bold">10분 이내 / TV 시리즈 에피소드</p>
                        </div>
                        <div class="border-2 border-yellowframe-dark p-4 bg-yellowframe-card">
                            <p class="font-mono text-[11px] font-bold text-yellowframe-muted">MY ROLE IN TEAM</p>
                            <p class="mt-1 text-xs md:text-sm font-bold">원동화 작화 파트 담당</p>
                        </div>
                    </div>
                </div>
            `
        }
    };

    function openPlanModal(type) {
        const data = planData[type];
        if (!data) return;

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
