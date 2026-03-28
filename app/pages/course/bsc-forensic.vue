<template>
    <div
        class="min-h-screen bg-[#fcfdfd] py-16 px-4 sm:px-8 lg:px-12 font-sans antialiased text-slate-800"
    >
        <div class="max-w-6xl mx-auto">
            <nav
                class="flex items-center gap-2 text-sm font-medium text-slate-400 mb-8"
            >
                <span>Programmes</span>
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="w-4 h-4"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                >
                    <path d="M9 5l7 7-7 7" />
                </svg>
                <span class="text-[#1f3a6d]">B.Sc. Forensic Science</span>
            </nav>

            <div class="flex flex-col lg:flex-row gap-12">
                <aside class="lg:w-1/4">
                    <div
                        class="sticky top-10 space-y-2 bg-white p-4 rounded-3xl border border-slate-100 shadow-sm"
                    >
                        <button
                            v-for="tab in tabs"
                            :key="tab.id"
                            @click="activeTab = tab.id"
                            :class="[
                                'w-full text-left px-6 py-4 rounded-2xl transition-all duration-300 font-bold text-sm flex items-center justify-between group',
                                activeTab === tab.id
                                    ? 'bg-[#1f3a6d] text-white shadow-lg shadow-blue-900/20'
                                    : 'text-slate-500 hover:bg-slate-50 hover:text-[#1f3a6d]',
                            ]"
                        >
                            {{ tab.label }}
                            <svg
                                v-if="activeTab === tab.id"
                                xmlns="http://www.w3.org/2000/svg"
                                class="w-4 h-4"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M9 5l7 7-7 7"
                                />
                            </svg>
                        </button>
                    </div>
                </aside>

                <main class="lg:w-3/4">
                    <transition name="fade" mode="out-in">
                        <div :key="activeTab">
                            <div class="mb-10">
                                <h2
                                    class="text-3xl font-black text-[#1f3a6d] mb-2"
                                >
                                    {{ currentTabLabel }}
                                </h2>
                                <div
                                    class="w-16 h-1 bg-[#C8A84B] rounded-full"
                                ></div>
                            </div>

                            <div
                                v-if="activeTab !== 'outcomes'"
                                class="bg-white p-10 rounded-[2.5rem] border border-slate-100 min-h-[400px] flex items-center justify-center text-slate-400 italic"
                            >
                                Syllabus and Course Structure for
                                {{ currentTabLabel }} is being updated...
                            </div>

                            <div v-else class="space-y-6">
                                <div
                                    v-for="(outcome, index) in outcomes"
                                    :key="index"
                                    class="relative bg-white p-8 md:p-10 rounded-[2rem] border border-slate-100 shadow-sm hover:shadow-md transition-shadow group overflow-hidden"
                                >
                                    <div
                                        class="absolute top-0 left-0 w-1.5 h-full bg-[#C8A84B] opacity-0 group-hover:opacity-100 transition-opacity"
                                    ></div>

                                    <div class="flex gap-8 items-start">
                                        <span
                                            class="text-4xl font-black text-slate-100 shrink-0 group-hover:text-[#C8A84B]/10 transition-colors"
                                        >
                                            0{{ index + 1 }}
                                        </span>
                                        <p
                                            class="text-[16px] leading-[1.8] text-slate-600 font-medium"
                                        >
                                            {{ outcome }}
                                        </p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </transition>
                </main>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, computed } from "vue";

const activeTab = ref("outcomes");

const tabs = [
    { id: "fybsc", label: "First Year (FYBSc)" },
    { id: "sybsc", label: "Second Year (SYBSc)" },
    { id: "tybsc", label: "Third Year (TYBSc)" },
    { id: "outcomes", label: "Course Outcome" },
];

const currentTabLabel = computed(() => {
    return tabs.find((t) => t.id === activeTab.value)?.label;
});

const outcomes = [
    "Demonstrate an understanding of the fundamental concepts and theories of forensic science, chemical science, physical science, biological science, psychology, computer science, and law.",
    "Apply scientific principles and methods to the analysis and interpretation of forensic evidence, including crime scene investigation, laboratory analysis, and data interpretation.",
    "Communicate effectively, both orally and in writing, about complex forensic science concepts, techniques, and findings to a variety of audiences.",
    "Think critically and solve problems using analytical and logical reasoning skills to identify evidence, generate hypotheses, and make informed conclusions.",
    "Demonstrate ethical and professional conduct, including respect for privacy, adherence to scientific standards, and awareness of social and legal implications.",
];
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
    transition:
        opacity 0.2s ease,
        transform 0.2s ease;
}
.fade-enter-from,
.fade-leave-to {
    opacity: 0;
    transform: translateX(10px);
}
</style>
