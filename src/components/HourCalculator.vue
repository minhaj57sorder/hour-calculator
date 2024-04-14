<template>
    <div class="hour-claculator-container">
        <div class="hour-calculator-header">
            <h3>Hours Calculator</h3>
        </div>
        <div class="title-output-container">
            <div class="hours-minutes-outputs-titles">
                <h5>
                    Your Total :->
                </h5>
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
                <div v-for="i in totalInputLength" :key="i" class="hours-minutes-input-container">
                    <div class="hours-input"><input ref="inputHours" type="text" @input="calculate"></div>
                    <div class="hours-minutes-separator">:</div>
                    <div class="minutes-input"><input ref="inputMinutes" type="text" @input="calculate"></div>
                </div>
            </div>
        </div>
        <div class="add-more-input">
            <button @click="addInput">+ Add More Lines</button>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref, Ref } from 'vue'

interface Input {
    value: string;
}

const totalInputLength: Ref<number> = ref(8)
const totalHours: Ref<number> = ref(0)
const totalMinutes: Ref<number> = ref(0)
const inputHours: Ref<Input[]> = ref([])
const inputMinutes: Ref<Input[]> = ref([])

const addInput = (): void => {
    totalInputLength.value += 2
}

const calculate = (): void => {
    let minutes: number = inputMinutes.value.reduce((acc: number, curr: Input) => Number(acc) + Number(curr.value), 0)
    let hours: number = inputHours.value.reduce((acc: number, curr: Input) => Number(acc) + Number(curr.value), 0)
    totalHours.value = Math.floor(minutes / 60) + hours
    totalMinutes.value = minutes % 60
}
// import HourCalculator from '../components/HourCalculator.vue'
</script>

<style scoped></style>