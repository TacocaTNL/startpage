<template>
  <h1>Goede {{ dayPart }}, Jack</h1>
</template>

<script>
export default {
  name: 'IrohQuotes',
  data() {
      return  {
        dayPart: ''
      }
  },
      props: {
      },
  methods: {
      calculateDayPart() {
        let d = new Date();
        let dayInSeconds = d.getHours()*3600 + d.getMinutes()*60 + d.getSeconds();
        
        /* Check if it is night */
        if (dayInSeconds >= 0 && dayInSeconds < 21500) {
            this.dayPart = 'nacht';
        }
        
        /* Check if it is morning */
        if (dayInSeconds >= 21500 && dayInSeconds < 43000) {
            this.dayPart = 'morgen';
        }
        
        /* Check if it is afternoon */
        if (dayInSeconds >= 43000 && dayInSeconds < 64500) {
            this.dayPart = 'middag';
        }
        
        /* Check if it is evening */
        if (dayInSeconds >= 64500) {
            this.dayPart = 'avond';
        }
      }
  },
  mounted() {
      setInterval(() => {
          this.calculateDayPart();
      }, 1000);
  },
}
</script>

<style scoped>

</style>
