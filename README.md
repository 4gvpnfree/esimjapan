<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Apple ID Store</title>

<!-- FONT -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

<!-- TAILWIND -->
<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>

<!-- VUE 3 -->
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>

<!-- ICONS -->
<script src="https://unpkg.com/@phosphor-icons/web"></script>

<style>
[v-cloak]{display:none}
body{font-family:'Plus Jakarta Sans',sans-serif;background:#f8fafc}

/* Glass */
.glass-panel{
  background:rgba(255,255,255,.7);
  backdrop-filter:blur(20px);
  border:1px solid rgba(255,255,255,.5)
}
.card-premium{
  background:rgba(255,255,255,.9);
  border:1px solid rgba(226,232,240,.6);
  transition:.3s
}
.card-premium:hover{
  transform:translateY(-4px);
  box-shadow:0 20px 40px -5px rgba(59,130,246,.15)
}

/* Anim */
@keyframes blob{
  0%,100%{transform:translate(0,0) scale(1)}
  33%{transform:translate(30px,-50px) scale(1.1)}
  66%{transform:translate(-20px,20px) scale(.9)}
}
.animate-blob{animation:blob 7s infinite}
.animation-delay-2000{animation-delay:2s}
.animation-delay-4000{animation-delay:4s}
</style>
</head>

<body class="min-h-screen">

<div id="app" v-cloak class="relative flex flex-col min-h-screen">

<!-- HEADER -->
<header class="fixed w-full top-0 z-50 transition"
:class="scrolled?'glass-panel shadow':'bg-transparent py-4'">
  <div class="max-w-7xl mx-auto px-4 h-16 flex justify-between items-center">
    <div class="flex items-center gap-3">
      <div class="w-10 h-10 bg-black rounded-xl flex items-center justify-center text-white">
        <i class="ph-fill ph-apple-logo text-xl"></i>
      </div>
      <div>
        <h1 class="font-bold">Apple ID Store</h1>
        <span class="text-xs text-green-500 font-bold">● Online</span>
      </div>
    </div>
    <button @click="showGuide=true"
      class="px-4 py-2 bg-white rounded-full text-sm shadow">
      Hướng dẫn
    </button>
  </div>
</header>

<!-- MAIN -->
<main class="flex-1 pt-28 px-4 max-w-7xl mx-auto w-full">

<!-- SEARCH -->
<div class="max-w-md mx-auto mb-10">
  <input v-model="searchQuery"
    placeholder="Tìm email hoặc quốc gia..."
    class="w-full px-5 py-3 rounded-xl shadow border">
</div>

<!-- GRID -->
<div v-if="filteredAccounts.length"
 class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">

  <div v-for="(acc,i) in filteredAccounts"
   :key="i"
   class="card-premium rounded-3xl p-6">

    <div class="flex items-center gap-3 mb-4">
      <img :src="acc.flag" class="w-10 h-6 rounded">
      <strong>{{ acc.country }}</strong>
    </div>

    <div class="space-y-3">
      <div class="flex items-center gap-2">
        <input readonly :value="acc.email"
         class="flex-1 bg-slate-100 px-3 py-2 rounded text-xs">
        <button @click="copy(acc.email)">📋</button>
      </div>

      <div class="flex items-center gap-2">
        <input readonly value="••••••••"
         class="flex-1 bg-slate-100 px-3 py-2 rounded text-xs">
        <button @click="copy(acc.password)"
         class="px-3 py-2 bg-black text-white rounded text-xs">
         COPY
        </button>
      </div>
    </div>

    <div class="mt-4 text-xs text-slate-500">
      {{ cleanTime(acc.last_updated) }}
    </div>
  </div>
</div>

<div v-else class="text-center py-20 text-slate-400">
  Không có dữ liệu
</div>

</main>

<!-- GUIDE -->
<div v-if="showGuide"
 class="fixed inset-0 bg-black/50 flex items-center justify-center z-50">
  <div class="bg-white rounded-2xl p-6 max-w-md w-full">
    <h3 class="font-bold mb-3">Hướng dẫn</h3>
    <p class="text-sm text-slate-600 mb-4">
      Chỉ đăng nhập App Store – không đăng nhập iCloud.
    </p>
    <button @click="showGuide=false"
     class="w-full py-3 bg-black text-white rounded-xl">
     Đã hiểu
    </button>
  </div>
</div>

<!-- TOAST -->
<div v-if="toast.show"
 class="fixed top-24 right-4 bg-black text-white px-4 py-3 rounded-xl">
 {{ toast.message }}
</div>

</div>

<script>
const {createApp}=Vue;

const SERVER_DATA = <?= "DỮ LIỆU CỦA BẠN GIỮ NGUYÊN – KHÔNG SỬA" ?>;
</script>

<script>
createApp({
data(){
return{
 accounts: SERVER_DATA,
 searchQuery:'',
 showGuide:false,
 toast:{show:false,message:''},
 scrolled:false
}},
computed:{
 filteredAccounts(){
  if(!this.searchQuery) return this.accounts;
  const q=this.searchQuery.toLowerCase();
  return this.accounts.filter(a =>
    a.email.toLowerCase().includes(q) ||
    a.country.toLowerCase().includes(q)
  );
 }
},
methods:{
 copy(t){
  navigator.clipboard.writeText(t);
  this.toast={show:true,message:'Đã sao chép!'};
  setTimeout(()=>this.toast.show=false,2000);
 },
 cleanTime(s){
  return s.replace(/🕒|Cập nhật:/g,'').trim();
 },
 onScroll(){
  this.scrolled=window.scrollY>20;
 }
},
mounted(){
 window.addEventListener('scroll',this.onScroll);
}
}).mount('#app');
</script>

</body>
</html>
