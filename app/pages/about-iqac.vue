<template>
    <div
        class="min-h-screen bg-[#f8fafc] py-20 px-6 lg:px-12 font-sans antialiased text-slate-800"
    >
        <div class="max-w-6xl mx-auto">
            <header class="mb-20 text-center md:text-left">
                <div
                    class="flex flex-col md:flex-row md:items-center gap-6 mb-8"
                >
                    <div
                        class="inline-flex p-4 bg-[#1f3a6d] rounded-3xl shadow-xl shadow-blue-900/20 w-fit"
                    >
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            class="w-10 h-10 text-white"
                            fill="none"
                            viewBox="0 0 24 24"
                            stroke="currentColor"
                        >
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="1.5"
                                d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"
                            />
                        </svg>
                    </div>
                    <h1
                        class="text-4xl md:text-5xl font-black text-[#1f3a6d] tracking-tight"
                    >
                        About <span class="text-[#C8A84B]">IQAC</span>
                    </h1>
                </div>
                <p
                    class="text-xl md:text-2xl text-slate-500 max-w-4xl leading-relaxed italic border-l-4 border-[#C8A84B] pl-8 py-2"
                >
                    "To maintain the momentum of quality consciousness is the
                    crucial effort of IQAC."
                </p>
            </header>

            <section class="grid lg:grid-cols-5 gap-16 mb-24 items-start">
                <div class="lg:col-span-3 space-y-8">
                    <h2
                        class="text-2xl font-bold text-[#1f3a6d] flex items-center gap-3"
                    >
                        Vision & Purpose
                        <span class="flex-grow h-px bg-slate-200"></span>
                    </h2>
                    <div
                        class="space-y-6 text-slate-600 leading-loose text-[16.5px]"
                    >
                        <p>
                            In pursuance of its Action Plan for performance
                            evaluation, assessment, and accreditation and
                            quality up-gradation of institutions of higher
                            education, the
                            <span class="text-[#1f3a6d] font-semibold"
                                >National Assessment and Accreditation Council
                                (NAAC)</span
                            >
                            proposes that every accredited institution should
                            establish an Internal Quality Assurance Cell (IQAC).
                        </p>
                        <p>
                            Since quality enhancement is a continuous process,
                            the IQAC becomes an integral part of the
                            institution’s system, working towards the
                            realization of goals for quality enhancement and
                            sustenance.
                        </p>
                    </div>
                </div>

                <div
                    class="lg:col-span-2 bg-white p-12 rounded-[3rem] border border-slate-100 shadow-2xl shadow-slate-200/40 relative"
                >
                    <div
                        class="absolute top-0 right-0 p-8 opacity-5 text-[#1f3a6d]"
                    >
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            class="w-24 h-24"
                            fill="currentColor"
                            viewBox="0 0 24 24"
                        >
                            <path
                                d="M14.017 21L14.017 18C14.017 16.8954 14.9124 16 16.017 16H19.017C20.1216 16 21.017 16.8954 21.017 18V21M14.017 21H21.017M14.017 21V12C14.017 10.8954 14.9124 10 16.017 10H19.017C20.1216 10 21.017 10.8954 21.017 12V16M3.01709 21V12C3.01709 10.8954 3.91252 10 5.01709 10H8.01709C9.12166 10 10.0171 10.8954 10.0171 12V21M3.01709 21H10.0171M3.01709 21V18C3.01709 16.8954 3.91252 16 5.01709 16H8.01709C9.12166 16 10.0171 16.8954 10.0171 18V21M12.0171 6C13.6739 6 15.0171 4.65685 15.0171 3C15.0171 1.34315 13.6739 0 12.0171 0C10.3602 0 9.01709 1.34315 9.01709 3C9.01709 4.65685 10.3602 6 12.0171 6Z"
                            />
                        </svg>
                    </div>
                    <h3
                        class="text-[#C8A84B] font-black uppercase tracking-[0.2em] text-[10px] mb-6"
                    >
                        Core Objective
                    </h3>
                    <p
                        class="text-[#1f3a6d] text-xl font-bold leading-relaxed italic relative z-10"
                    >
                        "To develop a system for conscious, consistent and
                        catalytic action to improve academic and administrative
                        performance."
                    </p>
                </div>
            </section>

            <div class="mb-24">
                <h2
                    class="text-3xl font-black text-[#1f3a6d] text-center mb-16"
                >
                    Strategies & Functions
                </h2>
                <div class="grid md:grid-cols-3 gap-10">
                    <div
                        v-for="(item, i) in functions"
                        :key="i"
                        class="group bg-white p-10 rounded-[2.5rem] border border-slate-100 transition-all hover:shadow-xl hover:-translate-y-2"
                    >
                        <div
                            class="w-14 h-14 bg-slate-50 rounded-2xl flex items-center justify-center text-[#C8A84B] mb-8 group-hover:bg-[#1f3a6d] group-hover:text-white transition-all duration-500"
                            v-html="item.icon"
                        ></div>
                        <h4
                            class="text-[#1f3a6d] font-bold mb-4 text-xl leading-tight"
                        >
                            {{ item.title }}
                        </h4>
                        <p class="text-slate-500 text-[15px] leading-relaxed">
                            {{ item.text }}
                        </p>
                    </div>
                </div>
            </div>

            <div
                class="bg-[#1f3a6d] p-12 md:p-16 rounded-[4rem] text-center relative overflow-hidden shadow-2xl shadow-blue-900/30"
            >
                <div
                    class="absolute inset-0 bg-[url('https://www.transparenttextures.com/patterns/cubes.png')] opacity-10"
                ></div>
                <h3 class="text-white text-3xl font-bold mb-6 relative z-10">
                    IQAC Committee
                </h3>
                <p
                    class="text-blue-100/70 mb-10 max-w-2xl mx-auto text-base leading-loose relative z-10"
                >
                    Our committee oversees periodic institutional assessments
                    and maintains the rigorous documentation standards required
                    for national accreditation.
                </p>
                <button
                    class="bg-[#C8A84B] text-white px-12 py-5 rounded-2xl font-black text-sm uppercase tracking-[0.15em] hover:bg-[#b8983d] transition-all relative z-10 shadow-xl active:scale-95"
                >
                    View Committee Members
                </button>
            </div>
        </div>
    </div>
</template>

<script setup>
const functions = [
    {
        title: "Quality Benchmarks",
        text: "Defining and applying quality parameters for academic and administrative activities across all departments.",
        icon: `<svg xmlns="http://www.w3.org/2000/svg" class="w-7 h-7" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-6 9l2 2 4-4" /></svg>`,
    },
    {
        title: "Learner-Centricity",
        text: "Facilitating a learner-centric environment conducive to high-quality education and faculty development.",
        icon: `<svg xmlns="http://www.w3.org/2000/svg" class="w-7 h-7" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253" /></svg>`,
    },
    {
        title: "Feedback Loops",
        text: "Managing feedback from students, parents, and stakeholders to inform institutional quality improvement.",
        icon: `<svg xmlns="http://www.w3.org/2000/svg" class="w-7 h-7" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z" /></svg>`,
    },
];
</script>
