<template>
    <div class="card-wrapper" :class="{ active: active }">
        <div 
        class="circle"><img :src="icon" :alt="text" /></div>
        <div class="text">{{ text }}</div>
    </div>
</template>

<script>
export default {
    props: {
        icon: {
            type: String,
            required: true
        },
        text: {
            type: String,
            required: true
        },
        active: {
            type: Boolean,
            default: false
        }
    }
}
</script>
<style scoped>
.card-wrapper {
    border: 1px solid var(--neutral-300);
    border-radius: 16px;
    box-shadow: 0 2px 6px 0 rgba(19, 18, 66, 0.07);
    background: var(--neutral-100);
    display: flex;
    align-items: center;
    gap: 20px;
    padding: 15px;
    width: 100%;
    max-width: 255px;
    cursor: pointer;
}
.circle {
    border-radius: 100%;
    background-color: rgba(74, 58, 255, 0.15);
    width: 66px;
    height: 66px;
    display: flex;
    align-items: center;
    justify-content: center
}
.text {
    font-family: var(--font-family);
    font-weight: 500;
    font-size: 18px;
    line-height: 111%;
    color: var(--neutral-800);
}
.card-wrapper.active {
    border: 1px solid var(--primary-color-1);
}
    
</style>