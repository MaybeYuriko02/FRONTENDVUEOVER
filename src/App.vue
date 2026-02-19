<template>
  <div class="min-h-screen flex flex-col selection:bg-pink-200 selection:text-pink-900">
    <!-- Navbar Minimalista y Centrada -->
    <nav class="sticky top-0 z-50 bg-white/80 backdrop-blur-xl border-b border-pink-50 h-20 px-6 flex items-center justify-between">
      <router-link to="/" class="flex items-center gap-3">
        <div class="w-10 h-10 pink-gradient-bg rounded-full flex items-center justify-center text-white font-serif italic text-xl shadow-md">TS</div>
        <span class="font-serif font-black text-xl text-pink-500 tracking-tighter uppercase italic hidden sm:block">Swiftie Hub</span>
      </router-link>
      
      <div class="flex gap-8 text-[10px] font-black uppercase tracking-[0.2em] text-pink-400">
        <router-link to="/" class="hover:text-pink-600 transition-colors" active-class="text-pink-600">Inicio</router-link>
        <router-link to="/products" class="hover:text-pink-600 transition-colors" active-class="text-pink-600">Catálogo</router-link>
      </div>

      <button class="p-2 text-pink-300 hover:text-pink-500 transition-colors text-2xl">
        💖
      </button>
    </nav>

    <!-- Contenido Principal Centrado -->
    <main class="flex-1 w-full py-16">
      <router-view v-slot="{ Component }">
        <transition name="fade" mode="out-in">
          <component :is="Component" />
        </transition>
      </router-view>
    </main>

    <footer class="py-10 text-center border-t border-pink-50">
      <p class="text-[9px] font-bold text-pink-200 uppercase tracking-[0.5em]">
        Handcrafted with love for Taylor &bull; 2024
      </p>
    </footer>
  </div>
</template>
