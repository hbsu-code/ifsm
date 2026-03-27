<template>
    <header class="w-full sticky top-0 z-50">
        <!-- TOP BAR -->
        <div
            class="bg-[#1B2A4A] text-white/60 text-xs py-2 px-8 flex justify-between"
        >
            <span class="text-white/80">Government of Maharashtra</span>
            <div class="flex gap-1">
                <a
                    v-for="link in topLinks"
                    :key="link.label"
                    :href="link.href"
                    class="px-3 py-1 hover:text-white"
                >
                    {{ link.label }}
                </a>
            </div>
        </div>

        <!-- MAIN HEADER -->
        <div
            class="bg-white border-b px-4 py-3 flex justify-between items-center gap-2"
        >
            <!-- LOGO -->
            <div class="flex items-center gap-3 shrink-0">
                <img src="/logo.png" class="h-12" />
                <h1 class="text-lg font-bold text-[#1B2A4A]">
                    Institute of Forensic Science
                </h1>
            </div>

            <!-- NAVBAR -->
            <nav
                class="hidden lg:flex items-center gap-0.5 flex-1 justify-end flex-wrap"
            >
                <div
                    v-for="(item, index) in navItems"
                    :key="item.label"
                    class="relative shrink-0"
                    :ref="
                        (el) => {
                            if (el) navRefs[index] = el;
                        }
                    "
                    @mouseenter="onNavEnter(item.label)"
                    @mouseleave="onNavLeave(item.label)"
                >
                    <a
                        :href="item.href"
                        class="px-3 py-2 rounded-full text-sm font-medium whitespace-nowrap block transition-colors"
                        :class="
                            openNav === item.label
                                ? 'bg-[#EEF2F9] text-[#1B2A4A]'
                                : 'text-gray-600 hover:bg-gray-100'
                        "
                    >
                        {{ item.label }}
                    </a>

                    <!-- Level 1 dropdown -->
                    <div
                        v-if="item.children && openNav === item.label"
                        class="absolute top-full mt-1 w-64 bg-white border border-gray-100 shadow-xl rounded-xl z-50 py-2"
                        :class="
                            rightEdgeItems.has(index) ? 'right-0' : 'left-0'
                        "
                    >
                        <template
                            v-for="child in item.children"
                            :key="child.label"
                        >
                            <div
                                class="relative"
                                @mouseenter="onL1Enter(child.label)"
                                @mouseleave="onL1Leave(child.label)"
                            >
                                <a
                                    :href="child.href"
                                    class="flex justify-between items-center gap-3 px-4 py-2.5 text-sm font-medium text-[#1B2A4A]/75 hover:text-[#1B2A4A] hover:bg-[#EEF2F9] rounded-lg mx-1.5 transition-all"
                                >
                                    <span class="flex items-center gap-2.5">
                                        <span
                                            class="w-1.5 h-1.5 rounded-full transition-colors"
                                            :class="
                                                openL1 === child.label
                                                    ? 'bg-[#C8A84B]'
                                                    : 'bg-[#1B2A4A]/10'
                                            "
                                        ></span>
                                        {{ child.label }}
                                    </span>
                                    <svg
                                        v-if="child.children"
                                        xmlns="http://www.w3.org/2000/svg"
                                        class="w-3.5 h-3.5 shrink-0 transition-opacity"
                                        :class="
                                            openL1 === child.label
                                                ? 'opacity-100'
                                                : 'opacity-30'
                                        "
                                        :style="
                                            rightEdgeItems.has(index)
                                                ? 'transform: rotate(180deg)'
                                                : ''
                                        "
                                        viewBox="0 0 24 24"
                                        fill="none"
                                        stroke="currentColor"
                                        stroke-width="2.5"
                                    >
                                        <polyline points="9 18 15 12 9 6" />
                                    </svg>
                                </a>

                                <!-- Level 2 dropdown -->
                                <div
                                    v-if="
                                        child.children && openL1 === child.label
                                    "
                                    class="absolute top-0 w-56 bg-white border border-gray-100 shadow-xl rounded-xl z-[60] py-2"
                                    :class="
                                        rightEdgeItems.has(index)
                                            ? 'right-full mr-2'
                                            : 'left-full ml-2'
                                    "
                                >
                                    <template
                                        v-for="grandchild in child.children"
                                        :key="grandchild.label"
                                    >
                                        <div
                                            class="relative"
                                            @mouseenter="
                                                onL2Enter(grandchild.label)
                                            "
                                            @mouseleave="
                                                onL2Leave(grandchild.label)
                                            "
                                        >
                                            <a
                                                :href="grandchild.href"
                                                class="flex justify-between items-center gap-3 px-4 py-2.5 text-sm font-medium text-[#1B2A4A]/75 hover:text-[#1B2A4A] hover:bg-[#EEF2F9] rounded-lg mx-1.5 transition-all"
                                            >
                                                <span
                                                    class="flex items-center gap-2.5"
                                                >
                                                    <span
                                                        class="w-1.5 h-1.5 rounded-full transition-colors"
                                                        :class="
                                                            openL2 ===
                                                            grandchild.label
                                                                ? 'bg-[#C8A84B]'
                                                                : 'bg-[#1B2A4A]/10'
                                                        "
                                                    ></span>
                                                    {{ grandchild.label }}
                                                </span>
                                                <svg
                                                    v-if="grandchild.children"
                                                    xmlns="http://www.w3.org/2000/svg"
                                                    class="w-3.5 h-3.5 shrink-0 opacity-30"
                                                    viewBox="0 0 24 24"
                                                    fill="none"
                                                    stroke="currentColor"
                                                    stroke-width="2.5"
                                                >
                                                    <polyline
                                                        points="9 18 15 12 9 6"
                                                    />
                                                </svg>
                                            </a>
                                        </div>
                                    </template>
                                </div>
                            </div>
                        </template>
                    </div>
                </div>
            </nav>
        </div>
    </header>
