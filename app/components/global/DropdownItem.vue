<template>
    <ul class="dropdown-list py-1.5">
        <li v-for="item in items" :key="item.label" class="relative group/item">
            <a
                href="#"
                class="dropdown-link flex justify-between items-center gap-3 px-4 py-2.5 text-sm font-medium text-[#1B2A4A]/75 hover:text-[#1B2A4A] hover:bg-[#EEF2F9] rounded-lg mx-1.5 transition-all duration-150"
                :class="{ 'has-children': item.children }"
            >
                <!-- Icon dot accent -->
                <span class="flex items-center gap-2.5">
                    <span
                        class="dot w-1.5 h-1.5 rounded-full bg-[#1B2A4A]/20 group-hover/item:bg-[#C8A84B] transition-colors duration-200 flex-shrink-0"
                    ></span>
                    {{ item.label }}
                </span>

                <!-- Chevron for items with children -->
                <svg
                    v-if="item.children"
                    xmlns="http://www.w3.org/2000/svg"
                    class="chevron w-3.5 h-3.5 text-[#1B2A4A]/30 group-hover/item:text-[#C8A84B] transition-all duration-150 flex-shrink-0"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2.5"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                >
                    <polyline points="9 18 15 12 9 6" />
                </svg>
            </a>

            <!-- Nested dropdown -->
            <div
                v-if="item.children"
                class="nested-dropdown absolute left-full top-0 ml-2 w-60 bg-white border border-gray-100 shadow-xl shadow-[#1B2A4A]/10 rounded-xl opacity-0 invisible pointer-events-none group-hover/item:opacity-100 group-hover/item:visible group-hover/item:pointer-events-auto transition-all duration-200 origin-top-left scale-95 group-hover/item:scale-100"
                style="z-index: 100"
            >
                <!-- Nested header accent -->
                <div
                    class="h-0.5 w-full bg-gradient-to-r from-[#C8A84B] to-[#1B2A4A]/20 rounded-t-xl"
                ></div>
                <DropdownItem :items="item.children" />
            </div>
        </li>
    </ul>
</template>

<script setup>
defineProps({
    items: Array,
});
</script>

<style scoped>
.dropdown-list {
    /* Subtle inner shadow to ground the list */
}

.dropdown-link {
    letter-spacing: 0.01em;
}

.dropdown-link.has-children {
    /* Slightly different treatment for parent items */
}

/* Smooth slide-in for nested dropdowns */
.nested-dropdown {
    transform-origin: top left;
}

/* Stagger children on hover of parent for depth feel */
.group\/item:hover .dot {
    transform: scale(1.4);
}
</style>
