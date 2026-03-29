<template>
    <div class="news-dashboard">
        <div class="news-grid">
            <aside class="news-sidebar">
                <div class="sidebar-content">
                    <div class="status-chip">
                        <span class="pulse-dot"></span>
                        Live Updates
                    </div>
                    <h2 class="display-title">
                        University <br /><span>Bulletin</span>
                    </h2>
                    <p class="display-subtitle">
                        Stay informed with the latest academic circulars, event
                        schedules, and department announcements.
                    </p>

                    <div class="sidebar-footer">
                        <button class="primary-btn" @click="viewAll">
                            View Archive
                            <svg viewBox="0 0 24 24" width="18" height="18">
                                <path
                                    fill="currentColor"
                                    d="M12,4L10.59,5.41L16.17,11H4V13H16.17L10.59,18.59L12,20L20,12L12,4Z"
                                />
                            </svg>
                        </button>
                    </div>
                </div>
            </aside>

            <main class="news-main">
                <div
                    class="ticker-viewport"
                    @mouseenter="isPaused = true"
                    @mouseleave="isPaused = false"
                    :class="{ 'is-paused': isPaused }"
                >
                    <div class="vignette top"></div>
                    <div class="vignette bottom"></div>

                    <div class="ticker-track">
                        <div
                            v-for="(item, i) in [...news, ...news]"
                            :key="i"
                            class="ticker-card"
                            @click="selectItem(item)"
                        >
                            <div
                                class="card-accent"
                                :class="{ 'is-new': item.new }"
                            ></div>
                            <div class="card-info">
                                <span class="card-label" v-if="item.new"
                                    >Announcement</span
                                >
                                <p class="card-text">{{ item.text }}</p>
                            </div>
                            <div class="card-meta">
                                <span v-if="item.new" class="new-badge"
                                    >New</span
                                >
                                <div class="arrow-icon">→</div>
                            </div>
                        </div>
                    </div>
                </div>
            </main>
        </div>
    </div>
</template>

<script setup>
import { ref } from "vue";

const news = [
    { text: "23_Admission_PGD_DCFRL", new: true },
    { text: "23_Admission_PGD_FSRL", new: true },
    { text: "Workshop on Cyber Forensics 2026", new: false },
    { text: "Annual Convocation Ceremony Updates", new: false },
    { text: "Revised Exam Schedule: Semester IV", new: false },
];

const isPaused = ref(false);
const selectItem = (item) => console.log("Opening:", item.text);
const viewAll = () => console.log("Navigating to full list...");
</script>

<style scoped>
/* Container Layout */
.news-dashboard {
    --bg-dark: #0f172a;
    --accent: #f0b429;
    --text-muted: #94a3b8;
    --glass: rgba(255, 255, 255, 0.03);

    max-width: 1000px;
    margin: 3rem auto;
    background: var(--bg-dark);
    border-radius: 32px;
    overflow: hidden;
    border: 1px solid rgba(255, 255, 255, 0.1);
    box-shadow: 0 50px 100px -20px rgba(0, 0, 0, 0.5);
}

.news-grid {
    display: grid;
    grid-template-columns: 1fr 1.5fr;
    min-height: 450px;
}

/* Left Column Styling */
.news-sidebar {
    padding: 3rem;
    background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
    display: flex;
    flex-direction: column;
    justify-content: center;
    border-right: 1px solid rgba(255, 255, 255, 0.05);
}

.status-chip {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(240, 180, 41, 0.1);
    color: var(--accent);
    padding: 6px 12px;
    border-radius: 99px;
    font-size: 0.75rem;
    font-weight: 700;
    text-transform: uppercase;
    margin-bottom: 1.5rem;
    width: fit-content;
}

.pulse-dot {
    width: 8px;
    height: 8px;
    background: var(--accent);
    border-radius: 50%;
    animation: pulse-glow 2s infinite;
}

.display-title {
    font-size: 2.5rem;
    line-height: 1.1;
    font-weight: 800;
    color: white;
    margin-bottom: 1rem;
}

.display-title span {
    color: var(--accent);
}

.display-subtitle {
    color: var(--text-muted);
    font-size: 1rem;
    line-height: 1.6;
}

.primary-btn {
    margin-top: 2rem;
    background: var(--accent);
    color: #000;
    border: none;
    padding: 12px 24px;
    border-radius: 12px;
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: 10px;
    cursor: pointer;
    transition: transform 0.2s;
}

.primary-btn:hover {
    transform: translateY(-2px);
    background: #ffc845;
}

/* Right Column (Ticker) Styling */
.news-main {
    background: rgba(0, 0, 0, 0.2);
    padding: 1rem;
    position: relative;
}

.ticker-viewport {
    height: 400px;
    overflow: hidden;
    position: relative;
}

.vignette {
    position: absolute;
    left: 0;
    right: 0;
    height: 60px;
    z-index: 2;
    pointer-events: none;
}
.vignette.top {
    top: 0;
    background: linear-gradient(to bottom, var(--bg-dark), transparent);
}
.vignette.bottom {
    bottom: 0;
    background: linear-gradient(to top, var(--bg-dark), transparent);
}

.ticker-track {
    display: flex;
    flex-direction: column;
    gap: 12px;
    animation: scroll-v 25s linear infinite;
}

.is-paused .ticker-track {
    animation-play-state: paused;
}

@keyframes scroll-v {
    0% {
        transform: translateY(0);
    }
    100% {
        transform: translateY(-50%);
    }
}

.ticker-card {
    background: var(--glass);
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 16px;
    padding: 16px;
    display: flex;
    align-items: center;
    gap: 16px;
    cursor: pointer;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.ticker-card:hover {
    background: rgba(255, 255, 255, 0.08);
    border-color: var(--accent);
    transform: translateX(8px);
}

.card-accent {
    width: 4px;
    height: 40px;
    border-radius: 2px;
    background: #334155;
}
.card-accent.is-new {
    background: var(--accent);
    box-shadow: 0 0 15px var(--accent);
}

.card-info {
    flex: 1;
}
.card-label {
    font-size: 0.65rem;
    text-transform: uppercase;
    color: var(--accent);
    font-weight: 800;
    display: block;
    margin-bottom: 4px;
}
.card-text {
    color: #f1f5f9;
    font-size: 0.9rem;
    font-weight: 500;
    margin: 0;
}

.new-badge {
    background: #ef4444;
    color: white;
    padding: 2px 8px;
    border-radius: 4px;
    font-size: 0.65rem;
    font-weight: 900;
}

.arrow-icon {
    color: var(--text-muted);
    opacity: 0;
    transition: 0.3s;
}
.ticker-card:hover .arrow-icon {
    opacity: 1;
    transform: translateX(5px);
    color: var(--accent);
}

/* Keyframes */
@keyframes pulse-glow {
    0% {
        opacity: 1;
        transform: scale(1);
    }
    50% {
        opacity: 0.4;
        transform: scale(1.2);
    }
    100% {
        opacity: 1;
        transform: scale(1);
    }
}

/* Responsive */
@media (max-width: 850px) {
    .news-grid {
        grid-template-columns: 1fr;
    }
    .news-sidebar {
        border-right: none;
        border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        padding: 2rem;
    }
    .display-title {
        font-size: 1.8rem;
    }
}
</style>
