<template>
    <div class="subscription-wrapper">
        <input placeholder="Enter your email" type="email" class="subscription-input" />
        <button class="subscribe-btn">Subscribe</button>
    </div>
</template>

<style scoped>
.subscription-wrapper {
    position: relative;
    max-width: 600px;
    width: 100%;
}
.subscription-input {
    border: 1px solid var(--neutral-300);
    border-radius: 60px;
    max-width: 555px;
    width: 100%;
    box-shadow: 0 8px 25px 0 rgba(13, 10, 44, 0.06);
    background: var(--neutral-100);
    padding: 30px 0px 30px 0px;
}
.subscription-input::placeholder {
    line-height: 111%;
    color: var(--neutral-600);
    padding-left: 25px;
}
.subscription-input:focus {
    outline: none;
    border: 1px solid var(--primary-color-1);
    box-shadow: 0 8px 25px 0 rgba(13, 10, 44, 0.06);
}
.subscribe-btn {
    position: absolute;
    top: 50%;
    right: 10%;
    transform: translateY(-50%);
    border-radius: 56px;
    padding: 16px 32px 19px 32px;
    box-shadow: 0 3px 12px 0 rgba(74, 58, 255, 0.18);
    background: var(--primary-color-1);
    border: 1px sold var(--primary-color-1);
    font-weight: 700;
    line-height: 111%;
    text-align: center;
    color: var(--neutral-100);
    cursor: pointer;
}
.subscribe-btn:hover {
    background: var(--neutral-100);
    color: var(--primary-color-1);
}

@media (max-width: 500px) {
    .subscription-wrapper {
        max-width: 350px;
        width: 100%;
        text-align: center;
    }
    .subscription-input {
        padding: 15px 0px 15px 0px;
        max-width: 320px;
    }
    .subscribe-btn {
        padding: 10px 20px 12px 20px;
        font-size: 12px;
    }
}
</style>