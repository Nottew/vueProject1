<template id="square-template">
  <div class="square">
   
  </div>
</template>

<script>

export default {
  name: 'square',
  data () {
    return {
      first: ''
    }
  },
  methods: {

  },
  computed: {
    firstComputed () {
      return this.first + '!' //будет меняться тогда, когда одна из переменных внутри изменится (first)
    }
  },
  created () {
    console.log('createdF1');
  },
  mounted () {
    console.log('mountedF1')
  },
  destroyed () {
    console.log('f1 has been destroyed');
  }
}
</script>

<style scoped>
</style>