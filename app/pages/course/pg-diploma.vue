<template>
    <div
        class="min-h-screen bg-[#f8fafc] py-20 px-6 lg:px-12 font-sans antialiased text-slate-800"
    >
        <div class="max-w-7xl mx-auto">
            <header class="mb-20 text-center">
                <h1
                    class="text-4xl md:text-5xl font-black text-[#1f3a6d] mb-6 tracking-tight"
                >
                    Post Graduate <span class="text-[#C8A84B]">Diplomas</span>
                </h1>
                <div
                    class="w-24 h-1.5 bg-[#C8A84B] mx-auto rounded-full mb-8"
                ></div>
                <p
                    class="text-slate-500 max-w-2xl mx-auto text-lg leading-relaxed"
                >
                    Specialized professional programs bridging the gap between
                    scientific theory and legal application.
                </p>
            </header>

            <div class="space-y-32">
                <section class="relative">
                    <div class="grid lg:grid-cols-12 gap-12 items-start">
                        <div class="lg:col-span-4 lg:sticky lg:top-10">
                            <span
                                class="text-xs font-black uppercase tracking-[0.3em] text-[#C8A84B] mb-4 block"
                                >Specialization 01</span
                            >
                            <h2
                                class="text-3xl font-extrabold text-[#1f3a6d] mb-6 leading-tight"
                            >
                                Forensic Science & Related Laws (FSRL)
                            </h2>
                            <div
                                class="bg-white p-8 rounded-3xl border border-slate-100 shadow-xl shadow-slate-200/40"
                            >
                                <button
                                    class="w-full py-4 bg-[#1f3a6d] text-white rounded-2xl font-bold flex items-center justify-center gap-3 hover:bg-[#2a4d8d] transition-all group"
                                >
                                    <svg
                                        xmlns="http://www.w3.org/2000/svg"
                                        class="w-5 h-5 opacity-70 group-hover:translate-y-0.5 transition-transform"
                                        fill="none"
                                        viewBox="0 0 24 24"
                                        stroke="currentColor"
                                    >
                                        <path
                                            stroke-linecap="round"
                                            stroke-linejoin="round"
                                            stroke-width="2"
                                            d="M12 10v6m0 0l-3-3m3 3l3-3m2 8H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
                                        />
                                    </svg>
                                    Download Syllabus
                                </button>
                            </div>
                        </div>

                        <div class="lg:col-span-8 space-y-6">
                            <div
                                v-for="(outcome, i) in fsrlOutcomes"
                                :key="i"
                                class="bg-white p-8 rounded-[2rem] border border-slate-100 flex gap-6 items-start group hover:border-[#C8A84B]/40 transition-colors"
                            >
                                <div
                                    class="shrink-0 w-10 h-10 rounded-xl bg-slate-50 flex items-center justify-center text-[#C8A84B] font-black text-sm group-hover:bg-[#C8A84B] group-hover:text-white transition-all"
                                >
                                    {{ i + 1 }}
                                </div>
                                <p
                                    class="text-slate-600 leading-relaxed text-[15.5px] pt-1.5"
                                >
                                    {{ outcome }}
                                </p>
                            </div>
                        </div>
                    </div>
                </section>

                <div class="flex items-center justify-center gap-4">
                    <div class="h-px flex-1 bg-slate-200"></div>
                    <div class="w-2 h-2 rounded-full bg-slate-200"></div>
                    <div class="h-px flex-1 bg-slate-200"></div>
                </div>

                <section class="relative">
                    <div class="grid lg:grid-cols-12 gap-12 items-start">
                        <div class="lg:col-span-8 space-y-6 order-2 lg:order-1">
                            <div
                                v-for="(outcome, i) in dcfOutcomes"
                                :key="i"
                                class="bg-white p-8 rounded-[2rem] border border-slate-100 flex gap-6 items-start group hover:border-[#1f3a6d]/40 transition-colors"
                            >
                                <div
                                    class="shrink-0 w-10 h-10 rounded-xl bg-slate-50 flex items-center justify-center text-[#1f3a6d] font-black text-sm group-hover:bg-[#1f3a6d] group-hover:text-white transition-all"
                                >
                                    {{ i + 1 }}
                                </div>
                                <p
                                    class="text-slate-600 leading-relaxed text-[15.5px] pt-1.5"
                                >
                                    {{ outcome }}
                                </p>
                            </div>
                        </div>

                        <div
                            class="lg:col-span-4 lg:sticky lg:top-10 order-1 lg:order-2"
                        >
                            <span
                                class="text-xs font-black uppercase tracking-[0.3em] text-[#C8A84B] mb-4 block"
                                >Specialization 02</span
                            >
                            <h2
                                class="text-3xl font-extrabold text-[#1f3a6d] mb-6 leading-tight"
                            >
                                Digital & Cyber Forensics (DCFRL)
                            </h2>
                            <div
                                class="bg-slate-50 p-1 rounded-3xl border border-slate-200"
                            >
                                <div
                                    class="bg-white p-8 rounded-[1.4rem] border border-slate-100 shadow-sm"
                                >
                                    <p
                                        class="text-sm text-slate-500 leading-relaxed mb-6 italic"
                                    >
                                        Focuses on the collection, preservation,
                                        and analysis of digital evidence in the
                                        modern cybersecurity landscape.
                                    </p>
                                    <button
                                        class="w-full py-4 bg-[#C8A84B] text-white rounded-2xl font-bold flex items-center justify-center gap-3 hover:bg-[#b8983d] transition-all"
                                    >
                                        Syllabus Overview
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </section>
            </div>
        </div>
    </div>
</template>

<script setup>
const fsrlOutcomes = [
    "Demonstrate a strong foundation in forensic science theories, including the principles of evidence collection, preservation, and analysis.",
    "Apply scientific methods to forensic evidence interpretation using specialized techniques in criminology and law.",
    "Communicate complex findings effectively, both orally and in writing, to law enforcement, attorneys, and the general public.",
    "Think critically and solve field-specific problems using analytical reasoning and hypothesis generation.",
    "Evaluate and apply the legal and ethical implications of forensic evidence to professional practice in the field.",
];

const dcfOutcomes = [
    "Master the principles of digital and cyber forensics, including the rigorous collection and analysis of digital evidence.",
    "Utilize specialized tools for computer, cyber security, and mobile forensics to interpret data in diverse contexts.",
    "Evaluate legal and ethical issues specific to the collection and preservation of digital evidence.",
    "Articulate complex digital findings to varied audiences, bridging the gap between technical and legal terminology.",
    "Apply professional best practices and tools necessary for career success in the digital forensic sector.",
];
</script>
