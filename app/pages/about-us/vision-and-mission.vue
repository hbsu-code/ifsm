<template>
    <div class="vm-page">
        <!-- Background grid -->
        <div class="bg-grid" aria-hidden="true"></div>

        <!-- Hero band -->
        <section class="hero">
            <div class="hero-inner">
                <p class="eyebrow">Institute of Forensic Science</p>
                <h1 class="page-title">
                    Vision <span class="amp">&amp;</span> Mission
                </h1>

                <!-- Motto card -->
                <div class="motto-card">
                    <span class="motto-label">Motto</span>
                    <blockquote class="motto-text">
                        "Scientific Knowledge for Justice"
                    </blockquote>
                </div>
            </div>

            <!-- Decorative scale icon -->
            <div class="hero-deco" aria-hidden="true">
                <svg
                    viewBox="0 0 120 120"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                >
                    <circle
                        cx="60"
                        cy="60"
                        r="58"
                        stroke="currentColor"
                        stroke-width="1.5"
                        stroke-dasharray="6 4"
                    />
                    <line
                        x1="60"
                        y1="20"
                        x2="60"
                        y2="100"
                        stroke="currentColor"
                        stroke-width="1.5"
                    />
                    <line
                        x1="20"
                        y1="40"
                        x2="100"
                        y2="40"
                        stroke="currentColor"
                        stroke-width="1.5"
                    />
                    <circle
                        cx="35"
                        cy="65"
                        r="12"
                        stroke="currentColor"
                        stroke-width="1.5"
                    />
                    <circle
                        cx="85"
                        cy="65"
                        r="12"
                        stroke="currentColor"
                        stroke-width="1.5"
                    />
                    <line
                        x1="35"
                        y1="40"
                        x2="35"
                        y2="53"
                        stroke="currentColor"
                        stroke-width="1.5"
                    />
                    <line
                        x1="85"
                        y1="40"
                        x2="85"
                        y2="53"
                        stroke="currentColor"
                        stroke-width="1.5"
                    />
                </svg>
            </div>
        </section>

        <!-- Content -->
        <div class="content-wrapper">
            <!-- Vision -->
            <section class="vm-section vision-section">
                <div class="section-header">
                    <div class="section-icon vision-icon">
                        <svg
                            viewBox="0 0 24 24"
                            fill="none"
                            stroke="currentColor"
                            stroke-width="1.8"
                            xmlns="http://www.w3.org/2000/svg"
                        >
                            <path
                                d="M1 12S5 4 12 4s11 8 11 8-4 8-11 8S1 12 1 12Z"
                            />
                            <circle cx="12" cy="12" r="3" />
                        </svg>
                    </div>
                    <div>
                        <p class="section-tag">Our</p>
                        <h2 class="section-title">Vision</h2>
                    </div>
                    <div class="section-number">01</div>
                </div>

                <ul class="vm-list">
                    <li
                        v-for="(item, i) in vision"
                        :key="i"
                        class="vm-item"
                        :style="`--i: ${i}`"
                    >
                        <span class="item-bullet">
                            <svg
                                viewBox="0 0 16 16"
                                fill="none"
                                xmlns="http://www.w3.org/2000/svg"
                            >
                                <path
                                    d="M3 8h10M9 4l4 4-4 4"
                                    stroke="currentColor"
                                    stroke-width="1.6"
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                />
                            </svg>
                        </span>
                        <p>{{ item }}</p>
                    </li>
                </ul>
            </section>

            <!-- Divider -->
            <div class="divider" aria-hidden="true">
                <span class="divider-line"></span>
                <span class="divider-diamond"></span>
                <span class="divider-line"></span>
            </div>

            <!-- Mission -->
            <section class="vm-section mission-section">
                <div class="section-header">
                    <div class="section-icon mission-icon">
                        <svg
                            viewBox="0 0 24 24"
                            fill="none"
                            stroke="currentColor"
                            stroke-width="1.8"
                            xmlns="http://www.w3.org/2000/svg"
                        >
                            <circle cx="12" cy="12" r="10" />
                            <circle cx="12" cy="12" r="4" />
                            <line x1="12" y1="2" x2="12" y2="8" />
                            <line x1="12" y1="16" x2="12" y2="22" />
                            <line x1="2" y1="12" x2="8" y2="12" />
                            <line x1="16" y1="12" x2="22" y2="12" />
                        </svg>
                    </div>
                    <div>
                        <p class="section-tag">Our</p>
                        <h2 class="section-title">Mission</h2>
                    </div>
                    <div class="section-number">02</div>
                </div>

                <ul class="vm-list">
                    <li
                        v-for="(item, i) in mission"
                        :key="i"
                        class="vm-item"
                        :style="`--i: ${i}`"
                    >
                        <span class="item-bullet">
                            <svg
                                viewBox="0 0 16 16"
                                fill="none"
                                xmlns="http://www.w3.org/2000/svg"
                            >
                                <path
                                    d="M3 8h10M9 4l4 4-4 4"
                                    stroke="currentColor"
                                    stroke-width="1.6"
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                />
                            </svg>
                        </span>
                        <p>{{ item }}</p>
                    </li>
                </ul>
            </section>
        </div>
    </div>
