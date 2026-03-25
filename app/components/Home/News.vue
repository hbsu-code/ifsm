<template>
    <section class="py-24 bg-white px-8">
        <div class="max-w-7xl mx-auto">
            <!-- Header -->
            <div
                class="flex flex-col md:flex-row md:items-end justify-between gap-4 mb-12"
            >
                <div>
                    <div
                        class="inline-flex items-center gap-2 bg-[#1B2A4A]/5 rounded-full px-4 py-1.5 mb-4"
                    >
                        <span
                            class="text-xs font-bold text-[#1B2A4A] tracking-wide uppercase"
                            >Latest Updates</span
                        >
                    </div>
                    <h2
                        class="text-4xl font-bold text-[#1B2A4A]"
                        style="font-family: Georgia, serif"
                    >
                        News & Events
                    </h2>
                </div>
                <a
                    href="/news"
                    class="inline-flex items-center gap-2 text-sm font-semibold text-[#1B2A4A] border-b-2 border-[#C9A84C] pb-0.5 hover:text-[#C9A84C] transition-colors self-start"
                >
                    View All →
                </a>
            </div>

            <div class="grid lg:grid-cols-3 gap-6">
                <!-- Featured card (large) -->
                <div
                    class="lg:col-span-2 bg-[#F5F4F0] rounded-3xl overflow-hidden group hover:shadow-md transition-all duration-300"
                >
                    <div class="h-56 bg-[#1B2A4A]/10 overflow-hidden">
                        <!-- <img src="/images/news-featured.jpg" alt="Featured News"
              class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500"
              @error="e => e.target.style.display='none'" /> -->
                    </div>
                    <div class="p-7">
                        <div class="flex items-center gap-3 mb-3">
                            <span
                                class="bg-[#C9A84C]/15 text-[#9A7030] text-xs font-bold px-3 py-1 rounded-full"
                                >EVENT</span
                            >
                            <span class="text-gray-400 text-xs"
                                >15 March 2025</span
                            >
                        </div>
                        <h3
                            class="font-bold text-[#1B2A4A] text-xl mb-2 leading-snug group-hover:text-[#C9A84C] transition-colors"
                            style="font-family: Georgia, serif"
                        >
                            National Symposium on Forensic DNA Technology — 2025
                        </h3>
                        <p class="text-gray-500 text-sm leading-relaxed mb-4">
                            IFSM hosted a national-level symposium bringing
                            together leading forensic experts, law enforcement,
                            and academics to discuss advancements in DNA
                            profiling.
                        </p>
                        <a
                            href="/news/1"
                            class="inline-flex items-center gap-2 text-sm font-bold text-[#1B2A4A] hover:text-[#C9A84C] transition-colors"
                        >
                            Read More
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
                    </div>
                </div>

                <!-- Right column -->
                <div class="flex flex-col gap-5">
                    <!-- Recent news cards -->
                    <div
                        v-for="news in recentNews"
                        :key="news.title"
                        class="bg-[#F5F4F0] rounded-2xl p-5 hover:bg-[#1B2A4A]/5 transition-colors group cursor-pointer"
                    >
                        <div class="flex items-center gap-2 mb-2">
                            <span
                                class="text-xs font-bold px-2.5 py-0.5 rounded-full"
                                :class="
                                    news.type === 'EVENT'
                                        ? 'bg-blue-50 text-blue-600'
                                        : 'bg-emerald-50 text-emerald-600'
                                "
                            >
                                {{ news.type }}
                            </span>
                            <span class="text-gray-400 text-xs">{{
                                news.date
                            }}</span>
                        </div>
                        <p
                            class="text-[#1B2A4A] text-sm font-semibold leading-snug group-hover:text-[#C9A84C] transition-colors"
                        >
                            {{ news.title }}
                        </p>
                    </div>

                    <!-- Notice board card -->
                    <div class="bg-[#1B2A4A] rounded-3xl p-6 flex-1">
                        <div class="flex items-center gap-2 mb-4">
                            <div
                                class="w-7 h-7 rounded-xl bg-[#C9A84C]/20 flex items-center justify-center"
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
                                        d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"
                                    />
                                </svg>
                            </div>
                            <h4
                                class="text-[#C9A84C] font-bold text-sm uppercase tracking-wide"
                            >
                                Notice Board
                            </h4>
                        </div>
                        <ul class="flex flex-col gap-3">
                            <li
                                v-for="notice in notices"
                                :key="notice"
                                class="text-blue-200/80 text-xs leading-relaxed hover:text-white transition-colors cursor-pointer flex items-start gap-2"
                            >
                                <span class="text-[#C9A84C] mt-0.5 shrink-0"
                                    >›</span
                                >
                                {{ notice }}
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
const recentNews = [
    {
        title: "Admissions open for M.Sc. Forensic Science 2025–26",
        date: "10 Mar 2025",
        type: "NEWS",
    },
    {
        title: "IFSM signs MoU with CBI Academy for joint training",
        date: "02 Mar 2025",
        type: "NEWS",
    },
    {
        title: "Annual Convocation Ceremony — March 2025",
        date: "22 Feb 2025",
        type: "EVENT",
    },
];

const notices = [
    "Admission 2025–26: Last date to apply — 30 April 2025",
    "Examination schedule for Sem IV released",
    "Workshop on Questioned Documents — April 18, 2025",
    "Scholarship applications invited for SC/ST/OBC students",
];
</script>
