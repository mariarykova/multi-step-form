<template>
    <button class="header-button">
        Clone now
    </button>
</template>

<style scoped>
    .header-button {
        border-radius: 56px;
        padding: 20px 40px 20px 40px;
        box-shadow: 0 3px 12px 0 rgba(74, 58, 255, 0.18);
        background: var(--primary-color-1);
        font-weight: 700;
        line-height: 111%;
        text-align: center;
        color: var(--neutral-100);
        border-color: transparent;
        cursor: pointer;
    }

    @media (max-width: 500px) {
        .header-button {
            padding: 10px 20px 10px 20px;
            font-size: 14px;
        }
    }
</style>