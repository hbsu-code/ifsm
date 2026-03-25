<template>
    <header class="w-full sticky top-0 z-50">
        <!-- TOP BAR (same) -->
        <div
            class="bg-[#1B2A4A] text-white/60 text-xs py-2 px-8 flex justify-between"
        >
            <span class="text-white/80">Government of Maharashtra</span>
            <div class="flex gap-1">
                <a
                    v-for="link in topLinks"
                    :key="link"
                    href="#"
                    class="px-3 py-1 hover:text-white"
                >
                    {{ link }}
                </a>
            </div>
        </div>

        <!-- MAIN HEADER -->
        <div
            class="bg-white border-b px-8 py-3 flex justify-between items-center"
        >
            <!-- LOGO -->
            <div class="flex items-center gap-3">
                <img src="/logo.png" class="h-12" />
                <div>
                    <h1 class="text-lg font-bold text-[#1B2A4A]">
                        Institute of Forensic Science
                    </h1>
                </div>
            </div>

            <!-- NAVBAR -->
            <nav class="hidden lg:flex gap-2">
                <div
                    v-for="item in navItems"
                    :key="item.label"
                    class="relative group"
                >
                    <!-- Main item -->
                    <a
                        href="#"
                        class="px-4 py-2 rounded-full text-sm font-medium text-gray-600 hover:bg-gray-100"
                    >
                        {{ item.label }}
                    </a>

                    <!-- LEVEL 1 -->
                    <div
                        v-if="item.children"
                        class="absolute left-0 top-full mt-2 w-64 bg-white shadow-lg rounded-xl opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all"
                    >
                        <DropdownItem :items="item.children" />
                    </div>
                </div>
            </nav>
        </div>
    </header>
</template>

<script setup>
const topLinks = ["RTI", "Tenders", "Sitemap"];

const navItems = [
    { label: "Home" },

    {
        label: "About Us",
        children: [
            { label: "Institute" },
            { label: "Vision and Mission" },
            { label: "Govt. Resolution" },
            { label: "Affiliation" },
            { label: "Academic Calendar" },
            { label: "Committee" },
            { label: "Code of Conduct" },
            { label: "Students Achievement" },
            { label: "Prospectus" },
            { label: "College Magazine" },
            {
                label: "Gov Body",
                children: [{ label: "Organogram" }],
            },
        ],
    },

    {
        label: "Administration",
        children: [
            { label: "Ministry" },
            { label: "DHTE" },
            { label: "DHE Pune" },
            { label: "Programs Outcomes" },
        ],
    },

    {
        label: "Department",
        children: [
            {
                label: "Forensic",
                children: [
                    { label: "Forensic Science" },
                    { label: "Forensic Chemistry" },
                    { label: "Forensic Physics" },
                    { label: "Forensic Biology" },
                    { label: "Psychology" },
                    { label: "Digital & Cyber Forensic" },
                    { label: "Forensic Law" },
                ],
            },
            {
                label: "IT",
                children: [{ label: "CS" }],
            },
            { label: "Visiting Faculty" },
        ],
    },

    {
        label: "Course",
        children: [
            { label: "B.Sc. Forensic" },
            { label: "M.Sc. Forensic" },
            { label: "P.G. Diploma" },
            { label: "Program Outcomes" },
        ],
    },

    {
        label: "Admissions",
        children: [{ label: "Admission Information" }],
    },

    { label: "Examination" },

    {
        label: "Students Corner",
        children: [
            { label: "Time Table" },
            { label: "Notice Period" },
            {
                label: "Extra Curricular Activities",
                children: [
                    { label: "NSS" },
                    { label: "Sports" },
                    { label: "Cultural" },
                ],
            },
            {
                label: "Facilities",
                children: [
                    { label: "Campus" },
                    { label: "Library" },
                    { label: "Auditorium" },
                    { label: "Hostel" },
                    { label: "Botanical Garden" },
                    { label: "Canteen" },
                ],
            },
            {
                label: "Cell And Center",
                children: [
                    { label: "Placement Cell" },
                    { label: "Competitive Exam Cell" },
                    { label: "Anti Ragging Cell" },
                    { label: "Anti Sexual Harassment" },
                    { label: "Students Council" },
                ],
            },
            {
                label: "Scholarships",
                children: [{ label: "Indian" }, { label: "International" }],
            },
            { label: "Grievance Redressal" },
        ],
    },

    {
        label: "NAAC",
        children: [
            { label: "Certificates" },
            { label: "NAAC Peer Team Report" },
            { label: "AQAR" },
            { label: "SSR" },
            { label: "SSR After DVV" },
        ],
    },

    {
        label: "IQAC",
        children: [
            { label: "About IQAC" },
            { label: "IQAC Composition" },
            { label: "IQAC Annual Report" },
            { label: "IQAC Committee" },
            { label: "IQAC Activities" },
            { label: "Minutes of Meeting" },
            { label: "Plan of Action" },
            { label: "Action Taken Report" },
            { label: "Best Practices" },
            { label: "Institutional Distinctiveness" },
            { label: "SSS" },
            { label: "Data Template" },
        ],
    },

    { label: "Downloads" },
];
</script>
