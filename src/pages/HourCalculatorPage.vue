<script setup lang="ts">
// import { ref } from 'vue'

// defineProps<{ msg: string }>()

// const count = ref(0)
import HourCalculator from '../components/HourCalculator.vue'
</script>

<template>
  <div class="calculate-hour-container">
    <header class="calculate-hour-page-header">
      <h2>Calculate Hours</h2>
    </header>
    <section>
      <HourCalculator/>
    </section>
    <!-- <section>Sponsors</section> -->
    <footer class="calculate-hour-page-footer">All rights reserved. Copyright © Hours Calculator</footer>
  </div>
</template>

<style scoped>

</style>
