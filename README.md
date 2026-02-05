<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Apple ID Store</title>

<!-- FONT -->
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">

<!-- TAILWIND -->
<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>

<!-- VUE -->
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>

<!-- ICON -->
<script src="https://unpkg.com/@phosphor-icons/web"></script>

<style>
body{font-family:Inter,sans-serif}
[v-cloak]{display:none}

/* Gradient title */
.gradient-text{
  background:linear-gradient(90deg,#2563eb,#7c3aed,#ec4899);
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
}

/* Glass */
.glass{
  background:rgba(255,255,255,.75);
  backdrop-filter:blur(20px);
  border:1px solid rgba(255,255,255,.4);
}

/* Card */
.card{
  background:white;
  border-radius:24px;
  border:1px solid #e5e7eb;
  transition:.25s;
}
.card:hover{
  transform:translateY(-6px);
  box-shadow:0 20px 40px rgba(0,0,0,.08);
}
</style>
</head>

<body class="bg-slate-50">

<div id="app" v-cloak>

<!-- HEADER -->
<header class="fixed top-0 w-full z-50 glass">
  <div class="max-w-7xl mx-auto px-4 h-16 flex justify-between items-center">
    <div class="flex items-center gap-3">
      <div class="w-10 h-10 bg-black rounded-xl flex items-center justify-center text-white">
        <i class="ph-fill ph-apple-logo text-xl"></i>
      </div>
      <div>
        <div class="font-bold">Apple ID Store</div>
        <div class="text-xs text-green-500 font-semibold">● ONLINE</div>
      </div>
    </div>
    <div class="flex gap-3">
      <button class="px-4 py-2 rounded-full border bg-white">Hướng dẫn</button>
      <button class="px-4 py-2 rounded-full bg-black text-white">Liên hệ</button>
    </div>
  </div>
</header>

<!-- HERO -->
<section class="pt-32 pb-16 text-center relative overflow-hidden">
  <h1 class="text-4xl md:text-6xl font-extrabold gradient-text">
    ID Apple Miễn Phí
  </h1>

  <div class="mt-6 max-w-xl mx-auto glass rounded-2xl p-5">
    <div class="font-semibold mb-2">
      HỆ THỐNG ID CHẤT LƯỢNG 5GSIEUTOCDO.COM
    </div>
    <div class="flex justify-center gap-6 text-sm text-slate-600">
      <span>🔄 Auto Update: 10s</span>
      <span>👥 Total: {{ accounts.length }}</span>
    </div>
  </div>

  <!-- SEARCH -->
  <div class="mt-12 max-w-xl mx-auto">
    <div class="flex items-center bg-white rounded-2xl shadow px-5 py-4">
      <i class="ph ph-magnifying-glass text-xl text-slate-400"></i>
      <input v-model="q" placeholder="Tìm kiếm quốc gia, email..."
       class="flex-1 outline-none px-3">
      <button @click="q=''" class="text-slate-400">
        <i class="ph ph-arrows-clockwise text-xl"></i>
      </button>
    </div>
  </div>
</section>

<!-- LIST -->
<section class="max-w-7xl mx-auto px-4 pb-20">
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">

    <div v-for="(a,i) in filtered" :key="i" class="card p-6">
      <div class="flex justify-between items-center mb-4">
        <div class="flex items-center gap-3">
          <img :src="a.flag" class="w-10 h-7 rounded">
          <div>
            <div class="text-xs text-slate-400">QUỐC GIA</div>
            <div class="font-bold">{{ a.country }}</div>
          </div>
        </div>
        <div class="text-xs text-slate-400">#ID: {{ i+1 }}</div>
      </div>

      <!-- EMAIL -->
      <div class="mb-4">
        <div class="text-xs text-slate-400 mb-1">TÀI KHOẢN</div>
        <div class="flex items-center gap-2 bg-slate-50 rounded-xl p-3">
          <i class="ph ph-envelope-simple text-blue-500"></i>
          <input readonly :value="a.email"
           class="flex-1 bg-transparent text-sm">
          <button @click="copy(a.email)">
            <i class="ph ph-copy"></i>
          </button>
        </div>
      </div>

      <!-- PASS -->
      <div>
        <div class="text-xs text-slate-400 mb-1">MẬT KHẨU</div>
        <div class="flex items-center gap-2 bg-slate-50 rounded-xl p-3">
          <i class="ph ph-lock text-purple-500"></i>
          <input readonly value="••••••••"
           class="flex-1 bg-transparent text-sm">
          <button @click="copy(a.password)"
           class="px-3 py-2 bg-black text-white rounded-lg text-xs">
           COPY
          </button>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- TOAST -->
<div v-if="toast"
 class="fixed top-24 right-4 bg-black text-white px-4 py-3 rounded-xl">
 {{ toast }}
</div>

</div>

<script>
const {createApp}=Vue;

createApp({
data(){
return{
 q:'',
 toast:'',
 accounts:[
  {
   country:'Hoa Kỳ',
   flag:'https://flagcdn.com/w40/us.png',
   email:'hirijeannma7033@outlook.com',
   password:'12345678'
  },
  {
   country:'Việt Nam',
   flag:'https://flagcdn.com/w40/vn.png',
   email:'nezihatronja8198@outlook.com',
   password:'12345678'
  },
  {
   country:'Hoa Kỳ',
   flag:'https://flagcdn.com/w40/us.png',
   email:'julianmauhudson@outlook.com',
   password:'12345678'
  }
 ]
}},
computed:{
 filtered(){
  if(!this.q) return this.accounts;
  const t=this.q.toLowerCase();
  return this.accounts.filter(a =>
   a.email.toLowerCase().includes(t) ||
   a.country.toLowerCase().includes(t)
  );
 }
},
methods:{
 copy(v){
  navigator.clipboard.writeText(v);
  this.toast='Đã sao chép!';
  setTimeout(()=>this.toast='',2000);
 }
}
}).mount('#app');
</script>

</body>
</html>
