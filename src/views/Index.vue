<template>
  <div class="index">
    <PizzaDescription/>
    <Tray/>
  </div>
</template>

<script>
// @ is an alias to /src
import PizzaDescription from '@/components/PizzaDescription.vue'
import Tray from '@/components/Tray.vue'
export default {
  name: 'Index',
  components: {
    PizzaDescription,
    Tray
  }
}
</script>

