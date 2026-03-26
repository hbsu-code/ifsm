<template>
    <div
        class="min-h-screen bg-white py-12 px-4 font-sans antialiased text-slate-900"
    >
        <div class="max-w-2xl mx-auto">
            <header class="mb-10 border-b border-slate-100 pb-8">
                <div
                    class="inline-block px-2 py-1 rounded bg-red-50 text-red-600 text-[10px] font-bold uppercase tracking-wider mb-3"
                >
                    Campus Safety
                </div>
                <h1
                    class="text-3xl md:text-4xl font-extrabold tracking-tight text-slate-900 mb-4"
                >
                    Discipline & Anti-Ragging
                </h1>
                <p class="text-sm text-slate-500 leading-relaxed max-w-lg">
                    Ensuring a safe, secure, and ragging-free environment for
                    every student on campus through strict adherence to UGC
                    guidelines.
                </p>
            </header>

            <article class="prose prose-slate prose-sm max-w-none">
                <p class="leading-relaxed text-slate-600">
                    The Discipline and Anti-Ragging Committee is a crucial body
                    responsible for maintaining order and ensuring that no
                    incidents of ragging take place. Headed by
                    <span
                        class="text-slate-900 font-semibold underline decoration-red-200 decoration-2 underline-offset-4"
                        >Mr. Santosh Lohakare</span
                    >, the committee is committed to creating a conducive
                    learning environment.
                </p>

                <div
                    class="my-10 bg-slate-50 rounded-xl p-6 border border-slate-100"
                >
                    <h3
                        class="text-xs font-bold uppercase tracking-widest text-slate-400 mb-4 mt-0"
                    >
                        Committee Members
                    </h3>
                    <div
                        class="grid grid-cols-1 sm:grid-cols-2 gap-y-4 gap-x-8"
                    >
                        <div class="flex items-center gap-3">
                            <div
                                class="w-8 h-8 rounded bg-red-100 text-red-600 flex items-center justify-center text-[10px] font-bold"
                            >
                                SL
                            </div>
                            <div>
                                <p class="text-sm font-bold m-0 text-slate-800">
                                    Mr. Santosh Lohakare
                                </p>
                                <p
                                    class="text-[10px] text-slate-500 m-0 uppercase tracking-wide"
                                >
                                    Chairman
                                </p>
                            </div>
                        </div>
                        <div class="flex items-center gap-3 text-slate-700">
                            <div
                                class="w-1.5 h-1.5 rounded-full bg-slate-300"
                            ></div>
                            <p class="text-sm font-medium m-0">
                                Mr. N.M. Fatangare
                            </p>
                        </div>
                        <div class="flex items-center gap-3 text-slate-700">
                            <div
                                class="w-1.5 h-1.5 rounded-full bg-slate-300"
                            ></div>
                            <p class="text-sm font-medium m-0">
                                Dr. Malojirao Bhosale
                            </p>
                        </div>
                        <div class="flex items-center gap-3 text-slate-700">
                            <div
                                class="w-1.5 h-1.5 rounded-full bg-slate-300"
                            ></div>
                            <p class="text-sm font-medium m-0">
                                Ms. Bhagyashree Kulkarni
                            </p>
                        </div>
                    </div>
                </div>

                <h4 class="text-slate-900 font-bold mb-2">
                    Core Responsibilities
                </h4>
                <ul class="text-slate-600 space-y-2 list-none p-0">
                    <li class="flex gap-3 text-sm">
                        <span class="text-red-500 font-bold">•</span>
                        Ensuring all students follow the institute's code of
                        conduct.
                    </li>
                    <li class="flex gap-3 text-sm">
                        <span class="text-red-500 font-bold">•</span>
                        Conducting regular interactions to address student
                        grievances effectively.
                    </li>
                    <li class="flex gap-3 text-sm">
                        <span class="text-red-500 font-bold">•</span>
                        Acting as mentors to provide academic and personal
                        support.
                    </li>
                </ul>

                <p class="leading-relaxed text-slate-600 mt-8">
                    Overall, our members are dedicated to zero-tolerance
                    policies regarding campus misconduct, working tirelessly to
                    uphold the high standards of excellence and safety our
                    institution is known for.
                </p>
            </article>

            <footer class="mt-12 pt-8 border-t border-slate-100">
                <div
                    class="flex flex-col sm:flex-row justify-between items-center gap-4 bg-red-600 rounded-lg p-6 text-white shadow-lg shadow-red-100"
                >
                    <div>
                        <p
                            class="text-xs font-bold uppercase tracking-widest opacity-80 mb-1"
                        >
                            Emergency Help
                        </p>
                        <p class="text-lg font-bold">Report an Incident</p>
                    </div>
                    <button
                        @click="$router.push('/grievance')"
                        class="bg-white text-red-600 px-6 py-2 rounded font-bold text-xs hover:bg-slate-50 transition-all shadow-sm"
                    >
                        Lodge Complaint
                    </button>
                </div>
            </footer>
        </div>
    </div>
</template>

<script setup>
// Navigation or Modal logic can be added here
</script>

<style scoped>
/* Refined spacing for list items */
li {
    margin-bottom: 0.5rem;
}
</style>
