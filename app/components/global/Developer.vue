<template>
    <footer class="footer">
        <p class="footer__text">
            Built by
            <a href="https://github.com/piyush-linux" class="footer__name"
                >Shubham Chavan</a
            >
            <span class="footer__dot">•</span>
            © {{ year }}
        </p>
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
    padding: 0.5rem 0;
    display: flex;
    justify-content: center;
    align-items: center;
    border-top: 1px solid rgba(0, 0, 0, 0.06);
    background: transparent;
}

.footer__text {
    font-family: "DM Sans", sans-serif;
    font-size: 12px;
    color: #9e9c94;
    letter-spacing: 0.08em;
}

.footer__name {
    font-family: "DM Serif Display", serif;
    font-style: italic;
    color: #1a1a18;
    margin: 0 4px;
}

.footer__dot {
    margin: 0 6px;
    opacity: 0.5;
}
</style>
