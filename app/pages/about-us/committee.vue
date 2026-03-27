<template>
    <div class="min-h-screen bg-[#F9F7F2] py-16 px-6 font-sans text-[#1A2B43]">
        <div class="max-w-6xl mx-auto">
            <div class="mb-16">
                <span
                    class="inline-flex items-center px-3 py-1 rounded-full bg-white border border-gray-200 text-xs font-semibold text-[#B1974F] mb-6 shadow-sm"
                >
                    <span class="w-2 h-2 rounded-full bg-[#B1974F] mr-2"></span>
                    Institutional Governance
                </span>
                <h1
                    class="text-5xl md:text-6xl font-serif font-bold leading-tight mb-4"
                >
                    Institute <span class="text-[#B1974F]">Committees.</span>
                </h1>
                <p class="text-gray-600 max-w-xl">
                    Official administrative bodies overseeing academic quality,
                    student welfare, and institutional integrity.
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div
                    v-for="(committee, index) in committees"
                    :key="index"
                    class="bg-white rounded-[2.5rem] p-8 shadow-sm border border-gray-100 hover:shadow-md transition-all flex flex-col"
                >
                    <div class="flex items-start justify-between mb-8">
                        <div
                            class="w-14 h-14 bg-[#F9F7F2] rounded-2xl flex items-center justify-center text-[#B1974F]"
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/vue"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke-width="1.5"
                                stroke="currentColor"
                                class="w-7 h-7"
                                v-html="committee.svgPath"
                            ></svg>
                        </div>
                        <span
                            class="text-[10px] uppercase tracking-widest font-bold text-gray-400"
                        >
                            Session 2025-26
                        </span>
                    </div>

                    <h3 class="text-2xl font-serif font-bold mb-6 pr-4">
                        {{ committee.name }}
                    </h3>

                    <div class="flex-grow">
                        <table class="w-full text-left">
                            <thead>
                                <tr
                                    class="text-[11px] uppercase tracking-wider text-[#B1974F] border-b border-gray-50"
                                >
                                    <th class="pb-3 font-bold w-12">#</th>
                                    <th class="pb-3 font-bold">Member Name</th>
                                    <th class="pb-3 font-bold text-right">
                                        Designation
                                    </th>
                                </tr>
                            </thead>
                            <tbody class="divide-y divide-gray-50">
                                <tr
                                    v-for="(member, mIdx) in committee.members"
                                    :key="mIdx"
                                    class="group"
                                >
                                    <td class="py-4 text-sm text-gray-400">
                                        {{ mIdx + 1 }}
                                    </td>
                                    <td
                                        class="py-4 text-sm font-semibold text-[#1A2B43]"
                                    >
                                        {{ member.name }}
                                    </td>
                                    <td
                                        class="py-4 text-sm text-gray-500 text-right italic"
                                    >
                                        <span
                                            :class="
                                                member.designation.includes(
                                                    'In charge',
                                                )
                                                    ? 'text-[#B1974F] font-medium non-italic underline underline-offset-4 decoration-gray-200'
                                                    : ''
                                            "
                                        >
                                            {{ member.designation }}
                                        </span>
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from "vue";

const committees = ref([
    {
        name: "Internal Quality Assurance Cell",
        // Shield Icon
        svgPath:
            '<path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75m-3-7.036A11.959 11.959 0 013.598 6 11.99 11.99 0 003 9.744c0 5.052 3.13 9.392 7.502 11.107a11.91 11.91 0 007.496-11.107c0-1.307-.21-2.565-.598-3.743A11.959 11.959 0 0112 2.714z" />',
        members: [
            { name: "Mr. N.M. Fatangare", designation: "In charge" },
            { name: "Dr. Shrinaag Panchbhai", designation: "Member" },
            { name: "Mrs. Ashwini Pol", designation: "Member" },
            { name: "Ms. Fayth D’Silva", designation: "Member" },
            { name: "Mr. Milind Meshram", designation: "Member" },
        ],
    },
    {
        name: "Examination Committee",
        // Academic Cap Icon
        svgPath:
            '<path stroke-linecap="round" stroke-linejoin="round" d="M4.26 10.174L10.72 13.522a2 2 0 001.76 0l6.46-3.348M11.03 3.912a2 2 0 011.94 0l7.53 3.903a1 1 0 010 1.77l-7.53 3.903a2 2 0 01-1.94 0L3.47 9.585a1 1 0 010-1.77l7.56-3.903z" /><path stroke-linecap="round" stroke-linejoin="round" d="M3.5 12V16.5A1.5 1.5 0 005 18H19A1.5 1.5 0 0020.5 16.5V12" />',
        members: [
            { name: "Dr. Shrinaag Panchbhai", designation: "In charge" },
            { name: "Mrs. Neeta Khobragade", designation: "Member" },
            { name: "Mr. Santosh Lohakare", designation: "Member" },
            { name: "Ms. Sheetal Solanki", designation: "Member" },
        ],
    },
    {
        name: "Research & Development",
        // Beaker/Science Icon
        svgPath:
            '<path stroke-linecap="round" stroke-linejoin="round" d="M9.75 3.104v1.242c0 .283.23.514.514.514h3.472c.283 0 .514-.23.514-.514V3.104M4.5 18.75h15m-15 0a1.5 1.5 0 01-1.5-1.5V15a1.5 1.5 0 011.5-1.5h15a1.5 1.5 0 011.5 1.5v2.25a1.5 1.5 0 01-1.5 1.5m-15 0h15" />',
        members: [
            { name: "Dr. Shrihari Sanap", designation: "In charge" },
            { name: "Dr. Pravin More", designation: "Member" },
            { name: "Mr. Santosh Dunghav", designation: "Member" },
        ],
    },
    {
        name: "Student Grievance & Women Development",
        // Heart/User Group Icon
        svgPath:
            '<path stroke-linecap="round" stroke-linejoin="round" d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12z" />',
        members: [
            {
                name: "Dr. Vandana Kamble",
                designation: "In charge Student Redressal",
            },
            { name: "Mrs. Bhagyashree Kulkarni", designation: "Member" },
            { name: "Mrs. Neeta Khobragade", designation: "Member" },
            { name: "Mrs. Ashwini Pol", designation: "Member" },
            { name: "Ms. Fayth D’Silva", designation: "Member" },
        ],
    },
]);
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=Inter:wght@400;500;600;700&display=swap");

.font-serif {
    font-family: "DM Serif Display", serif;
}
.font-sans {
    font-family: "Inter", sans-serif;
}
</style>
