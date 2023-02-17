<template>
  <div>
    <parentComponent/>
  </div>
</template>

<script>
import parentComponent from './components/parentComponent.vue'
export default {
  name: 'App',
  components: {
    parentComponent
  }
}
</script>

