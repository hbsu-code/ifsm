<template>
    <div
        class="min-h-screen bg-white py-10 px-4 md:px-8 font-sans text-slate-700"
    >
        <div class="mx-auto">
            <header class="mb-10 border-b pb-6">
                <h1 class="text-3xl font-bold text-[#1B2A4A] mb-1">
                    Code of Conduct
                </h1>
                <p
                    class="text-xs uppercase tracking-widest text-slate-400 font-semibold"
                >
                    UGC Professional Ethics
                </p>
            </header>

            <div class="flex flex-col lg:flex-row gap-10">
                <aside class="lg:w-64 shrink-0">
                    <nav class="flex flex-col space-y-1">
                        <button
                            v-for="section in conductData"
                            :key="section.id"
                            @click="activeSection = section.id"
                            :class="[
                                'text-left px-4 py-2.5 text-sm font-semibold rounded-md transition-colors',
                                activeSection === section.id
                                    ? 'bg-[#1B2A4A] text-white'
                                    : 'text-slate-500 hover:bg-slate-100 hover:text-slate-900',
                            ]"
                        >
                            {{ section.shortTitle || section.title }}
                        </button>
                    </nav>
                </aside>

                <main class="flex-1">
                    <transition name="fade" mode="out-in">
                        <div :key="currentContent.id">
                            <h2
                                class="text-xl font-bold text-[#1B2A4A] mb-4 pb-2 border-b-2 border-[#C8A84B] inline-block"
                            >
                                {{ currentContent.title }}
                            </h2>

                            <p
                                class="text-sm text-slate-500 mb-8 leading-relaxed italic"
                            >
                                "{{ currentContent.intro }}"
                            </p>

                            <div
                                class="space-y-0 border-l-2 border-slate-100 ml-3"
                            >
                                <div
                                    v-for="(
                                        point, index
                                    ) in currentContent.points"
                                    :key="index"
                                    class="relative pl-8 pb-6 last:pb-0"
                                >
                                    <div
                                        class="absolute -left-[9px] top-1.5 w-4 h-4 rounded-full bg-white border-2 border-[#C8A84B]"
                                    ></div>

                                    <p
                                        class="text-[14px] leading-snug text-slate-600"
                                    >
                                        {{ point }}
                                    </p>
                                </div>
                            </div>
                        </div>
                    </transition>
                </main>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, computed } from "vue";

const activeSection = ref("responsibilities");

const currentContent = computed(() => {
    return conductData.find((s) => s.id === activeSection.value);
});

const conductData = [
    {
        id: "responsibilities",
        shortTitle: "Responsibilities",
        title: "Teachers & Responsibilities",
        intro: "Teachers must conduct themselves in accordance with the ideals of the profession.",
        points: [
            "Adhere to a responsible pattern of conduct expected by the community.",
            "Manage private affairs consistent with professional dignity.",
            "Seek continuous professional growth through study and research.",
            "Contribute to knowledge via professional meetings and seminars.",
            "Maintain active membership in professional organizations.",
            "Perform teaching and research duties conscientiously.",
            "Assist in institutional functions like admissions and exams.",
            "Participate in community service and extra-curricular activities.",
        ],
    },
    {
        id: "students",
        shortTitle: "Students",
        title: "Teachers & Students",
        intro: "Respect the right and dignity of the student in expressing opinions.",
        points: [
            "Deal fairly and impartially regardless of background.",
            "Recognize differences in aptitude and meet individual needs.",
            "Encourage attainment and personality development.",
            "Inculcate scientific outlook and respect for physical labor.",
            "Avoid vindictive behavior towards students.",
            "Assess merit solely on student attainment.",
            "Provide guidance beyond class hours without reward.",
            "Refrain from inciting students against colleagues or administration.",
        ],
    },
    {
        id: "colleagues",
        shortTitle: "Colleagues",
        title: "Teachers & Colleagues",
        intro: "Treat others as you wish to be treated.",
        points: [
            "Speak respectfully of teachers and render assistance.",
            "Refrain from lodging unsubstantiated allegations.",
            "Avoid discrimination based on caste, creed, or race.",
        ],
    },
    {
        id: "authorities",
        shortTitle: "Authorities",
        title: "Teachers & Authorities",
        intro: "Adhere to procedures consistent with the profession.",
        points: [
            "Refrain from undertaking employment like private tuitions.",
            "Co-operate in institutional policy formulation.",
            "Adhere to contract conditions and give due notice for changes.",
            "Refrain from taking leave except on unavoidable grounds.",
        ],
    },
    {
        id: "society",
        shortTitle: "Society",
        title: "Teachers & Society",
        intro: "Education is a public service.",
        points: [
            "Improve community education and moral life.",
            "Be aware of social problems and progress.",
            "Perform citizenship duties and community activities.",
            "Refrain from promoting communal hatred; work for National Integration.",
        ],
    },
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
