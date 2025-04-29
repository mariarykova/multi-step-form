# Vue 3 + Vite

# ✨ Project Quote Multi-Step Form - https://multi-step-form-six-black.vercel.app/

This is a responsive, accessible, and modern **multi-step form** built with Vue.js.  
It allows users to submit a project quote request through a structured 4-step process.

## 🚀 Features

- **Step 1:** Collect contact details (name, email, phone, company)
- **Step 2:** Choose one or more services (styled checkbox cards)
- **Step 3:** Select a project budget (custom radio buttons)
- **Step 4:** Review and submit

## 🎨 Tech Highlights

- Built with **Vue 3**
- Modular and reusable components (`StepOneInput`, `StepTwoCard`, `StepThreeSelect`)
- Custom-designed UI with CSS for clean styling and accessibility
- State managed through a shared `formData` object
- User input is validated (email, phone) before moving to the next step
- Final form data is saved to **localStorage** on submission

## 🧪 How to Run

```bash
npm install
npm run dev
