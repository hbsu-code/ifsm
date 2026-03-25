<template>
    <div
        class="min-h-screen bg-[#f8fafc] py-16 px-6 lg:px-12 font-sans antialiased text-slate-800"
    >
        <div class="max-w-5xl mx-auto">
            <header class="mb-12">
                <div class="flex items-center gap-3 mb-4">
                    <div class="w-1.5 h-8 bg-[#C8A84B] rounded-full"></div>
                    <h1 class="text-3xl md:text-4xl font-black text-[#1f3a6d]">
                        Downloads & Resources
                    </h1>
                </div>
                <p class="text-slate-500 text-lg max-w-2xl leading-relaxed">
                    Access official government resolutions, service rules, and
                    administrative charters governing the Institute of Forensic
                    Science.
                </p>
            </header>

            <div class="space-y-4">
                <div
                    v-for="(doc, index) in downloadLinks"
                    :key="index"
                    class="group bg-white p-6 md:p-8 rounded-2xl border border-slate-100 hover:border-[#1f3a6d]/20 hover:shadow-xl hover:shadow-slate-200/50 transition-all duration-300 flex flex-col md:flex-row md:items-center justify-between gap-6"
                >
                    <div class="flex items-start md:items-center gap-5">
                        <div
                            class="shrink-0 w-12 h-12 bg-slate-50 rounded-xl flex items-center justify-center text-[#1f3a6d] group-hover:bg-[#1f3a6d] group-hover:text-white transition-colors duration-300"
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                class="w-6 h-6"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M7 21h10a2 2 0 002-2V9.414a1 1 0 00-.293-.707l-5.414-5.414A1 1 0 0012.586 3H7a2 2 0 00-2 2v14a2 2 0 002 2z"
                                />
                            </svg>
                        </div>

                        <div class="space-y-1">
                            <span
                                v-if="doc.id"
                                class="text-[10px] font-black tracking-[0.2em] text-[#C8A84B] uppercase"
                            >
                                Ref: {{ doc.id }}
                            </span>
                            <h3
                                class="text-[16px] md:text-lg font-bold text-[#1f3a6d] leading-snug"
                            >
                                {{ doc.title }}
                            </h3>
                        </div>
                    </div>

                    <button
                        class="shrink-0 inline-flex items-center justify-center gap-2 px-6 py-3 bg-slate-100 text-[#1f3a6d] font-bold text-xs rounded-xl hover:bg-[#C8A84B] hover:text-white transition-all"
                    >
                        <svg
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
                                d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4"
                            />
                        </svg>
                        Download PDF
                    </button>
                </div>
            </div>

            <footer
                class="mt-16 pt-8 border-t border-slate-200 flex flex-col md:flex-row justify-between items-center gap-6"
            >
                <p class="text-slate-400 text-xs text-center md:text-left">
                    All documents are provided in English and Marathi versions
                    where applicable.<br />
                    Last updated: March 2026
                </p>
                <div class="flex gap-4">
                    <div
                        class="w-10 h-10 rounded-lg bg-slate-100 border border-slate-200"
                    ></div>
                    <div
                        class="w-10 h-10 rounded-lg bg-slate-100 border border-slate-200"
                    ></div>
                </div>
            </footer>
        </div>
    </div>
</template>

<script setup>
const downloadLinks = [
    { id: "", title: "Citizen Charter" },
    {
        id: "2.4.1",
        title: "GR dated 17th Aug 2009 (Marathi & English Version)",
    },
    { id: "6.2.1", title: "MCSR-1981 - Service Rules" },
    { id: "6.2.1", title: "Maharashtra Universities Act, 2016" },
    { id: "6.3.1", title: "Confidential Report - Faculty" },
    { id: "6.3.1", title: "Confidential Report - Group A & B" },
    { id: "6.3.1", title: "Confidential Report - Group B & C" },
    { id: "6.3.1", title: "PBAS CAS Application" },
];
</script>
