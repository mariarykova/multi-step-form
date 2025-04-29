<template>
    <h2 class="title">Our services</h2>
    <p class="subtitle">Please select which service you are interested in.</p>
    <div class="step-two-container">
        <StepTwoCard
            v-for="(service, index) in services"
            :key="index"
            :icon="service.icon"
            :text="service.text"
            :active="isServiceSelected(index)"
            @click="toggleService(index)"
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
        isServiceSelected(serviceIndex) {
    return this.form.service.some(selected => selected.index === serviceIndex);
  },
  toggleService(serviceIndex) {
    const selectedService = this.services[serviceIndex];
    const idx = this.form.service.findIndex(selected => selected.index === serviceIndex);

    if (idx > -1) {
      this.form.service.splice(idx, 1);
    } else {
      this.form.service.push({
        index: serviceIndex,
        text: selectedService.text,
      });
    }
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