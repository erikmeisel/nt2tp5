<template lang="html">

  <section class="src-components-navigator">
		<button id="reset" @click="$emit('onRestart')">{{ rbText }}</button>
		<span id="message">{{ txtContent }}</span>

		<button id="easy" @click="setEasy()" :class="isHard?'':'selected'">easy</button>
		<button id="hard" @click="setHard()" :class="isHard?'selected':''">hard</button>
  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-components-navigator',
    props: ['rbText','txtContent','isHard'],
    mounted () {

    },
    data () {
      return {

      }
    },
    methods: {
      setHard() {
        this.$emit('onDifChanged',true)
      },
      setEasy() {
        this.$emit('onDifChanged',false)
      }
    },
    computed: {

    }
}


</script>

<style scoped lang="css">
  .src-components-navigator {
    background: #ffffff;
    height: 30px;
    text-align: center;
    margin: 0;
    margin-top: -30px;
  }
  .selected {
    background-color: steelblue;
    color: white;
  }
  button {
    border: none;
    background-color: white;
    font-family: "Montserrat", "Avenir";
    text-transform: uppercase;
    height: 100%;
    font-weight: 700;
    letter-spacing: 1px;
    color: steelblue;
    transition: all 0.3s;
    outline: none;
  }
  button:hover {
    color: white;
    background-color: steelblue;
  }  
  #message {
    color: #000000;
    display: inline-block;
    width: 20%;
  }  
</style>
