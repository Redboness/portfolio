<template>
  <aside class="fixed left-0 top-0 bottom-0 w-64 bg-secondary text-white flex flex-col p-6 z-50 shadow-2xl">
    
    <!-- 1. LOGO -->
    <div class="flex items-center gap-3 mb-12 px-2">
      <div class="w-10 h-10 bg-white rounded-xl flex items-center justify-center text-secondary shadow-lg">
        <span class="text-2xl font-bold">L</span>
      </div>
      <span class="text-xl font-bold tracking-tight">Layda.Res</span>
    </div>

    <!-- 2. MENÚ PRINCIPAL -->
    <nav class="flex-1 space-y-2">
      <button 
        @click="$emit('change-section', 'inicio')"
        :class="activeSection === 'inicio' ? 'bg-white text-secondary shadow-lg scale-105' : 'bg-white/10 hover:bg-white/20'"
        class="flex items-center gap-4 w-full p-3 rounded-xl transition-all duration-300 font-bold text-left"
      >
        <span class="text-xl">🏠</span> Inicio
      </button>

      <button 
        @click="$emit('change-section', 'cv')"
        :class="activeSection === 'cv' ? 'bg-white text-secondary shadow-lg scale-105' : 'bg-white/10 hover:bg-white/20'"
        class="flex items-center gap-4 w-full p-3 rounded-xl transition-all duration-300 font-bold text-left"
      >
        <span class="text-xl">📄</span> Currículum
      </button>

      <button 
        @click="$emit('change-section', 'investigacion')"
        :class="activeSection === 'investigacion' ? 'bg-white text-secondary shadow-lg scale-105' : 'bg-white/10 hover:bg-white/20'"
        class="flex items-center gap-4 w-full p-3 rounded-xl transition-all duration-300 font-bold text-left"
      >
        <span class="text-xl">📊</span> Investigación
      </button>

      <button 
        @click="$emit('change-section', 'contacto')"
        :class="activeSection === 'contacto' ? 'bg-white text-secondary shadow-lg scale-105' : 'bg-white/10 hover:bg-white/20'"
        class="flex items-center gap-4 w-full p-3 rounded-xl transition-all duration-300 font-bold text-left"
      >
        <span class="text-xl">✉️</span> Contacto
      </button>
    </nav>

    <!-- 3. PANEL DE INCLUSIÓN (DUA) -->
    <div class="mt-auto pt-6 border-t border-white/20 space-y-4">
      <p class="text-[10px] uppercase tracking-widest opacity-60 font-black text-white">Inclusión (DUA)</p>
      
      <div class="grid grid-cols-1 gap-2">
        <!-- Modo Normal -->
        <button 
          @click="$emit('change-mode', 'normal')" 
          :class="activeMode === 'normal' ? 'bg-primary border-primary' : 'bg-white/5 border-transparent'"
          class="text-[10px] p-2.5 rounded-lg hover:bg-white/10 transition-all flex items-center gap-3 border"
        >
          <span class="text-sm">✨</span> 
          <span class="font-bold">Modo Estándar</span>
        </button>

        <!-- Modo TDAH -->
        <button 
          @click="$emit('change-mode', 'tdah')" 
          :class="activeMode === 'tdah' ? 'bg-primary border-primary' : 'bg-white/5 border-transparent'"
          class="text-[10px] p-2.5 rounded-lg hover:bg-white/10 transition-all flex items-center gap-3 border"
        >
          <span class="text-sm">🎯</span> 
          <span class="font-bold">Enfoque (TDAH)</span>
        </button>

        <!-- Modo Autismo -->
        <button 
          @click="$emit('change-mode', 'autismo')" 
          :class="activeMode === 'autismo' ? 'bg-primary border-primary' : 'bg-white/5 border-transparent'"
          class="text-[10px] p-2.5 rounded-lg hover:bg-white/10 transition-all flex items-center gap-3 border"
        >
          <span class="text-sm">🧩</span> 
          <span class="font-bold">Sensorial (Autismo)</span>
        </button>
      </div>

      <!-- Botón de Lectura Fácil (Opcional) -->
      <button class="flex items-center justify-between w-full p-2.5 rounded-lg bg-white/5 hover:bg-white/10 text-[10px] transition-all mt-2">
        <span class="font-bold">Lectura Fácil</span>
        <span>📖</span>
      </button>
    </div>

  </aside>
</template>

<script setup>
// Recibimos la sección y el modo activo desde App.vue
defineProps({
  activeSection: String,
  activeMode: String
})

// Avisamos a App.vue cuando el usuario hace clic
defineEmits(['change-section', 'change-mode'])
</script>

<style scoped>
/* Pequeño efecto de escala para que los botones se sientan vivos */
button:active {
  transform: scale(0.95);
}
</style>