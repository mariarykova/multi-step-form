<template>
    <div class="footer">
        <div>
            <img
            src="/svg/Logo-full.svg"
            alt="Logo"
            class="logo" />
            <div class="logo-text">Copyright © BRIX Templates | All Rights Reserved</div>
        </div>
        <div>
        <div class="subscribe-text">Subscribe to receive free Webflow cloneables every month.</div>
        <BaseSubscriptionInput/>
    </div>
    </div>
</template>

<script>
import BaseSubscriptionInput from '../Base/BaseSubscriptionInput.vue';
export default {
    name: 'Footer',
    components: {
        BaseSubscriptionInput
    }
}
</script>

<style scoped>
.footer {
     margin: 0 auto;
     padding: 50px 0px;
     display: flex;
     justify-content: space-between;
     align-items: center;
     max-width: 1240px;
    width: 100%;
    margin: 0 auto;
}
.logo-text {
font-size: 18px;
line-height: 167%;
color: var(--neutral-600);
padding-top: 10px;
}
.subscribe-text {
    font-weight: 500;
    font-size: 16px;
    line-height: 112%;
    color: var(--neutral-800);
    padding-bottom: 10px;
    }

    @media (max-width: 1025px) {
        .footer {
            flex-direction: column-reverse;
            gap: 25px;
            margin: 0 auto;
            text-align: center;
        }
    }

    @media (max-width: 500px) {
        .footer {
            padding: 25px 0px;
            gap: 15px
        }
        .subscribe-text {
            font-size: 10px;
        }
        .logo {
            width: 100%;
            max-width: 200px;
        }
        .logo-text {
            font-size: 12px
        }
    }
</style>