<template>
  <section id="sobre-mi" class="py-24 px-8 max-w-6xl mx-auto scroll-mt-20">
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
      
      <!-- Lado de la Imagen con Decoración Orgánica -->
      <div class="relative">
        <div class="absolute -top-10 -left-10 w-72 h-72 bg-pink-200/30 rounded-full blur-3xl"></div>
        <div class="relative z-10 rounded-[4rem] overflow-hidden border-8 border-white shadow-2xl rotate-2 hover:rotate-0 transition-transform duration-500">
          <img src="https://api.dicebear.com/7.x/avataaars/svg?seed=Layda&mood=happy" alt="Layda" class="w-full bg-pink-50" />
        </div>
        <!-- Una tarjetita flotante con un dato curioso -->
        <div class="absolute -bottom-6 -right-6 bg-white p-6 rounded-3xl shadow-xl z-20 border border-pink-100 animate-float flex flex-col items-center">
          <p class="text-xs font-bold text-primary uppercase tracking-widest">Mi filosofía</p>
          <p class="text-secondary font-medium text-center">"Aprender jugando, <br>crecer amando"</p>
        </div>
      </div>

      <!-- Lado del Texto Detallado -->
      <div class="space-y-6">
        <h2 class="text-4xl font-black text-secondary">Una mirada al corazón de mi <span class="text-primary">vocación</span></h2>
        <p class="text-gray-600 leading-relaxed">
          Desde que tengo memoria, siempre me ha fascinado la capacidad de asombro de los niños. Mi camino en la **Educación Infantil** no fue una elección, sino una respuesta a mi deseo de proteger y cultivar esa chispa.
        </p>
        
        <!-- Pequeña "Línea de vida" o hitos -->
        <div class="space-y-4 pt-4">
          <div class="flex gap-4 items-start">
            <div class="bg-pink-100 p-2.5 rounded-full text-pink-500">
              <SparklesIcon :size="18" />
            </div>
            <div>
              <h4 class="font-bold text-secondary">Compromiso ético</h4>
              <p class="text-sm text-gray-500">Investigación centrada en la dignidad y el valor de cada estudiante.</p>
            </div>
          </div>
          <div class="flex gap-4 items-start">
            <div class="bg-purple-100 p-2.5 rounded-full text-purple-500">
              <PaletteIcon :size="18" />
            </div>
            <div>
              <h4 class="font-bold text-secondary">Enfoque creativo</h4>
              <p class="text-sm text-gray-500">Integración del arte como lenguaje natural en la etapa infantil.</p>
            </div>
          </div>
        </div>

        <div class="pt-6">
          <div class="stats shadow-sm bg-white border border-pink-50 rounded-3xl w-full">
            <div class="stat place-items-center">
              <div class="stat-title text-[10px] font-bold uppercase tracking-tight">Experiencia</div>
              <div class="stat-value text-primary text-2xl">5+ años</div>
            </div>
            <div class="stat place-items-center border-x border-pink-50">
              <div class="stat-title text-[10px] font-bold uppercase tracking-tight">Investigación</div>
              <div class="stat-value text-secondary text-2xl">12 hitos</div>
            </div>
            <div class="stat place-items-center">
              <div class="stat-title text-[10px] font-bold uppercase tracking-tight">Impacto</div>
              <div class="stat-value text-pink-400 text-2xl">Continuo</div>
            </div>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>
<script setup>
import { SparklesIcon, PaletteIcon, GraduationCapIcon, MicroscopeIcon } from 'lucide-vue-next'
</script>

<style scoped>
@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}
.animate-float { animation: float 4s infinite ease-in-out; }
</style>