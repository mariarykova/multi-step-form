<template>
    <div class="subscription-wrapper">
        <input placeholder="Enter your email" type="email" class="subscription-input" />
        <button class="subscribe-btn">Subscribe</button>
    </div>
  
</template>

<style scoped>
.subscription-wrapper {
  position: relative;
  width: 640px;
  height: 77px;
}
.subscription-input {
    border: 1px solid var(--neutral-300);
    border-radius: 60px;
    width: 599px;
    height: 77px;
    box-shadow: 0 8px 25px 0 rgba(13, 10, 44, 0.06);
    background: var(--neutral-100);
    padding-left: 50px;
}

.subscription-input::placeholder {
    font-family: var(--font-family);
    font-weight: 400;
    font-size: 18px;
    line-height: 111%;
    color: var(--neutral-600);
}
.subscription-input:focus {
    outline: none;
    border: 1px solid var(--primary-color-1);
    box-shadow: 0 8px 25px 0 rgba(13, 10, 44, 0.06);
}
.subscribe-btn {
    position: absolute;
    top: 50%;
    right: 5px;
    transform: translateY(-50%);
    border-radius: 56px;
    padding: 16px 32px 19px 32px;
    width: 153px;
    height: 55px;
    box-shadow: 0 3px 12px 0 rgba(74, 58, 255, 0.18);
    background: var(--primary-color-1);
    border: 1px sold var(--primary-color-1);
    font-family: var(--font-family);
    font-weight: 700;
    font-size: 18px;
    line-height: 111%;
    text-align: center;
    color: var(--neutral-100);
    cursor: pointer;
}

.subscribe-btn:hover {
    background: var(--neutral-100);
    color: var(--primary-color-1);
}
</style>