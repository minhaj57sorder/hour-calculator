<script setup lang="ts">
import HourCalculator from '../components/HourCalculator.vue';

</script>

<template>
  <div class="calculate-hour-container">
    <div>
      <section class="header-section">

        <div class="container">
          <header class="calculate-hour-page-header">
            <div class="logo-container">
              <img src="/clock.png" alt="logo" class="logo-image" />
              <h2 class="logo">Calculate Hours</h2>
            </div>
            <div>
              <a href="/day-calculator/">Day Calculator</a>
            </div>
          </header>
        </div>
      </section>
      <section class="hour-calculator-main-container">

        <HourCalculator />
      </section>
      <!-- <section>Sponsors</section> -->
    </div>
  </div>
</template>

<style scoped></style>
