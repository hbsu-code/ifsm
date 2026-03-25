<template>
    <section class="py-24 bg-[#F5F4F0] px-8">
        <div class="max-w-7xl mx-auto">
            <div
                class="flex flex-col md:flex-row md:items-end justify-between gap-4 mb-12"
            >
                <div>
                    <div
                        class="inline-flex items-center gap-2 bg-white rounded-full px-4 py-1.5 mb-4 shadow-sm border border-gray-100"
                    >
                        <span
                            class="text-xs font-bold text-[#1B2A4A] tracking-wide uppercase"
                            >Our Team</span
                        >
                    </div>
                    <h2
                        class="text-4xl font-bold text-[#1B2A4A]"
                        style="font-family: Georgia, serif"
                    >
                        Faculty Highlights
                    </h2>
                </div>
                <a
                    href="/faculty"
                    class="inline-flex items-center gap-2 text-sm font-semibold text-[#1B2A4A] border-b-2 border-[#C9A84C] pb-0.5 hover:text-[#C9A84C] transition-colors self-start"
                >
                    Meet All Faculty →
                </a>
            </div>

            <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-5">
                <div
                    v-for="member in faculty"
                    :key="member.name"
                    class="bg-white rounded-3xl overflow-hidden border border-gray-100 hover:shadow-lg hover:-translate-y-1 transition-all duration-300 group"
                >
                    <!-- Photo -->
                    <div class="h-52 bg-[#1B2A4A]/5 relative overflow-hidden">
                        <!-- <img
                            :src="member.photo"
                            :alt="member.name"
                            class="w-full h-full object-cover object-top group-hover:scale-105 transition-transform duration-500"
                            @error="onImgError($event, member.name)"
                        /> -->
                        <!-- Avatar fallback (hidden by default) -->
                        <div
                            class="fallback hidden absolute inset-0 items-center justify-center bg-gradient-to-br from-[#1B2A4A] to-[#243560]"
                        >
                            <span
                                class="text-4xl font-bold text-white/30"
                                style="font-family: Georgia, serif"
                            >
                                {{
                                    member.name
                                        .split(" ")
                                        .map((n) => n[0])
                                        .join("")
                                        .slice(0, 2)
                                }}
                            </span>
                        </div>
                    </div>

                    <div class="p-5">
                        <div
                            class="w-6 h-0.5 bg-[#C9A84C] mb-3 group-hover:w-10 transition-all duration-300"
                        ></div>
                        <h3
                            class="font-bold text-[#1B2A4A] text-base leading-snug"
                        >
                            {{ member.name }}
                        </h3>
                        <p
                            class="text-[#C9A84C] text-xs font-semibold mt-1 mb-2"
                        >
                            {{ member.designation }}
                        </p>
                        <p class="text-gray-400 text-xs leading-relaxed">
                            {{ member.specialisation }}
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
const faculty = [
    {
        name: "Dr. Rajesh Sharma",
        designation: "Director & Professor",
        specialisation: "DNA Forensics, Molecular Biology, Forensic Genetics",
        photo: "/images/faculty-1.jpg",
    },
    {
        name: "Dr. Priya Mehta",
        designation: "Head — Toxicology",
        specialisation: "Forensic Toxicology, Drug Analysis, Poison Studies",
        photo: "/images/faculty-2.jpg",
    },
    {
        name: "Dr. Anil Patil",
        designation: "Associate Professor",
        specialisation:
            "Questioned Documents, Handwriting Analysis, Fingerprints",
        photo: "/images/faculty-3.jpg",
    },
    {
        name: "Dr. Sunita Desai",
        designation: "Assistant Professor",
        specialisation: "Digital Forensics, Cyber Crime, OSINT",
        photo: "/images/faculty-4.jpg",
    },
];

const onImgError = (e, name) => {
    e.target.style.display = "none";
    const fallback = e.target.nextElementSibling;
    if (fallback) {
        fallback.classList.remove("hidden");
        fallback.classList.add("flex");
    }
};
</script>
