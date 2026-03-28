<template>
    <section
        class="min-h-[88vh] flex items-center relative overflow-hidden px-8 py-20"
    >
        <!-- Soft background blobs -->
        <div
            class="absolute top-[-80px] right-[-80px] w-[420px] h-[420px] rounded-full blur-3xl pointer-events-none"
        ></div>
        <div
            class="absolute bottom-[-60px] left-[-60px] w-[300px] h-[300px] rounded-full blur-3xl pointer-events-none"
        ></div>

        <div
            class="max-w-7xl mx-auto w-full grid lg:grid-cols-2 gap-16 items-center"
        >
            <!-- Left: Text + CTAs -->
            <div>
                <!-- Badge pill -->
                <div
                    class="inline-flex items-center gap-2 bg-white rounded-full px-4 py-2 shadow-sm border border-gray-100 mb-8"
                >
                    <span
                        class="w-2 h-2 rounded-full bg-[#C9A84C] animate-pulse"
                    ></span>
                    <span
                        class="text-xs font-semibold text-[#1B2A4A] tracking-wide"
                        >Admissions Open 2025–26</span
                    >
                </div>

                <h2
                    class="text-5xl lg:text-6xl font-bold text-[#1B2A4A] leading-[1.1] mb-6"
                    style="font-family: Georgia, serif"
                >
                    Advancing Justice<br />
                    Through
                    <span class="relative inline-block">
                        <span class="relative z-10">Forensic</span>
                        <span
                            class="absolute bottom-1 left-0 right-0 h-3 bg-[#C9A84C]/25 -z-0 rounded"
                        ></span> </span
                    ><br />
                    <span class="text-[#C9A84C]">Science.</span>
                </h2>

                <p class="text-gray-500 text-lg leading-relaxed mb-10 max-w-md">
                    Maharashtra's premier institute for forensic science
                    education, research, and casework — equipping experts to
                    serve truth and justice since 1971.
                </p>

                <div class="flex flex-wrap gap-3">
                    <a
                        href="/admissions"
                        class="inline-flex items-center gap-2 bg-[#1B2A4A] text-white rounded-full px-7 py-3.5 font-semibold text-sm hover:bg-[#243560] transition-all duration-200 shadow-lg shadow-[#1B2A4A]/20"
                    >
                        Explore Programmes
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            class="h-4 w-4"
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
                    <a
                        href="/about"
                        class="inline-flex items-center gap-2 bg-white text-[#1B2A4A] rounded-full px-7 py-3.5 font-semibold text-sm border border-gray-200 hover:border-[#1B2A4A] transition-all duration-200 shadow-sm"
                    >
                        Learn More
                    </a>
                </div>
            </div>

            <!-- Right: Floating stat cards grid -->
            <div class="grid grid-cols-2 gap-4">
                <div
                    v-for="(stat, i) in stats"
                    :key="stat.label"
                    class="bg-white rounded-3xl p-6 shadow-sm border border-gray-100 hover:shadow-md hover:-translate-y-1 transition-all duration-300"
                    :class="i === 0 ? 'col-span-2' : ''"
                >
                    <div
                        class="flex items-start justify-between mb-3"
                        :class="i === 0 ? 'flex-row' : 'flex-col gap-3'"
                    >
                        <div
                            class="w-10 h-10 rounded-2xl flex items-center justify-center"
                            :class="
                                i % 2 === 0 ? 'bg-[#1B2A4A]' : 'bg-[#C9A84C]/15'
                            "
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                class="h-5 w-5"
                                :class="
                                    i % 2 === 0
                                        ? 'text-white'
                                        : 'text-[#C9A84C]'
                                "
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="1.8"
                                    :d="stat.icon"
                                />
                            </svg>
                        </div>
                        <div :class="i === 0 ? 'text-right' : ''">
                            <div
                                class="text-3xl font-bold text-[#1B2A4A]"
                                style="font-family: Georgia, serif"
                            >
                                {{ stat.value }}
                            </div>
                        </div>
                    </div>
                    <div v-if="i !== 0">
                        <p class="font-semibold text-[#1B2A4A] text-sm">
                            {{ stat.label }}
                        </p>
                        <p class="text-gray-400 text-xs mt-0.5">
                            {{ stat.sub }}
                        </p>
                    </div>
                    <div v-else class="flex items-end justify-between">
                        <div>
                            <p class="font-semibold text-[#1B2A4A] text-sm">
                                {{ stat.label }}
                            </p>
                            <p class="text-gray-400 text-xs mt-0.5">
                                {{ stat.sub }}
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
const stats = [
    {
        value: "50+",
        label: "Years of Excellence",
        sub: "Serving justice since 1971",
        icon: "M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z",
    },
    {
        value: "12+",
        label: "Programmes",
        sub: "UG, PG & Certificate",
        icon: "M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253",
    },
    {
        value: "5K+",
        label: "Alumni Network",
        sub: "Across India & abroad",
        icon: "M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z",
    },
    {
        value: "10K+",
        label: "Cases Analysed",
        sub: "Supporting law enforcement",
        icon: "M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z",
    },
];
</script>
