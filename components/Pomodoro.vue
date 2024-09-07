<template>
    <div class="md:p-6 p-2 flex flex-col justify-center">
      <Card :class="cardBgColor" class="text-white">
        <CardHeader class="p-4 md:p-6">
          <CardTitle>Pomodoro Technique</CardTitle>
          <CardDescription class="text-white">This technique helps maintain concentration, avoid burnout, and improve overall productivity.</CardDescription>
        </CardHeader>
        <CardContent>
          <div class="flex justify-center mt-4 gap-2">
            <Button
              class="bg-transparent"
              variant="outline"
              @click="getType('Pomodoro')"
            >
              Pomodoro
            </Button>
            <Button
              class="bg-transparent"
              variant="outline"
              @click="getType('Shortbreak')"
            >
              Short Break
            </Button>
            <Button
              class="bg-transparent"
              variant="outline"
              @click="getType('Longbreak')"
            >
              Long Break
            </Button>
          </div>
          <div class="text-center md:p-6 p-4 m-6">
            <h3 class="flex items-center justify-center text-6xl">{{ formattedTime }}</h3>
          </div>
          <div class="flex justify-center mt-6">
            <Button
              class="text-4xl px-14 py-6"
              :class="buttonColor"
              variant="outline"
              @click="startTimer"
              v-if="!isRunning"
            >
              Start
            </Button>
            <Button
              class="text-4xl px-14 py-6"
              :class="buttonColor"
              variant="outline"
              @click="stopTimer"
              v-if="isRunning"
            >
              Stop
            </Button>
          </div>
        </CardContent>
      </Card>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  const timer_type_pomodoro = 'Pomodoro';
  const timer_type_shortbreak = 'Shortbreak';
  const timer_type_longbreak = 'Longbreak';
  
  const pomodoroType = ref(timer_type_pomodoro);
  const timerValue = ref(1500); // 25 minutes
  const isRunning = ref(false);
  let intervalId = null;
  
  const getType = (type) => {
    pomodoroType.value = type;
    resetTimer();
  };
  
  const formattedTime = computed(() => {
    const minutes = Math.floor(timerValue.value / 60).toString().padStart(2, '0');
    const seconds = (timerValue.value % 60).toString().padStart(2, '0');
    return `${minutes}:${seconds}`;
  });
  
  const startTimer = () => {
    if (!isRunning.value) {
      isRunning.value = true;
      intervalId = setInterval(() => {
        if (timerValue.value > 0) {
          timerValue.value--;
          updateProgressBar();
        } else {
          stopTimer();
        }
      }, 1000);
    }
  };
  
  const stopTimer = () => {
    clearInterval(intervalId);
    isRunning.value = false;
  };
  
  const resetTimer = () => {
    stopTimer();
    switch (pomodoroType.value) {
      case timer_type_pomodoro:
        timerValue.value = 1500;
        break;
      case timer_type_shortbreak:
        timerValue.value = 300;
        break;
      case timer_type_longbreak:
        timerValue.value = 900;
        break;
    }
    updateProgressBar();
  };
  
  const updateProgressBar = () => {
    const progress = 360 * (timerValue.value / 1500);
    circularProgressBarStyle.value.background = `conic-gradient(#664efe ${progress}deg, #422f66 0deg)`;
  };
  
  const cardBgColor = computed(() => {
    switch (pomodoroType.value) {
      case timer_type_pomodoro:
        return 'bg-[#c65151]';
      case timer_type_shortbreak:
        return 'bg-[#38858a]'; // Example color for short break
      case timer_type_longbreak:
        return 'bg-[#397097]'; // Example color for long break
      default:
        return 'bg-[#c65151]';
    }
  });
  
  const buttonColor = computed(() => {
    switch (pomodoroType.value) {
      case timer_type_pomodoro:
        return 'text-[#c65151]';
      case timer_type_shortbreak:
        return 'text-[#38858a]'; // Example color for short break
      case timer_type_longbreak:
        return 'text-[#397097]'; // Example color for long break
      default:
        return 'text-[#c65151]';
    }
  });
  </script>
  
  
  <style scoped>
  /* Any scoped styles for this component (if needed) */
  </style>
  