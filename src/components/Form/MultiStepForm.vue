<script>
import StepOne from './StepOne.vue'
import StepTwo from './StepTwo.vue'
import StepThree from './StepThree.vue'
import StepFour from "./StepFour.vue"
import BaseButton from '../Base/BaseButton.vue'

export default {
  components: { StepOne, StepTwo, StepThree, StepFour, BaseButton },
  data() {
    return {
      step: 1,
      steps: [1, 2, 3, 4],
      formData: {
        name: '',
        email: '',
        phone: '',
        company: '',
        service: [],
        budget: "",
      }
    }
  },
  methods: {
    nextStep() {
      console.log("next step")
      if (this.step === 1 && !this.validateStepOne()) return;
      if (this.step < 4) {
        this.step++;
      } else if (this.step === 4) {
        this.submitForm();
      }
     
    },
    prevStep() {
      if (this.step > 1) this.step--;
      
    },
    validateStepOne() {
      const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      const phonePattern = /^\(\d{2}\) \d{4}-\d{4}$/;

      if (!emailPattern.test(this.formData.email)) {
        alert('Please enter a valid email address.');
        return false;
      }
      if (!phonePattern.test(this.formData.phone)) {
        alert('Please enter a valid phone number.');
        return false;
      }
      return true;
    },
    submitForm() {
      localStorage.setItem('projectQuote', JSON.stringify(this.formData));
      alert('Form submitted successfully! 🎉');
      this.step = 1;
      this.formData = { name: '', email: '', phone: '', company: '', service: [], budget: '' };
  }
  },
  watch: {
  step(newVal) {
    console.log('Now on step', newVal);
  }
}
}
</script>

<template>
  <div class="form-section">
    <h2 class="form-title">Get a project quote</h2>
    <p class="form-subtitle">Please fill the form below to receive a quote for your project. Feel free to add as much detail as needed.</p>
    <div class="form-wrapper">
    <div class="form-container">
    <div class="progress-container">
        <div
          v-for="(s, index) in steps"
          :key="index"
          class="progress-step"
        >
            <div
            class="step"
            :class="{ completed: step > index + 1, active: step === index + 1 }"
            >
            {{ index + 1 }}
            </div>
            <div
            v-if="index < steps.length - 1"
            class="line"
            :class="{
              filled: step > index + 1,
              half: step === index + 1
            }"
            ></div>
        </div>
    </div>

    <div class="seperated-line"></div>
    <form @submit.prevent="nextStep">
    <div class="form-steps">

        <StepOne 
          v-if='step === 1'
          v-model:form="formData"
          >
        </StepOne>
        <StepTwo 
            v-if="step === 2"
            v-model:form="formData"
            >
        </StepTwo>
        <StepThree 
            v-if="step === 3"
            v-model:form="formData"
            >
        </StepThree>
        <StepFour 
            v-if="step === 4"
            v-model:form="formData"
            >
        </StepFour>
    </div>


        <div class="form-btns">
    <div>
      <BaseButton v-show="step > 1" variant="secondary" @click="prevStep">Previous Step</BaseButton>
    </div>
    <div>
      <BaseButton 
      v-show="step < 4" 
      variant="primary" 
      type="submit"
     
      >Next Step</BaseButton>
    </div>
   </div>
      </form>
    </div>
    </div>
  </div>
</template>

<style scoped>
.form-section {
  background: var(--neutral-200);
  padding: 128px 0px 128px 0px
}
.form-container {
    border: 1px solid var(--neutral-300);
    border-radius: 34px;
    box-shadow: 0 5px 16px 0 rgba(8, 15, 52, 0.06);
    background: var(--neutral-100);
    width: 100%;
    max-width: 598px;
    padding: 25px 50px;
    margin: 0 auto;
}
.form-title {
    font-weight: 700;
    font-size: 34px;
    line-height: 135%;
    text-align: center;
    color: var(--neutral-800);
}
.form-subtitle {
    line-height: 167%;
    text-align: center;
    color: var(--neutral-600);
    width: 100%;
    max-width: 566px;
    margin: 0 auto;
    padding-bottom: 50px;
}
.form-wrapper {
    width: 100%;
    max-width: 700px;
    margin: 0 auto;
}
.progress-container {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 30px;
}

.progress-step {
  display: flex;
  align-items: center;
  position: relative;
}
.form-steps {
  padding: 20px 0px;
  margin: 0 auto;
}
.steps {
  display: flex;
  margin-bottom: 20px;
}
.step {
    font-size: 16px;
    line-height: 144%;
    color: var(--neutral-600);
    border-radius: 100%;
    background-color: var(--neutral-300);
    width: 34px;
    height: 34px;
    display: flex;
    align-items: center;
    justify-content: center;
}
.step.active {
  background-color: var(--primary-color-1);
  color: var(--neutral-100);
  border-color: var(--primary-color-1);
}

.step.completed {
    background-color: var(--primary-color-1);
  color: var(--neutral-100);
  border-color: var(--primary-color-1);
}
.line {
    position: relative;
    border-radius: 40px;
    width: 98px;
    height: 6px;
    background: var(--neutral-300);
    margin-left: 15px;
    margin-right: 15px;
}
.line.filled {
  background: var(--primary-color-1);
}
.line::before {
  content: '';
  position: absolute;
  height: 100%;
  width: 50%;
  left: 0;
  background: var(--neutral-300);
  border-radius: 40px;
}
.line::after {
  content: '';
  position: absolute;
  height: 100%;
  width: 50%;
  right: 0;
  background: var(--neutral-300);
  border-radius: 40px;
}
.line.half::before {
  background: var(--primary-color-1);
}
.line.filled::before,
.line.filled::after {
  background: var(--primary-color-1);
}
.seperated-line {
    border: 1px solid var(--neutral-400);
    max-width: 596px;
    width: 100%;
    height: 0px;
    margin: 0 auto;
}
.form-btns {
    display: flex;
    justify-content: space-between;
    margin-top: 25px;
}

@media (max-width: 1025px) {
  .form-section {
    padding: 50px 0px;
  }
}

@media (max-width: 701px) {
  .form-subtitle {
    max-width: 450px;
  }
  .line {
    width: 65px;
    margin-left: 10px;
    margin-right: 10px;
  }
  .form-wrapper {
      width: 100%;
      max-width: 500px;
      margin: 0 auto;
    }
    .form-container {
    max-width: 400px;
    padding: 25px 25px;
    }
}

  @media (max-width: 500px) {
    .form-section {
      padding: 25px 0px
    }
    .form-title {
      font-size: 25px;
    }
    .form-subtitle {
      max-width: 350px;
      padding-bottom: 25px;
      font-size: 12px;
    }
    .form-wrapper {
      width: 100%;
      max-width: 350px;
      margin: 0 auto;
    }
    .form-container {
    max-width: 350px;
    padding: 25px 0px;
    }
    .progress-container {
      margin-bottom: 15px;
    }
    .step {
      width: 25px;
      height: 25px;
      font-size: 12px;
    }
    .line {
      width: 50px;
    margin-left: 5px;
    margin-right: 5px;
    }
    .seperated-line {
    max-width: 300px;
}

.form-steps{
    padding: 10px 15px;
    margin: 0 auto;
}
  }
</style>