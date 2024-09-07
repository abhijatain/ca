<template>
      <div class="grid grid-cols-7 gap-1 p-0 m-0 ">
            <div class="h-6 w-6 border bg-blue-300"  v-for="n in 30"></div>
        </div>
</template>

<script setup>

import websiteHoursData from '~/assets/website_hours_2024.json';

// Convert imported JSON data to a format that calendar-heatmap expects
const heatmapData = websiteHoursData.map(entry => ({
  date: entry.date,
  count: entry.hours
}));
</script>