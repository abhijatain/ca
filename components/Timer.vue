<script>



export default {

  data() {
    return {
      time: { days: 0, hours: 0, minutes: 0, seconds: 0 },
      targetDate: new Date('2024-11-30'),
   
    };
  },
  mounted() {
    this.startTimer();

   
  },
  methods: {
    startTimer() {
      setInterval(() => {
        const diff = this.targetDate - new Date();
        this.time.days = Math.floor(diff / (1000 * 60 * 60 * 24));
        this.time.hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
        this.time.minutes = Math.floor((diff / 1000 / 60) % 60);
        this.time.seconds = Math.floor((diff / 1000) % 60);
      }, 1000);
    },
  },
};

</script>

<template>
    <div class="items-bottom">
                
                <Button variant="outline">{{ time.days }} D</Button>
                <span> : </span>
                <Button variant="outline">{{ time.hours }} H</Button>
                <span> : </span>
                <Button variant="outline">{{ time.minutes }} M</Button>
                <span class="hidden md:inline-block"> : </span>
                <Button variant="outline" class="hidden md:inline-block">{{ time.seconds }} S</Button>
            </div>
</template>