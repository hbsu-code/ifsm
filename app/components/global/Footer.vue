<template>
    <div>
        <!-- Footer -->
        <footer class="bg-[#1B2A4A] text-white px-8 pt-16 pb-8">
            <div class="max-w-7xl mx-auto">
                <div
                    class="grid md:grid-cols-4 gap-10 pb-12 border-b border-white/10"
                >
                    <!-- Brand -->
                    <div class="md:col-span-2">
                        <div class="flex items-center gap-4 mb-5">
                            <div
                                class="w-14 h-14 rounded-2xl bg-white/10 flex items-center justify-center p-1"
                            >
                                <!-- <img src="/logo.png" alt="IFSM Logo" class="h-12 w-auto object-contain" /> -->
                            </div>
                            <div>
                                <p
                                    class="text-[#C9A84C] text-[10px] font-bold tracking-widest uppercase"
                                >
                                    Govt. of Maharashtra
                                </p>
                                <h4
                                    class="text-white font-bold text-base leading-tight"
                                    style="font-family: Georgia, serif"
                                >
                                    Institute of Forensic Science, Mumbai
                                </h4>
                            </div>
                        </div>
                        <p
                            class="text-white/40 text-xs leading-relaxed max-w-sm"
                        >
                            Dedicated to excellence in forensic science
                            education, research, and supporting the criminal
                            justice system of Maharashtra and India since 1971.
                        </p>
                    </div>

                    <div>
                        <h5
                            class="text-[#C9A84C] text-xs font-bold uppercase tracking-wider mb-5"
                        >
                            Quick Links
                        </h5>
                        <ul class="flex flex-col gap-2.5">
                            <li v-for="link in quickLinks" :key="link.label">
                                <a
                                    :href="link.href"
                                    class="text-white/50 text-xs hover:text-white transition-colors flex items-center gap-1.5"
                                >
                                    <span class="text-[#C9A84C] text-xs"
                                        >›</span
                                    >
                                    {{ link.label }}
                                </a>
                            </li>
                        </ul>
                    </div>

                    <div>
                        <h5
                            class="text-[#C9A84C] text-xs font-bold uppercase tracking-wider mb-5"
                        >
                            Important Links
                        </h5>
                        <ul class="flex flex-col gap-2.5">
                            <li
                                v-for="link in importantLinks"
                                :key="link.label"
                            >
                                <a
                                    :href="link.href"
                                    class="text-white/50 text-xs hover:text-white transition-colors flex items-center gap-1.5"
                                >
                                    <span class="text-[#C9A84C] text-xs"
                                        >›</span
                                    >
                                    {{ link.label }}
                                </a>
                            </li>
                        </ul>
                    </div>
                </div>

                <div
                    class="pt-6 flex flex-wrap items-center justify-between gap-2 text-xs text-white/30"
                >
                    <span
                        >© {{ new Date().getFullYear() }} Institute of Forensic
                        Science, Mumbai. All Rights Reserved.</span
                    >
                    <span>Designed for Government of Maharashtra</span>
                </div>
            </div>
        </footer>
    </div>
</template>

<script setup>
import { ref } from "vue";

const form = ref({ name: "", phone: "", email: "", subject: "", message: "" });
const submitForm = () => {
    alert("Thank you! Your message has been sent.");
    form.value = { name: "", phone: "", email: "", subject: "", message: "" };
};

const contactInfo = [
    {
        label: "Address",
        value: "Near Vidyanagari Campus, Santacruz (E), Mumbai – 400 098",
        icon: "M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z M15 11a3 3 0 11-6 0 3 3 0 016 0z",
    },
    {
        label: "Phone",
        value: "+91 22 2652 XXXX",
        icon: "M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z",
    },
    {
        label: "Email",
        value: "director@ifsm.gov.in",
        icon: "M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z",
    },
];

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
