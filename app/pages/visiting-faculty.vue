<template>
    <div
        class="min-h-screen bg-[#f8fafc] py-16 px-4 sm:px-8 lg:px-12 font-sans antialiased"
    >
        <div class="max-w-7xl mx-auto">
            <div class="mb-12">
                <h1
                    class="text-3xl md:text-4xl font-extrabold text-[#1f3a6d] flex items-center gap-4"
                >
                    <span class="w-2 h-10 bg-[#C8A84B] rounded-full"></span>
                    Visiting Faculty
                </h1>
                <p class="mt-4 text-slate-500 max-w-2xl leading-relaxed">
                    Our visiting faculty members bring specialized industry
                    expertise and academic excellence from various forensic and
                    scientific domains across the globe.
                </p>
            </div>

            <div
                class="bg-white rounded-3xl shadow-xl shadow-slate-200/50 border border-slate-100 overflow-hidden"
            >
                <div class="">
                    <table class="w-full text-left border-collapse">
                        <thead>
                            <tr class="bg-[#1f3a6d] text-white">
                                <th
                                    class="py-5 px-6 text-xs font-bold uppercase tracking-wider w-16"
                                >
                                    Sr. No.
                                </th>
                                <th
                                    class="py-5 px-6 text-xs font-bold uppercase tracking-wider"
                                >
                                    Faculty Name
                                </th>
                                <th
                                    class="py-5 px-6 text-xs font-bold uppercase tracking-wider"
                                >
                                    Qualification
                                </th>
                                <th
                                    class="py-5 px-6 text-xs font-bold uppercase tracking-wider"
                                >
                                    Department
                                </th>
                                <th
                                    class="py-5 px-6 text-xs font-bold uppercase tracking-wider"
                                >
                                    Specialization
                                </th>
                                <th
                                    class="py-5 px-6 text-xs font-bold uppercase tracking-wider text-center"
                                >
                                    Resume
                                </th>
                            </tr>
                        </thead>
                        <tbody class="divide-y divide-slate-100">
                            <tr
                                v-for="(faculty, index) in facultyList"
                                :key="index"
                                class="hover:bg-slate-50/80 transition-colors group"
                            >
                                <td
                                    class="py-6 px-6 text-sm font-medium text-slate-400"
                                >
                                    {{ index + 1 }}
                                </td>

                                <td class="py-6 px-6">
                                    <div
                                        class="text-[15px] font-bold text-[#1f3a6d] group-hover:text-[#C8A84B] transition-colors"
                                    >
                                        {{ faculty.name }}
                                    </div>
                                </td>

                                <td class="py-6 px-6 text-sm text-slate-600">
                                    <span
                                        class="bg-slate-100 px-3 py-1 rounded-lg text-xs font-semibold"
                                    >
                                        {{ faculty.qualification }}
                                    </span>
                                </td>

                                <td
                                    class="py-6 px-6 text-sm text-slate-600 font-medium"
                                >
                                    {{ faculty.department }}
                                </td>

                                <td class="py-6 px-6">
                                    <div class="flex flex-wrap gap-2">
                                        <span
                                            v-for="spec in splitSpecs(
                                                faculty.specialization,
                                            )"
                                            :key="spec"
                                            class="text-[13px] text-slate-500 italic"
                                        >
                                            {{ spec
                                            }}{{
                                                isLast(
                                                    spec,
                                                    faculty.specialization,
                                                )
                                                    ? ""
                                                    : ","
                                            }}
                                        </span>
                                    </div>
                                </td>

                                <td class="py-6 px-6 text-center">
                                    <button
                                        class="inline-flex items-center gap-2 px-4 py-2 rounded-xl bg-[#f1f5f9] text-[#1f3a6d] text-xs font-bold hover:bg-[#1f3a6d] hover:text-white transition-all shadow-sm"
                                    >
                                        <svg
                                            xmlns="http://www.w3.org/2000/svg"
                                            class="w-4 h-4"
                                            fill="none"
                                            viewBox="0 0 24 24"
                                            stroke="currentColor"
                                        >
                                            <path
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"
                                            />
                                            <path
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z"
                                            />
                                        </svg>
                                        View
                                    </button>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>

            <div class="mt-8 text-center">
                <p class="text-slate-400 text-xs">
                    © 2024 Institute of Forensic Science • Visiting Faculty
                    Directory
                </p>
            </div>
        </div>
    </div>
</template>

<script setup>
const facultyList = [
    {
        name: "Sunil Kumar Yadav",
        qualification: "M.Sc. (Forensic Science)",
        department: "Forensic",
        specialization: "Cyber Forensic, Digital Forensic",
    },
    {
        name: "Feba Elsa Santhosh",
        qualification: "M.Sc.",
        department: "Chemistry",
        specialization: "Forensic chemistry and toxicology",
    },
    {
        name: "Ms. Neha Kharat",
        qualification: "M.Sc. Forensic Science",
        department: "Psychology",
        specialization: "Ballistics and explosives",
    },
];

const splitSpecs = (str) => str.split(",").map((s) => s.trim());
const isLast = (item, fullStr) => {
    const arr = splitSpecs(fullStr);
    return arr[arr.length - 1] === item;
};
</script>

<style scoped>
/* Custom scrollbar for the table container */
::-webkit-scrollbar {
    height: 8px;
}
::-webkit-scrollbar-track {
    background: #f1f5f9;
}
::-webkit-scrollbar-thumb {
    background: #cbd5e1;
    border-radius: 10px;
}
::-webkit-scrollbar-thumb:hover {
    background: #94a3b8;
}
</style>
