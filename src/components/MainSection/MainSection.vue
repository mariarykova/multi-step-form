<template>
    <div class="main-section">
        <div class="uptitle">Cloneables FOR WEBFLOW</div>
    <h1 class="title">Multi-step Form Webflow Cloneable Template</h1>
    <p class="subtext">
        Want to receive a monthly email in your inbox with awesome free Webflow cloneables, resources and more? Please submit your email below.
    </p>
    <div class="subscription">
        <BaseSubscriptionInput></BaseSubscriptionInput>
        <div class="subscription-text">
            <img src="/svg/checked.svg" alt="checked" />
            It's <span class="highlight">100% free</span> and we will never send more than one email per month</div>
    </div>
    <div class="preview">
        <div class="preview-text">Multi Step Form - Step 1</div>
        <button class="preview-btn">Preview Cloneable</button>
    </div>
    <!-- <div class="blob"> -->
        <img src="/images/main-bg.png" alt="background main" class="bg-main" />
    <!-- </div> -->

    </div>
    
</template>

<script>
import BaseSubscriptionInput from '../Base/BaseSubscriptionInput.vue';

export default {
    name: 'MainSection',
    components: {
        BaseSubscriptionInput
    }
}
</script>

<style scoped>
.main-section {
     padding-bottom: 44px;
     margin: 0 auto;
}
.uptitle {
    font-family: var(--font-family);
    font-weight: 500;
    font-size: 16px;
    line-height: 112%;
    letter-spacing: 0.24em;
    text-transform: uppercase;
    text-align: center;
    color: var(--primary-color-1);
    margin-bottom: 12px;
}
.title {
    font-family: var(--font-family);
    font-weight: 700;
    font-size: 50px;
    line-height: 124%;
    text-align: center;
    color: var(--neutral-800);
    width: 100%;
    max-width: 680px;
    padding-bottom: 12px;
    margin: 0 auto;

}
.subtext {
    font-family: var(--font-family);
    font-weight: 400;
    font-size: 18px;
    line-height: 167%;
    text-align: center;
    color: var(--neutral-600);
    width: 100%;
    max-width: 623px;
    margin: 0 auto;
    padding-bottom: 50px;
}
.subscription {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 50px;
    flex-direction: column;
}
.subscription-text {
    font-family: var(--font-family);
    font-weight: 400;
    font-size: 16px;
    line-height: 144%;
    text-align: center;
    color: var(--neutral-600);
    padding-top: 20px;
    display: flex;
    align-items: center;
    gap: 5px;
}

.highlight {
    color: var(--primary-color-1);
}
.blob {
    position: absolute;
    bottom: 0;
    left: 0;
    z-index: -1;
    backdrop-filter: blur(140.12591552734375px);
}
.preview {
    border-radius: 18px;
max-width: 1242px;
width: 100%;
padding: 20px 20px;
    box-shadow: 0 12px 24px 0 rgba(20, 20, 43, 0.04), 0 -2px 4px 0 rgba(20, 20, 43, 0.02), 0 3px 14px 0 rgba(74, 58, 255, 0.03);
background: var(--neutral-100);
margin: 0 auto;
display: flex;
justify-content: space-between;
align-items: center

}
.preview-text {
    font-family: var(--font-family);
font-weight: 700;
font-size: 24px;
line-height: 146%;
color: var(--neutral-800);
}
.preview-btn {
    border-radius: 50px;
padding: 16px 28px 17px 28px;
background: var(--secondary-color-1);
font-family: var(--font-family);
font-weight: 500;
font-size: 16px;
line-height: 112%;
color: var(--primary-color-1);
border: none;

}
.bg-main {
    position: absolute;
    bottom: 0;
    left: 0;
    z-index: -1;
    
}
</style>