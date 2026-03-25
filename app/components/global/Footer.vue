<template>
    <div>
        <!-- Contact Section -->
        <section class="py-24 bg-[#F5F4F0] px-8">
            <div class="max-w-7xl mx-auto">
                <div class="text-center mb-14">
                    <div
                        class="inline-flex items-center gap-2 bg-white rounded-full px-4 py-1.5 mb-4 shadow-sm border border-gray-100"
                    >
                        <span
                            class="text-xs font-bold text-[#1B2A4A] tracking-wide uppercase"
                            >Get in Touch</span
                        >
                    </div>
                    <h2
                        class="text-4xl font-bold text-[#1B2A4A]"
                        style="font-family: Georgia, serif"
                    >
                        Contact Us
                    </h2>
                </div>

                <div class="grid lg:grid-cols-3 gap-6">
                    <!-- Info cards -->
                    <div class="flex flex-col gap-4">
                        <div
                            v-for="info in contactInfo"
                            :key="info.label"
                            class="bg-white rounded-3xl p-6 border border-gray-100 hover:shadow-md transition-all duration-300 flex items-start gap-4"
                        >
                            <div
                                class="w-11 h-11 rounded-2xl bg-[#1B2A4A]/5 flex items-center justify-center shrink-0"
                            >
                                <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    class="h-5 w-5 text-[#1B2A4A]"
                                    fill="none"
                                    viewBox="0 0 24 24"
                                    stroke="currentColor"
                                >
                                    <path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        stroke-width="1.8"
                                        :d="info.icon"
                                    />
                                </svg>
                            </div>
                            <div>
                                <p
                                    class="text-[10px] font-bold text-gray-400 uppercase tracking-wider mb-1"
                                >
                                    {{ info.label }}
                                </p>
                                <p
                                    class="text-[#1B2A4A] text-sm font-medium leading-relaxed"
                                >
                                    {{ info.value }}
                                </p>
                            </div>
                        </div>
                    </div>

                    <!-- Contact form card -->
                    <div
                        class="lg:col-span-2 bg-white rounded-3xl p-8 border border-gray-100 shadow-sm"
                    >
                        <h3
                            class="font-bold text-[#1B2A4A] text-xl mb-6"
                            style="font-family: Georgia, serif"
                        >
                            Send us a Message
                        </h3>
                        <div class="flex flex-col gap-4">
                            <div class="grid grid-cols-2 gap-4">
                                <div>
                                    <label
                                        class="text-xs font-bold text-gray-400 uppercase tracking-wider block mb-1.5"
                                        >Name</label
                                    >
                                    <input
                                        v-model="form.name"
                                        type="text"
                                        placeholder="Your full name"
                                        class="w-full bg-[#F5F4F0] rounded-xl px-4 py-3 text-sm text-[#1B2A4A] placeholder-gray-400 border border-transparent focus:outline-none focus:border-[#C9A84C] transition-colors"
                                    />
                                </div>
                                <div>
                                    <label
                                        class="text-xs font-bold text-gray-400 uppercase tracking-wider block mb-1.5"
                                        >Phone</label
                                    >
                                    <input
                                        v-model="form.phone"
                                        type="tel"
                                        placeholder="+91 XXXXX XXXXX"
                                        class="w-full bg-[#F5F4F0] rounded-xl px-4 py-3 text-sm text-[#1B2A4A] placeholder-gray-400 border border-transparent focus:outline-none focus:border-[#C9A84C] transition-colors"
                                    />
                                </div>
                            </div>
                            <div>
                                <label
                                    class="text-xs font-bold text-gray-400 uppercase tracking-wider block mb-1.5"
                                    >Email</label
                                >
                                <input
                                    v-model="form.email"
                                    type="email"
                                    placeholder="your@email.com"
                                    class="w-full bg-[#F5F4F0] rounded-xl px-4 py-3 text-sm text-[#1B2A4A] placeholder-gray-400 border border-transparent focus:outline-none focus:border-[#C9A84C] transition-colors"
                                />
                            </div>
                            <div>
                                <label
                                    class="text-xs font-bold text-gray-400 uppercase tracking-wider block mb-1.5"
                                    >Subject</label
                                >
                                <select
                                    v-model="form.subject"
                                    class="w-full bg-[#F5F4F0] rounded-xl px-4 py-3 text-sm text-[#1B2A4A] border border-transparent focus:outline-none focus:border-[#C9A84C] transition-colors"
                                >
                                    <option value="">Select a subject</option>
                                    <option>Admission Inquiry</option>
                                    <option>Research Collaboration</option>
                                    <option>Casework Support</option>
                                    <option>General Inquiry</option>
                                </select>
                            </div>
                            <div>
                                <label
                                    class="text-xs font-bold text-gray-400 uppercase tracking-wider block mb-1.5"
                                    >Message</label
                                >
                                <textarea
                                    v-model="form.message"
                                    rows="4"
                                    placeholder="Write your message here..."
                                    class="w-full bg-[#F5F4F0] rounded-xl px-4 py-3 text-sm text-[#1B2A4A] placeholder-gray-400 border border-transparent focus:outline-none focus:border-[#C9A84C] transition-colors resize-none"
                                ></textarea>
                            </div>
                            <button
                                @click="submitForm"
                                class="w-full bg-[#1B2A4A] text-white rounded-full py-3.5 font-bold text-sm hover:bg-[#243560] transition-all duration-200 shadow-lg shadow-[#1B2A4A]/20"
                            >
                                Send Message →
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

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