</template>

<script setup>
import { ref, onMounted } from "vue";

const topLinks = [
    { label: "RTI", href: "/rti" },
    { label: "Tenders", href: "/tenders" },
    { label: "Sitemap", href: "/sitemap" },
];

const navItems = [
    { label: "Home", href: "/" },
    {
        label: "About Us",
        href: "/about-us",
        children: [
            { label: "Institute", href: "/about-us" },
            {
                label: "Vision and Mission",
                href: "/about-us/vision-and-mission",
            },
            {
                label: "Govt. Resolution",
                href: "https://web.archive.org/web/20240721052427/https://gr.maharashtra.gov.in/1145/Government-Resolutions",
            },
            { label: "Affiliation", href: "/about-us/affiliation" },
            // { label: "Academic Calendar", href: "/about-us/academic-calendar" },
            { label: "Committee", href: "/about-us/committee" },
            { label: "Code of Conduct", href: "/about-us/code-of-conduct" },
            // {
            //     label: "Students Achievement",
            //     href: "/about-us/students-achievement",
            // },
            // { label: "Prospectus", href: "/about-us/prospectus" },
            { label: "College Magazine", href: "/about-us/college-magazine" },
            {
                label: "Gov Body",
                href: "/about-us/gov-body",
                children: [
                    {
                        label: "Organogram",
                        href: "/about-us/gov-body/organogram",
                    },
                ],
            },
        ],
    },
    {
        label: "Administration",
        href: "/administration",
        children: [
            { label: "Ministry", href: "/administration/ministry" },
            { label: "DHTE", href: "/administration/dhte" },
            { label: "DHE Pune", href: "/administration/dhe-pune" },
            {
                label: "Programs Outcomes",
                href: "/administration/programs-outcomes",
            },
        ],
    },
    {
        label: "Department",
        href: "/department",
        children: [
            {
                label: "Forensic",
                href: "/department/forensic",
                children: [
                    {
                        label: "Forensic Science",
                        href: "/department/forensic/forensic-science",
                    },
                    {
                        label: "Forensic Chemistry",
                        href: "/department/forensic/forensic-chemistry",
                    },
                    {
                        label: "Forensic Physics",
                        href: "/department/forensic/forensic-physics",
                    },
                    {
                        label: "Forensic Biology",
                        href: "/department/forensic/forensic-biology",
                    },
                    {
                        label: "Psychology",
                        href: "/department/forensic/psychology",
                    },
                    {
                        label: "Digital & Cyber Forensic",
                        href: "/department/forensic/digital-cyber-forensic",
                    },
                    {
                        label: "Forensic Law",
                        href: "/department/forensic/forensic-law",
                    },
                ],
            },
            {
                label: "IT",
                href: "/department/it",
                children: [{ label: "CS", href: "/department/it/cs" }],
            },
            { label: "Visiting Faculty", href: "/department/visiting-faculty" },
        ],
    },
    {
        label: "Course",
        href: "/course",
        children: [
            { label: "B.Sc. Forensic", href: "/course/bsc-forensic" },
            { label: "M.Sc. Forensic", href: "/course/msc-forensic" },
            { label: "P.G. Diploma", href: "/course/pg-diploma" },
            { label: "Program Outcomes", href: "/course/program-outcomes" },
        ],
    },
    {
        label: "Admissions",
        href: "/admissions",
        children: [
            {
                label: "Admission Information",
                href: "/admissions/admission-information",
            },
        ],
    },
    { label: "Examination", href: "/examination" },
    {
        label: "Students Corner",
        href: "/students-corner",
        children: [
            { label: "Time Table", href: "/students-corner/time-table" },
            { label: "Notice Period", href: "/students-corner/notice-period" },
            {
                label: "Extra Curricular Activities",
                href: "/students-corner/extra-curricular-activities",
                children: [
                    {
                        label: "NSS",
                        href: "/students-corner/extra-curricular-activities/nss",
                    },
                    {
                        label: "Sports",
                        href: "/students-corner/extra-curricular-activities/sports",
                    },
                    {
                        label: "Cultural",
                        href: "/students-corner/extra-curricular-activities/cultural",
                    },
                ],
            },
            {
                label: "Facilities",
                href: "/students-corner/facilities",
                children: [
                    {
                        label: "Campus",
                        href: "/students-corner/facilities/campus",
                    },
                    {
                        label: "Library",
                        href: "/students-corner/facilities/library",
                    },
                    {
                        label: "Auditorium",
                        href: "/students-corner/facilities/auditorium",
                    },
                    {
                        label: "Hostel",
                        href: "/students-corner/facilities/hostel",
                    },
                    {
                        label: "Botanical Garden",
                        href: "/students-corner/facilities/botanical-garden",
                    },
                    {
                        label: "Canteen",
                        href: "/students-corner/facilities/canteen",
                    },
                ],
            },
            {
                label: "Cell And Center",
                href: "/students-corner/cell-and-center",
                children: [
                    {
                        label: "Placement Cell",
                        href: "/students-corner/cell-and-center/placement-cell",
                    },
                    {
                        label: "Competitive Exam Cell",
                        href: "/students-corner/cell-and-center/competitive-exam-cell",
                    },
                    {
                        label: "Anti Ragging Cell",
                        href: "/students-corner/cell-and-center/anti-ragging-cell",
                    },
                    {
                        label: "Anti Sexual Harassment",
                        href: "/students-corner/cell-and-center/anti-sexual-harassment",
                    },
                    {
                        label: "Students Council",
                        href: "/students-corner/cell-and-center/students-council",
                    },
                ],
            },
            {
                label: "Scholarships",
                href: "/students-corner/scholarships",
                children: [
                    {
                        label: "Indian",
                        href: "/students-corner/scholarships/indian",
                    },
                    {
                        label: "International",
                        href: "/students-corner/scholarships/international",
                    },
                ],
            },
            {
                label: "Grievance Redressal",
                href: "/students-corner/grievance-redressal",
            },
        ],
    },
    {
        label: "NAAC",
        href: "/naac",
        children: [
            { label: "Certificates", href: "/naac/certificates" },
            { label: "NAAC Peer Team Report", href: "/naac/peer-team-report" },
            { label: "AQAR", href: "/naac/aqar" },
            { label: "SSR", href: "/naac/ssr" },
            { label: "SSR After DVV", href: "/naac/ssr-after-dvv" },
        ],
    },
    {
        label: "IQAC",
        href: "/iqac",
        children: [
            { label: "About IQAC", href: "/iqac/about" },
            { label: "IQAC Composition", href: "/iqac/composition" },
            { label: "IQAC Annual Report", href: "/iqac/annual-report" },
            { label: "IQAC Committee", href: "/iqac/committee" },
            { label: "IQAC Activities", href: "/iqac/activities" },
            { label: "Minutes of Meeting", href: "/iqac/minutes-of-meeting" },
            { label: "Plan of Action", href: "/iqac/plan-of-action" },
            { label: "Action Taken Report", href: "/iqac/action-taken-report" },
            { label: "Best Practices", href: "/iqac/best-practices" },
            {
                label: "Institutional Distinctiveness",
                href: "/iqac/institutional-distinctiveness",
            },
            { label: "SSS", href: "/iqac/sss" },
            { label: "Data Template", href: "/iqac/data-template" },
        ],
    },
    { label: "Downloads", href: "/downloads" },
];

