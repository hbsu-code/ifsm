<template>
    <div class="min-h-screen bg-[#F9F7F2] py-12 px-6 font-sans text-[#1A2B43]">
        <div class="max-w-5xl mx-auto">
            <div class="mb-12">
                <span
                    class="inline-flex items-center px-3 py-1 rounded-full bg-white border border-gray-200 text-xs font-semibold text-[#B1974F] mb-6 shadow-sm"
                >
                    <span class="w-2 h-2 rounded-full bg-[#B1974F] mr-2"></span>
                    Official Documentation
                </span>
                <h1
                    class="text-5xl md:text-6xl font-serif font-bold leading-tight mb-6"
                >
                    College <span class="text-[#B1974F]">Affiliations.</span>
                </h1>
                <p class="text-lg text-gray-600 max-w-2xl leading-relaxed">
                    Maintaining transparency and academic excellence through
                    recognized affiliations and yearly certifications.
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div
                    v-for="(item, index) in affiliationData"
                    :key="index"
                    class="bg-white p-8 rounded-[2rem] shadow-sm hover:shadow-md transition-shadow border border-gray-100 flex flex-col justify-between"
                >
                    <div>
                        <div
                            class="w-12 h-12 bg-[#F9F7F2] rounded-full flex items-center justify-center mb-6"
                        >
                            <svg
                                class="w-6 h-6 text-[#1A2B43]"
                                fill="none"
                                stroke="currentColor"
                                viewBox="0 0 24 24"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="1.5"
                                    d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
                                ></path>
                            </svg>
                        </div>
                        <h2 class="text-3xl font-bold mb-2">{{ item.year }}</h2>
                        <p class="text-gray-500 text-sm mb-8 italic">
                            Certified Academic Session
                        </p>
                    </div>

                    <a
                        :href="item.link"
                        target="_blank"
                        class="inline-flex items-center justify-center px-6 py-3 bg-[#1A2B43] text-white rounded-full hover:bg-[#2A3B53] transition-all font-medium text-sm group"
                    >
                        View Document
                        <svg
                            class="w-4 h-4 ml-2 group-hover:translate-x-1 transition-transform"
                            fill="none"
                            stroke="currentColor"
                            viewBox="0 0 24 24"
                        >
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M17 8l4 4m0 0l-4 4m4-4H3"
                            ></path>
                        </svg>
                    </a>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from "vue";

const affiliationData = ref([
    { year: "2021–22", link: "#" },
    { year: "2020–21", link: "#" },
    { year: "2019–20", link: "#" },
]);
</script>

<style>
/* Applying the Serif look for headers similar to your image */
@import url("https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=Inter:wght@400;500;600&display=swap");

.font-serif {
    font-family: "DM+Serif+Display", serif;
}
.font-sans {
    font-family: "Inter", sans-serif;
}
</style>
