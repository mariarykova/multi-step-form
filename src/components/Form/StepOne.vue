<template>
        <h2 class="title">Contact details</h2>
        <p class="subtitle">Please complete a form with your personal data.</p>
        <div class="step-one-container">
            <BaseInput
                v-model="form.name"
                label="Name"
                type="text"
                placeholder="John Carter"
                icon="/svg/name.svg"
            />
            <BaseInput
                v-model="form.email"
                label="Email"
                type="email"
                placeholder="Email address"
                icon="/svg/email.svg"
            />
            <BaseInput
                v-model="form.phone"
                label="Phone number"
                type="tel"
                placeholder="(123) 456 - 7890"
                icon="/svg/phone.svg"
                mask="(##) ####-####"
                /> 
            <BaseInput
                v-model="form.company"
                label="Company"
                type="text"
                placeholder="Company name"
                icon="/svg/company.svg"
            />
        </div>
</template>

<script>
import BaseInput from '../Base/BaseInput.vue'

export default {
    components: { BaseInput },
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