<template>
    <div class="card-wrapper" :class="{ active: active }">
        <div 
        class="circle"><img :src="icon" :alt="text" class="image" /></div>
        <div class="text">{{ text }}</div>
    </div>
</template>

<script>
export default {
    props: {
        icon: {
            type: String,
            required: false
        },
        text: {
            type: String,
            required: true,
            default: 'Default Text'
        },
        active: {
            type: Boolean,
            default: false,
            required: false
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
    font-weight: 500;
    line-height: 111%;
    color: var(--neutral-800);
}
.card-wrapper.active {
    border: 1px solid var(--primary-color-1);
}

@media (max-width: 500px) {
    .circle[data-v-2aa0a84c] {
    width: 45px;
    height: 45px;
    }

    .image {
        width: 25px;
    }
    .text {
        font-size: 12px;
    }

}
    
</style>