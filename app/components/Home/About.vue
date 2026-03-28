<template>
    <div class="min-h-screen bg-[#F5F4F0] w-full font-sans text-slate-800">
        <div class="max-w-7xl mx-auto px-6 py-20">
            <!-- HEADER -->
            <header class="mb-20">
                <h1
                    class="text-5xl md:text-6xl font-black text-[#1f3a6d] leading-tight"
                >
                    Faculty <span class="text-[#C8A84B]">Directory</span>
                </h1>
                <p class="text-slate-500 max-w-2xl mt-4 text-lg">
                    Expert educators and forensic specialists dedicated to
                    academic excellence.
                </p>
            </header>

            <!-- FACULTY GRID -->
            <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-10 mb-28">
                <div
                    v-for="member in faculty"
                    :key="member.name"
                    class="group relative bg-white rounded-[2rem] overflow-hidden shadow-md hover:shadow-2xl transition-all duration-500"
                >
                    <!-- IMAGE -->
                    <div class="aspect-square overflow-hidden">
                        <img
                            src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2"
                            class="w-full h-full object-cover group-hover:scale-110 transition duration-700"
                        />
                    </div>

                    <!-- OVERLAY -->
                    <div
                        class="absolute inset-0 bg-gradient-to-t from-[#1f3a6d]/80 via-transparent to-transparent opacity-0 group-hover:opacity-100 transition"
                    ></div>

                    <!-- CONTENT -->
                    <div class="p-6 relative">
                        <h3 class="text-xl font-bold text-[#1f3a6d]">
                            {{ member.name }}
                        </h3>

                        <p
                            class="text-[#C8A84B] text-xs font-bold uppercase tracking-widest mt-1"
                        >
                            {{ member.designation }}
                        </p>

                        <p class="text-sm text-slate-500 mt-3 leading-relaxed">
                            {{ member.specialization }}
                        </p>
                    </div>
                </div>
            </div>

            <!-- TABLE -->
            <div
                class="bg-white rounded-[2rem] shadow-lg border border-slate-100 mb-28 overflow-hidden"
            >
                <div
                    class="p-8 border-b bg-slate-50 flex justify-between items-center"
                >
                    <h2 class="text-2xl font-bold text-[#1f3a6d]">
                        Examination Schedule
                    </h2>
                    <span class="text-sm text-slate-400">Updated 2026</span>
                </div>

                <div class="overflow-x-auto">
                    <table class="w-full min-w-[800px]">
                        <thead class="bg-[#1f3a6d] text-white sticky top-0">
                            <tr>
                                <th class="py-4 px-6 text-xs uppercase">#</th>
                                <th class="py-4 px-6 text-xs uppercase">
                                    Programme
                                </th>
                                <th class="py-4 px-6 text-xs uppercase">
                                    Eligibility
                                </th>
                                <th
                                    class="py-4 px-6 text-xs uppercase text-center"
                                >
                                    Seats
                                </th>
                            </tr>
                        </thead>

                        <tbody>
                            <tr
                                v-for="i in 5"
                                :key="i"
                                class="border-b hover:bg-slate-50 transition"
                            >
                                <td class="py-5 px-6 text-slate-300 font-bold">
                                    0{{ i }}
                                </td>

                                <td
                                    class="py-5 px-6 font-semibold text-[#1f3a6d]"
                                >
                                    B.Sc. Forensic Science
                                </td>

                                <td class="py-5 px-6 text-slate-600">
                                    HSC in Science Stream
                                </td>

                                <td class="py-5 px-6 text-center">
                                    <span
                                        class="bg-[#C8A84B]/10 text-[#C8A84B] px-4 py-1 rounded-full font-bold text-xs"
                                    >
                                        50
                                    </span>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>

            <!-- CTA -->
            <div
                class="relative bg-[#1f3a6d] rounded-[3rem] p-16 text-center text-white overflow-hidden shadow-2xl"
            >
                <!-- Glow Effects -->
                <div
                    class="absolute top-0 right-0 w-72 h-72 bg-white/5 rounded-full blur-3xl"
                ></div>
                <div
                    class="absolute bottom-0 left-0 w-72 h-72 bg-[#C8A84B]/10 rounded-full blur-3xl"
                ></div>

                <div class="relative z-10">
                    <h3 class="text-4xl font-black mb-6">Ready to apply?</h3>

                    <p class="text-blue-100/80 max-w-xl mx-auto mb-10">
                        Admissions for 2026 will begin after HSC results. Stay
                        updated and secure your future.
                    </p>

                    <button
                        class="bg-[#C8A84B] hover:bg-[#b8983d] px-10 py-4 rounded-2xl font-bold tracking-widest transition transform hover:scale-105"
                    >
                        Download Prospectus
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const faculty = [
    {
        name: "Dr. Sunil Yadav",
        designation: "Assistant Professor",
        specialization: "Cyber Forensics",
    },
    {
        name: "Ms. Neha Kharat",
        designation: "Visiting Faculty",
        specialization: "Psychology",
    },
    {
        name: "Feba Santhosh",
        designation: "Professor",
        specialization: "Toxicology",
    },
];
</script>
