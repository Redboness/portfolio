<template>
  <section class="py-24 px-8 bg-gradient-to-b from-white to-pink-50">
    <div class="max-w-4xl mx-auto">
      
      <div class="bg-white rounded-[3rem] shadow-2xl overflow-hidden flex flex-col md:flex-row border border-pink-100">
        
        <!-- Lado Izquierdo: Mensaje Amigable -->
        <div class="md:w-1/3 bg-secondary p-10 text-white flex flex-col justify-center space-y-6">
          <h2 class="text-3xl font-bold">¿Hablamos? 💌</h2>
          <p class="text-pink-100 text-sm leading-relaxed">
            Si tienes alguna duda sobre mis investigaciones o quieres colaborar en un proyecto educativo, ¡me encantaría leerte!
          </p>
          <div class="text-5xl animate-bounce text-center">✉️</div>
        </div>

        <!-- Lado Derecho: El Formulario -->
        <div class="md:w-2/3 p-10 md:p-16">
          <form @submit.prevent="handleSubmit" class="space-y-6">
            
            <div class="form-control">
              <label class="label"><span class="label-text font-bold text-secondary">Tu Nombre</span></label>
              <input type="text" placeholder="¿Cómo te llamas?" class="input input-bordered w-full rounded-2xl border-pink-100 focus:border-primary focus:ring-primary" />
            </div>

            <div class="form-control">
              <label class="label"><span class="label-text font-bold text-secondary">Correo Electrónico</span></label>
              <input type="email" placeholder="ejemplo@correo.com" class="input input-bordered w-full rounded-2xl border-pink-100 focus:border-primary" />
            </div>

            <div class="form-control">
              <label class="label"><span class="label-text font-bold text-secondary">Tu Mensaje</span></label>
              <textarea class="textarea textarea-bordered w-full rounded-3xl border-pink-100 focus:border-primary h-32" placeholder="Cuéntame en qué puedo ayudarte..."></textarea>
            </div>

            <button type="submit" class="btn btn-primary w-full rounded-full shadow-lg hover:scale-105 transition-transform">
              Enviar Mensaje Mágico ✨
            </button>
            
          </form>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
const handleSubmit = () => {
  alert("¡Gracias Layda! (Esto es una prueba, el mensaje se enviaría aquí) 🌸");
}
</script>