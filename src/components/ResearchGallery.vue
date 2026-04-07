<template>
  <section class="max-w-7xl mx-auto py-10 px-4 md:px-8 space-y-16">
    
    <!-- Título de la sección -->
    <div class="text-center space-y-4">
      <h2 class="text-4xl font-black text-slate-800 tracking-tight">Hitos académicos e investigación</h2>
      <p class="text-pink-600 font-bold uppercase tracking-widest text-[10px]">Compromiso con la formación y la innovación</p>
      <div class="w-16 h-1 bg-pink-100 mx-auto rounded-full mt-4"></div>
    </div>

    <!-- Contenedor de Proyectos -->
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-start">
      
      <!-- TARJETA TFG -->
      <div class="group bg-white rounded-[3rem] overflow-hidden border border-slate-100 shadow-sm hover:shadow-xl transition-all duration-500 p-8 md:p-12 space-y-8">
        <div class="flex justify-between items-start">
          <span class="bg-pink-50 text-pink-600 text-[10px] font-black px-4 py-1.5 rounded-full uppercase tracking-widest border border-pink-100">Matrícula de Honor | TFG</span>
          <GraduationCapIcon :size="24" class="opacity-30 group-hover:opacity-100 transition-opacity" />
        </div>
        
        <div class="space-y-4">
          <h3 class="text-3xl font-black text-slate-900 leading-tight">Trauma infantil y barreras de aprendizaje</h3>
          <p class="text-slate-500 leading-relaxed text-sm lg:text-base italic">
            Investigación cualitativa: Análisis de las barreras de aprendizaje de la infancia (revisión bibliográfica y estudio de caso).
          </p>
        </div>

        <div class="pt-8 border-t border-slate-50 flex items-center justify-between">
          <a href="/assets/TFG_LaydaLopez.pdf" target="_blank" 
            class="inline-flex items-center gap-3 bg-slate-900 text-white hover:bg-pink-600 transition-all rounded-2xl px-8 py-4 font-bold shadow-lg text-sm group">
            <span>Memoria TFG</span>
            <ArrowRightIcon :size="16" class="opacity-40 group-hover:translate-x-1 transition-transform" />
          </a>
          <div class="text-right">
            <p class="text-[10px] font-black text-slate-400 uppercase tracking-widest">Calificación</p>
            <p class="text-pink-600 font-bold text-sm">Matrícula de honor</p>
          </div>
        </div>
      </div>

      <!-- TARJETA TFM (PIMPOYO) -->
      <div class="group bg-pink-50/30 rounded-[3rem] overflow-hidden border border-pink-100/50 shadow-sm hover:shadow-xl transition-all duration-500 p-8 md:p-12 space-y-8">
        <div class="flex justify-between items-start">
          <span class="bg-white text-pink-700 text-[10px] font-black px-4 py-1.5 rounded-full uppercase tracking-widest border border-pink-100">Innovación EdTech | TFM</span>
          <BotIcon :size="24" class="opacity-30 group-hover:opacity-100 transition-opacity" />
        </div>
        
        <div class="space-y-4">
          <h3 class="text-3xl font-black text-slate-900 leading-tight">Pimpoyo: Chatbot Socrático con IA</h3>
          <p class="text-slate-500 leading-relaxed text-sm lg:text-base italic">
            Diseño y desarrollo de un asistente educativo innovador para el fomento de la alfabetización mediática y el pensamiento crítico.
          </p>
        </div>

        <!-- Reproductor de Vídeo -->
        <div class="aspect-video w-full bg-white rounded-3xl overflow-hidden shadow-2xl relative border border-white/50 group-hover:scale-[1.02] transition-transform duration-500">
          <iframe 
            src="https://drive.google.com/file/d/1VLsdmZDxlop9Y-SVq7QYy3kHp9aA8fbT/preview" 
            class="absolute inset-0 w-full h-full border-0" 
            allow="autoplay"
            loading="lazy">
          </iframe>
        </div>

        <div class="grid grid-cols-2 gap-4 pt-4">
          <a href="/assets/LopezLora_Layda_TFM.pdf" target="_blank" 
            class="flex flex-col items-center gap-2 bg-white hover:bg-slate-900 hover:text-white transition-all rounded-3xl p-5 border border-slate-100 text-center shadow-sm group/btn">
            <FolderOpenIcon :size="20" class="text-slate-400 group-hover/btn:text-white" />
            <span class="text-[10px] font-black uppercase tracking-widest opacity-80">Memoria TFM</span>
          </a>
          <a href="/assets/Guia_informativa_Pimpoyo.pdf" target="_blank" 
            class="flex flex-col items-center gap-2 bg-pink-500 hover:bg-pink-600 text-white transition-all rounded-3xl p-5 border border-pink-400 text-center shadow-lg">
            <BookIcon :size="20" />
            <span class="text-[10px] font-black uppercase tracking-widest">Guía Pimpoyo</span>
          </a>
        </div>
      </div>

    </div>
  </section>
</template>