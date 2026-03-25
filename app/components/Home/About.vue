<template>
    <section class="py-24 bg-white px-8">
        <div class="max-w-7xl mx-auto grid lg:grid-cols-2 gap-16 items-center">
            <!-- Left: Image card with floating badge -->
            <div class="relative">
                <div
                    class="rounded-3xl overflow-hidden bg-[#1B2A4A]/5 aspect-[4/3]"
                >
                    <!-- <img src="/images/institute-building.jpg" alt="Institute" -->
                    class="w-full h-full object-cover" @error="e => {
                    e.target.style.display='none';
                    e.target.nextElementSibling.style.display='flex' }" />
                    <div
                        class="hidden w-full h-full items-center justify-center text-[#1B2A4A]/20 flex-col gap-2"
                    >
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            class="h-16 w-16"
                            fill="none"
                            viewBox="0 0 24 24"
                            stroke="currentColor"
                        >
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="1"
                                d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-2 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4"
                            />
                        </svg>
                        <span class="text-sm">Institute Building</span>
                    </div>
                </div>

                <!-- Floating badge card -->
                <div
                    class="absolute -bottom-6 -right-4 bg-white rounded-2xl shadow-xl border border-gray-100 px-5 py-4 flex items-center gap-3"
                >
                    <div
                        class="w-10 h-10 rounded-xl bg-[#C9A84C]/15 flex items-center justify-center"
                    >
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            class="h-5 w-5 text-[#C9A84C]"
                            fill="none"
                            viewBox="0 0 24 24"
                            stroke="currentColor"
                        >
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z"
                            />
                        </svg>
                    </div>
                    <div>
                        <p class="text-xs font-bold text-[#1B2A4A]">
                            NAAC Accredited
                        </p>
                        <p class="text-[10px] text-gray-400">
                            Govt. of Maharashtra
                        </p>
                    </div>
                </div>

                <!-- Floating est. card -->
                <div
                    class="absolute -top-4 -left-4 bg-[#1B2A4A] rounded-2xl shadow-xl px-5 py-4"
                >
                    <p
                        class="text-[#C9A84C] text-xs font-bold tracking-widest uppercase"
                    >
                        Est.
                    </p>
                    <p
                        class="text-white text-2xl font-bold"
                        style="font-family: Georgia, serif"
                    >
                        1971
                    </p>
                </div>
            </div>

            <!-- Right: Text -->
            <div>
                <!-- Tag pill -->
                <div
                    class="inline-flex items-center gap-2 bg-[#1B2A4A]/5 rounded-full px-4 py-1.5 mb-6"
                >
                    <span
                        class="text-xs font-bold text-[#1B2A4A] tracking-wide uppercase"
                        >About the Institute</span
                    >
                </div>

                <h2
                    class="text-4xl font-bold text-[#1B2A4A] leading-snug mb-5"
                    style="font-family: Georgia, serif"
                >
                    Maharashtra's Centre for Forensic Excellence
                </h2>
                <p class="text-gray-500 leading-relaxed mb-4 text-[15px]">
                    The Institute of Forensic Science, Mumbai was established in
                    1971 under the Government of Maharashtra. It is the state's
                    premier institution dedicated to forensic science education,
                    training, and research.
                </p>
                <p class="text-gray-500 leading-relaxed mb-8 text-[15px]">
                    The institute offers academic programmes at undergraduate,
                    postgraduate, and doctoral levels, producing skilled
                    forensic professionals serving the criminal justice system
                    across India.
                </p>

                <!-- Pillars as clean info cards -->
                <div class="grid grid-cols-2 gap-3">
                    <div
                        v-for="pillar in pillars"
                        :key="pillar.title"
                        class="bg-[#F5F4F0] rounded-2xl p-4 hover:bg-[#1B2A4A]/5 transition-colors"
                    >
                        <div
                            class="w-8 h-8 rounded-xl bg-[#C9A84C]/15 flex items-center justify-center mb-3"
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                class="h-4 w-4 text-[#C9A84C]"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    :d="pillar.icon"
                                />
                            </svg>
                        </div>
                        <p class="font-bold text-[#1B2A4A] text-sm mb-1">
                            {{ pillar.title }}
                        </p>
                        <p class="text-gray-400 text-xs leading-relaxed">
                            {{ pillar.text }}
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
const pillars = [
    {
        title: "Our Mission",
        text: "Impart quality forensic education and produce competent professionals for investigative agencies.",
        icon: "M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z",
    },
    {
        title: "Our Vision",
        text: "Globally recognised centre of excellence in forensic science education and research.",
        icon: "M15 12a3 3 0 11-6 0 3 3 0 016 0z M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z",
    },
    {
        title: "Research",
        text: "Cutting-edge research in DNA, toxicology, digital forensics and criminalistics.",
        icon: "M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z",
    },
    {
        title: "Casework",
        text: "Supporting Maharashtra Police and CBI with expert forensic analysis and testimony.",
        icon: "M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2",
    },
];
</script>
