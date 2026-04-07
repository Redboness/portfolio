<template>
  <section class="py-24 px-8 bg-gradient-to-b from-white to-pink-50">
    <div class="max-w-4xl mx-auto">
      
      <div class="bg-white rounded-[3rem] shadow-2xl overflow-hidden flex flex-col md:flex-row border border-pink-100">
        
        <!-- Lado Izquierdo: Mensaje Amigable -->
        <div class="md:w-1/3 bg-secondary p-10 text-white flex flex-col justify-center items-center md:items-start space-y-6">
          <MailIcon :size="48" class="text-pink-400 mb-2" />
          <h2 class="text-3xl font-bold">¿Hablamos?</h2>
          <p class="text-pink-100 text-sm leading-relaxed text-center md:text-left">
            Si tienes alguna consulta sobre mis investigaciones o quieres colaborar en un proyecto educativo, me encantaría leerte.
          </p>
        </div>

        <!-- Lado Derecho: El Formulario -->
        <div class="md:w-2/3 p-10 md:p-16">
          <form @submit.prevent="handleSubmit" class="space-y-6">
            
            <div class="form-control">
              <label class="label"><span class="label-text font-bold text-secondary">Tu nombre</span></label>
              <input type="text" placeholder="¿Cómo te llamas?" class="input input-bordered w-full rounded-2xl border-pink-100 focus:border-primary focus:ring-primary" />
            </div>

            <div class="form-control">
              <label class="label"><span class="label-text font-bold text-secondary">Correo electrónico</span></label>
              <input type="email" placeholder="ejemplo@correo.com" class="input input-bordered w-full rounded-2xl border-pink-100 focus:border-primary" />
            </div>

            <div class="form-control">
              <label class="label"><span class="label-text font-bold text-secondary">Tu mensaje</span></label>
              <textarea class="textarea textarea-bordered w-full rounded-3xl border-pink-100 focus:border-primary h-32" placeholder="Cuéntame en qué puedo ayudarte..."></textarea>
            </div>

            <button type="submit" class="btn btn-primary w-full rounded-full shadow-lg hover:scale-105 transition-transform flex items-center justify-center gap-2">
              <MessageSquareIcon :size="18" />
              <span>Enviar mensaje profesional</span>
            </button>
            
          </form>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
import { MailIcon, MessageSquareIcon } from 'lucide-vue-next'

const handleSubmit = () => {
  alert("Gracias por tu interés. En un entorno real, este formulario enviaría tus datos a mi correo.");
}
</script>