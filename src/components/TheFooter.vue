<template>
  <footer class="bg-white/50 backdrop-blur-md border-t border-pink-100 pt-16 pb-8 px-8">
    <div class="max-w-7xl mx-auto">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-12 mb-12">
        
        <!-- Columna 1: Tu Marca -->
        <div class="space-y-4">
          <h3 class="text-2xl font-bold text-secondary">Layda<span class="text-primary">.Research</span></h3>
          <p class="text-gray-500 text-sm leading-relaxed">
            Dedicada a la investigación y mejora de la educación infantil a través del amor, la creatividad y la ciencia.
          </p>
          <div class="flex gap-4">
            <!-- Iconos de redes sociales (puedes poner tus enlaces reales) -->
            <a href="#" class="btn btn-circle btn-outline btn-primary btn-sm">in</a>
            <a href="#" class="btn btn-circle btn-outline btn-primary btn-sm">ig</a>
          </div>
        </div>

        <!-- Columna 2: Enlaces Rápidos -->
        <div>
          <h4 class="font-bold text-secondary mb-6 uppercase text-xs tracking-widest">Navegación</h4>
          <ul class="space-y-3 text-sm text-gray-500">
            <li><a href="#" class="hover:text-primary transition-colors">Sobre mí</a></li>
            <li><a href="#" class="hover:text-primary transition-colors">Investigaciones</a></li>
            <li><a href="#" class="hover:text-primary transition-colors">Metodología</a></li>
          </ul>
        </div>

        <!-- Columna 3: Frase Inspiradora -->
        <div class="bg-pink-50/50 p-6 rounded-[2rem] border border-pink-100">
          <p class="text-pink-600 italic text-sm text-center">
            "La educación no es la preparación para la vida; la educación es la vida en sí misma."
          </p>
          <p class="text-pink-400 text-xs text-center mt-2">— John Dewey</p>
        </div>

      </div>

      <!-- Línea final de Copyright -->
      <div class="border-t border-pink-50 pt-8 text-center">
        <p class="text-xs text-gray-400 flex items-center justify-center gap-1">
          <span>&copy; 2024 Layda Portfolio. Hecho con</span>
          <HeartIcon :size="12" class="text-pink-400 fill-pink-400" />
          <span>y mucha dedicación.</span>
        </p>
      </div>
    </div>
  </footer>
</template>