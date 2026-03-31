<!DOCTYPE html>
<html class="light" lang="ko">
<head>
    <meta charset="utf-8"/>
    <meta content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" name="viewport"/>
    <title>학업 비타민 - 통합 관리</title>
    <script src="https://cdn.tailwindcss.com?plugins=forms,container-queries"></script>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&family=Inter:wght@400;500;600&display=swap" rel="stylesheet"/>
    <link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&display=swap" rel="stylesheet"/>
    
    <script id="tailwind-config">
        tailwind.config = {
          darkMode: "class",
          theme: {
            extend: {
              colors: {
                "on-primary": "#ffffff",
                "secondary-fixed-dim": "#75daa8",
                "surface-container-lowest": "#ffffff",
                "secondary-fixed": "#92f7c3",
                "outline-variant": "#c1c6d6",
                "surface-container-high": "#e6e8f2",
                "primary-fixed": "#d7e2ff",
                "surface-container": "#ecedf7",
                "on-secondary-fixed-variant": "#005235",
                "tertiary": "#705d00",
                "on-surface-variant": "#414753",
                "tertiary-container": "#caa900",
                "secondary-container": "#92f7c3",
                "surface": "#f9f9ff",
                "primary-container": "#006adc",
                "background": "#f9f9ff",
                "on-secondary": "#ffffff",
                "on-surface": "#191c22",
                "tertiary-fixed": "#ffe171",
                "surface-container-highest": "#e1e2ec",
                "primary": "#0052ae",
                "surface-container-low": "#f2f3fd",
                "error": "#ba1a1a",
                "secondary": "#006c48",
                "on-secondary-fixed": "#002113",
                "outline": "#727785",
                "on-primary-fixed": "#001a40",
                "on-primary-container": "#edf1ff",
                "on-background": "#191c22"
              },
              fontFamily: {
                "headline": ["Plus Jakarta Sans"],
                "body": ["Inter"],
                "label": ["Inter"]
              },
              borderRadius: {"DEFAULT": "0.25rem", "lg": "0.5rem", "xl": "1.5rem", "2xl": "2rem", "full": "9999px"},
            },
          },
        }
    </script>

    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #e5e7eb; /* 깃허브에서 띄웠을 때 배경이 될 예쁜 회색 */
            -webkit-tap-highlight-color: transparent;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }
        .font-headline { font-family: 'Plus Jakarta Sans', sans-serif; }
        
        .material-symbols-outlined {
            font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 24;
        }

        /* 📱 리얼한 디바이스(휴대폰) 목업 뼈대 */
        .device-mockup {
            width: 390px;          /* 최신 스마트폰 가로 폭 */
            height: 844px;         /* 최신 스마트폰 세로 폭 */
            background-color: #111; /* 휴대폰 베젤 색상 */
            border-radius: 50px;   /* 기기 둥근 모서리 */
            padding: 14px;         /* 베젤 두께 */
            box-shadow: 
                0 0 0 2px #d1d5db, /* 메탈 테두리 느낌 */
                0 25px 50px -12px rgba(0, 0, 0, 0.3); /* 그림자 */
            position: relative;
            flex-shrink: 0;
        }

        /* 다이내믹 아일랜드 (노치) */
        .device-notch {
            position: absolute;
            top: 24px;
            left: 50%;
            transform: translateX(-50%);
            width: 120px;
            height: 32px;
            background-color: #000;
            border-radius: 20px;
            z-index: 100;
        }

        /* 실제 앱 화면 영역 */
        .mobile-container {
            width: 100%;
            height: 100%;
            background-color: #f9f9ff;
            border-radius: 38px; /* 베젤 안쪽 화면 라운드 */
            position: relative;
            display: flex;
            flex-direction: column;
            overflow: hidden; /* 화면 밖으로 넘치는 컨텐츠 숨김 */
        }

        /* 메인 스크롤 영역 */
        .main-scroll-area {
            flex: 1;
            overflow-y: auto;
            overflow-x: hidden;
            scrollbar-width: none; /* Firefox 스크롤바 숨김 */
        }
        .main-scroll-area::-webkit-scrollbar { 
            display: none; /* Chrome 스크롤바 숨김 */
        }

        /* 탭 컨텐츠 전환 애니메이션 */
        .tab-content { 
            display: none; 
            animation: fadeIn 0.3s ease;
        }
        .tab-content.active { 
            display: block; 
        }
        
        @keyframes fadeIn { 
            from { opacity: 0; transform: translateY(5px); } 
            to { opacity: 1; transform: translateY(0); } 
        }

        .no-scrollbar::-webkit-scrollbar { display: none; }
        .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
    </style>
