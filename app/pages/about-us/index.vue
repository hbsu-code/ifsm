<template>
    <section class="min-h-screen py-20 px-6 lg:px-16 overflow-hidden">
        <div class="max-w-7xl mx-auto">
            <div class="grid lg:grid-cols-12 gap-16 items-start">
                <div class="lg:col-span-5 relative group">
                    <div
                        class="relative z-10 bg-white p-3 rounded-2xl shadow-2xl transition-transform duration-500 group-hover:-translate-y-2"
                    >
                        <div
                            class="bg-gray-100 rounded-xl h-[500px] w-full overflow-hidden relative"
                        >
                            <div
                                class="absolute inset-0 bg-gradient-to-t from-[#1e3557]/40 to-transparent"
                            ></div>
                            <div
                                class="flex items-center justify-center h-full text-gray-400"
                            >
                                Main Campus Image
                            </div>
                        </div>
                    </div>

                    <div
                        class="absolute -top-6 -right-6 z-20 bg-[#c5a367] text-white w-24 h-24 rounded-full flex flex-col items-center justify-center shadow-xl border-4 border-white"
                    >
                        <span
                            class="text-[10px] tracking-[0.2em] uppercase opacity-80"
                            >Since</span
                        >
                        <span class="text-xl font-bold italic">2009</span>
                    </div>

                    <div
                        class="absolute -bottom-8 -left-8 z-20 bg-white/90 backdrop-blur-md shadow-xl rounded-2xl p-5 flex items-center gap-4 border border-gray-100 max-w-[240px]"
                    >
                        <div
                            class="bg-amber-50 w-12 h-12 rounded-lg flex items-center justify-center text-2xl shadow-inner"
                        >
                            🏅
                        </div>
                        <div>
                            <p
                                class="text-[10px] font-bold text-[#c5a367] uppercase tracking-widest"
                            >
                                Accreditation
                            </p>
                            <p class="text-sm font-bold text-[#1e3557]">
                                NAAC B+ Grade
                            </p>
                        </div>
                    </div>

                    <div
                        class="absolute -z-10 top-20 -left-20 w-64 h-64 border-[16px] border-[#efeae4] rounded-full"
                    ></div>
                </div>

                <div class="lg:col-span-7 lg:pl-8">
                    <div class="flex items-center gap-3 mb-6">
                        <div class="h-[1px] w-12 bg-[#c5a367]"></div>
                        <span
                            class="text-[11px] font-bold text-[#c5a367] tracking-[0.3em] uppercase"
                        >
                            Excellence in Criminology
                        </span>
                    </div>

                    <h1
                        class="text-4xl md:text-5xl font-serif font-medium text-[#1e3557] leading-[1.15] mb-8"
                    >
                        Maharashtra's Centre for <br />
                        <span class="italic text-[#c5a367]"
                            >Forensic Excellence</span
                        >
                    </h1>

                    <div class="relative mb-8">
                        <span
                            class="absolute -top-4 -left-2 text-6xl text-[#efeae4] font-serif leading-none"
                            >“</span
                        >
                        <p
                            class="relative z-10 pl-6 text-lg text-gray-600 italic leading-relaxed"
                        >
                            Crime is common. Logic is rare. Therefore it is upon
                            the logic rather than upon the crime that you should
                            dwell.
                        </p>
                        <p class="pl-6 mt-3 text-sm font-bold text-[#1e3557]">
                            — Arthur Conan Doyle
                        </p>
                    </div>

                    <div class="grid sm:grid-cols-2 gap-4">
                        <div
                            v-for="(pillar, idx) in pillars"
                            :key="idx"
                            class="p-5 rounded-2xl border border-gray-100 bg-white hover:border-[#c5a367] hover:shadow-lg transition-all duration-300 group"
                        >
                            <div
                                class="w-10 h-10 rounded-lg bg-[#f6f3ef] flex items-center justify-center mb-4 group-hover:bg-[#1e3557] group-hover:text-white transition-colors"
                            >
                                <component :is="pillar.icon" class="w-5 h-5" />
                            </div>
                            <h3 class="font-bold text-[#1e3557] mb-1">
                                {{ pillar.title }}
                            </h3>
                            <p class="text-xs text-gray-500 leading-relaxed">
                                {{ pillar.desc }}
                            </p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="mt-32 grid lg:grid-cols-12 gap-16">
                <div class="hidden lg:block lg:col-span-3 sticky top-24 h-fit">
                    <nav class="space-y-4 border-l-2 border-gray-100 ml-4">
                        <a
                            href="#about"
                            class="block pl-6 text-sm font-bold text-[#1e3557] border-l-2 border-[#c5a367] -ml-[2px]"
                            >About Institute</a
                        >
                        <a
                            href="#academic"
                            class="block pl-6 text-sm font-medium text-gray-400 hover:text-[#1e3557] transition-colors"
                            >Academic Structure</a
                        >
                        <a
                            href="#infrastructure"
                            class="block pl-6 text-sm font-medium text-gray-400 hover:text-[#1e3557] transition-colors"
                            >Infrastructure</a
                        >
                        <a
                            href="#nep"
                            class="block pl-6 text-sm font-medium text-gray-400 hover:text-[#1e3557] transition-colors"
                            >NEP 2020 Compliance</a
                        >
                    </nav>
                </div>

                <div
                    class="lg:col-span-8 space-y-10 text-gray-700 leading-loose text-base"
                >
                    <section id="about">
                        <h2
                            class="text-2xl font-serif font-bold text-[#1e3557] mb-6 flex items-center gap-4"
                        >
                            Institutional Profile
                            <div class="flex-1 h-[1px] bg-gray-100"></div>
                        </h2>
                        <div class="space-y-6 drop-cap">
                            <p>
                                Institute of Forensic Science offers a wide
                                range of programs including
                                <span class="text-[#1e3557] font-semibold"
                                    >B.Sc. and M.Sc. in Forensic Science</span
                                >
                                with specializations in Questioned Documents,
                                Fingerprints and Biometrics, Digital and Cyber
                                Forensics, Forensic Physics & Ballistics,
                                Forensic Chemistry & Toxicology, and Forensic
                                Biology, Serology & DNA Fingerprinting.
                            </p>
                            <p>
                                The institute is a constituent college of
                                <strong
                                    >Dr. Homi Bhabha State University,
                                    Mumbai</strong
                                >, located in the historic Institute of Science
                                campus. The campus blends heritage architecture
                                with modern infrastructure including advanced
                                laboratories and libraries.
                            </p>
                        </div>
                    </section>

                    <div
                        class="bg-[#1e3557] rounded-3xl p-10 text-white flex flex-col md:flex-row gap-8 items-center"
                    >
                        <div class="text-center md:text-left">
                            <h4 class="text-xl font-serif mb-2 text-[#c5a367]">
                                Academic Excellence
                            </h4>
                            <p class="text-sm text-gray-300">
                                Our multidisciplinary approach covers Law,
                                Psychology, and Digital Forensics to create
                                industry-ready professionals.
                            </p>
                        </div>
                        <div class="flex gap-4 shrink-0">
                            <div class="text-center">
                                <div class="text-3xl font-bold">07</div>
                                <div
                                    class="text-[10px] uppercase tracking-tighter opacity-60"
                                >
                                    Departments
                                </div>
                            </div>
                            <div class="w-[1px] h-12 bg-white/20"></div>
                            <div class="text-center">
                                <div class="text-3xl font-bold">15+</div>
                                <div
                                    class="text-[10px] uppercase tracking-tighter opacity-60"
                                >
                                    Specializations
                                </div>
                            </div>
                        </div>
                    </div>

                    <section id="nep" class="border-t border-gray-100 pt-10">
                        <h2
                            class="text-2xl font-serif font-bold text-[#1e3557] mb-6"
                        >
                            Future-Proof Curriculum
                        </h2>
                        <p class="mb-6">
                            NEP-2020 has been implemented from academic session
                            2023–24, introducing a
                            <span class="bg-[#efeae4] px-1 italic"
                                >flexible credit-based curriculum</span
                            >. The CBCS system allows students to choose
                            interdisciplinary subjects and build dynamic career
                            pathways aligned with modern industry needs.
                        </p>
                        <button
                            class="bg-[#1e3557] text-white px-8 py-3 rounded-full text-sm font-bold shadow-xl hover:bg-[#c5a367] transition-all duration-300 flex items-center gap-2"
                        >
                            Download Prospectus
                            <span>→</span>
                        </button>
                    </section>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
const pillars = [
    {
        title: "Our Mission",
        desc: "Educate and train professionals to combat modern crime.",
        icon: "TargetIcon",
    },
    {
        title: "Global Vision",
        desc: "Become a global forensic excellence hub for justice.",
        icon: "EyeIcon",
    },
    {
        title: "Research Lab",
        desc: "DNA, cyber forensics & toxicology innovation center.",
        icon: "FlaskIcon",
    },
    {
        title: "Law & Justice",
        desc: "Supporting law enforcement & the criminal justice system.",
        icon: "ScaleIcon",
    },
];

// In a real Vue project, you'd import icons from Lucide-Vue or Heroicons
// Component tags above like FlaskIcon are placeholders.

useHead({
    title: "About - Institute of Forensic Science",
});
</script>

<style scoped>
/* Custom Editorial Drop Cap */
.drop-cap p:first-of-type::first-letter {
    float: left;
    font-size: 3.5rem;
    line-height: 1;
    font-weight: bold;
    padding-right: 0.75rem;
    color: #c5a367;
    font-family: serif;
}
</style>
