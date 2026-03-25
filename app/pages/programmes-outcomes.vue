<template>
    <div
        class="min-h-screen bg-[#fcfdf2] py-20 px-6 lg:px-12 font-sans antialiased text-slate-800"
    >
        <div class="max-w-7xl mx-auto">
            <header class="text-center pb-24">
                <h1
                    class="text-5xl md:text-6xl font-black text-[#1f3a6d] tracking-tight mb-6"
                >
                    Programmes <span class="text-[#C8A84B]">Outcomes</span>
                </h1>
                <p
                    class="text-slate-500 max-w-2xl mx-auto text-xl leading-relaxed"
                >
                    The defined competencies and professional standards for
                    graduates of the Institute of Forensic Science.
                </p>
            </header>

            <section class="mb-32">
                <div class="flex flex-col lg:flex-row gap-16 items-start">
                    <div class="lg:w-1/3 lg:sticky lg:top-10">
                        <div class="flex items-center gap-4 mb-6">
                            <span
                                class="text-6xl font-outline text-transparent stroke-current text-slate-200"
                                style="-webkit-text-stroke: 2px #e2e8f0"
                                >01</span
                            >
                            <h2 class="text-4xl font-bold text-[#1f3a6d]">
                                B.Sc. Forensic Science
                            </h2>
                        </div>
                        <div
                            class="bg-white p-8 rounded-3xl border border-slate-200 shadow-sm"
                        >
                            <p class="text-slate-600 leading-loose mb-6">
                                A comprehensive 3-year journey covering
                                chemical, physical, and biological sciences to
                                build a foundation for criminal investigation.
                            </p>
                            <div class="flex flex-wrap gap-2">
                                <span
                                    class="px-4 py-2 bg-slate-100 rounded-full text-xs font-bold text-slate-500 uppercase tracking-widest"
                                    >3 Year Degree</span
                                >
                                <span
                                    class="px-4 py-2 bg-slate-100 rounded-full text-xs font-bold text-slate-500 uppercase tracking-widest"
                                    >Undergraduate</span
                                >
                            </div>
                        </div>
                    </div>

                    <div class="lg:w-2/3 grid sm:grid-cols-2 gap-8">
                        <div
                            v-for="(item, i) in bscOutcomes"
                            :key="i"
                            class="group bg-white p-10 rounded-[2.5rem] border border-slate-100 transition-all hover:shadow-xl hover:-translate-y-1"
                        >
                            <div
                                class="w-10 h-10 rounded-full bg-[#C8A84B]/10 text-[#C8A84B] flex items-center justify-center font-bold mb-6 group-hover:bg-[#C8A84B] group-hover:text-white transition-colors"
                            >
                                {{ i + 1 }}
                            </div>
                            <h4
                                class="text-xs font-black uppercase tracking-[0.2em] text-[#C8A84B] mb-3"
                            >
                                {{ item.category }}
                            </h4>
                            <p
                                class="text-slate-600 leading-relaxed text-[15.5px]"
                            >
                                {{ item.text }}
                            </p>
                        </div>
                    </div>
                </div>
            </section>

            <section class="mb-32 pt-24 border-t border-slate-200">
                <div
                    class="flex flex-col lg:flex-row-reverse gap-16 items-start"
                >
                    <div class="lg:w-1/3 lg:sticky lg:top-10">
                        <div class="flex items-center gap-4 mb-6">
                            <span
                                class="text-6xl font-outline text-transparent stroke-current text-slate-200"
                                style="-webkit-text-stroke: 2px #e2e8f0"
                                >02</span
                            >
                            <h2 class="text-4xl font-bold text-[#1f3a6d]">
                                M.Sc. Forensic Science
                            </h2>
                        </div>
                        <div
                            class="bg-[#1f3a6d] p-8 rounded-3xl text-white shadow-2xl shadow-blue-900/20"
                        >
                            <p class="opacity-80 leading-loose mb-6">
                                Advanced specialization in specialized crime
                                scene science, forensic medicine, and digital
                                forensics.
                            </p>
                            <button
                                class="w-full py-4 bg-[#C8A84B] rounded-2xl font-bold hover:bg-[#b8983d] transition-colors"
                            >
                                View Specialized Modules
                            </button>
                        </div>
                    </div>

                    <div class="lg:w-2/3 grid sm:grid-cols-2 gap-8">
                        <div
                            v-for="(item, i) in mscOutcomes"
                            :key="i"
                            class="bg-white p-10 rounded-[2.5rem] border border-slate-100 shadow-sm"
                        >
                            <div
                                class="text-[#1f3a6d] font-bold text-sm mb-4 flex items-center gap-2"
                            >
                                <div
                                    class="w-2 h-2 rounded-full bg-[#C8A84B]"
                                ></div>
                                {{ item.category }}
                            </div>
                            <p
                                class="text-slate-600 leading-relaxed text-[15.5px]"
                            >
                                {{ item.text }}
                            </p>
                        </div>
                    </div>
                </div>
            </section>

            <div class="grid lg:grid-cols-2 gap-12 pt-16">
                <div
                    v-for="diploma in [pgdf, pgdc]"
                    :key="diploma.title"
                    class="bg-white p-12 rounded-[3rem] border border-slate-200 relative"
                >
                    <h3
                        class="text-2xl font-extrabold text-[#1f3a6d] mb-10 pb-4 border-b border-slate-100"
                    >
                        {{ diploma.title }}
                    </h3>
                    <ul class="space-y-8">
                        <li
                            v-for="(point, index) in diploma.points"
                            :key="index"
                            class="flex gap-6 items-start"
                        >
                            <span
                                class="shrink-0 w-8 h-8 rounded-xl bg-slate-50 flex items-center justify-center text-[#C8A84B] font-bold text-sm"
                            >
                                {{ index + 1 }}
                            </span>
                            <p
                                class="text-slate-500 leading-relaxed text-[15px]"
                            >
                                {{ point }}
                            </p>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const bscOutcomes = [
    {
        category: "Conceptual Mastery",
        text: "Demonstrate an understanding of fundamental theories across chemical, physical, and biological sciences including psychology and law.",
    },
    {
        category: "Technical Application",
        text: "Apply scientific methods to the analysis of evidence, including crime scene investigation and data interpretation.",
    },
    {
        category: "Communication",
        text: "Articulate complex forensic concepts to diverse audiences, including law enforcement and the general public.",
    },
    {
        category: "Critical Analysis",
        text: "Utilize analytical reasoning to identify evidence, generate hypotheses, and reach informed conclusions.",
    },
];

