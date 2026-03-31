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
                "primary": "#0052ae",
                "primary-container": "#006adc",
                "on-primary-container": "#edf1ff",
                "primary-fixed": "#d7e2ff",
                "on-primary-fixed": "#001a40",
                "secondary": "#006c48",
                "secondary-fixed": "#92f7c3",
                "on-secondary-fixed": "#002113",
                "tertiary": "#705d00",
                "tertiary-fixed": "#ffe171",
                "surface": "#f9f9ff",
                "surface-container-low": "#f2f3fd",
                "surface-container-lowest": "#ffffff",
                "outline": "#727785",
                "outline-variant": "#c1c6d6",
                "error": "#ba1a1a"
              },
              fontFamily: {
                "headline": ["Plus Jakarta Sans", "sans-serif"],
                "body": ["Inter", "sans-serif"]
              },
              animation: {
                'fade-in': 'fadeIn 0.3s ease-out forwards',
              },
              keyframes: {
                fadeIn: {
                  '0%': { opacity: '0', transform: 'translateY(10px)' },
                  '100%': { opacity: '1', transform: 'translateY(0)' },
                }
              }
            }
          }
        }
    </script>

    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #e5e7eb; /* 데스크톱 배경색 */
            -webkit-tap-highlight-color: transparent;
            overflow-x: hidden;
            margin: 0;
        }
        .font-headline { font-family: 'Plus Jakarta Sans', sans-serif; }
        
        /* 스크롤바 숨기기 */
        .no-scrollbar::-webkit-scrollbar { display: none; }
        .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
        
        /* 탭 전환 효과를 위한 클래스 */
        .tab-content { 
            display: none; 
            opacity: 0; 
            transition: opacity 0.3s ease; 
        }
        .tab-content.active { 
            display: block; 
            opacity: 1; 
        }
        
        /* 모바일 고정 레이아웃 (데스크톱 뷰 대응) */
        .mobile-wrapper {
            display: flex;
            justify-content: center;
            width: 100%;
            min-height: 100vh;
        }
        .mobile-container {
            width: 100%;
            max-width: 480px;
            min-height: 100vh;
            position: relative;
            background: #f9f9ff;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
            overflow-x: hidden;
        }

        /* 하단 네비게이션이 스크롤을 가리지 않도록 여백 확보 */
        .main-content {
            padding-bottom: 120px;
        }
        
        /* 체크박스 트랜지션 */
        .check-transition { transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1); }
    </style>
</head>
<body>

