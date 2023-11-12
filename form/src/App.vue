<template>
  <div id="app">
    <div v-if="created">
      <Success />
    </div>
    <div v-else>
      <Form v-on:create="created = true" />
    </div>
  </div>
</template>

<script>
import Form from './components/Form.vue';
import Success from './components/Success.vue';


export default {
  name: 'App',
  components: {
    Form,
    Success,
    Success
},
data(){
  return {
    created: false,
  }
}
}
</script>

<style>

</style>
