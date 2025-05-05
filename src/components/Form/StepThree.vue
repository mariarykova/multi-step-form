<template>
    <h2 class="title">What’s your project budget?</h2>
    <p class="subtitle">Please select the project budget range you have in mind.</p>
    <div class="step-three-container">
    <StepThreeSelect
        v-for="option in budgets"
        :key="option.text"
        :text="option.text"
        v-model="form.budget"
        />
    </div>
</template>

<script>
import StepThreeSelect from "./StepThreeSelect.vue"

export default {
    components: { StepThreeSelect },
    props: ['form'],
    data() {
        return {
            budgets: [
                {
                text: "$5.000 - $10.000"
            },
            {
                text: "$10.000 - $20.000"
            },
            {
                text: "$20.000 - $50.000"
            },
            {
                text: "$50.000 +"
            }
        ]
        }
    },
}

</script>

<style scoped>
.step-three-container {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    justify-content: space-between;
}  
</style>