<div class="mobile-wrapper">
    <div class="mobile-container">
        
        <!-- Header -->
        <header class="w-full sticky top-0 z-30 bg-surface/90 backdrop-blur-lg border-b border-outline-variant/20 transition-all">
            <div class="flex justify-between items-center px-6 py-4">
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 rounded-full bg-primary-fixed flex items-center justify-center overflow-hidden ring-2 ring-surface">
                        <img src="https://lh3.googleusercontent.com/aida-public/AB6AXuAO7daZurEiCaHNH-1jRebquTiLWtEBWRp6PWkrcWoVJcA4w9PBekJFqSuW-uaOYF8ML3U6P6r96w6pulnk6jKWk6fVdi213V0VoGalIXxKSjUQmns7MSvSscDpY3DEDD1MTwaRnnjTnqiW0sajlLg1G77q9LmrIfTpvAMdrqVNRQLHMGcP_H5-NmM8SlEG7COwC56sp8UFdXUZFCsIoED2VvsD1nv8wrtrl_lXlHCs9mTGkOF0A4Zt28BhssfUd-_3Cr-w-3ddV4Du" 
                             alt="프로필" 
                             class="w-full h-full object-cover"
                             onerror="this.onerror=null; this.src='data:image/svg+xml;utf8,<svg xmlns=\'http://www.w3.org/2000/svg\' viewBox=\'0 0 100 100\'><rect width=\'100\' height=\'100\' fill=\'%23d7e2ff\'/><text x=\'50\' y=\'55\' font-size=\'40\' text-anchor=\'middle\' dominant-baseline=\'middle\' fill=\'%23001a40\' font-family=\'sans-serif\'>민</text></svg>'">
                    </div>
                    <h1 class="font-headline text-xl font-extrabold tracking-tight text-primary-container">학업 비타민</h1>
                </div>
                <button class="w-10 h-10 flex items-center justify-center rounded-full hover:bg-surface-container-low active:bg-surface-container-low transition-colors" onclick="showToast('검색 기능은 준비 중입니다.')">
                    <span class="material-symbols-outlined text-primary-container">search</span>
                </button>
            </div>
        </header>

        <!-- Main Content -->
        <main class="px-6 pt-6 main-content">
            
            <!-- Home Tab -->
            <section id="home" class="tab-content active space-y-8 animate-fade-in">
                <div class="space-y-1">
                    <p class="text-outline font-medium text-sm">안녕하세요, 민수님! 👋</p>
                    <h2 class="text-3xl font-extrabold font-headline leading-tight text-on-surface">오늘도 활기찬 <br/><span class="text-primary">학업 에너지를</span> 충전해요</h2>
                </div>

                <div class="grid grid-cols-1 gap-4">
                    <!-- High Priority Card -->
                    <div class="bg-gradient-to-br from-primary-container to-primary text-white p-6 rounded-[1.5rem] shadow-lg shadow-primary/30 relative overflow-hidden group hover:shadow-xl transition-shadow cursor-pointer" onclick="showToast('과제 상세 페이지로 이동합니다.')">
                        <!-- Background decoration -->
                        <div class="absolute -right-6 -top-6 w-32 h-32 bg-white/10 rounded-full blur-2xl"></div>
                        
                        <span class="inline-block px-3 py-1 bg-white/20 backdrop-blur-md rounded-full text-[10px] font-bold uppercase tracking-wider border border-white/10">High Priority</span>
                        <h4 class="text-xl font-bold mt-4 leading-snug">알고리즘 분석 <br> 기말 과제 제출</h4>
                        <p class="text-white/90 text-xs mt-3 flex items-center gap-1.5 font-medium">
                            <span class="material-symbols-outlined text-[16px]">schedule</span> 오늘 오후 11:59 까지
                        </p>
                        <button class="absolute right-5 bottom-5 w-11 h-11 bg-white text-primary rounded-full flex items-center justify-center shadow-lg hover:scale-105 active:scale-95 transition-transform">
                            <span class="material-symbols-outlined">play_arrow</span>
                        </button>
                    </div>

                    <!-- Quick Stats Cards -->
                    <div class="grid grid-cols-2 gap-4">
                        <div class="bg-surface-container-lowest p-5 rounded-2xl border border-outline-variant/20 shadow-sm hover:border-outline-variant/40 transition-colors cursor-pointer" onclick="showToast('마케팅 독후감 메모를 엽니다.')">
                            <div class="w-10 h-10 rounded-xl bg-secondary-fixed flex items-center justify-center mb-4">
                                <span class="material-symbols-outlined text-on-secondary-fixed">edit_note</span>
                            </div>
                            <h4 class="font-bold text-[15px] text-on-surface">마케팅 독후감</h4>
                            <p class="text-xs text-outline mt-1 font-medium">내일 오전 10:00</p>
                        </div>
                        <div class="bg-surface-container-lowest p-5 rounded-2xl border border-outline-variant/20 shadow-sm hover:border-outline-variant/40 transition-colors cursor-pointer" onclick="showToast('DB 팀미팅 일정을 확인합니다.')">
                            <div class="w-10 h-10 rounded-xl bg-tertiary-fixed flex items-center justify-center mb-4">
                                <span class="material-symbols-outlined text-on-tertiary-fixed">group</span>
                            </div>
                            <h4 class="font-bold text-[15px] text-on-surface">DB 팀미팅</h4>
                            <p class="text-xs text-outline mt-1 font-medium">D-2</p>
                        </div>
                    </div>
                </div>
                
                <!-- Upcoming Class -->
                <div class="bg-secondary/10 p-1.5 rounded-[1.5rem] shadow-sm overflow-hidden border border-secondary/20 cursor-pointer hover:bg-secondary/20 transition-colors" onclick="showToast('시간표 상세를 봅니다.')">
                    <div class="bg-surface-container-lowest rounded-[1.2rem] p-4 flex items-center gap-5">
                        <div class="text-center pr-5 border-r border-outline-variant/30 flex flex-col justify-center">
                            <p class="text-secondary font-black text-2xl leading-none">14:00</p>
                            <p class="text-[10px] font-bold text-secondary/70 mt-1.5 uppercase tracking-wide">In 45m</p>
                        </div>
                        <div class="flex-1">
                            <h4 class="font-bold text-base text-on-surface mb-0.5">경제학 원론</h4>
                            <p class="text-xs text-outline flex items-center gap-1">
                                <span class="material-symbols-outlined text-[14px]">location_on</span> 사회과학관 302호
                            </p>
                        </div>
                        <span class="material-symbols-outlined text-outline-variant">chevron_right</span>
                    </div>
                </div>
            </section>

            <!-- Todo Tab -->
            <section id="todo" class="tab-content space-y-6">
                <h2 class="font-headline text-2xl font-extrabold text-on-surface">오늘의 도전 🚀</h2>
                
                <!-- Category Pills -->
                <div class="flex gap-2 overflow-x-auto no-scrollbar pb-2 -mx-2 px-2">
                    <button class="px-5 py-2 rounded-full bg-primary text-white text-sm font-bold whitespace-nowrap shadow-sm">전체</button>
                    <button class="px-5 py-2 rounded-full bg-surface-container-lowest border border-outline-variant/20 text-outline text-sm font-medium whitespace-nowrap active:bg-surface-container-low">과제</button>
                    <button class="px-5 py-2 rounded-full bg-surface-container-lowest border border-outline-variant/20 text-outline text-sm font-medium whitespace-nowrap active:bg-surface-container-low">시험</button>
                    <button class="px-5 py-2 rounded-full bg-surface-container-lowest border border-outline-variant/20 text-outline text-sm font-medium whitespace-nowrap active:bg-surface-container-low">스터디</button>
                </div>
                
                <!-- Todo List -->
                <div class="space-y-3">
                    <!-- Todo Item 1 -->
                    <div class="todo-item bg-surface-container-lowest p-4 rounded-2xl border border-outline-variant/20 flex items-center gap-4 cursor-pointer select-none transition-colors active:bg-surface-container-low hover:border-outline-variant/50" onclick="toggleTodo(this)">
                        <div class="check-box w-6 h-6 rounded-full border-2 border-primary flex items-center justify-center check-transition shrink-0">
                            <span class="material-symbols-outlined text-[16px] text-white opacity-0 transition-opacity">check</span>
                        </div>
                        <div class="flex-1 transition-opacity">
                            <p class="todo-title font-bold text-[15px] text-on-surface transition-all">알고리즘 분석 보고서</p>
                            <p class="todo-desc text-xs text-error font-medium mt-0.5 transition-all">오늘까지</p>
                        </div>
                        <button class="p-2 text-outline hover:bg-surface-container-low rounded-full transition-colors" onclick="event.stopPropagation(); showToast('메뉴 열기')">
                            <span class="material-symbols-outlined text-[20px]">more_vert</span>
                        </button>
                    </div>

                    <!-- Todo Item 2 (High Priority style) -->
                    <div class="todo-item bg-secondary-fixed/20 p-4 rounded-2xl border border-secondary/30 flex items-center gap-4 cursor-pointer select-none transition-colors active:bg-secondary-fixed/30 hover:border-secondary/50" onclick="toggleTodo(this)">
                        <div class="check-box w-6 h-6 rounded-full border-2 border-secondary flex items-center justify-center check-transition shrink-0">
                            <span class="material-symbols-outlined text-[16px] text-white opacity-0 transition-opacity">check</span>
                        </div>
                        <div class="flex-1 transition-opacity">
                            <p class="todo-title font-bold text-[15px] text-on-surface transition-all">UX 디자인 수정</p>
                            <p class="todo-desc text-xs text-secondary font-medium mt-0.5 transition-all">내일 14:00</p>
                        </div>
                        <span class="bg-secondary text-white text-[10px] px-2.5 py-1 rounded-full font-bold shadow-sm whitespace-nowrap">집중 권장</span>
                    </div>

                    <!-- Todo Item 3 -->
                    <div class="todo-item bg-surface-container-lowest p-4 rounded-2xl border border-outline-variant/20 flex items-center gap-4 cursor-pointer select-none transition-colors active:bg-surface-container-low hover:border-outline-variant/50" onclick="toggleTodo(this)">
                        <div class="check-box w-6 h-6 rounded-full border-2 border-outline flex items-center justify-center check-transition shrink-0">
                            <span class="material-symbols-outlined text-[16px] text-white opacity-0 transition-opacity">check</span>
                        </div>
                        <div class="flex-1 transition-opacity">
                            <p class="todo-title font-bold text-[15px] text-on-surface transition-all">선형대수학 3장 복습</p>
                            <p class="todo-desc text-xs text-outline font-medium mt-0.5 transition-all">자유 기한</p>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Calendar Tab -->
            <section id="calendar" class="tab-content space-y-6">
                <!-- Calendar Card -->
                <div class="bg-surface-container-lowest rounded-3xl p-6 shadow-sm border border-outline-variant/10">
                    <div class="flex justify-between items-center mb-6">
                        <h2 class="font-headline font-extrabold text-xl text-on-surface">2026년 3월</h2>
                        <div class="flex gap-2">
                            <button class="w-8 h-8 flex items-center justify-center rounded-full bg-surface-container-low text-outline hover:text-on-surface transition-colors"><span class="material-symbols-outlined text-[20px]">chevron_left</span></button>
                            <button class="w-8 h-8 flex items-center justify-center rounded-full bg-surface-container-low text-outline hover:text-on-surface transition-colors"><span class="material-symbols-outlined text-[20px]">chevron_right</span></button>
                        </div>
                    </div>
                    <div class="grid grid-cols-7 text-center text-xs font-bold text-outline mb-3">
                        <div class="text-error/80">일</div><div>월</div><div>화</div><div>수</div><div>목</div><div>금</div><div class="text-primary/80">토</div>
                    </div>
                    <div class="grid grid-cols-7 gap-y-3 text-center text-sm font-medium text-on-surface">
                        <div class="h-9 flex items-center justify-center text-outline-variant">25</div>
                        <div class="h-9 flex items-center justify-center text-outline-variant">26</div>
                        <div class="h-9 flex items-center justify-center">1</div>
                        <div class="h-9 flex flex-col items-center justify-center relative">
                            <span class="w-9 h-9 flex items-center justify-center bg-primary text-white rounded-full font-bold shadow-md shadow-primary/30">2</span>
                        </div>
                        <div class="h-9 flex items-center justify-center relative">
                            3
                            <div class="absolute bottom-1 w-1 h-1 bg-error rounded-full"></div>
                        </div>
                        <div class="h-9 flex items-center justify-center relative">
                            4
                            <div class="absolute bottom-1 w-1 h-1 bg-secondary rounded-full"></div>
                        </div>
                        <div class="h-9 flex items-center justify-center text-primary/80">5</div>
                        <!-- 생략된 달력 일자들 공간 확보 -->
                        <div class="h-9 flex items-center justify-center text-error/80">6</div>
                        <div class="h-9 flex items-center justify-center">7</div>
                        <div class="h-9 flex items-center justify-center">8</div>
                        <div class="h-9 flex items-center justify-center">9</div>
                        <div class="h-9 flex items-center justify-center">10</div>
                        <div class="h-9 flex items-center justify-center">11</div>
                        <div class="h-9 flex items-center justify-center text-primary/80">12</div>
                    </div>
                </div>
                
                <!-- Timeline -->
                <div class="space-y-4">
                    <h3 class="font-headline font-bold text-base text-on-surface px-1">오늘의 일정</h3>
                    <div class="bg-surface-container-lowest p-5 rounded-2xl flex gap-4 items-center border border-outline-variant/10 shadow-sm relative overflow-hidden">
                        <div class="absolute left-0 top-0 bottom-0 w-1 bg-primary"></div>
                        <div class="text-xs font-bold text-outline pr-4 border-r border-outline-variant/30 flex flex-col items-center">
                            <span>09:00</span>
                            <span class="text-[10px] font-normal text-outline-variant mt-1">10:30</span>
                        </div>
                        <div class="flex-1">
                            <p class="text-[15px] font-bold text-on-surface">인공지능 개론</p>
                            <p class="text-xs text-outline mt-1 flex items-center gap-1">
                                <span class="material-symbols-outlined text-[14px]">location_on</span> 공학관 302호
                            </p>
                        </div>
                        <div class="w-10 h-10 bg-primary-fixed rounded-xl flex items-center justify-center text-primary">
                            <span class="material-symbols-outlined">psychology</span>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Settings Tab -->
            <section id="settings" class="tab-content space-y-8">
                <h2 class="font-headline text-2xl font-extrabold text-on-surface">설정</h2>
                
                <div class="bg-gradient-to-br from-surface-container-low to-primary-fixed/30 rounded-[1.5rem] p-6 relative overflow-hidden border border-primary-fixed">
                    <span class="bg-primary text-white text-[10px] px-3 py-1 rounded-full font-bold shadow-sm">현재 학기</span>
                    <h3 class="text-2xl font-black font-headline mt-4 text-on-surface">2026학년도 1학기</h3>
                    <p class="text-sm text-primary font-bold mt-2 bg-white/50 inline-block px-3 py-1 rounded-lg backdrop-blur-sm">기말고사까지 D-42</p>
                    <span class="material-symbols-outlined absolute -right-6 -bottom-6 text-9xl opacity-5 text-primary rotate-12 pointer-events-none">school</span>
                </div>

                <div class="space-y-3">
                    <button class="w-full flex items-center justify-between p-4.5 bg-surface-container-lowest rounded-2xl border border-outline-variant/20 hover:bg-surface-container-low active:bg-surface-container-low transition-colors shadow-sm" onclick="showToast('시간표 관리로 이동')">
                        <div class="flex items-center gap-4">
                            <div class="w-10 h-10 rounded-full bg-primary-fixed/50 flex items-center justify-center text-primary">
                                <span class="material-symbols-outlined text-[20px]">calendar_view_week</span>
                            </div>
                            <span class="font-bold text-[15px] text-on-surface">시간표 관리</span>
                        </div>
                        <span class="material-symbols-outlined text-outline">chevron_right</span>
                    </button>
                    
                    <button class="w-full flex items-center justify-between p-4.5 bg-surface-container-lowest rounded-2xl border border-outline-variant/20 hover:bg-surface-container-low active:bg-surface-container-low transition-colors shadow-sm" onclick="showToast('성적 목표 설정으로 이동')">
                        <div class="flex items-center gap-4">
                            <div class="w-10 h-10 rounded-full bg-secondary-fixed/50 flex items-center justify-center text-secondary">
                                <span class="material-symbols-outlined text-[20px]">grade</span>
                            </div>
                            <span class="font-bold text-[15px] text-on-surface">성적 목표 설정</span>
                        </div>
                        <span class="material-symbols-outlined text-outline">chevron_right</span>
                    </button>
                    
                    <button class="w-full flex items-center justify-between p-4.5 bg-surface-container-lowest rounded-2xl border border-outline-variant/20 hover:bg-error/5 active:bg-error/10 transition-colors shadow-sm text-error mt-4" onclick="showToast('로그아웃 되었습니다.')">
                        <div class="flex items-center gap-4">
                            <div class="w-10 h-10 rounded-full bg-error/10 flex items-center justify-center">
                                <span class="material-symbols-outlined text-[20px]">logout</span>
                            </div>
                            <span class="font-bold text-[15px]">로그아웃</span>
                        </div>
                    </button>
                </div>
            </section>

        </main>

        <!-- FAB Container (고정된 컨테이너 내부에서 우측 하단 정렬) -->
        <div id="fab-container" class="absolute bottom-28 right-6 z-40 transition-transform duration-300">
            <button onclick="showToast('새로운 항목을 추가합니다.')" class="w-[3.5rem] h-[3.5rem] rounded-2xl bg-gradient-to-br from-primary to-primary-container text-white shadow-lg shadow-primary/40 flex items-center justify-center active:scale-90 hover:-translate-y-1 transition-all">
                <span class="material-symbols-outlined text-[28px] font-bold">add</span>
            </button>
        </div>

        <!-- Bottom Navigation -->
        <nav class="absolute bottom-0 w-full z-50 bg-surface/85 backdrop-blur-xl border-t border-outline-variant/20 px-4 pb-8 pt-3 flex justify-around items-center shadow-[0_-10px_40px_-15px_rgba(0,0,0,0.1)]">
            <button onclick="showTab('home', this)" class="nav-item flex flex-col items-center gap-1 w-16 py-2 rounded-2xl transition-all active:scale-95 bg-primary-fixed text-on-primary-fixed">
                <span class="material-symbols-outlined fill-1 text-[24px]">home</span>
                <span class="text-[11px] font-bold">홈</span>
            </button>
            <button onclick="showTab('todo', this)" class="nav-item flex flex-col items-center gap-1 w-16 py-2 rounded-2xl transition-all active:scale-95 text-outline hover:bg-surface-container-low">
                <span class="material-symbols-outlined text-[24px]">check_circle</span>
                <span class="text-[11px] font-bold">투두</span>
            </button>
            <button onclick="showTab('calendar', this)" class="nav-item flex flex-col items-center gap-1 w-16 py-2 rounded-2xl transition-all active:scale-95 text-outline hover:bg-surface-container-low">
                <span class="material-symbols-outlined text-[24px]">calendar_month</span>
                <span class="text-[11px] font-bold">캘린더</span>
            </button>
            <button onclick="showTab('settings', this)" class="nav-item flex flex-col items-center gap-1 w-16 py-2 rounded-2xl transition-all active:scale-95 text-outline hover:bg-surface-container-low">
                <span class="material-symbols-outlined text-[24px]">settings</span>
                <span class="text-[11px] font-bold">설정</span>
            </button>
        </nav>
    </div>
