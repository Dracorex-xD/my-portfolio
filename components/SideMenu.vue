<template lang="en">
    <div class="sidebar-menu navbar standard">
        <heading heading="Menu:"/>
        <navigationBlock />
    </div>
</template>
<script>
export default {
    name: 'side-Menu',
}
</script>
<style scoped>
    .sidebar-menu {
        font-size: 1rem;
        background-color: var(--background-color);
        height: 100vh;
        width: 33vw;
        position: fixed;
        z-index: 10;
        top: 0;
        right: 0;
        animation: toLeft 1s forwards linear;
        box-shadow: 0 0 1.5rem var(--secondary-button-color);
        border-radius: 0.3rem;
        margin-top: 0.1rem;
    }

    .heading {
        font-size: 2rem;
    }

    @keyframes toLeft {
        0% {
            transform: translateX(1rem);
        }
        10% {
            transform: translateX(0rem);
        }
    }
</style>