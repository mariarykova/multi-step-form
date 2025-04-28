<template>
    <h2 class="title">Our services</h2>
    <p class="subtitle">Please select which service you are interested in.</p>
    <div class="step-two-container">
        <StepTwoCard
            v-for="(service, index) in services"
            :key="index"
            :icon="service.icon"
            :text="service.text"
            :active="form.service === index"
            @click="selectService(index)"
        />
       
    </div>
</template>

<script>
import StepTwoCard from "./StepTwoCard.vue"

export default {
    components: { StepTwoCard },
    props: ['form'],
    data() {
        return {
            services: [
                {
                icon: "./svg/development.svg",
                text: "Development"
            },
            {
                icon: "./svg/design.svg",
                text: "Web Design"
            },
            {
                icon: "./svg/marketing.svg",
                text: "Marketing"
            },
            {
                icon: "./svg/other.svg",
                text: "Other"
            }
        ]
        }
    },
    methods: {
        selectService(service) {
            this.form.service = service
        }
    }
}

</script>

<style scoped>
.step-two-container {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    justify-content: space-between;
}  
</style>