<template>
  <section class="py-24 px-8 max-w-7xl mx-auto">
    <!-- Título de la sección -->
    <div class="text-center mb-16 space-y-4">
      <h2 class="text-4xl font-black text-secondary">Mis Hitos Académicos</h2>
      <p class="text-primary font-medium italic">El fruto de mi esfuerzo y dedicación en la educación</p>
      <div class="w-24 h-1.5 bg-gradient-to-r from-primary to-secondary mx-auto rounded-full"></div>
    </div>

    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
      
      <!-- TARJETA TFG (Trabajo de Fin de Grado) -->
      <div class="group bg-white rounded-[3.5rem] overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-500 border border-pink-50 relative">
        <!-- Etiqueta flotante -->
        <div class="absolute top-6 right-6 bg-pink-100 text-pink-600 text-[10px] font-bold px-4 py-1 rounded-full z-20">GRADO</div>
        
        <div class="flex flex-col md:flex-row h-full">
          <!-- Lado Visual -->
          <div class="md:w-1/3 bg-gradient-to-br from-pink-50 to-rose-100 flex items-center justify-center p-8">
            <div class="relative">
              <span class="text-7xl group-hover:rotate-12 transition-transform duration-500 block">🎓</span>
              <span class="absolute -bottom-2 -right-2 text-2xl animate-bounce">✨</span>
            </div>
          </div>
          
          <!-- Lado Texto -->
          <div class="p-8 md:w-2/3 space-y-4">
            <h3 class="text-2xl font-bold text-secondary group-hover:text-primary transition-colors">TFG: Mi primer paso</h3>
            <p class="text-gray-500 text-sm leading-relaxed">
              Aquí puedes poner el título real de tu TFG. Por ejemplo: "Estrategias lúdicas para la lectoescritura en el aula de 5 años".
            </p>
            <div class="pt-4 flex items-center gap-4">
              <button class="btn btn-primary btn-sm rounded-full px-6 shadow-md">Ver Resumen</button>
              <span class="text-xs font-bold text-pink-300">Calificación: Sobresaliente 🌟</span>
            </div>
          </div>
        </div>
      </div>

      <!-- TARJETA TFM (Trabajo de Fin de Máster) -->
      <div class="group bg-white rounded-[3.5rem] overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-500 border border-purple-50 relative">
        <!-- Etiqueta flotante -->
        <div class="absolute top-6 right-6 bg-purple-100 text-purple-600 text-[10px] font-bold px-4 py-1 rounded-full z-20">MÁSTER</div>
        
        <div class="flex flex-col md:flex-row h-full">
          <!-- Lado Visual -->
          <div class="md:w-1/3 bg-gradient-to-br from-purple-50 to-pink-100 flex items-center justify-center p-8">
            <div class="relative">
              <span class="text-7xl group-hover:scale-110 transition-transform duration-500 block">🔬</span>
              <span class="absolute -top-2 -left-2 text-2xl animate-pulse">💡</span>
            </div>
          </div>
          
          <!-- Lado Texto -->
          <div class="p-8 md:w-2/3 space-y-4">
            <h3 class="text-2xl font-bold text-secondary group-hover:text-primary transition-colors">TFM: Especialización</h3>
            <p class="text-gray-500 text-sm leading-relaxed">
              Escribe aquí el título de tu Máster. Por ejemplo: "Neuroeducación aplicada al bienestar emocional en el segundo ciclo de infantil".
            </p>
            <div class="pt-4 flex items-center gap-4">
              <button class="btn btn-secondary btn-sm rounded-full px-6 shadow-md">Ver Proyecto</button>
              <span class="text-xs font-bold text-purple-300">Investigación Avanzada 📚</span>
            </div>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>