<script setup lang="ts">
import { ref } from 'vue';
import {commonData} from './commonstate.ts';

const commonState = ref(commonData);
commonState.value.currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="calculate-hour-page-footer">All rights reserved. Copyright © Hours Calculator {{ commonState.currentYear }}</footer>
</template>