</template>

<script setup>
const vision = [
    "Impart quality education in the field of forensic science and allied domains; promote awareness among the stakeholders.",
    "Create skillful resources and fulfil the acute shortage of forensic experts in the nation.",
    "Empowerment of students through imparting of knowledge, leadership qualities, inclusivity and social responsibility.",
    "Establish scientific temperament, cognitive skills to encourage creation and innovation in the field of forensic science.",
];

const mission = [
    "To provide quality education through innovative pedagogical practices for the enhancement of investigative and forensic skills with ethics and integrity.",
    "To harness potentials amongst the students so that they can become excellent forensic experts to aid the legal system and overcome the dynamic challenges.",
    "To create and innovate scientific temperament to conduct research in the field of forensic science and allied sciences.",
    "To support and execute outcome based education through collaboration and integration with stakeholders.",
];
</script>

<style scoped>
/* ─── Tokens ─── */
.vm-page {
    --navy: #1b2a4a;
    --gold: #c8a84b;
    --gold-lt: #e8c96a;
    --cream: #fafaf7;
    --border: rgba(27, 42, 74, 0.1);
    --text: #1b2a4a;
    --muted: rgba(27, 42, 74, 0.55);

    font-family: "Georgia", "Times New Roman", serif;
    background: var(--cream);
    color: var(--text);
    min-height: 100vh;
    position: relative;
    overflow-x: hidden;
}

