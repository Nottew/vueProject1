<template>
    <div class="container">
      <div>{{ header }}</div>
      <form>
        <input 
          v-for="(field, i) in fields"
          v-model='input'
          :type="field" 
          :key="i"
          @keyup.enter="handleEnter"
          @click="showWithLeft"
          @contextmenu="hideWithRight"
        >
        <div class="square"
        v-if="show"
        >1</div>
      </form>
    </div>
</template>

<script>
export default {
    name: 'Forms',
    data() {
        return {
          input: '',
          show: false
        }
    },
    props: {
      'fields': Array,
      'header': String,
      'footer': {
        type: Number
      }
    },
    methods: {
      handleEnter(event) {
        event.preventDefault()
        console.log( event.preventDefault() )
        // К родителю передать
        // $emit системное
        this.$emit('eventName', this.input)
        this.input = ''
      },
      showWithLeft () {
          this.show = true;
          console.log(show);
      },
      hideWithRight ( event ) {
          event.preventDefault();
          this.show = false;
          console.log(show);
      }
    }
}
</script>

<style scoped>
.container {
  width: 50%;
  margin: auto;
  background-color: #ebebeb;
  box-shadow: 1px 2px 2px grey;
}
</style>