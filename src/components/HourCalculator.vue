<template>
    <div class="hour-claculator-container">
        <div class="hour-calculator-header">
            <h3>Hours Calculator</h3>
        </div>
        <div class="title-output-container">
            <div class="hours-minutes-outputs-titles">
                <h5>{{ totalHours }}</h5>
                <h5>-:-</h5>
                <h5>{{ totalMinutes }}</h5>
            </div>
            <div class="hours-minutes-input-titles">
                <h5>Hours</h5>
                <h5>-:-</h5>
                <h5>Minutes</h5>
            </div>
        </div>
        <div class="hour-calculator-inputs-container-space">
            <div class="hour-calculator-inputs-container">
                <div v-for="i in totalInputLength" class="hours-minutes-input-container">
                    <div class="hours-input"><input ref="inputHours" type="text" @input="calculate"></div>
                    <div class="hours-minutes-separator">:</div>
                    <div class="minutes-input"><input ref="inputMinutes" type="text" @input="calculate"></div>
                </div>
            </div>
        </div>
        <div class="add-more-input">
            <button @click="addInput">Add input</button>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
// defineProps<{ msg: string }>()
const totalInputLength = ref(8)
const totalHours = ref(0)
const totalMinutes = ref(0)
const inputHours = ref([])
const inputMinutes = ref([])
const addInput = () => {
    totalInputLength.value += 2
}
const calculate = () => {
    console.log('Calculating...', inputHours.value[0].value, inputMinutes.value)
    let minutes = inputMinutes.value.reduce((acc, curr) => Number(acc) + Number(curr.value), 0)
    let hours = inputHours.value.reduce((acc, curr) => Number(acc) + Number(curr.value), 0)
    console.log('Total hours:', hours, minutes)
    totalHours.value = Math.floor(minutes / 60) + hours
    totalMinutes.value = minutes % 60
}
// import HourCalculator from '../components/HourCalculator.vue'
</script>

<style scoped></style>