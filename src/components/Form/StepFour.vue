<template>
    <div class="form-step-four">
        <img
        class="form-image"
        src="/svg/submit.svg"
        alt="Step four image"
    />
        <h2 class="title">Submit your quote request</h2>
        <p class="subtitle">Please review all the information you previously typed in the past steps, and if all is okay, submit your message to receive a project quote in 24 - 48 hours.</p>
        <button class="submit-btn" @click="$emit('submit')">Submit</button>

    </div>
</template>

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
.submit-btn {
    border-radius: 56px;
    padding: 20px 40px 21px 40px;
    font-weight: 700;
    font-size: 18px;
    line-height: 111%;
    text-align: center;
    color: var(--neutral-100);
    cursor: pointer;
    border: none;
    box-shadow: 0 3px 12px 0 rgba(74, 58, 255, 0.18);
    background: var(--primary-color-1);
}

@media (max-width: 500px) {
    .form-step-four {
    padding: 25px 0px;
}
.form-image {
    width: 100%;
    max-width: 100px;
}

.submit-btn {
    padding: 10px 20px;
    font-size: 14px;
}
}

</style>