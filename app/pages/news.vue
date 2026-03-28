<template>
    <div
        class="min-h-screen bg-[#F5F4F0] px-6 py-20 flex flex-col items-center"
    >
        <!-- TITLE -->
        <h1
            class="text-4xl md:text-5xl font-serif italic text-[#1f3a6d] text-center"
        >
            News, Circulars & Events
        </h1>

        <div class="w-28 h-[2px] bg-[#C8A84B] mt-4 mb-12"></div>

        <!-- NEWS LIST -->
        <div class="w-full max-w-2xl space-y-4">
            <div
                v-for="(item, i) in news"
                :key="i"
                class="bg-white px-6 py-4 rounded-xl border border-slate-100 flex justify-between items-center"
            >
                <div>
                    <p class="text-[#1f3a6d] font-medium">
                        {{ item.text }}
                    </p>
                    <p class="text-xs text-slate-400 mt-1">
                        {{ item.date }}
                    </p>
                </div>

                <span
                    v-if="item.new"
                    class="text-xs bg-red-500 text-white px-2 py-1 rounded"
                >
                    New
                </span>
            </div>
        </div>
    </div>
</template>

<script setup>
const news = [
    {
        text: "23_Admission_PGD_DCFRL",
        date: "March 2026",
        new: true,
    },
    {
        text: "23_Admission_PGD_FSRL",
        date: "March 2026",
        new: true,
    },
    {
        text: "Cyber Forensics Workshop",
        date: "Feb 2026",
        new: false,
    },
    {
        text: "Annual Conference 2026",
        date: "Jan 2026",
        new: false,
    },
];
</script>
