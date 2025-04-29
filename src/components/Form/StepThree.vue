<template>
    <h2 class="title">What’s your project budget?</h2>
    <p class="subtitle">Please select the project budget range you have in mind.</p>
    <div class="step-three-container">
        <StepThreeSelect
        v-for="(budget, index) in budgets"
        :key="index"
        :text="budget.text"
        :active="form.budget?.index === index"
        @click="selectBudget(index)"
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
    methods: {
        selectBudget(budgetIndex) {
            const selectedBudget = this.budgets[budgetIndex];
            this.form.budget = {
            index: budgetIndex,
            text: selectedBudget.text
            };
  }
    }
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