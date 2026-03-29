<template>
    <section class="relative overflow-hidden">
        <!-- Ambient background glow -->
        <div class="absolute inset-0 pointer-events-none">
            <div
                class="absolute top-0 left-1/4 w-96 h-96 bg-gradient-to-br from-blue-500/10 to-transparent rounded-full blur-3xl"
            ></div>
            <div
                class="absolute -bottom-32 right-1/4 w-80 h-80 bg-gradient-to-tl from-cyan-400/10 to-transparent rounded-full blur-3xl"
            ></div>
        </div>

        <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 pt-8">
            <!-- CAROUSEL SECTION -->
            <div class="relative">
                <!-- Main carousel container -->
                <div class="group relative">
                    <div
                        class="relative overflow-hidden rounded-2xl shadow-2xl border border-white/20 backdrop-blur-sm"
                    >
                        <!-- Image with parallax effect -->
                        <div
                            class="relative h-[320px] sm:h-[420px] lg:h-[550px]"
                        >
                            <img
                                :src="images[current]"
                                :key="current"
                                class="w-full h-full object-cover transition-all duration-700 ease-out"
                            />
                            <!-- Gradient overlay on bottom -->
                            <div
                                class="absolute inset-0 bg-gradient-to-t from-black/20 via-transparent to-transparent"
                            ></div>
                        </div>

                        <!-- Image counter badge -->
                        <div
                            class="absolute top-4 right-4 z-10 flex items-center gap-2 bg-black/40 backdrop-blur-md px-4 py-2 rounded-full border border-white/20"
                        >
                            <span class="text-white text-sm font-semibold">{{
                                current + 1
                            }}</span>
                            <span class="text-white/60 text-sm">/</span>
                            <span class="text-white/60 text-sm">{{
                                images.length
                            }}</span>
                        </div>

                        <!-- Navigation buttons with improved styling -->
                        <button
                            @click="prev"
                            @mouseenter="hoveredNav = 'left'"
                            @mouseleave="hoveredNav = null"
                            class="nav-button left-4 sm:left-6 group/nav"
                            aria-label="Previous image"
                        >
                            <svg
                                class="w-6 h-6 transition-transform duration-300"
                                fill="none"
                                stroke="currentColor"
                                viewBox="0 0 24 24"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2.5"
                                    d="M15 19l-7-7 7-7"
                                />
                            </svg>
                        </button>

                        <button
                            @click="next"
                            @mouseenter="hoveredNav = 'right'"
                            @mouseleave="hoveredNav = null"
                            class="nav-button right-4 sm:right-6 group/nav"
                            aria-label="Next image"
                        >
                            <svg
                                class="w-6 h-6 transition-transform duration-300"
                                fill="none"
                                stroke="currentColor"
                                viewBox="0 0 24 24"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2.5"
                                    d="M9 5l7 7-7 7"
                                />
                            </svg>
                        </button>

                        <!-- Progress indicators -->
                        <div
                            class="absolute bottom-4 left-1/2 -translate-x-1/2 z-10 flex gap-2"
                        >
                            <button
                                v-for="(_, index) in images"
                                :key="index"
                                @click="current = index"
                                :class="[
                                    'h-1.5 transition-all duration-300 rounded-full backdrop-blur-sm',
                                    current === index
                                        ? 'w-8 bg-white'
                                        : 'w-1.5 bg-white/40 hover:bg-white/60',
                                ]"
                                :aria-label="`Go to slide ${index + 1}`"
                            />
                        </div>
                    </div>
                </div>
            </div>

            <!-- ICON STRIP - Enhanced Menu -->
            <div class="-mt-20 px-20">
                <div
                    class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-4 sm:gap-3"
                >
                    <div
                        v-for="(item, idx) in menu"
                        :key="item.title"
                        @click="selectMenu(item)"
                        class="menu-item"
                        :style="{ '--item-index': idx }"
                    >
                        <div
                            class="relative h-full flex flex-col items-center justify-center p-6 sm:p-6 rounded-xl cursor-pointer group/item overflow-hidden"
                        >
                            <!-- Background gradient animation -->
                            <div
                                class="absolute inset-0 bg-gradient-to-br from-blue-50 to-cyan-50 group-hover/item:from-blue-100 group-hover/item:to-cyan-100 transition-all duration-300"
                            ></div>

                            <!-- Border glow effect -->
                            <div
                                class="absolute inset-0 rounded-xl border-2 border-transparent group-hover/item:border-blue-300 transition-all duration-300 opacity-0 group-hover/item:opacity-100"
                            ></div>

                            <!-- Content -->
                            <div
                                class="relative z-10 flex flex-col items-center text-center"
                            >
                                <div
                                    class="text-xl sm:text-5xl mb-3 sm:mb-4 transform transition-transform duration-300 group-hover/item:scale-110 group-hover/item:rotate-12"
                                >
                                    {{ item.icon }}
                                </div>
                                <p
                                    class="text-xs sm:text-sm font-semibold text-blue-900 group-hover/item:text-blue-700 transition-colors duration-300 leading-tight"
                                >
                                    {{ item.title }}
                                </p>
                            </div>

                            <!-- Shine effect on hover -->
                            <div
                                class="absolute inset-0 bg-gradient-to-r from-transparent via-white/30 to-transparent translate-x-[-100%] group-hover/item:translate-x-[100%] transition-transform duration-700"
                            ></div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Selected item info (optional) -->
            <transition name="fade">
                <div
                    v-if="selectedItem"
                    class="mt-8 p-4 sm:p-6 rounded-xl bg-gradient-to-r from-blue-50 to-cyan-50 border-2 border-blue-200 text-center animate-in fade-in slide-in-from-bottom-4 duration-300"
                >
                    <p class="text-sm text-blue-800">
                        <span class="font-semibold">{{
                            selectedItem.title
                        }}</span>
                        selected
                    </p>
                </div>
            </transition>
        </div>
    </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const images = ["/gal1.jpg", "/gal2.jpg", "/gal3.jpg", "/gal4.jpg"];