</head>
<body class="text-on-surface">

<!-- 디바이스 목업 (휴대폰 프레임) -->
<div class="device-mockup">
    <!-- 화면 상단 노치 -->
    <div class="device-notch"></div>
    
    <!-- 실제 앱 뷰포트 -->
    <div class="mobile-container">
        
        <!-- Top App Bar (스크롤 안에서 상단에 위치) -->
        <header class="w-full shrink-0 z-40 bg-[#f9f9ff]/90 backdrop-blur-md pt-12 pb-3 border-b border-[#e1e2ec]/50 shadow-sm relative">
            <div class="flex justify-between items-center px-6">
                <div class="flex items-center gap-3">
                    <div class="w-9 h-9 rounded-full bg-primary-fixed flex items-center justify-center overflow-hidden shrink-0">
                        <img alt="사용자 프로필 사진" class="w-full h-full object-cover" src="https://lh3.googleusercontent.com/aida-public/AB6AXuAO7daZurEiCaHNH-1jRebquTiLWtEBWRp6PWkrcWoVJcA4w9PBekJFqSuW-uaOYF8ML3U6P6r96w6pulnk6jKWk6fVdi213V0VoGalIXxKSjUQmns7MSvSscDpY3DEDD1MTwaRnnjTnqiW0sajlLg1G77q9LmrIfTpvAMdrqVNRQLHMGcP_H5-NmM8SlEG7COwC56sp8UFdXUZFCsIoED2VvsD1nv8wrtrl_lXlHCs9mTGkOF0A4Zt28BhssfUd-_3Cr-w-3ddV4Du"/>
                    </div>
                    <h1 class="font-headline text-lg font-extrabold tracking-tight text-[#006ADC]">학업 비타민</h1>
                </div>
                <button class="w-9 h-9 flex items-center justify-center rounded-full hover:bg-surface-container-low transition-colors active:scale-95 shrink-0">
                    <span class="material-symbols-outlined text-[#006ADC]">search</span>
                </button>
            </div>
        </header>

        <!-- 메인 스크롤 콘텐츠 영역 -->
        <main class="main-scroll-area pb-28" id="main-scroller">
            
            <!-- ========================================== -->
            <!-- 1. 홈 대시보드 -->
            <!-- ========================================== -->
            <section id="tab-home" class="tab-content active px-6 pt-6 space-y-8">
                <!-- Welcome Section -->
                <div class="space-y-1">
                    <p class="text-outline font-medium text-sm">안녕하세요, 민수님! 👋</p>
                    <h2 class="text-2xl font-extrabold font-headline tracking-tight leading-tight">오늘도 활기찬 <br/><span class="text-primary">학업 에너지를</span> 충전해요</h2>
                </div>

                <!-- 핵심 과제 Bento Grid -->
                <div class="space-y-4">
                    <div class="flex items-end justify-between">
                        <h3 class="text-lg font-headline font-bold tracking-tight">오늘의 핵심 과제</h3>
                        <span class="text-[11px] font-semibold text-primary">전체보기</span>
                    </div>
                    <div class="grid grid-cols-1 gap-3">
                        <!-- High Priority -->
                        <div class="bg-primary-container text-on-primary-container p-6 rounded-2xl shadow-sm relative overflow-hidden group">
                            <div class="relative z-10 space-y-3">
                                <span class="px-2.5 py-1 bg-white/20 rounded-full text-[10px] font-bold tracking-wider uppercase">High Priority</span>
                                <h4 class="text-xl font-bold leading-tight">알고리즘 분석 <br/> 기말 과제 제출</h4>
                                <div class="flex items-center gap-1.5 text-white/80">
                                    <span class="material-symbols-outlined text-[14px]">schedule</span>
                                    <span class="text-xs font-medium">오늘 오후 11:59 까지</span>
                                </div>
                            </div>
                            <div class="absolute -right-8 -bottom-8 w-40 h-40 bg-white/10 rounded-full blur-3xl group-hover:scale-110 transition-transform duration-500"></div>
                            <button class="absolute right-5 top-5 w-10 h-10 bg-white text-primary rounded-full flex items-center justify-center shadow-lg active:scale-90 transition-transform">
                                <span class="material-symbols-outlined text-[20px]" style="font-variation-settings: 'FILL' 1;">play_arrow</span>
                            </button>
                        </div>
                        <!-- Medium Priority Grid -->
                        <div class="grid grid-cols-2 gap-3">
                            <div class="bg-surface-container-lowest p-4 rounded-2xl shadow-sm border border-outline-variant/10 flex flex-col justify-between">
                                <div class="space-y-2">
                                    <div class="w-8 h-8 rounded-lg bg-secondary-fixed flex items-center justify-center">
                                        <span class="material-symbols-outlined text-[18px] text-on-secondary-fixed">edit_note</span>
                                    </div>
                                    <h4 class="text-sm font-bold leading-snug">마케팅 원론 <br/> 독후감 초안</h4>
                                </div>
                                <div class="mt-3 flex items-center justify-between">
                                    <span class="text-[9px] font-medium text-outline">내일 오전 10:00</span>
                                </div>
                            </div>
                            <div class="bg-surface-container-lowest p-4 rounded-2xl shadow-sm border border-outline-variant/10 flex flex-col justify-between">
                                <div class="space-y-2">
                                    <div class="w-8 h-8 rounded-lg bg-tertiary-fixed flex items-center justify-center">
                                        <span class="material-symbols-outlined text-[18px] text-on-tertiary-fixed">group</span>
                                    </div>
                                    <h4 class="text-sm font-bold leading-snug">데이터베이스 <br/> 팀미팅 준비</h4>
                                </div>
                                <div class="mt-3 flex items-center justify-between">
                                    <span class="text-[9px] font-medium text-outline">D-2</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- 수업 알림 -->
                <div class="space-y-3">
                    <h3 class="text-lg font-headline font-bold tracking-tight">수업 알림</h3>
                    <div class="bg-secondary p-[3px] rounded-2xl shadow-md relative overflow-hidden">
                        <div class="bg-white/95 backdrop-blur-md rounded-[14px] p-4 flex items-center gap-4">
                            <div class="flex flex-col items-center justify-center px-2 border-r border-outline-variant/30">
                                <span class="text-secondary font-extrabold text-xl">14:00</span>
                                <span class="text-[9px] font-bold text-outline tracking-widest uppercase mt-0.5">In 45m</span>
                            </div>
                            <div class="flex-1">
                                <h4 class="text-[15px] font-bold">경제학 원론</h4>
                                <p class="text-[11px] text-outline mt-0.5">사회과학관 302호</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- 퀵 액션 -->
                <div class="flex gap-2.5 overflow-x-auto pb-4 no-scrollbar">
                    <button class="shrink-0 px-4 py-2.5 bg-primary-fixed text-on-primary-fixed rounded-full font-bold text-xs flex items-center gap-1.5 active:scale-95 transition-transform">
                        <span class="material-symbols-outlined text-[16px]">add_task</span> 할일 추가
                    </button>
                    <button class="shrink-0 px-4 py-2.5 bg-surface-container-high text-on-surface-variant rounded-full font-bold text-xs flex items-center gap-1.5 hover:bg-surface-container-highest transition-colors">
                        <span class="material-symbols-outlined text-[16px]">timer</span> 집중 모드
                    </button>
                    <button class="shrink-0 px-4 py-2.5 bg-surface-container-high text-on-surface-variant rounded-full font-bold text-xs flex items-center gap-1.5 hover:bg-surface-container-highest transition-colors">
                        <span class="material-symbols-outlined text-[16px]">auto_stories</span> 학습 자료
                    </button>
                </div>
            </section>

            <!-- ========================================== -->
            <!-- 2. 투두 리스트 -->
            <!-- ========================================== -->
            <section id="tab-todo" class="tab-content px-6 pt-6 space-y-8">
                <div class="mb-4">
                    <h2 class="font-headline text-2xl font-extrabold tracking-tight mb-1">오늘의 도전 🚀</h2>
                    <p class="text-outline font-medium text-xs">오늘은 5개의 중요한 일정이 기다리고 있어요.</p>
                    <div class="flex gap-2.5 mt-5">
                        <div class="flex-1 bg-primary-fixed p-3.5 rounded-xl flex flex-col justify-between">
                            <span class="material-symbols-outlined text-primary text-[20px] mb-2">task_alt</span>
                            <div>
                                <p class="text-on-primary-fixed font-bold text-lg">80%</p>
                                <p class="text-on-primary-fixed-variant text-[9px] font-medium">과제 완료율</p>
                            </div>
                        </div>
                        <div class="flex-1 bg-secondary-fixed p-3.5 rounded-xl flex flex-col justify-between">
                            <span class="material-symbols-outlined text-secondary text-[20px] mb-2">timer</span>
                            <div>
                                <p class="text-on-secondary-fixed font-bold text-lg">4h 20m</p>
                                <p class="text-on-secondary-fixed-variant text-[9px] font-medium">집중 시간</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- 필터 -->
                <div class="flex gap-2 overflow-x-auto pb-1 no-scrollbar">
                    <button class="px-4 py-2 rounded-full bg-primary text-white text-[11px] font-bold whitespace-nowrap shadow-sm">전체</button>
                    <button class="px-4 py-2 rounded-full bg-surface-container-low text-on-surface-variant text-[11px] font-medium whitespace-nowrap">과제</button>
                    <button class="px-4 py-2 rounded-full bg-surface-container-low text-on-surface-variant text-[11px] font-medium whitespace-nowrap">시험</button>
                    <button class="px-4 py-2 rounded-full bg-surface-container-low text-on-surface-variant text-[11px] font-medium whitespace-nowrap">동아리</button>
                </div>

                <!-- 할일 목록 -->
                <div class="space-y-6">
                    <!-- 과제 섹션 -->
                    <div>
                        <h3 class="font-headline text-[15px] font-bold flex items-center gap-2 mb-3">
                            <span class="w-1.5 h-4 bg-primary rounded-full"></span> 과제 <span class="text-outline text-[10px] font-normal ml-0.5">2</span>
                        </h3>
                        <div class="space-y-2.5">
                            <div class="bg-surface-container-lowest p-3.5 rounded-xl border border-outline-variant/10 shadow-sm flex items-start gap-3">
                                <button class="mt-0.5 w-[18px] h-[18px] rounded-full border-2 border-primary flex items-center justify-center shrink-0"></button>
                                <div class="flex-1">
                                    <h4 class="text-on-surface font-semibold text-[13px] leading-tight">알고리즘 분석 보고서</h4>
                                    <div class="flex items-center gap-2 mt-1.5">
                                        <span class="text-[9px] font-medium text-error flex items-center gap-0.5"><span class="material-symbols-outlined text-[10px]">schedule</span> 오늘까지</span>
                                        <span class="text-[9px] text-outline">컴퓨터공학입문</span>
                                    </div>
                                </div>
                                <span class="material-symbols-outlined text-outline text-[18px]">more_vert</span>
                            </div>
                            
                            <div class="bg-secondary-fixed/20 p-3.5 rounded-xl border border-secondary/20 shadow-sm relative overflow-hidden flex items-start gap-3">
                                <div class="absolute top-0 right-0 p-1.5">
                                    <span class="bg-secondary text-white text-[8px] font-bold px-1.5 py-0.5 rounded-full">집중 권장</span>
                                </div>
                                <button class="mt-0.5 w-[18px] h-[18px] rounded-full border-2 border-secondary shrink-0"></button>
                                <div class="flex-1">
                                    <h4 class="text-on-surface font-semibold text-[13px] leading-tight pr-10">UX 와이어프레임 수정</h4>
                                    <div class="flex items-center gap-2 mt-1.5">
                                        <span class="text-[9px] font-medium text-outline">내일 14:00</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- 완료됨 섹션 -->
                    <div class="opacity-60">
                        <h3 class="font-headline text-[15px] font-bold flex items-center gap-2 mb-3">
                            <span class="w-1.5 h-4 bg-outline-variant rounded-full"></span> 완료됨 <span class="text-outline text-[10px] font-normal ml-0.5">1</span>
                        </h3>
                        <div class="bg-surface-container-low p-3.5 rounded-xl flex items-start gap-3">
                            <div class="mt-0.5 w-[18px] h-[18px] rounded-full bg-outline flex items-center justify-center text-white shrink-0">
                                <span class="material-symbols-outlined text-[12px]" style="font-variation-settings: 'FILL' 1;">check</span>
                            </div>
                            <div class="flex-1">
                                <h4 class="text-outline font-medium text-[13px] leading-tight line-through">동아리 주간 회의 참석</h4>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- ========================================== -->
            <!-- 3. 캘린더 -->
            <!-- ========================================== -->
            <section id="tab-calendar" class="tab-content px-4 pt-6 space-y-6">
                <div class="bg-surface-container-low rounded-[2rem] p-5 shadow-sm">
                    <!-- 달력 헤더 -->
                    <div class="flex justify-between items-center mb-5 px-1">
                        <h2 class="font-headline text-xl font-extrabold">2026년 3월</h2>
                        <div class="flex gap-1">
                            <button class="p-1 bg-surface-container-highest rounded-full"><span class="material-symbols-outlined text-[16px]">chevron_left</span></button>
                            <button class="p-1 bg-surface-container-highest rounded-full"><span class="material-symbols-outlined text-[16px]">chevron_right</span></button>
                        </div>
                    </div>
                    <!-- 요일 -->
                    <div class="grid grid-cols-7 text-center text-[10px] font-bold text-outline mb-2">
                        <div>일</div><div>월</div><div>화</div><div>수</div><div>목</div><div>금</div><div>토</div>
                    </div>
                    <!-- 날짜 그리드 (일부 샘플) -->
                    <div class="grid grid-cols-7 gap-y-1 text-center text-[13px] font-medium">
                        <div class="h-9 flex items-center justify-center text-outline-variant">22</div>
                        <div class="h-9 flex items-center justify-center text-outline-variant">23</div>
                        <div class="h-9 flex items-center justify-center">1</div>
                        <div class="h-9 flex flex-col items-center justify-center bg-tertiary-fixed rounded-t-xl">2</div>
                        <div class="h-9 flex flex-col items-center justify-center bg-tertiary-fixed relative">
                            3 <div class="absolute bottom-1 w-1 h-1 bg-primary rounded-full"></div>
                        </div>
                        <div class="h-9 flex flex-col items-center justify-center bg-tertiary-fixed rounded-b-xl">4</div>
                        <div class="h-9 flex items-center justify-center">5</div>
                        <div class="h-9 flex items-center justify-center">6</div>
                        <div class="h-9 flex items-center justify-center">
                            <div class="w-7 h-7 bg-primary text-white rounded-full flex items-center justify-center shadow-lg font-bold">7</div>
                        </div>
                        <div class="h-9 flex items-center justify-center">8</div>
                        <div class="h-9 flex items-center justify-center">9</div>
                        <div class="h-9 flex items-center justify-center">10</div>
                        <div class="h-9 flex items-center justify-center">11</div>
                        <div class="h-9 flex items-center justify-center">12</div>
                    </div>
                    <div class="mt-4 flex items-center gap-4 text-[9px] font-medium text-outline justify-center">
                        <div class="flex items-center gap-1"><div class="w-1.5 h-1.5 bg-tertiary-fixed rounded-full"></div><span>시험/중요</span></div>
                        <div class="flex items-center gap-1"><div class="w-1.5 h-1.5 bg-primary rounded-full"></div><span>일정 있음</span></div>
                    </div>
                </div>
                
                <!-- 시간표 & 일정 -->
                <div class="px-2 space-y-3">
                    <div class="flex items-center justify-between mb-2">
                        <h3 class="font-headline text-[15px] font-bold">오늘의 일정</h3>
                        <span class="text-[9px] font-bold text-primary bg-primary-fixed px-2 py-0.5 rounded-full">3개</span>
                    </div>
                    
                    <div class="bg-surface-container-lowest p-3.5 rounded-2xl flex items-start gap-3 shadow-sm border border-outline-variant/10">
                        <div class="flex flex-col items-center justify-center text-outline border-r border-outline-variant/30 pr-3">
                            <span class="text-[11px] font-bold">09:00</span>
                        </div>
                        <div class="flex-1">
                            <h4 class="font-bold text-[13px] mb-0.5">인공지능 개론</h4>
                            <p class="text-[9px] text-outline flex items-center gap-1"><span class="material-symbols-outlined text-[10px]">location_on</span> 공학관 302호</p>
                        </div>
                        <div class="p-1.5 bg-secondary-container rounded-lg"><span class="material-symbols-outlined text-[14px] text-on-secondary-container">psychology</span></div>
                    </div>

                    <div class="bg-secondary-fixed/20 p-3.5 rounded-2xl flex items-start gap-3 ring-1 ring-secondary/20">
                        <div class="flex flex-col items-center justify-center text-secondary border-r border-secondary/30 pr-3">
                            <span class="text-[11px] font-bold">13:30</span>
                        </div>
                        <div class="flex-1">
                            <div class="flex items-center gap-2 mb-0.5">
                                <h4 class="font-bold text-[13px]">UX 디자인 실습</h4>
                                <span class="text-[7px] px-1 py-0.5 bg-secondary text-white rounded font-bold">진행 중</span>
                            </div>
                            <p class="text-[9px] text-outline flex items-center gap-1"><span class="material-symbols-outlined text-[10px]">location_on</span> 조형관 105호</p>
                        </div>
                    </div>
                </div>
            </section>

            <!-- ========================================== -->
            <!-- 4. 설정 -->
            <!-- ========================================== -->
            <section id="tab-settings" class="tab-content px-6 pt-6 space-y-8">
                <!-- Welcome -->
                <div class="mb-6">
                    <h2 class="font-headline text-2xl font-extrabold tracking-tight mb-1">환영합니다, 민수님</h2>
                    <p class="text-outline font-medium text-[11px]">오늘도 당신의 성장을 응원합니다.</p>
                </div>

                <!-- 요약 카드 -->
                <div class="bg-surface-container-low rounded-2xl p-5 relative overflow-hidden group mb-6">
                    <div class="relative z-10">
                        <span class="inline-block px-2.5 py-1 bg-primary-container text-white rounded-full text-[9px] font-bold mb-2">현재 학기</span>
                        <h3 class="text-xl font-extrabold font-headline mb-0.5">2026학년도 1학기</h3>
                        <p class="text-[11px] font-medium text-outline">기말고사까지 D-42</p>
                    </div>
                    <div class="absolute right-[-10px] bottom-[-20px] opacity-5 text-primary">
                        <span class="material-symbols-outlined text-[100px]" style="font-variation-settings: 'FILL' 1;">school</span>
                    </div>
                </div>

                <!-- 메뉴 리스트 -->
                <div class="space-y-2.5">
                    <h3 class="text-[10px] font-bold text-outline px-1 mb-1.5">학기 관리</h3>
                    
                    <button class="w-full flex items-center justify-between p-3.5 bg-surface-container-lowest rounded-xl border border-outline-variant/10 active:bg-surface-container-high transition-colors">
                        <div class="flex items-center gap-3">
                            <div class="w-8 h-8 rounded-lg bg-primary-container/10 flex items-center justify-center text-primary-container">
                                <span class="material-symbols-outlined text-[18px]">calendar_view_week</span>
                            </div>
                            <div class="text-left">
                                <p class="font-bold text-[13px]">시간표 관리</p>
                                <p class="text-[9px] text-outline">나의 강의 일정 확인</p>
                            </div>
                        </div>
                        <span class="material-symbols-outlined text-outline text-[18px]">chevron_right</span>
                    </button>
                    
                    <button class="w-full flex items-center justify-between p-3.5 bg-surface-container-lowest rounded-xl border border-outline-variant/10 active:bg-surface-container-high transition-colors">
                        <div class="flex items-center gap-3">
                            <div class="w-8 h-8 rounded-lg bg-secondary/10 flex items-center justify-center text-secondary">
                                <span class="material-symbols-outlined text-[18px]">grade</span>
                            </div>
                            <div class="text-left">
                                <p class="font-bold text-[13px]">성적 목표 설정</p>
                                <p class="text-[9px] text-outline">이번 학기 목표 학점 달성</p>
                            </div>
                        </div>
                        <span class="material-symbols-outlined text-outline text-[18px]">chevron_right</span>
                    </button>

                    <button class="w-full flex items-center justify-between p-3.5 bg-surface-container-lowest rounded-xl border border-outline-variant/10 active:bg-surface-container-high transition-colors">
                        <div class="flex items-center gap-3">
                            <div class="w-8 h-8 rounded-lg bg-surface-container-highest flex items-center justify-center text-on-surface-variant">
                                <span class="material-symbols-outlined text-[18px]">notifications_active</span>
                            </div>
                            <div class="text-left">
                                <p class="font-bold text-[13px]">알림 설정</p>
                            </div>
                        </div>
                        <span class="material-symbols-outlined text-outline text-[18px]">chevron_right</span>
                    </button>
                </div>

                <div class="pt-4 pb-8 flex justify-center">
                    <button class="px-5 py-2.5 rounded-full text-error font-bold bg-error-container/20 hover:bg-error-container/40 transition-colors flex items-center gap-1.5 text-xs">
                        <span class="material-symbols-outlined text-[16px]">logout</span> 로그아웃
                    </button>
                </div>
            </section>
        </main>

        <!-- 공통 Floating Action Button (FAB) (앱 내부 absolute 위치) -->
        <div id="main-fab" class="absolute bottom-24 right-5 z-40">
            <button class="w-12 h-12 rounded-full bg-gradient-to-br from-primary to-primary-container text-white shadow-xl shadow-primary/30 flex items-center justify-center active:scale-90 transition-transform">
                <span class="material-symbols-outlined text-[24px]">add</span>
            </button>
        </div>

        <!-- 통합 Bottom Navigation Bar (앱 내부 absolute 위치) -->
        <nav class="absolute bottom-0 left-0 w-full z-50 bg-[#f9f9ff]/90 backdrop-blur-xl border-t border-[#c1c6d6]/30 shadow-[0_-10px_20px_rgba(0,0,0,0.03)] rounded-t-[1.5rem] flex justify-around items-center px-2 pb-6 pt-2">
            
            <button onclick="switchTab('tab-home', this)" class="nav-btn flex flex-col items-center justify-center bg-[#d7e2ff] text-[#001a40] rounded-2xl px-4 py-1.5 transition-all duration-300">
                <span class="material-symbols-outlined text-[22px]" style="font-variation-settings: 'FILL' 1;">home</span>
                <span class="font-['Inter'] text-[9px] font-medium mt-0.5">홈</span>
            </button>
            
            <button onclick="switchTab('tab-todo', this)" class="nav-btn flex flex-col items-center justify-center text-[#727785] px-4 py-1.5 transition-all duration-300">
                <span class="material-symbols-outlined text-[22px]" style="font-variation-settings: 'FILL' 0;">check_circle</span>
                <span class="font-['Inter'] text-[9px] font-medium mt-0.5">투두</span>
            </button>
            
            <button onclick="switchTab('tab-calendar', this)" class="nav-btn flex flex-col items-center justify-center text-[#727785] px-4 py-1.5 transition-all duration-300">
                <span class="material-symbols-outlined text-[22px]" style="font-variation-settings: 'FILL' 0;">calendar_month</span>
                <span class="font-['Inter'] text-[9px] font-medium mt-0.5">캘린더</span>
            </button>
            
            <button onclick="switchTab('tab-settings', this)" class="nav-btn flex flex-col items-center justify-center text-[#727785] px-4 py-1.5 transition-all duration-300">
                <span class="material-symbols-outlined text-[22px]" style="font-variation-settings: 'FILL' 0;">settings</span>
                <span class="font-['Inter'] text-[9px] font-medium mt-0.5">설정</span>
            </button>
            
        </nav>
        
    </div>
