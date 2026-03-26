<template>
    <ul class="py-2 bg-white rounded-xl">
        <li
            v-for="item in items"
            :key="item.label"
            class="relative"
            @mouseenter="openItem(item.label)"
            @mouseleave="closeItem(item.label)"
        >
            <a
                href="#"
                class="flex justify-between items-center gap-3 px-4 py-2.5 text-sm font-medium text-[#1B2A4A]/75 hover:text-[#1B2A4A] hover:bg-[#EEF2F9] rounded-lg mx-1.5 transition-all"
            >
                <span class="flex items-center gap-2.5">
                    <span
                        class="w-1.5 h-1.5 rounded-full transition-colors"
                        :class="
                            activeItem === item.label
                                ? 'bg-[#C8A84B]'
                                : 'bg-[#1B2A4A]/10'
                        "
                    ></span>
                    {{ item.label }}
                </span>
                <svg
                    v-if="item.children"
                    xmlns="http://www.w3.org/2000/svg"
                    class="w-3.5 h-3.5 transition-all shrink-0"
                    :class="[
                        activeItem === item.label
                            ? 'opacity-100'
                            : 'opacity-30',
                        isRightAligned ? 'rotate-180' : '',
                    ]"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2.5"
                >
                    <polyline points="9 18 15 12 9 6" />
                </svg>
            </a>

            <!-- Sub-menu -->
            <div
                v-if="item.children && activeItem === item.label"
                class="absolute top-0 w-60 bg-white border border-gray-100 shadow-xl rounded-xl z-[110]"
                :class="isRightAligned ? 'right-full mr-2' : 'left-full ml-2'"
            >
                <DropdownItem
                    :items="item.children"
                    :is-right-aligned="isRightAligned"
                />
            </div>
        </li>
    </ul>
</template>

<script setup>
import { ref } from "vue";

defineProps({
    items: Array,
    isRightAligned: Boolean,
});

const activeItem = ref(null);
const timers = {};

function openItem(label) {
    if (timers[label]) {
        clearTimeout(timers[label]);
        timers[label] = null;
    }
    activeItem.value = label;
}

function closeItem(label) {
    timers[label] = setTimeout(() => {
        if (activeItem.value === label) {
            activeItem.value = null;
        }
    }, 120);
}
</script>
