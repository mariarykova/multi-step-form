<script>
import Logo from '../../assets/Logo-full.svg'
import BaseButton from '../Base/BaseButton.vue'

export default {
    name: 'Header',
    components: {
        BaseButton
    },
    data() {
        return {
            Logo
        }
    }
}
</script>
<template>
    <header class="container header">
        <img :src="Logo" alt="Logo" class="header-logo" />
        <BaseButton variant="primary">Clone Now</BaseButton>
    </header>
    

</template>

<style scoped>
    .header {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    @media (max-width: 701px) {
        .header-logo {
            max-width: 350px;
        }
        .header-button {
            padding: 15px 30px 15px 30px;
        }
    }

    @media (max-width: 500px) {
        .header-logo {
            max-width: 150px;
            width: 100%;
        }
    }

</style>