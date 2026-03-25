<template>
    <div
        class="min-h-screen bg-[#f8fafc] py-16 px-6 lg:px-12 font-sans antialiased text-slate-800"
    >
        <div class="max-w-5xl mx-auto">
            <header class="mb-12 border-b border-slate-200 pb-10">
                <div class="flex items-center gap-4 mb-4">
                    <div
                        class="p-3 bg-[#1f3a6d] rounded-2xl shadow-lg shadow-blue-900/20"
                    >
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            class="w-8 h-8 text-white"
                            fill="none"
                            viewBox="0 0 24 24"
                            stroke="currentColor"
                        >
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
                            />
                        </svg>
                    </div>
                    <h1 class="text-4xl font-black text-[#1f3a6d]">
                        Examination
                    </h1>
                </div>
                <p class="text-slate-500 text-lg max-w-2xl leading-relaxed">
                    Access official university circulars, gracing schemes, and
                    revaluation procedures governing the Institute of Forensic
                    Science.
                </p>
            </header>

            <div class="grid gap-6 md:grid-cols-1 lg:grid-cols-1">
                <div
                    v-for="(doc, index) in examinationDocs"
                    :key="index"
                    class="group bg-white p-8 rounded-[2rem] border border-slate-100 shadow-sm hover:shadow-xl hover:border-[#C8A84B]/30 transition-all duration-300 flex flex-col md:flex-row md:items-center justify-between gap-6"
                >
                    <div class="flex items-center gap-6">
                        <span
                            class="text-xs font-black text-slate-300 group-hover:text-[#C8A84B] transition-colors"
                        >
                            {{ doc.id }}
                        </span>
                        <h3
                            class="text-xl font-bold text-[#1f3a6d] group-hover:translate-x-1 transition-transform"
                        >
                            {{ doc.title }}
                        </h3>
                    </div>

                    <a
                        href="#"
                        class="inline-flex items-center justify-center gap-3 px-8 py-4 bg-slate-50 text-[#1f3a6d] font-bold text-sm rounded-2xl group-hover:bg-[#1f3a6d] group-hover:text-white transition-all shadow-inner"
                    >
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            class="w-5 h-5"
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
                        Download Circular
                    </a>
                </div>
            </div>

            <div
                class="mt-16 p-10 bg-slate-100/50 rounded-[2.5rem] border border-dashed border-slate-200 text-center"
            >
                <p class="text-slate-500 text-sm italic">
                    For any discrepancies or further queries regarding the
                    examination process, please contact the
                    <span class="text-[#1f3a6d] font-bold"
                        >Controller of Examinations</span
                    >
                    during office hours.
                </p>
            </div>
        </div>
    </div>
</template>

<script setup>
const examinationDocs = [
    { id: "2.5.1", title: "Rules for Revaluation" },
    { id: "2.5.1", title: "University Gracing Scheme" },
    { id: "2.5.1", title: "Revaluation University Circular" },
];
</script>