/* ─── Background grid ─── */
.bg-grid {
    position: fixed;
    inset: 0;
    background-image:
        linear-gradient(var(--border) 1px, transparent 1px),
        linear-gradient(90deg, var(--border) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
}

/* ─── Hero ─── */
.hero {
    position: relative;
    z-index: 1;
    background: var(--navy);
    color: white;
    padding: 72px 48px 80px;
    overflow: hidden;
}

.hero::before {
    content: "";
    position: absolute;
    inset: 0;
    background: radial-gradient(
        ellipse 70% 80% at 110% 50%,
        rgba(200, 168, 75, 0.18) 0%,
        transparent 70%
    );
}

.hero-inner {
    position: relative;
    z-index: 1;
    max-width: 800px;
}

.eyebrow {
    font-family: "Courier New", monospace;
    font-size: 0.72rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 12px;
}

.page-title {
    font-size: clamp(2.8rem, 6vw, 5rem);
    font-weight: 400;
    line-height: 1.05;
    letter-spacing: -0.02em;
    color: white;
    margin: 0 0 40px;
}

.amp {
    color: var(--gold);
    font-style: italic;
}

/* Motto */
.motto-card {
    display: inline-flex;
    flex-direction: column;
    gap: 8px;
    border-left: 3px solid var(--gold);
    padding: 16px 24px;
    background: rgba(255, 255, 255, 0.05);
    border-radius: 0 8px 8px 0;
    backdrop-filter: blur(4px);
}

.motto-label {
    font-family: "Courier New", monospace;
    font-size: 0.65rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
}

.motto-text {
    font-size: 1.25rem;
    font-style: italic;
    color: rgba(255, 255, 255, 0.9);
    margin: 0;
    line-height: 1.4;
}

/* Deco */
.hero-deco {
    position: absolute;
    right: 5%;
    top: 50%;
    transform: translateY(-50%);
    width: clamp(100px, 16vw, 180px);
    color: rgba(200, 168, 75, 0.2);
    animation: spin-slow 40s linear infinite;
}

@keyframes spin-slow {
    to {
        transform: translateY(-50%) rotate(360deg);
    }
}

/* ─── Content wrapper ─── */
.content-wrapper {
    position: relative;
    z-index: 1;
    max-width: 900px;
    margin: 0 auto;
    padding: 64px 32px 96px;
}

/* ─── Section ─── */
.vm-section {
    margin-bottom: 16px;
}

.section-header {
    display: flex;
    align-items: center;
    gap: 20px;
    margin-bottom: 36px;
}

.section-icon {
    width: 52px;
    height: 52px;
    border-radius: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
}

.section-icon svg {
    width: 24px;
    height: 24px;
}

.vision-icon {
    background: rgba(27, 42, 74, 0.08);
    color: var(--navy);
}

.mission-icon {
    background: rgba(200, 168, 75, 0.12);
    color: #a07c28;
}

.section-tag {
    font-family: "Courier New", monospace;
    font-size: 0.65rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
    margin: 0 0 2px;
}

.section-title {
    font-size: 2.2rem;
    font-weight: 400;
    letter-spacing: -0.02em;
    margin: 0;
    color: var(--navy);
}

.section-number {
    margin-left: auto;
    font-family: "Courier New", monospace;
    font-size: 3.5rem;
    font-weight: 700;
    color: var(--border);
    line-height: 1;
    user-select: none;
}

/* ─── List items ─── */
.vm-list {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.vm-item {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    background: white;
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 24px;
    transition:
        box-shadow 0.2s,
        transform 0.2s,
        border-color 0.2s;
    animation: fade-up 0.5s ease both;
    animation-delay: calc(var(--i) * 80ms);
}

.vm-item:hover {
    box-shadow: 0 6px 24px rgba(27, 42, 74, 0.08);
    transform: translateY(-2px);
    border-color: rgba(200, 168, 75, 0.4);
}

@keyframes fade-up {
    from {
        opacity: 0;
        transform: translateY(16px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.item-bullet {
    flex-shrink: 0;
    width: 32px;
    height: 32px;
    border-radius: 8px;
    background: var(--cream);
    border: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--gold);
    margin-top: 2px;
}

.item-bullet svg {
    width: 16px;
    height: 16px;
}

.vm-item p {
    margin: 0;
    font-size: 1rem;
    line-height: 1.75;
    color: var(--text);
}

/* ─── Divider ─── */
.divider {
    display: flex;
    align-items: center;
    gap: 16px;
    margin: 52px 0;
}

.divider-line {
    flex: 1;
    height: 1px;
    background: var(--border);
}

.divider-diamond {
    width: 10px;
    height: 10px;
    border: 1.5px solid var(--gold);
    transform: rotate(45deg);
    flex-shrink: 0;
}

/* ─── Responsive ─── */
@media (max-width: 640px) {
    .hero {
        padding: 48px 24px 56px;
    }
    .content-wrapper {
        padding: 40px 20px 72px;
    }
    .section-number {
        display: none;
    }
    .hero-deco {
        display: none;
    }
    .vm-item {
        padding: 16px 18px;
    }
}
</style>
