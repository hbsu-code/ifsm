<template>
    <div
        class="min-h-screen bg-[#f9fafb] py-16 px-6 lg:px-12 font-sans antialiased text-slate-800"
    >
        <div class="max-w-6xl mx-auto">
            <nav
                class="flex items-center gap-2 text-xs font-bold uppercase tracking-widest text-slate-400 mb-6"
            >
                <span>Postgraduate</span>
                <span class="text-slate-300">/</span>
                <span class="text-[#C8A84B]">M.Sc. Forensic Science</span>
            </nav>

            <div class="flex flex-col lg:flex-row gap-16">
                <aside class="lg:w-64 shrink-0">
                    <div class="sticky top-12 space-y-3">
                        <button
                            v-for="tab in ['MSc I', 'MSc II', 'Course Outcome']"
                            :key="tab"
                            @click="activeTab = tab"
                            :class="[
                                'w-full text-left px-6 py-4 rounded-2xl font-bold text-sm transition-all duration-300',
                                activeTab === tab
                                    ? 'bg-[#1f3a6d] text-white shadow-xl shadow-blue-900/20'
                                    : 'bg-white text-slate-500 border border-slate-100 hover:border-[#C8A84B] hover:text-[#1f3a6d]',
                            ]"
                        >
                            {{ tab }}
                        </button>
                    </div>
                </aside>

                <main class="flex-1">
                    <transition name="page-fade" mode="out-in">
                        <div :key="activeTab">
                            <div class="mb-12">
                                <h2
                                    class="text-4xl font-black text-[#1f3a6d] tracking-tight mb-4"
                                >
                                    {{ activeTab }}
                                </h2>
                                <div
                                    class="w-20 h-1.5 bg-[#C8A84B] rounded-full"
                                ></div>
                            </div>

                            <div
                                v-if="activeTab !== 'Course Outcome'"
                                class="bg-white border border-slate-100 rounded-[2.5rem] p-12 text-center shadow-sm"
                            >
                                <div
                                    class="inline-flex p-4 bg-slate-50 rounded-full mb-6"
                                >
                                    <svg
                                        xmlns="http://www.w3.org/2000/svg"
                                        class="w-8 h-8 text-slate-300"
                                        fill="none"
                                        viewBox="0 0 24 24"
                                        stroke="currentColor"
                                    >
                                        <path
                                            stroke-linecap="round"
                                            stroke-linejoin="round"
                                            stroke-width="2"
                                            d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253"
                                        />
                                    </svg>
                                </div>
                                <p class="text-slate-400 font-medium">
                                    Detailed syllabus for {{ activeTab }} is
                                    currently being updated for the new academic
                                    session.
                                </p>
                            </div>

                            <div v-else class="grid gap-8">
                                <div
                                    v-for="(outcome, index) in outcomes"
                                    :key="index"
                                    class="group bg-white p-10 rounded-[2rem] border border-slate-100 shadow-sm transition-all hover:shadow-md relative overflow-hidden"
                                >
                                    <div
                                        class="absolute -right-4 -top-4 text-8xl font-black text-slate-50 group-hover:text-slate-100 transition-colors pointer-events-none"
                                    >
                                        {{ index + 1 }}
                                    </div>

                                    <div class="relative z-10">
                                        <h4
                                            class="text-[#C8A84B] font-black text-xs uppercase tracking-widest mb-4"
                                        >
                                            Outcome Pillar 0{{ index + 1 }}
                                        </h4>
                                        <p
                                            class="text-[15.5px] leading-[1.9] text-slate-600 max-w-[90%]"
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
import { ref } from "vue";

const activeTab = ref("Course Outcome");

const outcomes = [
    "Demonstrate advanced knowledge and understanding of fundamental concepts and theories, including crime scene science, forensic medicine, and digital and cyber forensics.",
    "Apply specialized scientific methods to evidence analysis using advanced equipment for questioned documents, DNA fingerprinting, forensic toxicology, and IT security.",
    "Effectively communicate technical forensic findings, both orally and in writing, to law enforcement, attorneys, and the general public.",
    "Execute critical thinking and complex problem-solving using analytical reasoning to generate hypotheses and formulate informed forensic conclusions.",
    "Uphold rigorous ethical and professional standards, ensuring privacy, confidentiality, and awareness of the legal implications of forensic evidence.",
];
</script>

<style scoped>
.page-fade-enter-active,
.page-fade-leave-active {
    transition:
        opacity 0.3s ease,
        transform 0.3s ease;
}
.page-fade-enter-from {
    opacity: 0;
    transform: translateY(10px);
}
.page-fade-leave-to {
    opacity: 0;
    transform: translateY(-10px);
}
</style>
