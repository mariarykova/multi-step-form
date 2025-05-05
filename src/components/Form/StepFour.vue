<template>
    <div class="form-step-four">
        <img
        class="form-image"
        src="/svg/submit.svg"
        alt="Step four image"
    />
        <h2 class="title">Submit your quote request</h2>
        <p class="subtitle">Please review all the information you previously typed in the past steps, and if all is okay, submit your message to receive a project quote in 24 - 48 hours.</p>
        <BaseButton variant="primary" type="submit">Submit</BaseButton>
    </div>
</template>

<script>
import BaseButton from '../Base/BaseButton.vue'
export default {
    name: 'StepFour',
    components: { BaseButton },
    emits: ['submit'],
}
</script>
<style scoped>
.form-step-four {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    padding: 50px 0px;
}
.subtitle {
    text-align: center;
    width: 100%;
    max-width: 495px;
}

@media (max-width: 500px) {
    .form-step-four {
    padding: 25px 0px;
}
.form-image {
    width: 100%;
    max-width: 100px;
}

}

</style>