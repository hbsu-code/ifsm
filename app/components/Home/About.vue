<template>
    <div
        class="min-h-screen bg-[#F5F4F0] w-full font-sans antialiased text-slate-800"
    >
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16 md:py-24">
            <header class="mb-16 text-center md:text-left">
                <h1
                    class="text-4xl md:text-6xl font-black text-[#1f3a6d] tracking-tight mb-4"
                >
                    Faculty <span class="text-[#C8A84B]">Directory</span>
                </h1>
                <p class="text-slate-500 max-w-2xl text-lg leading-relaxed">
                    Expert educators and forensic specialists dedicated to
                    academic excellence.
                </p>
            </header>

            <div
                class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 w-full mb-24"
            >
                <div
                    v-for="member in faculty"
                    :key="member.name"
                    class="group bg-white rounded-[2rem] border border-slate-100 shadow-sm hover:shadow-xl hover:-translate-y-1 transition-all duration-300 overflow-hidden"
                >
                    <div
                        class="aspect-square bg-slate-100 overflow-hidden relative"
                    >
                        <div
                            class="absolute inset-0 bg-[#1f3a6d]/5 group-hover:bg-transparent transition-colors"
                        ></div>
                    </div>

                    <div class="p-8">
                        <h3 class="text-xl font-bold text-[#1f3a6d] mb-1">
                            {{ member.name }}
                        </h3>
                        <p
                            class="text-[#C8A84B] font-bold text-xs uppercase tracking-widest mb-4"
                        >
                            {{ member.designation }}
                        </p>
                        <p
                            class="text-slate-500 text-sm leading-relaxed line-clamp-2 italic"
                        >
                            Specialization: {{ member.specialization }}
                        </p>
                    </div>
                </div>
            </div>

            <div
                class="bg-white rounded-[2.5rem] shadow-xl shadow-slate-200/50 border border-slate-100 overflow-hidden mb-24"
            >
                <div
                    class="p-8 md:p-12 border-b border-slate-50 bg-slate-50/30"
                >
                    <h2 class="text-2xl font-bold text-[#1f3a6d]">
                        Examination Schedule
                    </h2>
                </div>

                <div class="max-w-full">
                    <table
                        class="w-full text-left border-collapse min-w-[800px]"
                    >
                        <thead class="bg-[#1f3a6d] text-white">
                            <tr>
                                <th
                                    class="py-5 px-8 text-xs font-bold uppercase tracking-wider"
                                >
                                    Sr. No.
                                </th>
                                <th
                                    class="py-5 px-8 text-xs font-bold uppercase tracking-wider"
                                >
                                    Programme
                                </th>
                                <th
                                    class="py-5 px-8 text-xs font-bold uppercase tracking-wider"
                                >
                                    Eligibility
                                </th>
                                <th
                                    class="py-5 px-8 text-xs font-bold uppercase tracking-wider text-center"
                                >
                                    Capacity
                                </th>
                            </tr>
                        </thead>
                        <tbody class="divide-y divide-slate-100">
                            <tr
                                v-for="i in 3"
                                :key="i"
                                class="hover:bg-slate-50 transition-colors"
                            >
                                <td
                                    class="py-6 px-8 text-sm font-bold text-slate-300"
                                >
                                    0{{ i }}
                                </td>
                                <td class="py-6 px-8 font-bold text-[#1f3a6d]">
                                    B.Sc. Forensic Science
                                </td>
                                <td class="py-6 px-8 text-sm text-slate-600">
                                    HSC in Science Stream
                                </td>
                                <td class="py-6 px-8 text-center">
                                    <span
                                        class="px-4 py-1.5 bg-slate-100 rounded-full text-xs font-black"
                                        >50</span
                                    >
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>

            <div
                class="bg-[#1f3a6d] p-10 md:p-20 rounded-[3rem] text-center relative overflow-hidden shadow-2xl"
            >
                <div
                    class="absolute -right-20 -top-20 w-64 h-64 bg-white/5 rounded-full pointer-events-none"
                ></div>
                <div
                    class="absolute -left-20 -bottom-20 w-64 h-64 bg-[#C8A84B]/10 rounded-full pointer-events-none"
                ></div>

                <div class="relative z-10">
                    <h3 class="text-3xl md:text-4xl font-black text-white mb-6">
                        Ready to apply?
                    </h3>
                    <p
                        class="text-blue-100/70 mb-10 max-w-xl mx-auto leading-relaxed"
                    >
                        The admission notification for the 2026 academic year
                        will be released following the HSC results.
                    </p>
                    <button
                        class="bg-[#C8A84B] hover:bg-[#b8983d] text-white px-10 py-4 rounded-2xl font-bold uppercase tracking-widest transition-all shadow-lg active:scale-95"
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