const mscOutcomes = [
    {
        category: "Advanced Knowledge",
        text: "Deep understanding of crime scene science, forensic medicine, and digital/cyber forensics.",
    },
    {
        category: "Specialized Analysis",
        text: "Proficiency in DNA profiling, toxicology, and IT security using specialized laboratory equipment.",
    },
    {
        category: "Strategic Ethics",
        text: "Maintain rigorous ethical standards regarding privacy, confidentiality, and legal implications.",
    },
    {
        category: "Peer Leadership",
        text: "Collaborate effectively within the justice system to present findings with authority and precision.",
    },
];

const pgdf = {
    title: "PGD FSRL",
    points: [
        "Mastery in evidence collection and preservation techniques.",
        "Application of specialized scientific principles in criminology.",
        "Critical problem solving using logical reasoning skills.",
        "Comprehensive understanding of field-specific legal implications.",
    ],
};

const pgdc = {
    title: "PGD DCFRL",
    points: [
        "Expertise in digital evidence collection and preservation.",
        "Proficiency in cyber security and mobile forensic tools.",
        "Evaluation of ethical issues in digital analysis.",
        "Career readiness for digital forensic professional roles.",
    ],
};
</script>

<style scoped>
/* Added for that "Government Print" look */
.font-outline {
    -webkit-text-stroke: 1px #cbd5e1;
}
</style>
