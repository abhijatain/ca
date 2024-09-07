<script setup lang="ts">
import { BarChart } from '@/components/ui/chart-bar'

const data = [
{ x: 'Monday', Hours: 5 },
  { x: 'Tuesday', Hours: 6 },
  { x: 'Wednesday', Hours: 4 },
  { x: 'Thursday', Hours: 7 },
  { x: 'Friday', Hours: 6 },
  { x: 'Saturday', Hours: 8 },
  { x: 'Sunday', Hours: 3 }
]
</script>

<template>
  <BarChart
  
    :data="data"
    index="x"
    :categories="['Hours']"
    :y-formatter="(tick, i) => {
      return typeof tick === 'number'
        ? ` ${new Intl.NumberFormat('us').format(tick).toString()}`
        : ''
    }"
  />
</template>

