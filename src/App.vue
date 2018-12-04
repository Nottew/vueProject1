<template>
  <div>
   <Forms 
       :fields="fields1" 
       header="header"
       @eventName="parentEvent"
   >Hello</Forms>
   <Forms/>
   <ul>
     <li v-for="(item, index) in items" :key="index">
       {{ item }}
     </li>
   </ul>
  </div>
</template>

<script>
import Forms from './components/Forms'

export default {
  name: 'App',
  data() {
    return {
      currentView: 'square',
      fields1: ['text', 'radio', 'checkbox', 'submit'],
      fields2: ['text', 'text', 'submit'],
      fields2: ['text', 'text', 'submit', 'text'],
      items: [],
    }
  },
  components: {
    // Forms: Forms
    Forms
  },
  methods: {
    parentEvent(value) {
      this.items.push(value)
    }
  }
}
</script>

<style>

</style>