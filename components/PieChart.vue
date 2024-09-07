<script setup lang="ts">
import { VisSingleContainer, VisDonut, VisBulletLegend } from '@unovis/vue'
import { data } from '../data/pie.ts'
import { Donut } from '@unovis/ts'

const legendItems = Object.entries(data).map(([_, data]) => ({
  name: data.key.charAt(0).toUpperCase() + data.key.slice(1)
}))

const events = {
    [Donut.selectors.segment]: (d: DataRecord) => `<span>x :  ${d.key}<br / >y :  ${d.value}< / span>`
    
  }
</script>

<template>
    <div class="flex flex-col gap-6 mt-2 ">
       
  <VisBulletLegend :items="legendItems" class="ms-4 md:ms-0"/>
  <VisSingleContainer :height="300">
  <VisDonut
    :value="d => d.value"
    :data="data"
    :showEmptySegments="true"
    :padAngle="0.01"
    :arcWidth="100"
    :events="events"
    centralLabel="Questions" 
  centralSubLabel="Chapter 1 progress"
  />
 
</VisSingleContainer>
    </div>

</template>
