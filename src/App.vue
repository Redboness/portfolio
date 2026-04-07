<template>
  <!-- Contenedor Principal: Fondo gris muy suave para que resalte el panel -->
  <div class="min-h-screen bg-[#f8fafc] font-sans flex overflow-hidden">
    
    <!-- 1. BARRA LATERAL -->
    <SideNav @change-section="currentSection = $event" :active-section="currentSection" />

    <!-- 2. PANEL BLANCO PRINCIPAL (El Dashboard) -->
    <main class="flex-1 m-4 ml-64 bg-white rounded-[3rem] shadow-2xl overflow-y-auto p-10 relative border border-slate-100">
      
      <!-- CABECERA -->
      <header class="flex justify-between items-center mb-12 border-b pb-6 border-slate-50">
        <div>
          <h2 class="font-bold text-2xl uppercase tracking-tighter text-slate-800">
            {{ currentSection === 'inicio' ? 'Panel de impacto' : 
               currentSection === 'cv' ? 'Currículum vitae' : 
               currentSection === 'investigacion' ? 'Investigación' : 'Contacto' }}
          </h2>
        </div>
        
        <div class="flex items-center gap-3 bg-slate-50 p-2 pr-6 rounded-full border border-slate-100">
          <div class="avatar">
            <div class="w-10 rounded-full ring ring-pink-500 ring-offset-2">
              <img src="https://api.dicebear.com/7.x/avataaars/svg?seed=Layda" />
            </div>
          </div>
          <div class="flex flex-col">
            <span class="font-bold text-sm text-slate-800 leading-none">Layda López</span>
            <span class="text-[10px] text-slate-500 font-medium">Maestra e investigadora</span>
          </div>
        </div>
      </header>

      <!-- CONTENIDO DINÁMICO -->
      <div :key="currentSection" class="animate-fade-in">
        
        <!-- --- SECCIÓN INICIO (EL GANCHO) --- -->
        <div v-if="currentSection === 'inicio'" class="grid grid-cols-12 gap-10">
          
          <!-- HERO -->
          <div class="col-span-12 lg:col-span-8 bg-gradient-to-br from-white to-slate-50 p-12 rounded-[3rem] border border-slate-100 shadow-sm relative overflow-hidden">
            <div class="relative z-10">
              <div class="inline-block bg-pink-100 text-pink-700 mb-6 px-4 py-1 rounded-full font-bold uppercase tracking-wider text-[10px]">Vocación e innovación</div>
              <h1 class="text-4xl lg:text-5xl font-black text-slate-900 mb-6 leading-tight">
                Educación Infantil con enfoque en <span class="text-pink-600">bienestar e IA</span>.
              </h1>
              <p class="text-slate-600 max-w-xl text-lg leading-relaxed">
                Maestra de Educación Infantil (UAH) e Investigadora (UNED). Especializada en metodologías activas y herramientas digitales.
              </p>
              <button @click="currentSection = 'cv'" class="mt-10 bg-slate-900 text-white hover:bg-pink-600 transition-colors rounded-2xl px-10 py-4 font-bold shadow-lg">Ver mi trayectoria</button>
            </div>
            <GraduationCapIcon :size="240" class="absolute right-[-40px] bottom-[-40px] opacity-[0.03] rotate-12 pointer-events-none text-slate-900" />
          </div>

          <!-- IMPACTO -->
          <div class="col-span-12 lg:col-span-4 bg-white p-8 rounded-[3rem] border border-slate-100 shadow-sm flex flex-col justify-center">
            <h3 class="font-bold text-slate-400 mb-6 text-center uppercase text-[10px] tracking-widest">Impacto académico</h3>
            <ResearchStats />
          </div>

          <!-- HITOS (RESUMEN RÁPIDO) -->
          <div class="col-span-12 mt-4">
            <h2 class="text-2xl font-black text-slate-800 mb-8">Hitos significativos</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
              <div class="p-8 rounded-[2.5rem] bg-white border border-slate-100 hover:border-pink-200 transition-all shadow-sm">
                <span class="bg-pink-50 text-pink-600 text-[10px] font-black px-3 py-1 rounded-full uppercase">Investigación</span>
                <h4 class="font-bold text-xl text-slate-800 mt-4">Trauma y Aprendizaje</h4>
                <p class="text-slate-500 mt-3 text-sm leading-relaxed italic">Publicación sobre barreras de aprendizaje con Matrícula de Honor.</p>
              </div>
              <div class="p-8 rounded-[2.5rem] bg-white border border-slate-100 hover:border-pink-200 transition-all shadow-sm">
                <span class="bg-slate-100 text-slate-600 text-[10px] font-black px-3 py-1 rounded-full uppercase">Innovación</span>
                <h4 class="font-bold text-xl text-slate-800 mt-4">Pimpoyo: Chatbot IA</h4>
                <p class="text-slate-500 mt-3 text-sm leading-relaxed italic">Desarrollo de herramientas digitales para el pensamiento crítico.</p>
              </div>
            </div>
            <div class="mt-8 text-center">
              <button @click="currentSection = 'investigacion'" class="text-pink-600 font-bold text-sm hover:underline flex items-center gap-2 mx-auto">
                <span>Explorar investigación detallada</span>
                <ArrowRightIcon :size="16" />
              </button>
            </div>
          </div>
        </div>

        <!-- --- SECCIÓN CV (TRAYECTORIA) --- -->
        <div v-if="currentSection === 'cv'" class="grid grid-cols-12 gap-10">
          <!-- Experiencia -->
          <div class="col-span-12 lg:col-span-7 space-y-8">
            <h2 class="text-3xl font-black text-slate-900">Experiencia profesional</h2>
            <div class="space-y-6">
              <div v-for="exp in experiencia" :key="exp.puesto" 
                class="flex gap-8 p-6 rounded-[2rem] bg-slate-50/50 border border-slate-100 hover:bg-white hover:shadow-md transition-all">
                <div class="text-pink-600 font-black text-xs min-w-[80px] pt-1">{{exp.fecha}}</div>
                <div>
                  <h4 class="font-bold text-slate-900 text-lg">{{exp.puesto}}</h4>
                  <p class="text-xs text-slate-400 font-bold uppercase tracking-widest mt-1">{{exp.lugar}}</p>
                  <p class="text-slate-500 text-sm mt-3 leading-relaxed">{{exp.desc}}</p>
                </div>
              </div>
            </div>
          </div>

          <!-- Skills -->
          <div class="col-span-12 lg:col-span-5 space-y-10">
            <h2 class="text-3xl font-black text-slate-900">Habilidades</h2>
            <div class="bg-white p-8 rounded-[2.5rem] border border-slate-100 shadow-sm">
              <h4 class="text-[10px] font-black text-slate-400 uppercase mb-8 text-center tracking-widest">Competencias transversales</h4>
              <div class="flex justify-around">
                <div v-for="skill in transversalSkills" :key="skill.name" class="flex flex-col items-center gap-3">
                  <div class="relative w-16 h-16">
                    <svg class="w-full h-full" viewBox="0 0 36 36">
                      <path class="stroke-slate-100" stroke-width="3" fill="none" d="M18 2.0845 a 15.9155 15.9155 0 0 1 0 31.831 a 15.9155 15.9155 0 0 1 0 -31.831" />
                      <path class="stroke-pink-500" stroke-width="3" :stroke-dasharray="skill.value + ', 100'" stroke-linecap="round" fill="none" d="M18 2.0845 a 15.9155 15.9155 0 0 1 0 31.831 a 15.9155 15.9155 0 0 1 0 -31.831" />
                    </svg>
                    <div class="absolute inset-0 flex items-center justify-center text-[10px] font-black text-slate-800">{{skill.value}}%</div>
                  </div>
                  <span class="text-[9px] font-black text-slate-500 uppercase tracking-tighter">{{skill.name}}</span>
                </div>
              </div>
            </div>
            <!-- Formación Rápida -->
            <div class="bg-slate-900 text-white p-8 rounded-[2.5rem] shadow-xl">
              <h4 class="text-pink-500 font-black text-xs uppercase mb-6">Formación destacada</h4>
              <div class="space-y-6">
                <div v-for="edu in formacion" :key="edu.titulo" class="border-l border-white/20 pl-4">
                  <p class="text-[10px] font-bold opacity-50">{{edu.fecha}}</p>
                  <p class="font-bold text-sm">{{edu.titulo}}</p>
                  <p class="text-[10px] opacity-50">{{edu.lugar}}</p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- --- OTRAS SECCIONES --- -->
        <div v-if="currentSection === 'investigacion'">
          <ResearchGallery />
        </div>
        <div v-if="currentSection === 'contacto'">
          <ContactForm />
        </div>

      </div>

      <TheFooter class="mt-20 border-t border-slate-50 pt-10" />
    </main>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'
