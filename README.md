
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Apple ID Store</title>
    
    <!-- FONTS: Plus Jakarta Sans (Modern & Geometric) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <!-- TAILWIND CSS -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4" type="e9fa4ba069feb37efaaceb7b-text/javascript"></script>
    <script type="e9fa4ba069feb37efaaceb7b-text/javascript">
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: { sans: ['Plus Jakarta Sans', 'sans-serif'] },
                    colors: {
                        brand: { 50: '#f9fafb', 100: '#f3f4f6', 900: '#000000' }
                    },
                    animation: {
                        'blob': 'blob 7s infinite',
                        'fade-in-up': 'fadeInUp 0.5s ease-out forwards',
                    },
                    keyframes: {
                        blob: {
                            '0%': { transform: 'translate(0px, 0px) scale(1)' },
                            '33%': { transform: 'translate(30px, -50px) scale(1.1)' },
                            '66%': { transform: 'translate(-20px, 20px) scale(0.9)' },
                            '100%': { transform: 'translate(0px, 0px) scale(1)' },
                        },
                        fadeInUp: {
                            '0%': { opacity: '0', transform: 'translateY(20px)' },
                            '100%': { opacity: '1', transform: 'translateY(0)' },
                        }
                    }
                }
            }
        }
    </script>
    
    <!-- VUE JS 3 -->
    <script src="https://unpkg.com/vue@3/dist/vue.global.js" type="e9fa4ba069feb37efaaceb7b-text/javascript"></script>

    <!-- ICONS -->
    <script src="https://unpkg.com/@phosphor-icons/web" type="e9fa4ba069feb37efaaceb7b-text/javascript"></script>

    <style>
        [v-cloak] { display: none; }
        body { background-color: #f8fafc; color: #1e293b; }
        
        /* Modern Glass Effect */
        .glass-panel {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.5);
        }

        .card-premium {
            background: rgba(255, 255, 255, 0.9);
            border: 1px solid rgba(226, 232, 240, 0.6);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        .card-premium:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px -5px rgba(59, 130, 246, 0.15);
            border-color: rgba(59, 130, 246, 0.3);
        }

        /* Mesh Gradient Background */
        .bg-mesh {
            background-color: #f8fafc;
            background-image: 
                radial-gradient(at 0% 0%, hsla(253,16%,7%,1) 0, transparent 50%), 
                radial-gradient(at 50% 0%, hsla(225,39%,30%,1) 0, transparent 50%), 
                radial-gradient(at 100% 0%, hsla(339,49%,30%,1) 0, transparent 50%);
            background-size: 100% 600px;
            background-repeat: no-repeat;
        }

        /* Staggered Animation Delay for Cards */
        .delay-100 { animation-delay: 100ms; }
        .delay-200 { animation-delay: 200ms; }
        .delay-300 { animation-delay: 300ms; }
    </style>
