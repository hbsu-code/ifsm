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
                        href="#"
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
                                    href="#"
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
                                                href="#"
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
            { label: "Gov Body", children: [{ label: "Organogram" }] },
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
            { label: "IT", children: [{ label: "CS" }] },
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
