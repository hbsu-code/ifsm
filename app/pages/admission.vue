<template>
    <div
        class="min-h-screen bg-[#f8fafc] py-16 px-6 lg:px-12 font-sans antialiased text-slate-800"
    >
        <div class="max-w-6xl mx-auto">
            <header class="mb-16 text-center md:text-left">
                <h1 class="text-4xl md:text-5xl font-black text-[#1f3a6d] mb-4">
                    Admission <span class="text-[#C8A84B]">Information</span>
                </h1>
                <p class="text-slate-500 max-w-2xl leading-relaxed text-lg">
                    Detailed eligibility criteria, intake capacity, and
                    notification schedules for the upcoming academic session.
                </p>
            </header>

            <div
                class="bg-white rounded-[2.5rem] shadow-xl shadow-slate-200/50 border border-slate-100 overflow-hidden"
            >
                <div class="overflow-x-auto">
                    <table class="w-full text-left border-collapse">
                        <thead>
                            <tr class="bg-[#1f3a6d] text-white">
                                <th
                                    class="py-6 px-8 text-xs font-black uppercase tracking-widest w-20"
                                >
                                    Sr.
                                </th>
                                <th
                                    class="py-6 px-8 text-xs font-black uppercase tracking-widest min-w-[200px]"
                                >
                                    Course Name
                                </th>
                                <th
                                    class="py-6 px-8 text-xs font-black uppercase tracking-widest min-w-[350px]"
                                >
                                    Eligibility Criteria
                                </th>
                                <th
                                    class="py-6 px-8 text-xs font-black uppercase tracking-widest text-center"
                                >
                                    Capacity
                                </th>
                                <th
                                    class="py-6 px-8 text-xs font-black uppercase tracking-widest"
                                >
                                    Notification
                                </th>
                            </tr>
                        </thead>
                        <tbody class="divide-y divide-slate-100">
                            <tr
                                v-for="(course, index) in admissions"
                                :key="index"
                                class="hover:bg-slate-50/50 transition-colors"
                            >
                                <td
                                    class="py-8 px-8 align-top text-slate-400 font-bold"
                                >
                                    0{{ index + 1 }}
                                </td>

                                <td class="py-8 px-8 align-top">
                                    <div
                                        class="text-lg font-bold text-[#1f3a6d] leading-tight"
                                    >
                                        {{ course.name }}
                                    </div>
                                </td>

                                <td class="py-8 px-8 align-top">
                                    <p
                                        class="text-[14.5px] leading-relaxed text-slate-600"
                                    >
                                        {{ course.eligibility }}
                                    </p>
                                </td>

                                <td class="py-8 px-8 align-top text-center">
                                    <span
                                        class="inline-block px-4 py-2 rounded-xl bg-[#f1f5f9] text-[#1f3a6d] font-black text-sm"
                                    >
                                        {{ course.capacity }}
                                    </span>
                                </td>

                                <td class="py-8 px-8 align-top">
                                    <div class="space-y-3">
                                        <span
                                            class="text-xs font-bold text-[#C8A84B] uppercase tracking-wider block"
                                            >Expected Date:</span
                                        >
                                        <p
                                            class="text-sm text-slate-500 leading-relaxed"
                                        >
                                            {{ course.notification }}
                                        </p>
                                    </div>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>

            <div class="mt-20 grid md:grid-cols-3 gap-8">
                <div
                    v-for="(step, i) in steps"
                    :key="i"
                    class="bg-[#1f3a6d] p-8 rounded-3xl text-white relative overflow-hidden group"
                >
                    <div
                        class="absolute -right-4 -bottom-4 text-7xl font-black opacity-10 group-hover:scale-110 transition-transform"
                    >
                        {{ i + 1 }}
                    </div>
                    <h4 class="text-[#C8A84B] font-bold mb-2">
                        Step {{ i + 1 }}
                    </h4>
                    <p class="text-sm leading-relaxed opacity-80">{{ step }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const admissions = [
    {
        name: "B.Sc. Forensic Science",
        eligibility:
            "HSC (12th Standard) in Science stream from a recognized board.",
        capacity: "50",
        notification:
            "After results of HSC. Notification is declared by University of Mumbai on the official website.",
    },
    {
        name: "M.Sc. Forensic Science",
        eligibility:
            "Bachelor’s degree with Forensic Science as one of the core subjects during graduation.",
        capacity: "20",
        notification:
            "After graduation results. Check University of Mumbai and College websites for official notification.",
    },
    {
        name: "PGD FSRL",
        eligibility:
            "Bachelor Degree in Science (Physics, Chemistry, Biology, etc.), Pharmacy, Law, or Medical Sciences (MBBS, BHMS, BDS).",
        capacity: "40",
        notification:
            "Post-graduation results. Students must apply via both University and College portals.",
    },
    {
        name: "PGD DCFRL",
        eligibility:
            "Bachelor Degree with IT, Computer Science, Bioinformatics, Mathematics, Electronics, or Physics as a major subject.",
        capacity: "40",
        notification:
            "Post-graduation results. Detailed schedule will be posted on the University of Mumbai website.",
    },
];

const steps = [
    "Monitor the University of Mumbai official website for admission notifications after your results.",
    "Complete the Pre-Admission Online Enrollment on the University of Mumbai portal.",
    "Submit the specific application form on the Institute/College website as per the notification.",
];
</script>
