<template>
    <div
        class="min-h-screen bg-white py-12 px-4 font-sans antialiased text-slate-900"
    >
        <div class="max-w-2xl mx-auto">
            <header class="mb-10 border-b border-slate-100 pb-8">
                <div
                    class="inline-block px-2 py-1 rounded bg-indigo-50 text-indigo-600 text-[10px] font-bold uppercase tracking-wider mb-3"
                >
                    Internal Complaints Committee (ICC)
                </div>
                <h1
                    class="text-3xl md:text-4xl font-extrabold tracking-tight text-slate-900 mb-4"
                >
                    Anti-Sexual Harassment Cell
                </h1>
                <p class="text-sm text-slate-500 leading-relaxed max-w-lg">
                    Upholding a zero-tolerance policy to ensure a safe,
                    inclusive, and dignified environment for all students and
                    staff.
                </p>
            </header>

            <article class="prose prose-slate prose-sm max-w-none">
                <p class="leading-relaxed text-slate-600">
                    Our institute is committed to a harassment-free campus.
                    Guided by the
                    <span
                        class="text-slate-900 font-semibold underline decoration-indigo-200 decoration-2 underline-offset-4"
                        >Vishakha Guidelines</span
                    >
                    (Supreme Court, 1997), we have established a robust
                    framework for the prevention, prohibition, and redressal of
                    sexual harassment.
                </p>

                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 my-8">
                    <div
                        class="p-4 border border-slate-100 rounded-lg bg-slate-50/50"
                    >
                        <h3
                            class="text-xs font-bold text-indigo-600 uppercase tracking-tight mb-2"
                        >
                            Legal Framework
                        </h3>
                        <p class="text-xs text-slate-600 leading-normal m-0">
                            Strict adherence to Vishakha Guidelines and the POSH
                            Act for all institutional proceedings.
                        </p>
                    </div>
                    <div
                        class="p-4 border border-slate-100 rounded-lg bg-slate-50/50"
                    >
                        <h3
                            class="text-xs font-bold text-indigo-600 uppercase tracking-tight mb-2"
                        >
                            Confidentiality
                        </h3>
                        <p class="text-xs text-slate-600 leading-normal m-0">
                            All complaints are handled by an impartial committee
                            in a highly sensitive and private manner.
                        </p>
                    </div>
                </div>

                <h4 class="text-slate-900 font-bold mb-3">Our Approach</h4>
                <div class="space-y-4">
                    <div class="flex gap-4">
                        <div
                            class="flex-none w-1 rounded-full bg-indigo-100"
                        ></div>
                        <p class="text-sm text-slate-600 leading-relaxed m-0">
                            <strong class="text-slate-800"
                                >Dedicated Committee:</strong
                            >
                            We have appointed experienced members trained to
                            provide support to complainants and ensure
                            appropriate action against the accused.
                        </p>
                    </div>
                    <div class="flex gap-4">
                        <div
                            class="flex-none w-1 rounded-full bg-indigo-100"
                        ></div>
                        <p class="text-sm text-slate-600 leading-relaxed m-0">
                            <strong class="text-slate-800"
                                >Awareness & Prevention:</strong
                            >
                            Regular workshops and seminars are conducted to
                            educate the campus community on recognizing and
                            preventing harassment.
                        </p>
                    </div>
                </div>

                <p
                    class="leading-relaxed text-slate-600 mt-8 italic border-l-2 border-slate-100 pl-4 text-xs"
                >
                    By fostering a culture of mutual respect and creating
                    awareness, we aim to maintain a campus free from
                    discrimination and harassment.
                </p>
            </article>

            <footer class="mt-12 pt-8 border-t border-slate-100">
                <div
                    class="flex flex-col sm:flex-row justify-between items-center gap-6"
                >
                    <div class="text-center sm:text-left">
                        <p
                            class="text-xs font-bold text-slate-400 uppercase tracking-widest mb-1"
                        >
                            Need Support?
                        </p>
                        <p
                            class="text-sm font-medium text-slate-700 underline decoration-indigo-500 underline-offset-4 decoration-dotted cursor-pointer"
                        >
                            View ICC Member Contacts
                        </p>
                    </div>
                    <button
                        @click="$router.push('/grievance')"
                        class="w-full sm:w-auto bg-indigo-600 text-white px-8 py-2.5 rounded shadow-lg shadow-indigo-100 text-xs font-bold hover:bg-indigo-700 active:scale-95 transition-all"
                    >
                        Lodge a Private Complaint
                    </button>
                </div>
            </footer>
        </div>
    </div>
</template>

<script setup></script>

<style scoped>
/* Optional: Refine link animations */
.decoration-dotted:hover {
    text-decoration-style: solid;
    color: #4f46e5;
}
</style>
