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
          <button @click="openPdf('/assets/TFG_LaydaLopez.pdf')" 
            class="inline-flex items-center gap-3 bg-white text-slate-900 border border-slate-200 hover:border-pink-500 hover:text-pink-600 transition-all rounded-2xl px-8 py-4 font-bold shadow-sm text-sm group">
            <span>Memoria TFG</span>
            <EyeIcon :size="16" class="opacity-40 group-hover:opacity-100 transition-opacity" />
          </button>
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

        <!-- Reproductor de Vídeo (Oculto por defecto) -->
        <div class="space-y-4">
          <button 
            @click="showVideo = !showVideo"
            class="w-full flex items-center justify-center gap-3 p-4 rounded-2xl border-2 border-dashed border-pink-200 text-pink-600 font-bold hover:bg-pink-50 transition-all"
          >
            <PlayIcon v-if="!showVideo" :size="20" />
            <XIcon v-else :size="20" />
            <span>{{ showVideo ? 'Cerrar video técnico' : 'Ver vídeo técnico' }}</span>
          </button>

          <transition 
            enter-active-class="transition duration-500 ease-out"
            enter-from-class="transform scale-95 opacity-0"
            enter-to-class="transform scale-100 opacity-100"
            leave-active-class="transition duration-300 ease-in"
            leave-from-class="transform scale-100 opacity-100"
            leave-to-class="transform scale-95 opacity-0"
          >
            <div v-if="showVideo" class="aspect-video w-full bg-white rounded-3xl overflow-hidden shadow-2xl relative border border-white/50">
              <iframe 
                src="https://drive.google.com/file/d/1VLsdmZDxlop9Y-SVq7QYy3kHp9aA8fbT/preview" 
                class="absolute inset-0 w-full h-full border-0" 
                allow="autoplay"
                loading="lazy">
              </iframe>
            </div>
          </transition>
        </div>

        <div class="grid grid-cols-2 gap-4 pt-4">
          <button @click="openPdf('/assets/LopezLora_Layda_TFM.pdf')" 
            class="flex flex-col items-center gap-2 bg-white text-slate-900 hover:text-pink-600 hover:border-pink-500 transition-all rounded-3xl p-5 border border-slate-200 text-center shadow-sm group/btn">
            <FolderOpenIcon :size="20" class="text-slate-400 group-hover/btn:text-pink-500" />
            <span class="text-[10px] font-black uppercase tracking-widest opacity-80">Memoria TFM</span>
          </button>
          <button @click="openPdf('/assets/Guia_informativa_Pimpoyo.pdf')" 
            class="flex flex-col items-center gap-2 bg-pink-500 hover:bg-pink-600 text-white transition-all rounded-3xl p-5 border border-pink-400 text-center shadow-lg group/btn">
            <BookIcon :size="20" />
            <span class="text-[10px] font-black uppercase tracking-widest">Guía Pimpoyo</span>
          </button>
        </div>
      </div>

    </div>

    <!-- VISOR DE PDF INTEGRADO (Teleportado al body para evitar recortes y conflictos de z-index) -->
    <Teleport to="body">
      <transition
        enter-active-class="transition duration-300 ease-out"
        enter-from-class="opacity-0"
        enter-to-class="opacity-100"
        leave-active-class="transition duration-200 ease-in"
        leave-from-class="opacity-100"
        leave-to-class="opacity-0"
      >
        <div v-if="activePdf" 
          class="fixed inset-0 z-[1000] bg-slate-900/90 backdrop-blur-sm flex items-center justify-center p-4 md:p-10"
        >
          <div 
            :class="isExpanded ? 'w-full h-full rounded-0' : 'max-w-5xl w-full h-[90vh] rounded-[2rem] shadow-2xl'"
            class="bg-white overflow-hidden flex flex-col transition-all duration-500"
          >
            <!-- Barra de controles (Flex-shrink-0 para que nunca se recorte) -->
            <div class="flex-shrink-0 bg-white border-b border-slate-100 px-6 py-4 flex items-center justify-between">
              <div class="flex items-center gap-4">
                <div class="bg-pink-100 p-2 rounded-lg text-pink-600">
                  <FileTextIcon :size="18" />
                </div>
                <h4 class="font-bold text-slate-800 text-sm hidden sm:block">Visualizador de documentos</h4>
              </div>
              
              <div class="flex items-center gap-2">
                <button @click="isExpanded = !isExpanded" class="p-2 hover:bg-slate-50 rounded-lg transition-colors text-slate-400 hover:text-slate-900" title="Expandir/Contraer">
                  <MaximizeIcon v-if="!isExpanded" :size="20" />
                  <MinimizeIcon v-else :size="20" />
                </button>
                <a :href="activePdf" target="_blank" class="p-2 hover:bg-slate-50 rounded-lg transition-colors text-slate-400 hover:text-slate-900" title="Abrir en nueva pestaña">
                  <ExternalLinkIcon :size="20" />
                </a>
                <div class="w-px h-6 bg-slate-100 mx-2"></div>
                <button @click="closePdf" class="p-2 bg-slate-100 hover:bg-pink-500 hover:text-white rounded-lg transition-all text-slate-500" title="Cerrar">
                  <XIcon :size="20" />
                </button>
              </div>
            </div>
            
            <!-- El PDF -->
            <div class="flex-1 bg-slate-50 relative">
              <iframe :src="activePdf" class="absolute inset-0 w-full h-full border-0"></iframe>
            </div>
          </div>
        </div>
      </transition>
    </Teleport>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import { 
  GraduationCapIcon, 
  BotIcon, 
  FolderOpenIcon, 
  BookIcon, 
  PlayIcon, 
  XIcon, 
  EyeIcon, 
  FileTextIcon,
  MaximizeIcon,
  MinimizeIcon,
  ExternalLinkIcon
} from 'lucide-vue-next'

const showVideo = ref(false)
const activePdf = ref(null)
const isExpanded = ref(false)

const openPdf = (url) => {
  activePdf.value = url
  document.body.style.overflow = 'hidden'
}

const closePdf = () => {
  activePdf.value = null
  isExpanded.value = false
  document.body.style.overflow = 'auto'
}
</script>