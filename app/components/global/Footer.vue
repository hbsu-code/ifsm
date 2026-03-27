<template>
    <footer class="bg-[#1B2A4A] text-white pt-16 pb-8 mt-auto overflow-hidden">
        <div class="max-w-7xl mx-auto px-8">
            <div
                class="grid md:grid-cols-4 gap-12 pb-12 border-b border-white/10"
            >
                <!-- Brand -->
                <div class="md:col-span-1 space-y-6">
                    <div class="flex items-center gap-4">
                        <div
                            class="w-14 h-14 rounded-2xl bg-white/10 flex items-center justify-center p-1 overflow-hidden"
                        >
                            <img
                                src="/logo.png"
                                alt="IFS Mumbai Logo"
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
                                class="text-white font-bold text-base leading-tight tracking-tight"
                                style="font-family: &quot;Georgia&quot;, serif"
                            >
                                Institute of Forensic Science, Mumbai
                            </h4>
                        </div>
                    </div>
                    <p class="text-white/40 text-sm leading-relaxed">
                        Dedicated to excellence in forensic science education,
                        research, and supporting the criminal justice system of
                        Maharashtra and India since 1971.
                    </p>
                    <!-- Top bar links -->
                    <div class="flex gap-3">
                        <a
                            v-for="link in topLinks"
                            :key="link.label"
                            :href="link.href"
                            class="text-[10px] font-black uppercase tracking-widest text-white/30 hover:text-[#C9A84C] transition-colors border border-white/10 hover:border-[#C9A84C]/40 rounded-full px-3 py-1"
                        >
                            {{ link.label }}
                        </a>
                    </div>
                </div>

                <!-- Quick Links -->
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
                                    >—</span
                                >
                                {{ link.label }}
                            </a>
                        </li>
                    </ul>
                </div>

                <!-- Academics -->
                <div>
                    <h5
                        class="text-[#C9A84C] text-xs font-black uppercase tracking-widest mb-6"
                    >
                        Academics
                    </h5>
                    <ul class="flex flex-col gap-3">
                        <li v-for="link in academicLinks" :key="link.label">
                            <a
                                :href="link.href"
                                class="text-white/50 text-[13px] hover:text-[#C9A84C] transition-all flex items-center gap-2 group"
                            >
                                <span
                                    class="text-[#C9A84C] opacity-0 group-hover:opacity-100 transition-all"
                                    >—</span
                                >
                                {{ link.label }}
                            </a>
                        </li>
                    </ul>
                </div>

                <!-- Important Links -->
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
                                :target="link.external ? '_blank' : undefined"
                                :rel="
                                    link.external
                                        ? 'noopener noreferrer'
                                        : undefined
                                "
                                class="text-white/50 text-[13px] hover:text-[#C9A84C] transition-all flex items-center gap-2 group"
                            >
                                <span
                                    class="text-[#C9A84C] opacity-0 group-hover:opacity-100 transition-all"
                                    >—</span
                                >
                                {{ link.label }}
                                <svg
                                    v-if="link.external"
                                    class="w-2.5 h-2.5 opacity-40"
                                    viewBox="0 0 10 10"
                                    fill="none"
                                    stroke="currentColor"
                                    stroke-width="1.5"
                                >
                                    <path d="M1 9 9 1M4 1h5v5" />
                                </svg>
                            </a>
                        </li>
                    </ul>
                </div>
            </div>

            <!-- Bottom bar -->
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
                    <a
                        href="/privacy-policy"
                        class="hover:text-white/60 transition-colors"
                        >Privacy Policy</a
                    >
                    <a
                        href="/terms-of-use"
                        class="hover:text-white/60 transition-colors"
                        >Terms of Use</a
                    >
                    <a
                        href="/sitemap"
                        class="hover:text-white/60 transition-colors"
                        >Sitemap</a
                    >
                    <span
                        class="bg-white/5 px-3 py-1 rounded-full text-white/50"
                    >
                        Designed for Govt. of Maharashtra
                    </span>
                </div>
            </div>
        </div>
    </footer>
</template>

<script setup>
// Matches Header.vue topLinks
const topLinks = [
    { label: "RTI", href: "/rti" },
    { label: "Tenders", href: "/tenders" },
    { label: "Sitemap", href: "/sitemap" },
];

// Primary site pages from navItems
const quickLinks = [
    { label: "Home", href: "/" },
    { label: "About Us", href: "/about-us" },
    { label: "Administration", href: "/administration" },
    { label: "Admissions", href: "/admissions/admission-information" },
    { label: "Examination", href: "/examination" },
    { label: "Downloads", href: "/downloads" },
    { label: "NAAC", href: "/naac" },
    { label: "IQAC", href: "/iqac" },
];

// Courses + Departments + Students Corner highlights
const academicLinks = [
    { label: "B.Sc. Forensic", href: "/course/bsc-forensic" },
    { label: "M.Sc. Forensic", href: "/course/msc-forensic" },
    { label: "P.G. Diploma", href: "/course/pg-diploma" },
    { label: "Department – Forensic", href: "/department/forensic" },
    { label: "Department – IT", href: "/department/it" },
    { label: "Students Corner", href: "/students-corner" },
    { label: "Time Table", href: "/students-corner/time-table" },
    {
        label: "Grievance Redressal",
        href: "/students-corner/grievance-redressal",
    },
];

// External + internal compliance/support links
const importantLinks = [
    {
        label: "Maharashtra Government",
        href: "https://www.maharashtra.gov.in",
        external: true,
    },
    { label: "UGC", href: "https://www.ugc.ac.in", external: true },
    { label: "NAAC", href: "https://naac.gov.in", external: true },
    { label: "RTI Portal", href: "/rti" },
    {
        label: "Grievance Redressal",
        href: "/students-corner/grievance-redressal",
    },
    {
        label: "Anti-Ragging Cell",
        href: "/students-corner/cell-and-center/anti-ragging-cell",
    },
    {
        label: "Placement Cell",
        href: "/students-corner/cell-and-center/placement-cell",
    },
    { label: "Scholarships", href: "/students-corner/scholarships" },
];
</script>

<style scoped>
footer {
    width: 100%;
    overflow-x: hidden;
}
</style>
