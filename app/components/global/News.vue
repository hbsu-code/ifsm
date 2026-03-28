<template>
    <section class="news">
        <!-- HEADER -->
        <h2 class="news__title">News, Circulars & Events</h2>
        <div class="news__divider"></div>

        <!-- SCROLL AREA -->
        <div class="news__container" @mouseenter="pause" @mouseleave="start">
            <div
                class="news__list"
                :style="{ transform: `translateY(-${offset}px)` }"
            >
                <div
                    v-for="(item, i) in loopedNews"
                    :key="i"
                    class="news__item"
                >
                    <span class="news__text">{{ item.text }}</span>
                    <span v-if="item.new" class="news__badge">New</span>
                </div>
            </div>
        </div>

        <!-- CTA -->
        <button class="news__btn">View All</button>
    </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const news = [
    { text: "23_Admission_PGD_DCFRL", new: true },
    { text: "23_Admission_PGD_FSRL", new: true },
    { text: "Workshop on Cyber Forensics", new: false },
    { text: "Annual Conference 2026", new: false },
];

// duplicate for infinite scroll illusion
const loopedNews = [...news, ...news];

const offset = ref(0);
let interval = null;

const start = () => {
    interval = setInterval(() => {
        offset.value += 1;

        // reset for seamless loop
        if (offset.value >= news.length * 50) {
            offset.value = 0;
        }
    }, 30);
};

const pause = () => clearInterval(interval);

onMounted(start);
onUnmounted(() => clearInterval(interval));
</script>

<style scoped>
.news {
    background: #314f86;
    padding: 3rem 2rem;
    border-radius: 1.5rem;
    text-align: center;
    color: white;
    max-width: 700px;
    margin: auto;
}

/* TITLE */
.news__title {
    font-family: "DM Serif Display", serif;
    font-size: 2rem;
    font-style: italic;
}

.news__divider {
    height: 3px;
    width: 80%;
    background: #f0b429;
    margin: 1rem auto 2rem;
}

/* SCROLL AREA */
.news__container {
    height: 140px;
    overflow: hidden;
    position: relative;
}

.news__list {
    transition: transform 0.1s linear;
}

/* ITEM */
.news__item {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    height: 50px;
    font-size: 1.2rem;
    color: #f0b429;
}

/* BADGE */
.news__badge {
    background: #d7263d;
    color: white;
    font-size: 0.7rem;
    padding: 3px 8px;
    border-radius: 4px;
}

/* BUTTON */
.news__btn {
    margin-top: 2rem;
    background: #0d2c6c;
    color: white;
    padding: 0.8rem 2rem;
    border-radius: 999px;
    font-weight: 600;
    transition: 0.3s;
}

.news__btn:hover {
    background: #08204d;
}
</style>
