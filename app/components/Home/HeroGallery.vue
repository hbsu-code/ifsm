<template>
    <section class="relative pb-24">
        <!-- CAROUSEL -->
        <div class="relative max-w-7xl mx-auto pt-6">
            <div class="overflow-hidden rounded-lg border-[6px]">
                <img
                    :src="images[current]"
                    class="w-full h-[400px] md:h-[500px] object-cover transition duration-500"
                />

                <!-- LEFT -->
                <button @click="prev" class="nav left">‹</button>

                <!-- RIGHT -->
                <button @click="next" class="nav right">›</button>
            </div>
        </div>

        <!-- ICON STRIP -->
        <div
            class="absolute left-1/2 -bottom-16 -translate-x-1/2 w-full max-w-6xl px-4"
        >
            <div
                class="bg-[#e9e9e9] rounded-lg shadow-md grid grid-cols-2 md:grid-cols-6 divide-x"
            >
                <div
                    v-for="item in menu"
                    :key="item.title"
                    class="flex flex-col items-center justify-center py-6 hover:bg-gray-100 transition cursor-pointer"
                >
                    <div class="text-3xl text-[#0f3d5c] mb-2">
                        {{ item.icon }}
                    </div>
                    <p class="text-sm font-medium text-gray-700">
                        {{ item.title }}
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const images = ["/gal1.jpg", "/gal2.jpg", "/gal3.jpg", "/gal4.jpg"];

const current = ref(0);
let interval;

const next = () => {
    current.value = (current.value + 1) % images.length;
};

const prev = () => {
    current.value = (current.value - 1 + images.length) % images.length;
};

onMounted(() => {
    interval = setInterval(next, 4000);
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
.nav {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(0, 0, 0, 0.4);
    color: white;
    padding: 8px 12px;
    border-radius: 50%;
    cursor: pointer;
}

.left {
    left: 10px;
}

.right {
    right: 10px;
}
</style>
