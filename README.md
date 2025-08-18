<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>আমার শপ | হোম</title>

  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Font Awesome for icons -->
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" rel="stylesheet"/>

  <style>
    /* custom scrollbar (optional) */
    ::-webkit-scrollbar{height:6px;width:6px}
    ::-webkit-scrollbar-thumb{background:#e5e7eb;border-radius:9999px}
    .shadow-card{box-shadow:0 6px 18px rgba(0,0,0,.06)}
  </style>
</head>
<body class="bg-[#f6f7fb] text-gray-800">

  <!-- Top search bar -->
  <header class="sticky top-0 z-30 bg-white/95 backdrop-blur border-b border-gray-100">
    <div class="max-w-6xl mx-auto px-3 py-3 flex items-center gap-3">
      <a href="#" class="text-2xl font-black text-orange-500">দোকান</a>
      <div class="flex-1">
        <div class="flex items-center gap-2 rounded-full border border-gray-200 px-4 py-2">
          <i class="fa-solid fa-magnifying-glass text-gray-400"></i>
          <input class="flex-1 outline-none text-sm" placeholder="পণ্য সার্চ করুন…" />
          <i class="fa-solid fa-microphone text-gray-400"></i>
          <i class="fa-regular fa-image text-gray-400"></i>
        </div>
      </div>
      <a class="hidden sm:flex items-center gap-2 text-sm text-gray-600" href="#"><i class="fa-regular fa-user"></i> লগইন</a>
    </div>
  </header>

  <main class="max-w-6xl mx-auto px-3 pb-24">

    <!-- Banner slider -->
    <section class="mt-3">
      <div class="relative overflow-hidden rounded-2xl shadow-card">
        <div id="slides" class="whitespace-nowrap transition-all duration-500">
          <img class="inline-block w-full h-40 sm:h-56 object-cover" src="https://picsum.photos/1200/400?random=11" alt="">
          <img class="inline-block w-full h-40 sm:h-56 object-cover" src="https://picsum.photos/1200/400?random=12" alt="">
          <img class="inline-block w-full h-40 sm:h-56 object-cover" src="https://picsum.photos/1200/400?random=13" alt="">
        </div>
        <div class="absolute inset-x-0 bottom-2 flex justify-center gap-2">
          <button class="dot w-2 h-2 rounded-full bg-white/70"></button>
          <button class="dot w-2 h-2 rounded-full bg-white/40"></button>
          <button class="dot w-2 h-2 rounded-full bg-white/40"></button>
        </div>
      </div>
    </section>

    <!-- Quick categories -->
    <section class="mt-5 grid grid-cols-4 sm:grid-cols-8 gap-3">
      <!-- item -->
      <a class="bg-white rounded-xl p-3 shadow-card flex flex-col items-center gap-2" href="#">
        <span class="w-10 h-10 grid place-content-center rounded-xl bg-orange-50 text-orange-500"><i class="fa-solid fa-bolt"></i></span>
        <span class="text-xs text-center font-medium">৯৯% OFF</span>
      </a>
      <a class="bg-white rounded-xl p-3 shadow-card flex flex-col items-center gap-2" href="#">
        <span class="w-10 h-10 grid place-content-center rounded-xl bg-lime-50 text-lime-600"><i class="fa-solid fa-truck-fast"></i></span>
        <span class="text-xs text-center font-medium">ফ্রি ডেলিভারি</span>
      </a>
      <a class="bg-white rounded-xl p-3 shadow-card flex flex-col items-center gap-2" href="#">
        <span class="w-10 h-10 grid place-content-center rounded-xl bg-purple-50 text-purple-600"><i class="fa-solid fa-wand-magic-sparkles"></i></span>
        <span class="text-xs text-center font-medium">বিউটি</span>
      </a>
      <a class="bg-white rounded-xl p-3 shadow-card flex flex-col items-center gap-2" href="#">
        <span class="w-10 h-10 grid place-content-center rounded-xl bg-sky-50 text-sky-600"><i class="fa-solid fa-bag-shopping"></i></span>
        <span class="text-xs text-center font-medium">শপ নাও</span>
      </a>
      <a class="bg-white rounded-xl p-3 shadow-card flex flex-col items-center gap-2" href="#">
        <span class="w-10 h-10 grid place-content-center rounded-xl bg-teal-50 text-teal-600"><i class="fa-solid fa-star"></i></span>
        <span class="text-xs text-center font-medium">চয়েস</span>
      </a>
      <a class="bg-white rounded-xl p-3 shadow-card flex flex-col items-center gap-2" href="#">
        <span class="w-10 h-10 grid place-content-center rounded-xl bg-rose-50 text-rose-500"><i class="fa-solid fa-fire"></i></span>
        <span class="text-xs text-center font-medium">হট ডিল</span>
      </a>
      <a class="bg-white rounded-xl p-3 shadow-card flex flex-col items-center gap-2" href="#">
        <span class="w-10 h-10 grid place-content-center rounded-xl bg-amber-50 text-amber-600"><i class="fa-solid fa-certificate"></i></span>
        <span class="text-xs text-center font-medium">অরিজিনাল</span>
      </a>
      <a class="bg-white rounded-xl p-3 shadow-card flex flex-col items-center gap-2" href="#">
        <span class="w-10 h-10 grid place-content-center rounded-xl bg-indigo-50 text-indigo-600"><i class="fa-solid fa-tags"></i></span>
        <span class="text-xs text-center font-medium">কুপন</span>
      </a>
    </section>

    <!-- Vouchers -->
    <section class="mt-6">
      <div class="bg-white rounded-2xl p-3 shadow-card">
        <div class="flex items-center justify-between">
          <h3 class="font-semibold">ভাউচার নিন ও সেভ করুন</h3>
          <a href="#" class="text-sm text-orange-600">আরো দেখুন</a>
        </div>
        <div class="mt-3 grid grid-cols-2 sm:grid-cols-4 gap-3">
          <a class="border-2 border-dashed border-orange-300 rounded-xl p-3 text-center">
            <div class="text-lg font-bold text-orange-600">৮% OFF</div>
            <div class="text-xs">Daraz ভাউচার</div>
          </a>
          <a class="border-2 border-dashed border-sky-300 rounded-xl p-3 text-center">
            <div class="text-lg font-bold text-sky-600">৳৮০</div>
            <div class="text-xs">ফ্রি শিপিং</div>
          </a>
          <a class="border-2 border-dashed border-lime-300 rounded-xl p-3 text-center">
            <div class="text-lg font-bold text-lime-600">৳৫০</div>
            <div class="text-xs">কয়েন বোনাস</div>
          </a>
          <a class="border-2 border-dashed border-rose-300 rounded-xl p-3 text-center">
            <div class="text-lg font-bold text-rose-600">১৫% OFF</div>
            <div class="text-xs">নতুন ব্যবহারকারী</div>
          </a>
        </div>
      </div>
    </section>

    <!-- Flash Sale -->
    <section class="mt-6">
      <div class="bg-white rounded-2xl p-4 shadow-card">
        <div class="flex items-center justify-between">
          <div class="flex items-center gap-2">
            <i class="fa-solid fa-bolt text-orange-500"></i>
            <h3 class="font-semibold">ফ্ল্যাশ সেল</h3>
            <span class="text-xs text-gray-500">শেষ হতে: <span id="countdown" class="font-semibold text-rose-600">--:--:--</span></span>
          </div>
          <a href="#" class="text-sm text-orange-600">সব দেখুন</a>
        </div>

        <div class="mt-3 grid grid-cols-2 sm:grid-cols-4 lg:grid-cols-6 gap-3">
          <!-- product card -->
          <div class="rounded-xl border border-gray-100 bg-white overflow-hidden hover:shadow-card transition">
            <img class="w-full h-36 object-cover" src="https://picsum.photos/400/300?random=21" alt="">
            <div class="p-3">
              <p class="text-sm line-clamp-2">চিয়া সিডস ২০০গ্রাম প্যাক</p>
              <div class="mt-1 flex items-center gap-2">
                <span class="text-lg font-bold text-rose-600">৳১৪৩</span>
                <span class="text-xs line-through text-gray-400">৳৩৪৯</span>
                <span class="text-xs text-emerald-600">-59%</span>
              </div>
              <div class="mt-2 h-1 bg-gray-100 rounded">
                <div class="h-1 bg-orange-500 rounded" style="width:60%"></div>
              </div>
              <p class="mt-1 text-[11px] text-gray-500">১.৮k বিক্রি</p>
            </div>
          </div>

          <div class="rounded-xl border border-gray-100 bg-white overflow-hidden hover:shadow-card transition">
            <img class="w-full h-36 object-cover" src="https://picsum.photos/400/300?random=22" alt="">
            <div class="p-3">
              <p class="text-sm line-clamp-2">৬ ইন ১ মেকআপ কম্বো সেট</p>
              <div class="mt-1 flex items-center gap-2">
                <span class="text-lg font-bold text-rose-600">৳২৬০</span>
                <span class="text-xs line-through text-gray-400">৳২৯৫</span>
                <span class="text-xs text-emerald-600">-12%</span>
              </div>
              <div class="mt-2 h-1 bg-gray-100 rounded">
                <div class="h-1 bg-orange-500 rounded" style="width:85%"></div>
              </div>
              <p class="mt-1 text-[11px] text-gray-500">৭.২k বিক্রি</p>
            </div>
          </div>

          <div class="rounded-xl border border-gray-100 bg-white overflow-hidden hover:shadow-card transition">
            <img class="w-full h-36 object-cover" src="https://picsum.photos/400/300?random=23" alt="">
            <div class="p-3">
              <p class="text-sm line-clamp-2">ডিজিটাল পোর্টেবল স্কেল</p>
              <div class="mt-1 flex items-center gap-2">
                <span class="text-lg font-bold text-rose-600">৳৩৫০</span>
                <span class="text-xs line-through text-gray-400">৳৬৫০</span>
                <span class="text-xs text-emerald-600">-46%</span>
              </div>
              <div class="mt-2 h-1 bg-gray-100 rounded">
                <div class="h-1 bg-orange-500 rounded" style="width:40%"></div>
              </div>
              <p class="mt-1 text-[11px] text-gray-500">৪.১k বিক্রি</p>
            </div>
          </div>

          <div class="rounded-xl border border-gray-100 bg-white overflow-hidden hover:shadow-card transition">
            <img class="w-full h-36 object-cover" src="https://picsum.photos/400/300?random=24" alt="">
            <div class="p-3">
              <p class="text-sm line-clamp-2">পুরুষদের লুঙ্গি — ৩ পিস</p>
              <div class="mt-1 flex items-center gap-2">
                <span class="text-lg font-bold text-rose-600">৳১৮৫</span>
                <span class="text-xs line-through text-gray-400">৳২৯৯</span>
                <span class="text-xs text-emerald-600">-38%</span>
              </div>
              <div class="mt-2 h-1 bg-gray-100 rounded">
                <div class="h-1 bg-orange-500 rounded" style="width:70%"></div>
              </div>
              <p class="mt-1 text-[11px] text-gray-500">৪.১k বিক্রি</p>
            </div>
          </div>

          <div class="rounded-xl border border-gray-100 bg-white overflow-hidden hover:shadow-card transition">
            <img class="w-full h-36 object-cover" src="https://picsum.photos/400/300?random=25" alt="">
            <div class="p-3">
              <p class="text-sm line-clamp-2">বেবি সিরিয়াল নেসলে ৩৫০গ্রাম</p>
              <div class="mt-1 flex items-center gap-2">
                <span class="text-lg font-bold text-rose-600">৳৮৫</span>
                <span class="text-xs line-through text-gray-400">৳২৩৫</span>
                <span class="text-xs text-emerald-600">-57%</span>
              </div>
              <div class="mt-2 h-1 bg-gray-100 rounded">
                <div class="h-1 bg-orange-500 rounded" style="width:55%"></div>
              </div>
              <p class="mt-1 text-[11px] text-gray-500">৭২৮ বিক্রি</p>
            </div>
          </div>

          <div class="rounded-xl border border-gray-100 bg-white overflow-hidden hover:shadow-card transition">
            <img class="w-full h-36 object-cover" src="https://picsum.photos/400/300?random=26" alt="">
            <div class="p-3">
              <p class="text-sm line-clamp-2">ওয়্যারলেস ইয়ারবাডস — Pro</p>
              <div class="mt-1 flex items-center gap-2">
                <span class="text-lg font-bold text-rose-600">৳২৯৯</span>
                <span class="text-xs line-through text-gray-400">৳৬৫০</span>
                <span class="text-xs text-emerald-600">-54%</span>
              </div>
              <div class="mt-2 h-1 bg-gray-100 rounded">
                <div class="h-1 bg-orange-500 rounded" style="width:25%"></div>
              </div>
              <p class="mt-1 text-[11px] text-gray-500">১.৮k বিক্রি</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- As low as section -->
    <section class="mt-6">
      <div class="flex items-center justify-between mb-2">
        <h3 class="font-semibold">মাত্র <span class="text-emerald-600">৳৮৫</span> থেকে</h3>
        <a href="#" class="text-sm text-orange-600">শপ নাও | ফ্রি গিফট</a>
      </div>
      <div class="grid grid-cols-2 sm:grid-cols-4 lg:grid-cols-6 gap-3">
        <!-- simple repeat -->
        <template id="simple-card">
          <div class="rounded-xl border border-gray-100 bg-white overflow-hidden hover:shadow-card transition">
            <img class="w-full h-36 object-cover" src="" alt="">
            <div class="p-3">
              <p class="text-sm line-clamp-2">প্রোডাক্ট শিরোনাম</p>
              <div class="mt-1 flex items-center gap-2">
                <span class="text-lg font-bold text-rose-600">৳৮৫</span>
                <span class="text-xs line-through text-gray-400">৳২২০</span>
                <span class="text-xs text-emerald-600">-61%</span>
              </div>
              <p class="mt-1 text-[11px] text-gray-500"><i class="fa-solid fa-star text-amber-400"></i> 4.5 (320) • 2.3k sold</p>
            </div>
          </div>
        </template>
        <!-- we will clone by JS -->
        <div id="aslow" class="contents"></div>
      </div>
    </section>

  </main>

  <!-- Bottom nav (mobile style) -->
  <nav class="fixed inset-x-0 bottom-0 z-30 bg-white border-t border-gray-200">
    <div class="max-w-6xl mx-auto grid grid-cols-4 text-center">
      <a class="py-2 text-orange-600">
        <i class="fa-solid fa-house text-xl"></i><div class="text-xs">হোম</div>
      </a>
      <a class="py-2 text-gray-500">
        <i class="fa-regular fa-message text-xl"></i><div class="text-xs">মেসেজ</div>
      </a>
      <a class="py-2 text-gray-500">
        <i class="fa-solid fa-cart-shopping text-xl"></i><div class="text-xs">কার্ট</div>
      </a>
      <a class="py-2 text-gray-500">
        <i class="fa-regular fa-user text-xl"></i><div class="text-xs">অ্যাকাউন্ট</div>
      </a>
    </div>
  </nav>

  <footer class="text-center text-xs text-gray-400 py-6">
    © <span id="y"></span> আমার ই-কমার্স — ডেমো হোমপেজ
  </footer>

  <script>
    // year
    document.getElementById('y').textContent = new Date().getFullYear();

    // slider
    const slides = document.getElementById('slides');
    const dots   = Array.from(document.querySelectorAll('.dot'));
    let index=0;
    function show(i){
      index = i % 3;
      slides.style.transform = `translateX(-${index*100}%)`;
      dots.forEach((d,di)=>d.style.background = di===index? 'rgba(255,255,255,.95)': 'rgba(255,255,255,.4)');
    }
    dots.forEach((d,i)=>d.addEventListener('click',()=>show(i)));
    setInterval(()=>show(index+1), 3500);

    // countdown to next hour (Flash Sale)
    function updateCountdown(){
      const now=new Date();
      const next=new Date(now);
      next.setHours(now.getHours()+1,0,0,0);
      const s=Math.max(0,Math.floor((next-now)/1000));
      const h=String(Math.floor(s/3600)).padStart(2,'0');
      const m=String(Math.floor((s%3600)/60)).padStart(2,'0');
      const ss=String(s%60).padStart(2,'0');
      document.getElementById('countdown').textContent=`${h}:${m}:${ss}`;
    }
    setInterval(updateCountdown,1000); updateCountdown();

    // generate "as low as" mock cards
    const imgs=[27,28,29,30,31,32,33,34,35,36,37,38].map(n=>`https://picsum.photos/400/300?random=${n}`);
    const container=document.getElementById('aslow');
    const tpl=document.getElementById('simple-card');
    imgs.forEach(src=>{
      const node=tpl.content.cloneNode(true);
      node.querySelector('img').src=src;
      container.appendChild(node);
    });
  </script>
</body>
</html>
