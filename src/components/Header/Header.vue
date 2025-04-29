<script>
import Logo from '../../assets/Logo-full.svg'
import HeaderButton from './HeaderButton.vue'

export default {
    name: 'Header',
    components: {
        HeaderButton
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
        <HeaderButton />
    </header>
       

</template>

<style scoped>
    .header {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    @media (max-width: 500px) {
        .header-logo {
            max-width: 150px;
            width: 100%;
        }
    }

</style>