const current = ref(0);
const hoveredNav = ref(null);
const selectedItem = ref(null);
let interval;

const next = () => {
    current.value = (current.value + 1) % images.length;
};

const prev = () => {
    current.value = (current.value - 1 + images.length) % images.length;
};

const selectMenu = (item) => {
    selectedItem.value = item;
    setTimeout(() => {
        selectedItem.value = null;
    }, 2000);
};

onMounted(() => {
    interval = setInterval(next, 5000);
});

onUnmounted(() => clearInterval(interval));

const menu = [
    { title: "Admission", icon: "🏛️" },
    { title: "Academic Calendar", icon: "📅" },
    { title: "Library", icon: "📘" },
    { title: "E-Resource", icon: "▶️" },
    { title: "Exam", icon: "📝" },
    { title: "Research", icon: "📚" },
];
</script>

<style scoped>
/* Navigation buttons */
.nav-button {
    @apply absolute top-1/2 -translate-y-1/2 z-20
         w-12 h-12 sm:w-14 sm:h-14
         flex items-center justify-center
         rounded-full
         bg-black/40 hover:bg-black/60
         text-white
         backdrop-blur-sm
         border border-white/20
         transition-all duration-300
         cursor-pointer
         hover:scale-110
         active:scale-95;
}

.nav-button:hover {
    @apply shadow-lg;
}

.nav-button svg {
    @apply group-hover/nav:translate-x-1 transition-transform duration-300;
}

.nav-button:nth-child(2) svg {
    @apply group-hover/nav:-translate-x-1;
}

/* Menu items with stagger animation */
.menu-item {
    animation: slideUp 0.6s ease-out backwards;
}

.menu-item:nth-child(1) {
    animation-delay: 0.1s;
}
.menu-item:nth-child(2) {
    animation-delay: 0.15s;
}
.menu-item:nth-child(3) {
    animation-delay: 0.2s;
}
.menu-item:nth-child(4) {
    animation-delay: 0.25s;
}
.menu-item:nth-child(5) {
    animation-delay: 0.3s;
}
.menu-item:nth-child(6) {
    animation-delay: 0.35s;
}

@keyframes slideUp {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Fade transition for selected item */
.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}

/* Smooth image transitions */
img {
    @apply transition-opacity duration-300;
}

/* Responsive text sizing */
@media (max-width: 640px) {
    .nav-button {
        @apply w-10 h-10;
    }
}

/* Accessibility - reduce motion */
@media (prefers-reduced-motion: reduce) {
    .menu-item,
    .nav-button,
    img {
        @apply transition-none;
        animation: none !important;
    }
}
</style>
