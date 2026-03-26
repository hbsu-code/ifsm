<template>
    <div
        class="min-h-screen bg-white py-12 px-4 font-sans antialiased text-slate-900"
    >
        <div class="max-w-2xl mx-auto">
            <header class="mb-10 border-b border-slate-100 pb-8">
                <h1
                    class="text-3xl md:text-4xl font-extrabold tracking-tight text-slate-900 mb-4"
                >
                    Placement Cell
                </h1>
                <div class="flex items-center gap-4">
                    <div
                        class="h-12 w-12 rounded-full bg-slate-100 flex items-center justify-center border border-slate-200 text-slate-600 font-bold text-sm"
                    >
                        DB
                    </div>
                    <div>
                        <p class="text-sm font-bold text-slate-900">
                            Dr. Deepika Bhandari
                        </p>
                        <p class="text-xs text-blue-600 font-medium">
                            Head of Placement & Career Services
                        </p>
                    </div>
                </div>
            </header>

            <article
                class="prose prose-slate prose-sm sm:prose-base max-w-none"
            >
                <p
                    class="leading-relaxed text-slate-600 first-letter:text-4xl first-letter:font-bold first-letter:text-slate-900 first-letter:mr-1 first-letter:float-left"
                >
                    The placement cell at our institute is headed by
                    <span
                        class="text-slate-900 font-semibold underline decoration-blue-200 decoration-2 underline-offset-4"
                        >Dr. Deepika Bhandari</span
                    >, who has done an excellent job of creating a dynamic and
                    vibrant platform for students, alumni, and faculty to
                    exchange information about job openings and references.
                </p>

                <p class="leading-relaxed text-slate-600 mt-6">
                    The group on social media has proven to be a valuable
                    resource for both current students and alumni, as they can
                    access a wide range of opportunities across various
                    industries and sectors. Dr. Bhandari's leadership and vision
                    have enabled the placement cell to be proactive in reaching
                    out to potential employers, organizing job fairs, and
                    offering guidance and support to students on career-related
                    matters.
                </p>

                <div
                    class="my-8 bg-slate-50 rounded-lg p-5 border-l-4 border-blue-600 flex items-start gap-4"
                >
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-5 w-5 text-blue-600 mt-1 shrink-0"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"
                        />
                    </svg>
                    <p class="text-sm text-slate-700 leading-snug m-0">
                        The placement cell's efforts have resulted in a
                        <strong class="text-slate-900"
                            >high placement rate</strong
                        >
                        for students, earning a reputation for being one of the
                        most effective and efficient cells in the region.
                    </p>
                </div>

                <p class="leading-relaxed text-slate-600 mt-6">
                    Dr. Bhandari and her team are dedicated to ensuring that
                    students are equipped with the skills and resources they
                    need to succeed in their chosen careers, and they continue
                    to work tirelessly to maintain the placement cell's high
                    standards of excellence.
                </p>
            </article>

            <footer
                class="mt-12 pt-8 border-t border-slate-100 flex justify-between items-center"
            >
                <button
                    class="text-xs font-bold uppercase tracking-widest text-blue-600 hover:text-blue-800 transition-colors"
                >
                    Download Report →
                </button>
                <button
                    class="bg-slate-900 text-white px-5 py-2 rounded text-xs font-bold hover:bg-slate-800 transition-all shadow-sm"
                >
                    Get in Touch
                </button>
            </footer>
        </div>
    </div>
</template>

<script setup></script>

<style scoped>
/* Target the first letter for a classic editorial look */
.prose p:first-of-type::first-letter {
    line-height: 1;
    margin-top: 0.1em;
}
</style>
