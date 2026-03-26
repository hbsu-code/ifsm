<template>
    <footer class="bg-[#1B2A4A] text-white pt-16 pb-8 mt-auto overflow-hidden">
        <div class="max-w-7xl mx-auto px-8">
            <div
                class="grid md:grid-cols-4 gap-12 pb-12 border-b border-white/10"
            >
                <div class="md:col-span-2 space-y-6">
                    <div class="flex items-center gap-4">
                        <div
                            class="w-14 h-14 rounded-2xl bg-white/10 flex items-center justify-center p-1 overflow-hidden"
                        >
                            <img
                                src="/logo.png"
                                alt="IFSM Logo"
                                class="h-10 w-auto object-contain brightness-0 invert"
                            />
                        </div>
                        <div>
                            <p
                                class="text-[#C9A84C] text-[10px] font-black tracking-[0.2em] uppercase mb-1"
                            >
                                Govt. of Maharashtra
                            </p>
                            <h4
                                class="text-white font-bold text-lg leading-tight tracking-tight"
                                style="font-family: &quot;Georgia&quot;, serif"
                            >
                                Institute of Forensic Science, Mumbai
                            </h4>
                        </div>
                    </div>
                    <p class="text-white/40 text-sm leading-relaxed max-w-sm">
                        Dedicated to excellence in forensic science education,
                        research, and supporting the criminal justice system of
                        Maharashtra and India since 1971.
                    </p>
                </div>

                <div>
                    <h5
                        class="text-[#C9A84C] text-xs font-black uppercase tracking-widest mb-6"
                    >
                        Quick Links
                    </h5>
                    <ul class="flex flex-col gap-3">
                        <li v-for="link in quickLinks" :key="link.label">
                            <a
                                :href="link.href"
                                class="text-white/50 text-[13px] hover:text-[#C9A84C] transition-all flex items-center gap-2 group"
                            >
                                <span
                                    class="text-[#C9A84C] opacity-0 group-hover:opacity-100 transition-all"
                                    >-</span
                                >
                                {{ link.label }}
                            </a>
                        </li>
                    </ul>
                </div>

                <div>
                    <h5
                        class="text-[#C9A84C] text-xs font-black uppercase tracking-widest mb-6"
                    >
                        Important Links
                    </h5>
                    <ul class="flex flex-col gap-3">
                        <li v-for="link in importantLinks" :key="link.label">
                            <a
                                :href="link.href"
                                target="_blank"
                                class="text-white/50 text-[13px] hover:text-[#C9A84C] transition-all flex items-center gap-2 group"
                            >
                                <span
                                    class="text-[#C9A84C] opacity-0 group-hover:opacity-100 transition-all"
                                    >-</span
                                >
                                {{ link.label }}
                            </a>
                        </li>
                    </ul>
                </div>
            </div>

            <div
                class="pt-8 flex flex-col md:flex-row items-center justify-between gap-4 text-[11px] text-white/30 font-medium"
            >
                <div class="flex items-center gap-2">
                    <span
                        >© {{ new Date().getFullYear() }} Institute of Forensic
                        Science, Mumbai.</span
                    >
                    <span class="hidden md:inline text-white/10">|</span>
                    <span>All Rights Reserved.</span>
                </div>
                <div class="flex items-center gap-4">
                    <span
                        class="hover:text-white/60 cursor-default transition-colors"
                        >Privacy Policy</span
                    >
                    <span
                        class="hover:text-white/60 cursor-default transition-colors"
                        >Terms of Use</span
                    >
                    <span
                        class="bg-white/5 px-3 py-1 rounded-full text-white/50"
                        >Designed for Govt. of Maharashtra</span
                    >
                </div>
            </div>
        </div>
    </footer>
</template>

<script setup>
const quickLinks = [
    { label: "About the Institute", href: "/about" },
    { label: "Academic Programmes", href: "/academics" },
    { label: "Admissions", href: "/admissions" },
    { label: "Faculty & Staff", href: "/faculty" },
    { label: "Research", href: "/research" },
    { label: "News & Events", href: "/news" },
];

const importantLinks = [
    { label: "Maharashtra Government", href: "https://www.maharashtra.gov.in" },
    { label: "UGC", href: "https://www.ugc.ac.in" },
    { label: "NAAC", href: "https://naac.gov.in" },
    { label: "RTI Portal", href: "#" },
    { label: "Grievance Redressal", href: "#" },
    { label: "Anti-Ragging Cell", href: "#" },
];
</script>

<style scoped>
footer {
    /* Ensures footer doesn't create horizontal scroll on small screens */
    width: 100%;
    overflow-x: hidden;
}
</style>