<script data-cfasync="false" nonce="02e9b65d-e07f-493c-9435-7a0f6189550d">try{(function(w,d){!function(bH,bI,bJ,bK){if(bH.zaraz)console.error("zaraz is loaded twice");else{bH[bJ]=bH[bJ]||{};bH[bJ].executed=[];bH.zaraz={deferred:[],listeners:[]};bH.zaraz._v="5876";bH.zaraz._n="02e9b65d-e07f-493c-9435-7a0f6189550d";bH.zaraz.q=[];bH.zaraz._f=function(bL){return async function(){var bM=Array.prototype.slice.call(arguments);bH.zaraz.q.push({m:bL,a:bM})}};for(const bN of["track","set","debug"])bH.zaraz[bN]=bH.zaraz._f(bN);bH.zaraz.init=()=>{var bO=bI.getElementsByTagName(bK)[0],bP=bI.createElement(bK),bQ=bI.getElementsByTagName("title")[0];bQ&&(bH[bJ].t=bI.getElementsByTagName("title")[0].text);bH[bJ].x=Math.random();bH[bJ].w=bH.screen.width;bH[bJ].h=bH.screen.height;bH[bJ].j=bH.innerHeight;bH[bJ].e=bH.innerWidth;bH[bJ].l=bH.location.href;bH[bJ].r=bI.referrer;bH[bJ].k=bH.screen.colorDepth;bH[bJ].n=bI.characterSet;bH[bJ].o=(new Date).getTimezoneOffset();if(bH.dataLayer)for(const bR of Object.entries(Object.entries(dataLayer).reduce((bS,bT)=>({...bS[1],...bT[1]}),{})))zaraz.set(bR[0],bR[1],{scope:"page"});bH[bJ].q=[];for(;bH.zaraz.q.length;){const bU=bH.zaraz.q.shift();bH[bJ].q.push(bU)}bP.defer=!0;for(const bV of[localStorage,sessionStorage])Object.keys(bV||{}).filter(bX=>bX.startsWith("_zaraz_")).forEach(bW=>{try{bH[bJ]["z_"+bW.slice(7)]=JSON.parse(bV.getItem(bW))}catch{bH[bJ]["z_"+bW.slice(7)]=bV.getItem(bW)}});bP.referrerPolicy="origin";bP.src="/cdn-cgi/zaraz/s.js?z="+btoa(encodeURIComponent(JSON.stringify(bH[bJ])));bO.parentNode.insertBefore(bP,bO)};["complete","interactive"].includes(bI.readyState)?zaraz.init():bH.addEventListener("DOMContentLoaded",zaraz.init)}}(w,d,"zarazData","script");window.zaraz._p=async bc=>new Promise(bd=>{if(bc){bc.e&&bc.e.forEach(be=>{try{const bf=d.querySelector("script[nonce]"),bg=bf?.nonce||bf?.getAttribute("nonce"),bh=d.createElement("script");bg&&(bh.nonce=bg);bh.innerHTML=be;bh.onload=()=>{d.head.removeChild(bh)};d.head.appendChild(bh)}catch(bi){console.error(`Error executing script: ${be}\n`,bi)}});Promise.allSettled((bc.f||[]).map(bj=>fetch(bj[0],bj[1])))}bd()});zaraz._p({"e":["(function(w,d){})(window,document)"]});})(window,document)}catch(e){throw fetch("/cdn-cgi/zaraz/t"),e;};</script></head>
<body class="antialiased min-h-screen flex flex-col bg-slate-50 relative selection:bg-blue-500 selection:text-white">

    <!-- Ambient Background Blobs -->
    <div class="fixed inset-0 pointer-events-none overflow-hidden -z-10">
        <div class="absolute top-0 left-1/4 w-96 h-96 bg-blue-400 rounded-full mix-blend-multiply filter blur-3xl opacity-20 animate-blob"></div>
        <div class="absolute top-0 right-1/4 w-96 h-96 bg-purple-400 rounded-full mix-blend-multiply filter blur-3xl opacity-20 animate-blob animation-delay-2000"></div>
        <div class="absolute -bottom-8 left-1/3 w-96 h-96 bg-pink-400 rounded-full mix-blend-multiply filter blur-3xl opacity-20 animate-blob animation-delay-4000"></div>
    </div>

    <div id="app" v-cloak class="relative flex-1 flex flex-col">
        
        <!-- HEADER -->
        <header class="fixed w-full top-0 z-50 transition-all duration-300" :class="{'glass-panel shadow-sm': scrolled, 'bg-transparent py-4': !scrolled}">
            <div class="max-w-7xl mx-auto px-4 lg:px-8 flex items-center justify-between h-16">
                <!-- Logo -->
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 bg-slate-900 rounded-xl flex items-center justify-center text-white shadow-lg shadow-blue-500/20 ring-4 ring-white/50">
                        <i class="ph-fill ph-apple-logo text-xl"></i>
                    </div>
                    <div>
                        <h1 class="font-bold text-base tracking-tight text-slate-900 leading-none mb-0.5">Apple ID Store</h1>
                        <div class="flex items-center gap-1.5">
                            <span class="relative flex h-2 w-2">
                                <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
                                <span class="relative inline-flex rounded-full h-2 w-2 bg-emerald-500"></span>
                            </span>
                            <span class="text-[10px] font-bold uppercase tracking-wider text-slate-500">Online</span>
                        </div>
                    </div>
                </div>

                <!-- Actions -->
                <div class="flex items-center gap-3">
                    <button @click="showGuide = true" class="group flex items-center gap-2 bg-white/80 hover:bg-white backdrop-blur px-4 py-2 rounded-full border border-slate-200 hover:border-blue-300 transition-all shadow-sm">
                        <div class="w-6 h-6 rounded-full bg-blue-50 text-blue-600 flex items-center justify-center group-hover:scale-110 transition-transform">
                            <i class="ph-bold ph-book-open text-xs"></i>
                        </div>
                        <span class="text-xs font-bold text-slate-700">Hướng dẫn</span>
                    </button>
                    
                    <a href="https://t.me/your_telegram" target="_blank" class="hidden sm:flex items-center gap-2 bg-slate-900 text-white px-5 py-2 rounded-full text-xs font-bold hover:bg-blue-600 hover:shadow-lg hover:shadow-blue-500/30 transition-all transform hover:-translate-y-0.5">
                        <i class="ph-bold ph-telegram-logo text-lg"></i>
                        <span>Liên hệ</span>
                    </a>
                </div>
            </div>
        </header>

        <!-- MAIN CONTENT -->
        <main class="flex-1 pt-32 pb-16 px-4 lg:px-8 max-w-7xl mx-auto w-full">
            
            <!-- HERO SECTION -->
            <div class="text-center mb-16 relative">
                <span class="inline-block py-1 px-3 rounded-full bg-blue-50 border border-blue-100 text-blue-600 text-[10px] font-bold uppercase tracking-widest mb-4 animate-fade-in-up">
                    Premium Accounts                </span>
                <h2 class="text-4xl md:text-5xl lg:text-6xl font-extrabold tracking-tight text-slate-900 mb-6 animate-fade-in-up delay-100">
                     <br class="hidden md:block" />
                    <span class="bg-clip-text text-transparent bg-gradient-to-r from-blue-600 via-purple-600 to-pink-600">ID Apple Miễn Phí</span>
                </h2>
                <div class="max-w-2xl mx-auto backdrop-blur-sm bg-white/30 rounded-2xl p-4 border border-white/50 shadow-sm animate-fade-in-up delay-200">
                     <p class="text-slate-600 text-sm md:text-base font-medium leading-relaxed">
                        HỆ THỐNG ID CHẤT LƯỢNG 5GSIEUTOCDO.COM                    </p>
                    <div class="mt-3 flex items-center justify-center gap-4 text-xs font-mono text-slate-400">
                         <span class="flex items-center gap-1.5"><i class="ph-fill ph-arrows-clockwise text-blue-500"></i> Auto Update: 10s</span>
                         <span class="flex items-center gap-1.5"><i class="ph-fill ph-users text-purple-500"></i> Total: {{ accounts.length }}</span>
                    </div>
                </div>
            </div>

            <!-- SEARCH BAR -->
            <div class="max-w-md mx-auto mb-12 relative group z-10 animate-fade-in-up delay-300">
                <div class="absolute inset-0 bg-gradient-to-r from-blue-500 to-purple-600 rounded-2xl blur opacity-20 group-hover:opacity-40 transition duration-500"></div>
                <div class="relative bg-white rounded-2xl shadow-xl flex items-center p-2">
                    <div class="pl-4 text-slate-400">
                        <i class="ph-bold ph-magnifying-glass text-xl"></i>
                    </div>
                    <input type="text" v-model="searchQuery" placeholder="Tìm kiếm quốc gia, email..." class="w-full bg-transparent border-none focus:ring-0 text-sm font-medium text-slate-700 placeholder-slate-400 px-4 py-3 h-full">
                    <button @click="fetchData" :class="{'animate-spin': loading}" class="p-3 bg-slate-50 hover:bg-slate-100 rounded-xl text-slate-500 transition-colors">
                        <i class="ph-bold ph-arrows-clockwise"></i>
                    </button>
                </div>
            </div>

            <!-- LOADING SKELETON -->
            <div v-if="loading && accounts.length === 0" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div v-for="n in 6" :key="n" class="bg-white rounded-3xl p-6 border border-slate-100 h-56 animate-pulse shadow-sm">
                    <div class="flex items-center gap-4 mb-6">
                        <div class="w-10 h-10 bg-slate-100 rounded-full"></div>
                        <div class="h-4 bg-slate-100 rounded w-32"></div>
                    </div>
                    <div class="space-y-4">
                        <div class="h-12 bg-slate-100 rounded-xl"></div>
                        <div class="h-12 bg-slate-100 rounded-xl"></div>
                    </div>
                </div>
            </div>

            <!-- ACCOUNTS GRID -->
            <div v-else-if="filteredAccounts.length > 0" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div v-for="(acc, index) in filteredAccounts" :key="index" class="card-premium rounded-3xl p-6 relative overflow-hidden group animate-fade-in-up" :style="{ animationDelay: (index * 100) + 'ms' }">
                    
                    <!-- ID Badge -->
                    <div class="absolute top-0 right-0 bg-slate-50 px-4 py-2 rounded-bl-2xl border-b border-l border-slate-100 text-[10px] font-bold text-slate-400">
                        #{{ acc.id || index+1 }}
                    </div>

                    <!-- Header: Country -->
                    <div class="flex items-center gap-4 mb-6">
                        <div class="relative">
                            <div class="absolute inset-0 bg-blue-500 rounded-xl blur opacity-20"></div>
                            <img v-if="acc.flag" :src="acc.flag" class="w-12 h-8 object-cover rounded-lg shadow-sm relative z-10" alt="flag">
                            <div v-else class="w-12 h-8 bg-slate-200 rounded-lg relative z-10"></div>
                        </div>
                        <div>
                            <span class="block text-xs font-bold text-slate-400 uppercase tracking-wider mb-0.5">Quốc gia</span>
                            <h3 class="text-base font-bold text-slate-800">{{ acc.country || 'Unknown' }}</h3>
                        </div>
                    </div>

                    <!-- Content -->
                    <div class="space-y-4">
                        <!-- Email -->
                        <div class="group/field">
                            <label class="text-[10px] uppercase font-bold text-slate-400 pl-1 mb-1 block">Tài khoản</label>
                            <div class="flex items-center bg-slate-50 hover:bg-white border border-slate-200 hover:border-blue-500/50 p-1.5 rounded-2xl transition-all shadow-sm">
                                <div class="w-10 h-10 bg-white rounded-xl flex items-center justify-center text-blue-500 shadow-sm border border-slate-100 shrink-0">
                                    <i class="ph-duotone ph-envelope-simple text-lg"></i>
                                </div>
                                <input type="text" readonly :value="acc.email" class="w-full bg-transparent border-none text-xs font-semibold text-slate-700 px-3 truncate focus:ring-0 cursor-text select-all">
                                <button @click="copy(acc.email)" class="w-10 h-10 hover:bg-blue-50 text-slate-400 hover:text-blue-600 rounded-xl flex items-center justify-center transition-colors">
                                    <i class="ph-bold ph-copy"></i>
                                </button>
                            </div>
                        </div>

                        <!-- Password -->
                        <div class="group/field">
                            <label class="text-[10px] uppercase font-bold text-slate-400 pl-1 mb-1 block">Mật khẩu</label>
                            <div class="flex items-center bg-slate-50 hover:bg-white border border-slate-200 hover:border-purple-500/50 p-1.5 rounded-2xl transition-all shadow-sm">
                                <div class="w-10 h-10 bg-white rounded-xl flex items-center justify-center text-purple-500 shadow-sm border border-slate-100 shrink-0">
                                    <i class="ph-duotone ph-lock-key text-lg"></i>
                                </div>
                                <input type="text" readonly value="••••••••" class="w-full bg-transparent border-none text-xs font-bold text-slate-700 px-3 tracking-widest focus:ring-0 cursor-default">
                                <button @click="copy(acc.password)" class="px-4 h-10 bg-slate-900 hover:bg-purple-600 text-white rounded-xl text-[10px] font-bold transition-all shadow-lg shadow-purple-500/20 active:scale-95 flex items-center gap-2">
                                    <span>COPY</span>
                                    <i class="ph-bold ph-copy-simple"></i>
                                </button>
                            </div>
                        </div>
                    </div>

                    <!-- Footer -->
                    <div class="mt-6 flex items-center justify-between">
                         <div class="flex items-center gap-1.5 text-[10px] font-bold text-slate-400 bg-slate-50 px-2 py-1 rounded-lg">
                            <i class="ph-fill ph-clock-counter-clockwise"></i>
                            {{ cleanTime(acc.last_updated) }}
                        </div>
                        <div class="flex items-center gap-1 text-[10px] font-bold text-emerald-600 bg-emerald-50 px-2 py-1 rounded-lg border border-emerald-100">
                             <span class="relative flex h-1.5 w-1.5 mr-1">
                                <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
                                <span class="relative inline-flex rounded-full h-1.5 w-1.5 bg-emerald-500"></span>
                            </span>
                            LIVE
                        </div>
                    </div>
                </div>
            </div>

            <!-- EMPTY STATE -->
            <div v-else class="text-center py-24 relative z-10">
                <div class="w-20 h-20 bg-white rounded-3xl shadow-xl flex items-center justify-center mx-auto mb-6 ring-8 ring-white/50">
                    <i class="ph-duotone ph-ghost text-4xl text-slate-300"></i>
                </div>
                <h3 class="text-xl font-bold text-slate-800 mb-2">Chưa có dữ liệu</h3>
                <p class="text-slate-500 text-sm mb-6 max-w-xs mx-auto">Hệ thống đang cập nhật hoặc kết nối gián đoạn. Vui lòng thử lại.</p>
                <button @click="fetchData" class="px-8 py-3 bg-slate-900 text-white rounded-2xl text-sm font-bold hover:bg-blue-600 transition-all shadow-lg hover:shadow-blue-500/30">
                    <i class="ph-bold ph-arrows-clockwise mr-2"></i> Tải lại trang
                </button>
            </div>
        </main>

        <!-- FOOTER -->
        <footer class="py-8 text-center border-t border-slate-200/60 bg-white/50 backdrop-blur-sm">
            <div class="flex items-center justify-center gap-2 mb-2 text-slate-900 font-bold">
                 <i class="ph-fill ph-apple-logo text-xl"></i>
                 <span>Apple ID Store</span>
            </div>
            <p class="text-xs text-slate-400 font-medium">&copy; 2026 All rights reserved.</p>
        </footer>

        <!-- GUIDE POPUP MODAL -->
        <transition name="fade">
            <div v-if="showGuide" class="fixed inset-0 z-[100] flex items-center justify-center p-4">
                <div @click="closeGuide" class="absolute inset-0 bg-slate-900/60 backdrop-blur-sm transition-opacity"></div>
                
                <div class="relative bg-white rounded-[2rem] w-full max-w-lg shadow-2xl overflow-hidden flex flex-col max-h-[90vh] animate-fade-in-up">
                    <div class="p-6 border-b border-slate-100 flex items-center justify-between bg-slate-50/50">
                        <div class="flex items-center gap-3">
                            <div class="w-10 h-10 rounded-full bg-blue-50 text-blue-600 flex items-center justify-center">
                                <i class="ph-duotone ph-book-open-text text-xl"></i>
                            </div>
                            <div>
                                <h3 class="font-bold text-lg text-slate-800">Hướng dẫn sử dụng</h3>
                                <p class="text-xs text-slate-400 font-medium">Đọc kỹ để sử dụng an toàn</p>
                            </div>
                        </div>
                        <button @click="closeGuide" class="w-8 h-8 rounded-full bg-slate-100 hover:bg-slate-200 flex items-center justify-center text-slate-500 transition-colors">
                            <i class="ph-bold ph-x"></i>
                        </button>
                    </div>

                    <div class="p-6 overflow-y-auto">
                        <div class="space-y-6">
                            <!-- Image -->
                            <div class="rounded-2xl overflow-hidden shadow-lg ring-4 ring-slate-50">
                                <img src="https://loadipvpn.site/upload/uploads/img_7206b2a0fe.png" class="w-full h-auto object-cover" alt="Guide">
                            </div>

                            <!-- Steps -->
                            <div class="space-y-3">
                                <div class="flex gap-4">
                                    <div class="w-8 h-8 rounded-full bg-slate-900 text-white flex items-center justify-center shrink-0 font-bold text-sm">1</div>
                                    <p class="text-sm text-slate-600 pt-1.5"><strong class="text-slate-900">Đăng xuất</strong> tài khoản cũ trên App Store.</p>
                                </div>
                                <div class="flex gap-4">
                                    <div class="w-8 h-8 rounded-full bg-slate-900 text-white flex items-center justify-center shrink-0 font-bold text-sm">2</div>
                                    <p class="text-sm text-slate-600 pt-1.5"><strong class="text-slate-900">Sao chép</strong> Email & Mật khẩu ở trang này và đăng nhập.</p>
                                </div>
                                <div class="flex gap-4">
                                    <div class="w-8 h-8 rounded-full bg-slate-900 text-white flex items-center justify-center shrink-0 font-bold text-sm">3</div>
                                    <p class="text-sm text-slate-600 pt-1.5">Chọn <strong>"Các lựa chọn khác"</strong> -> <strong>"Không nâng cấp"</strong>.</p>
                                </div>
                            </div>

                            <!-- Warning -->
                            <div class="bg-red-50 text-red-800 p-4 rounded-2xl text-sm border border-red-100 flex gap-3 shadow-sm">
                                <i class="ph-fill ph-warning-octagon text-2xl shrink-0 text-red-500"></i>
                                <div>
                                    <h4 class="font-bold text-red-900 mb-1">CẢNH BÁO QUAN TRỌNG</h4>
                                    <p class="opacity-90 leading-relaxed">Tuyệt đối <strong>KHÔNG</strong> đăng nhập vào iCloud (Cài đặt) để tránh bị khóa máy vĩnh viễn.</p>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="p-4 border-t border-slate-100 bg-slate-50/50">
                        <button @click="closeGuide" class="w-full py-3.5 bg-slate-900 text-white font-bold rounded-xl hover:bg-blue-600 transition-all shadow-lg shadow-slate-900/20 active:scale-95">
                            Tôi đã hiểu, bắt đầu thôi!
                        </button>
                    </div>
                </div>
            </div>
        </transition>

        <!-- TOAST -->
        <div class="fixed top-24 right-4 z-50">
            <transition-group name="list" tag="div" class="flex flex-col gap-3">
                <div v-if="toast.show" class="bg-slate-900 text-white pl-4 pr-6 py-3 rounded-2xl shadow-xl flex items-center gap-3 animate-fade-in-up border border-white/10">
                    <div class="w-8 h-8 bg-green-500 rounded-full flex items-center justify-center shrink-0 text-slate-900">
                        <i class="ph-bold ph-check"></i>
                    </div>
                    <div>
                        <h5 class="font-bold text-sm">Thành công</h5>
                        <p class="text-xs text-slate-300">{{ toast.message }}</p>
                    </div>
                </div>
            </transition-group>
        </div>

    </div>

    <!-- SCRIPT -->
    <script type="e9fa4ba069feb37efaaceb7b-text/javascript">
        const { createApp } = Vue;

        // SERVER DATA
        const SERVER_DATA = [{"flag":"https:\/\/flagcdn.com\/w40\/vn.png","country":"Vi\u1ec7t Nam","email":"nezihatronja8198@outlook.com","password":"@@6iEais","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 1 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #1"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"cyrill_gardie@outlook.sa","password":"f0w!94DG","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 2 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #2"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"hirijeannma7033@outlook.com","password":"O&oNHGq4","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 10 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #3"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"domingajazmi9423@outlook.com","password":"qrZ#88yU","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 16 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #4"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"ashermendez4so@outlook.com","password":"TDWAE9GctYhB","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 17 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #5"},{"flag":"https:\/\/flagcdn.com\/w40\/vn.png","country":"Vi\u1ec7t Nam","email":"wilmadaywaltqv@hotmail.com","password":"TDv3fxK4bWmD","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 17 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #6"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"ethanxxm18763@icloud.com","password":"CZv3t4Yxva","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 17 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #7"},{"flag":"https:\/\/flagcdn.com\/w40\/hk.png","country":"H\u1ed3ng K\u00f4ng","email":"philipmrg85504@icloud.com","password":"8pz3r5nQFS","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 17 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #8"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"\u7f8e\u56fd","email":"ni2ch9o2br4o@icloud.com","password":"WVQses6BwU","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 18 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #9"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"li633563763@icloud.com","password":"CFbQHpS1WE","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 18 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #10"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"jack.asherdfq274@icloud.com","password":"uiMX#fT0","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 18 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #11"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"carterhuxuhen@outlook.com","password":"TDBnUMSdu4h2","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 18 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #12"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"waylandnailah@gmail.com","password":"TD39CDK2CzYf","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 19 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #13"},{"flag":"https:\/\/flagcdn.com\/w40\/jp.png","country":"Nh\u1eadt B\u1ea3n","email":"8@kuaiyun1.com","password":"MfeyWbW9WQ","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 19 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #14"},{"flag":"https:\/\/flagcdn.com\/w40\/au.png","country":"\u00dac","email":"wu985826536225@icloud.com","password":"aaKbbj75UA","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 19 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #15"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"dujgkvq499266@icloud.com","password":"kNYn5gSSMx","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 21 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #16"},{"flag":"https:\/\/flagcdn.com\/w40\/jp.png","country":"Nh\u1eadt B\u1ea3n","email":"6@kuaiyun1.com","password":"PPH7QumfbQ","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 21 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #17"},{"flag":"https:\/\/flagcdn.com\/w40\/tw.png","country":"\u0110\u00e0i Loan","email":"7@kuaiyun1.com","password":"j3TkW2j5Rg","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 21 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #18"},{"flag":"https:\/\/flagcdn.com\/w40\/hk.png","country":"H\u1ed3ng K\u00f4ng","email":"gn0o6gevrd0fu1ejm1@icloud.com","password":"68RZdsrH5W","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 22 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #19"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"13@kuaiyun1.com","password":"stC3txV542","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 23 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #20"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"bi5rap1mp36sk0wz0sa@icloud.com","password":"DkykWd8ze2","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 23 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #21"},{"flag":"https:\/\/flagcdn.com\/w40\/kr.png","country":"H\u00e0n Qu\u1ed1c","email":"doirupkumbm4qybcih@icloud.com","password":"r38rx5Z4kg","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 23 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #22"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"2@kuaiyun1.com","password":"KpPY88MsRh","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 23 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #23"},{"flag":"https:\/\/flagcdn.com\/w40\/tw.png","country":"\u0110\u00e0i Loan","email":"irlong.lsoz252@icloud.com","password":"bVZ2587kM3","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 24 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #24"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"geridominiqu9281@outlook.com","password":"TdS!M28v","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 25 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #25"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"ihsivupa378@outlook.com","password":"@w9AreUs","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 25 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #26"},{"flag":"https:\/\/flagcdn.com\/w40\/cn.png","country":"Trung Qu\u1ed1c","email":"victorqkf61067@icloud.com","password":"YDZE2Kgvdy","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 25 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #27"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"ypsphwigu0ui1ryru6@icloud.com","password":"7w7y2kP6vf","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 27 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #28"},{"flag":"https:\/\/flagcdn.com\/w40\/hk.png","country":"H\u1ed3ng K\u00f4ng","email":"xq4x0zo65nrxw3jj@icloud.com","password":"UrTG6JtCpV","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 27 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #29"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"etzgemcx253vmcmd@icloud.com","password":"G2GQtW8dKY","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 28 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #30"},{"flag":"https:\/\/flagcdn.com\/w40\/jp.png","country":"Nh\u1eadt B\u1ea3n","email":"kdi5vzw153sxdb2akc@icloud.com","password":"vrwYKD3vdA","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 29 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #31"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"wyattu5kznelson@outlook.com","password":"TDyxz1SF9j3K","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 29 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #32"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"eliasu2riley@outlook.com","password":"TDUud8gbbqgX","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 30 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #33"},{"flag":"https:\/\/flagcdn.com\/w40\/jp.png","country":"Nh\u1eadt B\u1ea3n","email":"9@kuaiyun1.com","password":"jtC5n9Ntrg","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 30 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #34"},{"flag":"https:\/\/flagcdn.com\/w40\/cn.png","country":"Trung Qu\u1ed1c","email":"lindafkl33302@icloud.com","password":"w24N3fcyxy","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 30 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #35"},{"flag":"https:\/\/flagcdn.com\/w40\/kr.png","country":"H\u00e0n Qu\u1ed1c","email":"sadrszk050552@icloud.com","password":"Pxy2kppHtF","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 33 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #36"},{"flag":"https:\/\/flagcdn.com\/w40\/tw.png","country":"\u0110\u00e0i Loan","email":"huai284600975@icloud.com","password":"YF9rCJnWuE","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 35 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #37"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"julianmauhudson@outlook.com","password":"TDSSuCdSWZ5u","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 36 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #38"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"renatahadnotqw@hotmail.com","password":"TD1JcYprKwCU","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 41 Ph\u00fat Tr\u01b0\u1edbc","id":"ID: #39"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"marisolyml41086@icloud.com","password":"fT1rvfuCFd","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 1 Gi\u1edd Tr\u01b0\u1edbc","id":"ID: #40"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"janetteqvg91520@icloud.com","password":"SFcHAjN5qF","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 1 Gi\u1edd Tr\u01b0\u1edbc","id":"ID: #41"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"cmxwade10912@icloud.com","password":"zT3t4vaEdT","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 1 Gi\u1edd Tr\u01b0\u1edbc","id":"ID: #42"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"josephjid91802@icloud.com","password":"bKm64Atctg","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 1 Gi\u1edd Tr\u01b0\u1edbc","id":"ID: #43"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"3@kuaiyun1.com","password":"DRgquD8zYc","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 1 Gi\u1edd Tr\u01b0\u1edbc","id":"ID: #44"},{"flag":"https:\/\/flagcdn.com\/w40\/hk.png","country":"H\u1ed3ng K\u00f4ng","email":"owenajosephxi880@icloud.com","password":"34tY9ZUpcy","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 1 Gi\u1edd Tr\u01b0\u1edbc","id":"ID: #45"},{"flag":"https:\/\/flagcdn.com\/w40\/jp.png","country":"Nh\u1eadt B\u1ea3n","email":"michaeld.thomas7619@icloud.com","password":"wWKbWV938w","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 1 Gi\u1edd Tr\u01b0\u1edbc","id":"ID: #46"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"luca.leviy4736@icloud.com","password":"CKFg9cSXXj","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 1 Gi\u1edd Tr\u01b0\u1edbc","id":"ID: #47"},{"flag":"https:\/\/flagcdn.com\/w40\/in.png","country":"\u1ea4n \u0110\u1ed9","email":"elizabethkry31289@icloud.com","password":"2Y5WJhpUsW","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 2 Gi\u1edd Tr\u01b0\u1edbc","id":"ID: #48"},{"flag":"https:\/\/flagcdn.com\/w40\/us.png","country":"Hoa K\u1ef3","email":"cfodlrvdco192@outlook.com","password":"1aGd1tW#","last_updated":"\ud83d\udd52 C\u1eadp nh\u1eadt: 5 Gi\u1edd Tr\u01b0\u1edbc","id":"ID: #49"}];

        createApp({
            data() {
                return {
                    accounts: SERVER_DATA || [],
                    loading: false,
                    searchQuery: '',
                    showGuide: false,
                    toast: { show: false, message: '' },
                    scrolled: false
                }
            },
            computed: {
                filteredAccounts() {
                    if (!this.searchQuery) return this.accounts;
                    const lower = this.searchQuery.toLowerCase();
                    return this.accounts.filter(acc => 
                        (acc.email && acc.email.toLowerCase().includes(lower)) ||
                        (acc.country && acc.country.toLowerCase().includes(lower))
                    );
                }
            },
            methods: {
                handleScroll() {
                    this.scrolled = window.scrollY > 20;
                },
                copy(text) {
                    if (!text) return;
                    navigator.clipboard.writeText(text).then(() => {
                        this.showToast('Đã sao chép vào bộ nhớ tạm!');
                    }).catch(() => {
                        // Fallback
                        const el = document.createElement('textarea');
                        el.value = text;
                        document.body.appendChild(el);
                        el.select();
                        document.execCommand('copy');
                        document.body.removeChild(el);
                        this.showToast('Đã sao chép thủ công!');
                    });
                },
                showToast(msg) {
                    this.toast.message = msg;
                    this.toast.show = true;
                    setTimeout(() => { this.toast.show = false; }, 3000);
                },
                closeGuide() {
                    this.showGuide = false;
                    localStorage.setItem('guide_seen_v3', 'true'); // New Version
                },
                cleanTime(str) {
                    if(!str) return 'Just now';
                    return str.replace('🕒', '').replace('Cập nhật:', '').trim();
                }
            },
            mounted() {
                window.addEventListener('scroll', this.handleScroll);
                if (!localStorage.getItem('guide_seen_v3')) {
                    this.showGuide = true;
                }
                setTimeout(() => { window.location.reload(); }, 60000);
            }
        }).mount('#app');
    </script>
<script src="/cdn-cgi/scripts/7d0fa10a/cloudflare-static/rocket-loader.min.js" data-cf-settings="e9fa4ba069feb37efaaceb7b-|49" defer></script><script defer src="https://static.cloudflareinsights.com/beacon.min.js/vcd15cbe7772f49c399c6a5babf22c1241717689176015" integrity="sha512-ZpsOmlRQV6y907TI0dKBHq9Md29nnaEIPlkf84rnaERnq6zvWvPUqr2ft8M1aS28oN72PdrCzSjY4U6VaAw1EQ==" data-cf-beacon='{"version":"2024.11.0","token":"8bd60584d28149468e93c33dd45fd257","r":1,"server_timing":{"name":{"cfCacheStatus":true,"cfEdge":true,"cfExtPri":true,"cfL4":true,"cfOrigin":true,"cfSpeedBrain":true},"location_startswith":null}}' crossorigin="anonymous"></script>
</body>
</html>
