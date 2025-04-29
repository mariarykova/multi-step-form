<template>
    <div :class="['card', theme]">
      <div class="card-content">
        <img v-if="logo" :src="logo" alt="Logo" class="card-logo" />
        <h3 class="card-title">{{ title }}</h3>
        <p class="card-text">{{ text }}</p>
        <button
            :class="['card-button', theme]"
            @click="$emit('button-click')"
        >
            {{ buttonText }}
        </button>
      </div>
     
      <img v-if="image" :src="image" alt="Card Image" class="card-main-image" />
    </div>
  </template>
  
  <script>
  export default {
    props: {
      logo: {
        type: String,
        default: null,
        required: false
      },
      title: {
        type: String,
        required: true,
        default: "Default Title"
      },
      text: {
        type: String,
        required: true,
        default: "Default text goes here. This is a placeholder for the card content."},
      buttonText: {
        type: String,
        default: "Click me",
        required: false
      },
      image: {
        type: String,
        default: null,
        required: false
      },
      theme: {
        type: String,
        default: 'light',
        required: false
      }
    },
    emits: ['button-click']
  }
  </script>
  
  <style scoped>
  .card {
    border-radius: 16px;
    padding: 30px 0px;
    max-width: 606px;
    display: flex;
    flex-direction: column;
    align-items: start;
  }
  .card-content{
    padding: 0px 50px;
  }
  .card-logo {
    width: auto;
    height: auto;
    object-fit: contain;
    margin-bottom: 1rem;
  }
  .card-main-image {
    width: 100%;
    object-fit: cover;
    border-radius: 12px;
    margin-top: 2rem;
  }
  .card-title {
    font-weight: 700;
    font-size: 24px;
    line-height: 146%;
    margin-bottom: 0.5rem;
  }
  .card-text {
    line-height: 167%;
    margin-bottom: 2rem;
  }
  .card-button {
    border-radius: 56px;
    padding: 20px 40px 21px 40px;
    font-weight: 700;
    text-decoration: underline;
    text-decoration-skip-ink: none;
    text-align: center;
    cursor: pointer;
    border: none;
    transition: background-color 0.3s, box-shadow 0.3s;
  }
  
  /* THEMES */

  /* --- Light Theme --- */
  .card.light {
    background: linear-gradient(90deg, #4a3aff 0%, #6d3aff 100%);
  }
  .card.light .card-title {
    color: var(--neutral-100);
  }
  .card.light .card-text {
    color: var(--neutral-100);
    opacity: 0.8;
  }
  .card-button.light {
    box-shadow: 0 3px 12px 0 rgba(20, 20, 43, 0.1);
    background: var(--neutral-100);
    color: var(--primary-color-1);
  }
  
  /* --- Dark Theme --- */
  .card.dark {
    background: var(--neutral-100);
    border: 1px solid var(--neutral-300);
  }
  .card.dark .card-title {
    color: var(--neutral-800);
  }
  .card.dark .card-text {
    color: var(--neutral-600);
  }
  .card-button.dark {
    color: var(--neutral-100);
    background: #ff2d46;
    box-shadow: 0 3px 12px 0 rgba(255, 45, 70, 0.18);
  }

  @media (max-width: 500px) {
    .card {
      padding: 30px 10px;
      max-width: 300px;
    }
    .card-content {
      padding: 0px 0px;
    }
    .card-logo {
      max-width: 150px;
      width: 100%;
    }
    .card-title {
      font-size: 16px;
    }
    .card-text {
      font-size: 12px;
    }
    .card-button {
      padding: 10px 15px;
      font-size: 12px;
    }
  }
  </style>
  