</div>

<script>
    // 탭 전환 로직
    function showTab(tabId, el) {
        // 모든 탭 페이드 아웃 및 숨김 처리
        const tabs = document.querySelectorAll('.tab-content');
        tabs.forEach(tab => {
            tab.style.opacity = '0';
            setTimeout(() => {
                if(tab.id !== tabId) tab.style.display = 'none';
                tab.classList.remove('active');
            }, 150); // 트랜지션 시간의 반
        });
        
        // 선택한 탭 보이기 및 페이드 인
        setTimeout(() => {
            const activeTab = document.getElementById(tabId);
            activeTab.style.display = 'block';
            // 리플로우 강제 유발
            void activeTab.offsetWidth; 
            activeTab.style.opacity = '1';
            activeTab.classList.add('active');
            
            // 컨테이너 스크롤 상단으로 부드럽게 이동
            document.querySelector('.mobile-container').scrollTo({top: 0, behavior: 'smooth'});
        }, 150);
        
        // 네비게이션 스타일 업데이트
        document.querySelectorAll('.nav-item').forEach(nav => {
            nav.classList.remove('bg-primary-fixed', 'text-on-primary-fixed');
            nav.classList.add('text-outline', 'hover:bg-surface-container-low');
            nav.querySelector('.material-symbols-outlined').style.fontVariationSettings = "'FILL' 0";
        });
        
        el.classList.add('bg-primary-fixed', 'text-on-primary-fixed');
        el.classList.remove('text-outline', 'hover:bg-surface-container-low');
        el.querySelector('.material-symbols-outlined').style.fontVariationSettings = "'FILL' 1";

        // 설정 페이지에서는 FAB를 스케일 아웃 애니메이션으로 숨김
        const fab = document.getElementById('fab-container');
        if(tabId === 'settings') {
            fab.style.transform = 'scale(0) translateY(20px)';
            fab.style.opacity = '0';
            fab.style.pointerEvents = 'none';
        } else {
            fab.style.transform = 'scale(1) translateY(0)';
            fab.style.opacity = '1';
            fab.style.pointerEvents = 'auto';
        }
    }

    // 투두 아이템 토글 (체크/체크해제) 로직
    function toggleTodo(el) {
        const checkbox = el.querySelector('.check-box');
        const icon = checkbox.querySelector('span');
        const title = el.querySelector('.todo-title');
        const desc = el.querySelector('.todo-desc');

        // 상태 확인을 위해 보더 클래스 확인 (primary, secondary, outline 등 다양한 상태 존재)
        const isChecked = checkbox.classList.contains('bg-primary') || checkbox.classList.contains('bg-secondary') || checkbox.classList.contains('bg-outline');

        if (isChecked) {
            // 체크 해제
            checkbox.classList.remove('bg-primary', 'bg-secondary', 'bg-outline', 'border-transparent');
            icon.classList.add('opacity-0');
            
            title.classList.remove('line-through', 'text-outline-variant');
            desc.classList.remove('text-outline-variant');
            desc.classList.add(el.dataset.originalColorClass || 'text-outline'); 
        } else {
            // 원본 색상 저장
            if(!el.dataset.originalColorClass) {
                const descClasses = Array.from(desc.classList);
                const colorClass = descClasses.find(c => c.startsWith('text-') && c !== 'text-xs' && c !== 'text-outline-variant');
                el.dataset.originalColorClass = colorClass || 'text-outline';
            }

            // 체크 됨 (원래 테두리 색상에 맞춰 배경 채우기)
            if(checkbox.classList.contains('border-primary')) checkbox.classList.add('bg-primary', 'border-transparent');
            else if(checkbox.classList.contains('border-secondary')) checkbox.classList.add('bg-secondary', 'border-transparent');
            else checkbox.classList.add('bg-outline', 'border-transparent');
            
            icon.classList.remove('opacity-0');
            
            title.classList.add('line-through', 'text-outline-variant');
            desc.classList.remove(el.dataset.originalColorClass);
            desc.classList.add('text-outline-variant');
        }
    }

    // 커스텀 토스트 메시지 시스템
    let toastTimeout;
    function showToast(message) {
        // 기존 토스트 제거
        const existingToast = document.getElementById('custom-toast');
        if (existingToast) { existingToast.remove(); clearTimeout(toastTimeout); }

        const toast = document.createElement('div');
        toast.id = 'custom-toast';
        toast.className = 'absolute top-20 left-1/2 -translate-x-1/2 bg-on-surface text-surface px-5 py-3 rounded-xl shadow-xl z-[60] text-sm font-medium transition-all duration-300 transform -translate-y-4 opacity-0 flex items-center gap-2 max-w-[90%] w-max';
        
        toast.innerHTML = `<span class="material-symbols-outlined text-[18px]">info</span> ${message}`;
        
        // 모바일 컨테이너 내부에 추가 (포지셔닝을 위해)
        document.querySelector('.mobile-container').appendChild(toast);

        // 표시 애니메이션
        requestAnimationFrame(() => {
            requestAnimationFrame(() => {
                toast.classList.remove('-translate-y-4', 'opacity-0');
            });
        });

        // 숨김 애니메이션
        toastTimeout = setTimeout(() => {
            toast.classList.add('-translate-y-4', 'opacity-0');
            setTimeout(() => toast.remove(), 300);
        }, 2500);
    }
</script>

</body>
</html>