import { GraduationCapIcon, ArrowRightIcon } from 'lucide-vue-next'
import SideNav from './components/SideNav.vue'
import ResearchStats from './components/ResearchStats.vue'
import ResearchGallery from './components/ResearchGallery.vue'
import ContactForm from './components/ContactForm.vue'
import TheFooter from './components/TheFooter.vue'

const currentSection = ref('inicio')

const experiencia = [
  { fecha: 'OCT 2024 - ACT', puesto: 'Profesora de Inglés', lugar: 'Colegio ADDIS / Mater Purissima', desc: 'Diseño de sesiones dinámicas e inmersión total lingüística.' },
  { fecha: 'JUL 2024 - ACT', puesto: 'Asistente de Fotografía Infantil', lugar: 'Analkanewborn', desc: 'Atención a recién nacidos y coordinación profesional con familias.' },
  { fecha: '1 AÑO', puesto: 'Voluntariado Docente', lugar: 'Cruz Roja Española', desc: 'Acompañamiento emocional, atención a la diversidad y planificación lúdica.' },
  { fecha: '6 MESES', puesto: 'Prácticas de Intervención', lugar: 'CEIP El Guernica / Pablo Neruda', desc: 'Liderazgo docente, diseño de ambientes y evaluación pedagógica.' },
  { fecha: '3 AÑOS', puesto: 'Administración y Recepción', lugar: 'DHL / Inditex / Haitong Bank', desc: 'Gestión administrativa, atención al cliente y logística.' }
]

const transversalSkills = [
  { name: 'Gestión', value: 90 }, { name: 'Atención', value: 85 }, { name: 'Logística', value: 80 }
]

const formacion = [
  { fecha: '2024-2025', titulo: 'Máster Investigación e Innovación', lugar: 'UNED' },
  { fecha: '2020-2024', titulo: 'Grado Magisterio Infantil', lugar: 'Univ. de Alcalá (UAH)' },
  { fecha: '2023', titulo: 'Curso Front-End Dev', lugar: 'FreeCodeCamp' },
  { fecha: '2018-2020', titulo: 'Bachillerato Ciencias Sociales', lugar: 'Mater Purissima' }
]

onMounted(() => {
  gsap.from("main", { opacity: 0, y: 20, duration: 1, ease: "power2.out" })
})
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@400;600;700&display=swap');

.animate-fade-in { animation: fadeIn 0.6s ease-out; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

body { font-family: 'Quicksand', sans-serif; margin: 0; color: #1e293b; background: #f8fafc; }
progress::-webkit-progress-value { background-color: #db2777; transition: width 1.5s ease-in-out; }
main::-webkit-scrollbar { width: 5px; }
main::-webkit-scrollbar-thumb { background-color: #e2e8f0; border-radius: 10px; }
</style>