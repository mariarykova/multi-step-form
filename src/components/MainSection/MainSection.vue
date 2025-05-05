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
            <div>It's <span class="highlight">100% free</span> and we will never send more than one email per month</div></div>
    </div>
    <div class="preview">
        <div class="preview-text">Multi Step Form - Step 1</div>
        <button class="preview-btn">Preview Cloneable</button>
    </div>
        <img src="/images/main-bg.png" alt="background main" class="bg-main" />
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
     padding-top: 42px;
     margin: 0 auto;
}
.uptitle {
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
    margin-bottom: 115px;
    flex-direction: column;
}
.subscription-text {
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
    max-width: 1000px;
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
    font-weight: 700;
    font-size: 24px;
    line-height: 146%;
    color: var(--neutral-800);
}
.preview-btn {
    border-radius: 50px;
    padding: 16px 28px 17px 28px;
    background: var(--secondary-color-1);
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

@media (max-width: 1025px) {
    .preview {
        max-width: 600px;
    }
}
@media (max-width: 701px) {
    .preview {
        max-width: 450px;
        padding: 15px 15px;
    }
    .preview-text {
    font-size: 16px;
}
.preview-btn {
    padding: 14px 20px 14px 20px;
    font-size: 14px;
}
.subscription {
    margin-bottom: 50px;
}
.subscription-text {
    font-size: 14px;
}
.subtext {
    max-width: 450px;
}

}

@media (max-width: 500px) {
    .uptitle {
        font-size: 12px;
    }
    .title {
        font-size: 24px;
    }
    .subtext {
        font-size: 12px;
        padding-bottom: 25px;
        max-width: 350px;
    }
    .subscription {
        margin-bottom: 50px;
    }
    .subscription-text {
        font-size: 10px;
    }
    .preview {
        max-width: 350px;
        padding: 5px 10px;
    }
    .preview-text {
        font-size: 12px;
    }
    .preview-btn[data-v-c47bc215] {
        padding: 10px 15px;
        font-size: 12px;
}
.bg-main {
    width: 100%;
max-width: 300px;
}
.main-section {
     padding-bottom: 25px;
     padding-top: 25px;
}
}
</style>