</div>

<script>
    function switchTab(tabId, btn) {
        // 1. 모든 탭 숨기기
        const allTabs = document.querySelectorAll('.tab-content');
        allTabs.forEach(tab => {
            tab.classList.remove('active');
        });
        
        // 2. 선택한 탭 보이기
        const targetTab = document.getElementById(tabId);
        if (targetTab) {
            targetTab.classList.add('active');
        }

        // 3. 네비게이션 버튼 스타일 초기화 (비활성 상태로)
        const allNavBtns = document.querySelectorAll('.nav-btn');
        allNavBtns.forEach(nav => {
            nav.classList.remove('bg-[#d7e2ff]', 'text-[#001a40]', 'rounded-2xl');
            nav.classList.add('text-[#727785]');
            const icon = nav.querySelector('.material-symbols-outlined');
            if(icon) icon.style.fontVariationSettings = "'FILL' 0";
        });

        // 4. 클릭한 버튼 스타일 적용 (활성 상태로)
        if (btn) {
            btn.classList.remove('text-[#727785]');
            btn.classList.add('bg-[#d7e2ff]', 'text-[#001a40]', 'rounded-2xl');
            const btnIcon = btn.querySelector('.material-symbols-outlined');
            if(btnIcon) btnIcon.style.fontVariationSettings = "'FILL' 1";
        }

        // 5. FAB 버튼 가시성 제어 (가이드에 따라 설정 탭에서는 숨김)
        const fab = document.getElementById('main-fab');
        if (fab) {
            if (tabId === 'tab-settings') {
                fab.style.display = 'none';
            } else {
                fab.style.display = 'block';
            }
        }

        // 6. 디바이스 컨테이너 스크롤을 맨 위로 부드럽게 이동
        try {
            const scroller = document.getElementById('main-scroller');
            if (scroller) {
                scroller.scrollTo({ top: 0, behavior: 'smooth' });
            }
        } catch (error) {
            const fallbackScroller = document.getElementById('main-scroller');
            if(fallbackScroller) fallbackScroller.scrollTop = 0;
        }
    }
</script>

</body>
</html>
