<template>         
    <div class=" bg-groc col-sm-12">
      <div class="contadorText">
        <h2>
          <span id="days">{{this.dies}} dies, </span>  
          <span id="hours">{{this.hores}} hores, </span>  
          <span id="minutes">{{this.minuts}} minuts, </span>  
          <span id="seconds">{{this.segons}} segons</span> 
        </h2>
      </div>
    </div>
    
</template>


<script>
    const DATE_TARGET = new Date('07/16/2022 16:01');

    const MILLISECONDS_OF_A_SECOND = 1000;
    const MILLISECONDS_OF_A_MINUTE = MILLISECONDS_OF_A_SECOND * 60;
    const MILLISECONDS_OF_A_HOUR = MILLISECONDS_OF_A_MINUTE * 60;
    const MILLISECONDS_OF_A_DAY = MILLISECONDS_OF_A_HOUR * 24
    export default {
        name: 'CountDown',
        props: {
            seconds: {
                type: Number,
                required: true
            }
        },
        data () {
            return {
                dies: null,
                hores: null,
                minuts: null,
                segons: null,
            }
        },
        methods: {
            updateCountdown() {

              // Calcs
              var NOW = new Date()
              var DURATION = DATE_TARGET - NOW;
              var REMAINING_DAYS = Math.floor(DURATION / MILLISECONDS_OF_A_DAY);
              var REMAINING_HOURS = Math.floor((DURATION % MILLISECONDS_OF_A_DAY) / MILLISECONDS_OF_A_HOUR);
              var REMAINING_MINUTES = Math.floor((DURATION % MILLISECONDS_OF_A_HOUR) / MILLISECONDS_OF_A_MINUTE);
              var REMAINING_SECONDS = Math.floor((DURATION % MILLISECONDS_OF_A_MINUTE) / MILLISECONDS_OF_A_SECOND);
              
              this.dies = REMAINING_DAYS;
              this.hores = REMAINING_HOURS;
              this.minuts = REMAINING_MINUTES;
              this.segons = REMAINING_SECONDS;
          },
        },
        mounted () {
            this.updateCountdown()
        },
        beforeMount() {
          
          setInterval(() => {
            this.updateCountdown()
          }, 1000)
        }
    }
</script>

<style scoped>
.contadorText{
  position: relative;
  z-index: 333;
  /* IMPORTANTE */
  text-align: center;
  width: 100%;
  z-index: 1;
}
</style>
