<script>
import StepOne from './StepOne.vue'
import StepTwo from './StepTwo.vue'
import StepThree from './StepThree.vue'
import StepFour from "./StepFour.vue"

export default {
  components: { StepOne, StepTwo, StepThree, StepFour },
  data() {
    return {
      step: 4,
      steps: ['1', '2', '3', '4'],
      formData: {
        name: '',
        email: '',
        phone: '',
        company: '',
        service: 0,
        budget: '',
      }
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
            <!-- Circle -->
            <div
            class="step"
            :class="{ completed: step > index + 1, active: step === index + 1 }"
            >
            {{ index + 1 }}
            </div>

            <!-- Line (except last step) -->
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
    <StepOne 
        v-if="step === 1"
        v-model:form="formData">
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
    <button class="previous-btn">Previous step</button>
    <button class="next-btn">Next step</button>
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
    font-family: var(--font-family);
    font-weight: 700;
    font-size: 34px;
    line-height: 135%;
    text-align: center;
    color: var(--neutral-800);
}
.form-subtitle {
    font-family: var(--font-family);
    font-weight: 400;
    font-size: 18px;
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
.steps {
  display: flex;
  margin-bottom: 20px;
}
.step {
    font-family: var(--font-family);
    font-weight: 400;
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

/* Right half (filled if next step is active or passed) */
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
    width: 596px;
    height: 0px;
   margin: 0 auto;
}

.form-btns {
    display: flex;
    justify-content: space-between;
    margin-top: 25px;
}


.next-btn {
    border-radius: 56px;
    padding: 20px 40px 21px 40px;
    box-shadow: 0 3px 12px 0 rgba(74, 58, 255, 0.18);
    background: var(--primary-color-1);
    font-family: var(--font-family);
    font-weight: 700;
    font-size: 18px;
    line-height: 111%;
    text-align: center;
    color: var(--neutral-100);
    border: none;
    cursor: pointer;
}

.previous-btn {
  border: 1px solid var(--primary-color-1);
border-radius: 66px;
padding: 19px 40px 21px 40px;
font-family: var(--font-family);
font-weight: 400;
font-size: 18px;
line-height: 111%;
text-align: center;
color: var(--primary-color-1);
background: var(--neutral-100);
cursor: pointer;
}
</style>