// --- Refs & state ---
const navRefs = ref({});
const rightEdgeItems = ref(new Set());

const openNav = ref(null);
const openL1 = ref(null);
const openL2 = ref(null);

const timers = {};

// Detect right-edge items after mount
onMounted(() => {
    setTimeout(() => {
        const set = new Set();
        Object.entries(navRefs.value).forEach(([i, el]) => {
            const rect = el.getBoundingClientRect();
            if (window.innerWidth - rect.right < 280) set.add(Number(i));
        });
        rightEdgeItems.value = set;
    }, 100);
});

// --- Nav (level 0) ---
function onNavEnter(label) {
    clearTimeout(timers.nav);
    openNav.value = label;
    openL1.value = null;
    openL2.value = null;
}
function onNavLeave(label) {
    timers.nav = setTimeout(() => {
        if (openNav.value === label) {
            openNav.value = null;
            openL1.value = null;
            openL2.value = null;
        }
    }, 150);
}

// --- Level 1 ---
function onL1Enter(label) {
    clearTimeout(timers.nav);
    clearTimeout(timers.l1);
    openL1.value = label;
    openL2.value = null;
}
function onL1Leave(label) {
    timers.l1 = setTimeout(() => {
        if (openL1.value === label) {
            openL1.value = null;
            openL2.value = null;
        }
    }, 150);
}

// --- Level 2 ---
function onL2Enter(label) {
    clearTimeout(timers.l1);
    clearTimeout(timers.l2);
    openL2.value = label;
}
function onL2Leave(label) {
    timers.l2 = setTimeout(() => {
        if (openL2.value === label) openL2.value = null;
    }, 150);
}
</script>
