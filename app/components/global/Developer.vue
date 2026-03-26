<template>
    <footer class="footer">
        <div class="footer__left">
            <span class="footer__label">Built by</span>
            <span class="footer__name">Shubham Chavan</span>
        </div>
        <span class="footer__year">© {{ year }}</span>
    </footer>
</template>

<script setup>
import { computed } from "vue";
const year = computed(() => new Date().getFullYear());
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400&display=swap");

.footer {
    width: 100%;
    padding: 0.5rem 2rem;
    border-top: 1px solid rgba(0, 0, 0, 0.08);
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: transparent;
}

.footer__left {
    display: flex;
    align-items: baseline;
    gap: 0.5rem;
}

.footer__label {
    font-family: "DM Sans", sans-serif;
    font-size: 11px;
    font-weight: 400;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: #9e9c94;
}

.footer__name {
    font-family: "DM Serif Display", serif;
    font-size: 15px;
    font-style: italic;
    color: #1a1a18;
}

.footer__year {
    font-family: "DM Sans", sans-serif;
    font-size: 11px;
    font-weight: 300;
    letter-spacing: 0.08em;
    color: #9e9c94;
}
</style>
