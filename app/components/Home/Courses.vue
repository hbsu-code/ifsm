<template>
    <section class="py-24 bg-[#F5F4F0] px-8">
        <div class="max-w-7xl mx-auto">
            <!-- Header -->
            <div
                class="flex flex-col md:flex-row md:items-end justify-between gap-6 mb-12"
            >
                <div>
                    <div
                        class="inline-flex items-center gap-2 bg-white rounded-full px-4 py-1.5 mb-4 shadow-sm border border-gray-100"
                    >
                        <span
                            class="text-xs font-bold text-[#1B2A4A] tracking-wide uppercase"
                            >Academic Programmes</span
                        >
                    </div>
                    <h2
                        class="text-4xl font-bold text-[#1B2A4A]"
                        style="font-family: Georgia, serif"
                    >
                        Courses Offered
                    </h2>
                </div>
                <a
                    href="/academics"
                    class="inline-flex items-center gap-2 text-sm font-semibold text-[#1B2A4A] border-b-2 border-[#C9A84C] pb-0.5 hover:text-[#C9A84C] transition-colors self-start md:self-auto"
                >
                    View All →
                </a>
            </div>

            <!-- Tab pills -->
            <div class="flex gap-2 mb-8 flex-wrap">
                <button
                    v-for="tab in tabs"
                    :key="tab"
                    @click="activeTab = tab"
                    class="px-5 py-2 rounded-full text-sm font-semibold transition-all duration-200 border"
                    :class="
                        activeTab === tab
                            ? 'bg-[#1B2A4A] text-white border-[#1B2A4A] shadow-md shadow-[#1B2A4A]/15'
                            : 'bg-white text-gray-500 border-gray-200 hover:border-[#1B2A4A] hover:text-[#1B2A4A]'
                    "
                >
                    {{ tab }}
                </button>
            </div>

            <!-- Cards -->
            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-5">
                <div
                    v-for="course in filteredCourses"
                    :key="course.name"
                    class="bg-white rounded-3xl p-6 border border-gray-100 hover:shadow-lg hover:-translate-y-1 transition-all duration-300 group flex flex-col"
                >
                    <!-- Top row -->
                    <div class="flex items-start justify-between mb-5">
                        <div
                            class="w-12 h-12 rounded-2xl bg-[#1B2A4A]/5 flex items-center justify-center group-hover:bg-[#1B2A4A] transition-colors duration-300"
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                class="h-6 w-6 text-[#1B2A4A] group-hover:text-white transition-colors duration-300"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="1.5"
                                    :d="course.icon"
                                />
                            </svg>
                        </div>
                        <span
                            class="text-xs font-bold px-3 py-1 rounded-full"
                            :class="{
                                'bg-emerald-50 text-emerald-600':
                                    course.level === 'UG',
                                'bg-blue-50 text-blue-600':
                                    course.level === 'PG',
                                'bg-amber-50 text-amber-600':
                                    course.level === 'Certificate',
                                'bg-purple-50 text-purple-600':
                                    course.level === 'PhD',
                            }"
                        >
                            {{ course.level }}
                        </span>
                    </div>

                    <h3
                        class="font-bold text-[#1B2A4A] text-base mb-2 leading-snug"
                    >
                        {{ course.name }}
                    </h3>
                    <p
                        class="text-gray-400 text-sm leading-relaxed flex-1 mb-5"
                    >
                        {{ course.desc }}
                    </p>

                    <div
                        class="flex items-center justify-between pt-4 border-t border-gray-100"
                    >
                        <div
                            class="flex items-center gap-1.5 text-xs text-gray-400"
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                class="h-3.5 w-3.5"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"
                                />
                            </svg>
                            {{ course.duration }}
                        </div>
                        <a
                            href="/academics"
                            class="inline-flex items-center gap-1 text-xs font-bold text-[#C9A84C] hover:text-[#9A7030] transition-colors"
                        >
                            Details
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                class="h-3.5 w-3.5"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M17 8l4 4m0 0l-4 4m4-4H3"
                                />
                            </svg>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref, computed } from "vue";

const tabs = ["All", "UG", "PG", "PhD", "Certificate"];
const activeTab = ref("All");

const courses = [
    {
        name: "B.Sc. Forensic Science",
        level: "UG",
        duration: "3 Years",
        desc: "Foundational programme covering core forensic disciplines including criminalistics, toxicology, and serology.",
        icon: "M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2",
    },
    {
        name: "M.Sc. Forensic Science",
        level: "PG",
        duration: "2 Years",
        desc: "Advanced study with specialisations in DNA analysis, digital forensics, questioned documents, and more.",
        icon: "M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253",
    },
    {
        name: "Ph.D. in Forensic Science",
        level: "PhD",
        duration: "3–5 Years",
        desc: "Doctoral research programme pushing the frontiers of forensic science knowledge and methodology.",
        icon: "M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z",
    },
    {
        name: "M.Sc. Digital Forensics",
        level: "PG",
        duration: "2 Years",
        desc: "Specialised programme in cyber crime investigation, electronic evidence, and digital crime analysis.",
        icon: "M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z",
    },
    {
        name: "Certificate in Crime Scene Investigation",
        level: "Certificate",
        duration: "6 Months",
        desc: "Practical training for law enforcement in crime scene management and evidence collection.",
        icon: "M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z",
    },
    {
        name: "Certificate in Forensic Toxicology",
        level: "Certificate",
        duration: "6 Months",
        desc: "Intensive course on toxicological analysis of biological and chemical substances.",
        icon: "M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z",
    },
];

const filteredCourses = computed(() =>
    activeTab.value === "All"
        ? courses
        : courses.filter((c) => c.level === activeTab.value),
);
</script>
