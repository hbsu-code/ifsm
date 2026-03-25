<template>
    <section class="py-24 bg-white px-8">
        <div class="max-w-7xl mx-auto">
            <div
                class="flex flex-col md:flex-row md:items-end justify-between gap-4 mb-12"
            >
                <div>
                    <div
                        class="inline-flex items-center gap-2 bg-[#1B2A4A]/5 rounded-full px-4 py-1.5 mb-4"
                    >
                        <span
                            class="text-xs font-bold text-[#1B2A4A] tracking-wide uppercase"
                            >Campus & Labs</span
                        >
                    </div>
                    <h2
                        class="text-4xl font-bold text-[#1B2A4A]"
                        style="font-family: Georgia, serif"
                    >
                        Gallery
                    </h2>
                </div>
                <a
                    href="/gallery"
                    class="inline-flex items-center gap-2 text-sm font-semibold text-[#1B2A4A] border-b-2 border-[#C9A84C] pb-0.5 hover:text-[#C9A84C] transition-colors self-start"
                >
                    View Full Gallery →
                </a>
            </div>

            <!-- Bento-style rounded grid -->
            <div
                class="grid grid-cols-2 md:grid-cols-4 gap-4 auto-rows-[180px]"
            >
                <div
                    v-for="(item, i) in galleryItems"
                    :key="i"
                    class="rounded-3xl overflow-hidden group cursor-pointer relative bg-[#1B2A4A]/5"
                    :class="item.span"
                >
                    <!-- <img :src="item.src" :alt="item.caption"
            class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500"
            @error="e => e.target.style.opacity='0'" /> -->
                    <!-- Caption overlay -->
                    <div
                        class="absolute inset-0 bg-gradient-to-t from-[#1B2A4A]/70 via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-all duration-300 flex items-end p-4"
                    >
                        <span
                            class="text-white text-sm font-semibold translate-y-2 group-hover:translate-y-0 transition-transform duration-300"
                        >
                            {{ item.caption }}
                        </span>
                    </div>
                    <!-- Empty state placeholder pattern -->
                    <div
                        class="absolute inset-0 flex items-center justify-center opacity-20 pointer-events-none"
                    >
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            class="h-10 w-10 text-[#1B2A4A]"
                            fill="none"
                            viewBox="0 0 24 24"
                            stroke="currentColor"
                        >
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="1"
                                d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z"
                            />
                        </svg>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
const galleryItems = [
    {
        src: "/images/gallery-1.jpg",
        caption: "Forensic Laboratory",
        span: "md:col-span-2 md:row-span-2",
    },
    { src: "/images/gallery-2.jpg", caption: "DNA Analysis Lab", span: "" },
    {
        src: "/images/gallery-3.jpg",
        caption: "Digital Forensics Lab",
        span: "",
    },
    { src: "/images/gallery-4.jpg", caption: "Toxicology Lab", span: "" },
    { src: "/images/gallery-5.jpg", caption: "Convocation 2024", span: "" },
    {
        src: "/images/gallery-6.jpg",
        caption: "National Symposium",
        span: "md:col-span-2",
    },
];
</script>
