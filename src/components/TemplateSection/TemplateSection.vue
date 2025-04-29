<template>
    <div class="template-section-wrapper">
        <div class="template-section">
        <BaseCard
            logo="./svg/logo-white.svg"
            title="Take a look at our amazing premium Webflow Templates"
            text="Also than having free Webflow cloneables, we create cutting-edge premium Webflow templates too."
            buttonText="Browse templates"
            image="./images/img-template.png"
            @button-click="handleCardClick"
            theme="light"
            />

        <BaseCard
          logo="./svg/logo-color.svg"
          title="Looking to design & develop an amazing Webflow website?"
          text="If you want to get a hand from the amazing team behind BRIX Templates, get in touch with BRIX Agency today."
          buttonText="Get a quote"
          image="./images/img-quote.png"
          @button-click="handleMarketingClick"
          theme="dark"
        />
        </div>
        <img src="/images/template-bg.png" alt="background template" class="bg-template" />
    </div>
</template>

<script>
import BaseCard from '../Base/BaseCard.vue';

export default {
  components: { BaseCard },
  methods: {
    handleCardClick() {
      console.log('Card 1 button clicked!');
    },
    handleMarketingClick() {
      console.log('Card 2 button clicked!');
    }
  }
}

</script>

<style scoped>
.template-section-wrapper {
    position: relative;
}
.template-section {
    padding: 128px 0px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1240px;
    width: 100%;
    margin: 0 auto;
    position: relative;
    z-index: 1;
}
.bg-template {
    position: absolute;
    bottom: 0;
    right: 0;

}

@media (max-width: 1025px) {
  .template-section {
    flex-direction: column;
    gap: 50px;
    padding: 50px 0px;
  }
  @media (max-width: 500px) {
  .template-section {
    gap: 25px;
    padding: 25px 0px;
  }
}

}
</style>