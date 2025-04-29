<template>
    <h2 class="title">Contact details</h2>
    <p class="subtitle">Please complete a form with your personal data.</p>
    <div class="step-one-container">
        <StepOneInput
            v-model="form.name"
            label="Name"
            type="text"
            placeholder="John Carter"
            icon="/svg/name.svg"
        />
        <StepOneInput
            v-model="form.email"
            label="Email"
            type="email"
            placeholder="Email address"
            icon="/svg/email.svg"
        />
        <StepOneInput
            v-model="form.phone"
            label="Phone number"
            type="tel"
            placeholder="(123) 456 - 7890"
            icon="/svg/phone.svg"
        />
        <StepOneInput
            v-model="form.company"
            label="Company"
            type="text"
            placeholder="Company name"
            icon="/svg/company.svg"
        />

    </div>
</template>

<script>
import StepOneInput from './StepOneInput.vue'

export default {
    components: { StepOneInput },
    props: ['form'],
}
</script>

<style scoped>
.step-one-container {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    justify-content: space-between;
}

@media (max-width: 500px) {
    .step-one-container {
        gap: 0.5rem;
        justify-content: center;
}
}
</style>