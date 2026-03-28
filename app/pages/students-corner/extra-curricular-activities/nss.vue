<template>
    <div
        class="min-h-screen bg-white py-12 px-4 font-sans antialiased text-slate-900"
    >
        <div class="max-w-3xl mx-auto">
            <header class="mb-8 border-b border-slate-100 pb-8">
                <div
                    class="inline-block px-2 py-1 rounded bg-orange-50 text-orange-600 text-[10px] font-bold uppercase tracking-wider mb-3"
                >
                    Community Service
                </div>
                <h1
                    class="text-3xl md:text-4xl font-extrabold tracking-tight text-slate-900 mb-2"
                >
                    National Service Scheme
                </h1>
                <p class="text-sm text-slate-500 font-medium italic">
                    "Not Me, But You"
                </p>
            </header>

            <div class="flex flex-col md:flex-row gap-10">
                <aside class="md:w-48 shrink-0">
                    <ul class="space-y-1">
                        <li v-for="tab in tabs" :key="tab.id">
                            <button
                                @click="activeTab = tab.id"
                                :class="[
                                    'w-full text-left px-3 py-2 rounded text-xs font-bold transition-all uppercase tracking-tight',
                                    activeTab === tab.id
                                        ? 'bg-slate-900 text-white shadow-md'
                                        : 'text-slate-500 hover:bg-slate-50 hover:text-slate-900',
                                ]"
                            >
                                {{ tab.name }}
                            </button>
                        </li>
                    </ul>
                </aside>

                <main class="flex-1">
                    <transition name="fade" mode="out-in">
                        <div :key="activeTab">
                            <section
                                v-if="activeTab === 'about'"
                                class="prose prose-slate prose-sm max-w-none"
                            >
                                <h2
                                    class="text-xl font-bold text-slate-900 mb-4 mt-0"
                                >
                                    About NSS
                                </h2>
                                <p class="leading-relaxed text-slate-600">
                                    The National Service Scheme (NSS) is a
                                    volunteer program launched by the Government
                                    of India with the objective of fostering
                                    <span
                                        class="text-slate-900 font-semibold underline decoration-orange-200 decoration-2 underline-offset-4"
                                        >social consciousness</span
                                    >
                                    and promoting community service among youth.
                                </p>
                                <div
                                    class="grid grid-cols-1 sm:grid-cols-2 gap-4 my-6"
                                >
                                    <div
                                        class="p-3 bg-slate-50 border border-slate-100 rounded text-xs text-slate-600"
                                    >
                                        <strong
                                            class="block text-slate-900 mb-1 tracking-tight uppercase"
                                            >Core Activities</strong
                                        >
                                        Blood donation, literacy campaigns, and
                                        health camps.
                                    </div>
                                    <div
                                        class="p-3 bg-slate-50 border border-slate-100 rounded text-xs text-slate-600"
                                    >
                                        <strong
                                            class="block text-slate-900 mb-1 tracking-tight uppercase"
                                            >Vision</strong
                                        >
                                        Building a sustainable, inclusive
                                        society through empathy.
                                    </div>
                                </div>
                                <p class="leading-relaxed text-slate-600">
                                    NSS volunteers work towards the betterment
                                    of the community, contributing to positive
                                    changes across India through environmental
                                    conservation and health initiatives.
                                </p>
                            </section>

                            <section
                                v-else
                                class="min-h-[200px] flex items-center justify-center border-2 border-dashed border-slate-100 rounded-xl"
                            >
                                <div class="text-center">
                                    <p
                                        class="text-slate-400 font-bold uppercase text-[10px] tracking-widest mb-2"
                                    >
                                        {{ activeTab }} Details
                                    </p>
                                    <p class="text-xs text-slate-500 italic">
                                        Content coming soon...
                                    </p>
                                </div>
                            </section>
                        </div>
                    </transition>
                </main>
            </div>

            <footer
                class="mt-16 pt-8 border-t border-slate-100 flex justify-between items-center"
            >
                <p
                    class="text-[10px] text-slate-400 font-bold uppercase tracking-widest"
                >
                    Join the movement
                </p>
                <button
                    class="bg-orange-600 text-white px-6 py-2 rounded text-xs font-bold hover:bg-orange-700 active:scale-95 transition-all shadow-lg shadow-orange-100"
                >
                    Volunteer Now
                </button>
            </footer>
        </div>
    </div>
</template>

<script setup>
import { ref } from "vue";

const activeTab = ref("about");

const tabs = [
    { id: "about", name: "About NSS" },
    { id: "camps", name: "About Camps" },
    { id: "gallery", name: "Photo Gallery" },
    { id: "news", name: "News & Media" },
    { id: "links", name: "NSS Links" },
];
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.2s ease;
}
.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}
</style>
