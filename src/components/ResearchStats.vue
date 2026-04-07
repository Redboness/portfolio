<template>
  <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
    <!-- Gráfico de Líneas: Evolución de Investigaciones -->
    <div class="bg-white p-6 rounded-[2.5rem] shadow-sm border border-pink-100">
      <h3 class="text-secondary font-bold mb-4 flex items-center gap-2">
        <TrendingUpIcon :size="18" class="text-pink-500" />
        <span>Actividad Investigadora</span>
      </h3>
      <div class="h-[250px]">
        <Line :data="lineData" :options="chartOptions" />
      </div>
    </div>

    <!-- Gráfico de Tarta: Áreas de Especialización -->
    <div class="bg-white p-6 rounded-[2.5rem] shadow-sm border border-pink-100">
      <h3 class="text-secondary font-bold mb-4 flex items-center gap-2">
        <TargetIcon :size="18" class="text-pink-500" />
        <span>Áreas de Enfoque</span>
      </h3>
      <div class="h-[250px] flex justify-center">
        <Doughnut :data="doughnutData" :options="chartOptions" />
      </div>
    </div>
  </div>
</template>

<script setup>
import {
  Chart as ChartJS,
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend,
  ArcElement
} from 'chart.js'
import { Line, Doughnut } from 'vue-chartjs'
import { TrendingUpIcon, TargetIcon } from 'lucide-vue-next'

ChartJS.register(
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend,
  ArcElement
)

const lineData = {
  labels: ['2020', '2021', '2022', '2023', '2024', '2025'],
  datasets: [
    {
      label: 'Publicaciones',
      backgroundColor: '#f472b6',
      borderColor: '#f472b6',
      data: [2, 5, 3, 8, 6, 10],
      tension: 0.4
    }
  ]
}

const doughnutData = {
  labels: ['Neuroeducación', 'Literatura', 'Aulas Verdes', 'Juego'],
  datasets: [
    {
      backgroundColor: ['#f472b6', '#9f7aea', '#fbbf24', '#60a5fa'],
      data: [40, 20, 25, 15]
    }
  ]
}

const chartOptions = {
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    legend: {
      position: 'bottom',
      labels: {
        usePointStyle: true,
        font: {
          family: 'Quicksand'
        }
      }
    }
  }
}
</script>
