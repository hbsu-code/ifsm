<template>
    <section class="py-20 px-6">
        <div class="max-w-7xl mx-auto grid lg:grid-cols-2 gap-16 items-center">
            <!-- LEFT: IMAGE -->
            <div class="relative">
                <div class="rounded-2xl overflow-hidden shadow-md">
                    <img
                        src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2"
                        alt="Director"
                        class="w-full h-full object-cover"
                    />
                </div>

                <!-- Floating Tag -->
                <div
                    class="absolute bottom-4 left-4 bg-white px-4 py-2 rounded-xl shadow text-sm"
                >
                    <p class="text-gray-400 text-xs">Leadership</p>
                    <p class="font-semibold text-[#1f2a44]">Vision 2026</p>
                </div>
            </div>

            <!-- RIGHT: CONTENT -->
            <div>
                <!-- Badge -->
                <div
                    class="inline-flex items-center gap-2 bg-white px-4 py-1 rounded-full shadow-sm border text-sm text-gray-600 mb-6"
                >
                    <span class="w-2 h-2 bg-yellow-400 rounded-full"></span>
                    Director’s Message
                </div>

                <!-- Heading -->
                <h2
                    class="text-4xl md:text-5xl font-extrabold text-[#1f2a44] leading-tight"
                >
                    Leading with Vision,<br />
                    Building the
                    <span class="text-yellow-500">Future.</span>
                </h2>

                <!-- Quote -->
                <p class="mt-6 text-lg text-gray-600 leading-relaxed max-w-xl">
                    In a world defined by rapid change, our compass remains the
                    same:
                    <span class="font-semibold text-[#1f2a44]">
                        empathy-driven innovation.
                    </span>
                    We don’t just build systems—we build bridges between human
                    potential and scientific truth.
                </p>

                <p class="mt-4 text-gray-500 leading-relaxed max-w-xl">
                    Every decision we make is rooted in integrity, research, and
                    a deep commitment to justice and societal impact.
                </p>

                <!-- Signature -->
                <div class="mt-10 flex items-center gap-6">
                    <div
                        class="h-12 w-[2px] bg-gradient-to-b from-[#1f2a44] to-transparent"
                    ></div>

                    <div>
                        <h5 class="text-2xl font-signature text-[#1f2a44]">
                            Dr. Jane Sterling
                        </h5>
                        <p
                            class="text-sm text-gray-400 uppercase tracking-widest"
                        >
                            Founding Director
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Inter:wght@300;400;600;800&display=swap");

.font-signature {
    font-family: "Dancing Script", cursive;
}

section {
    font-family: "Inter", sans-serif;
}
</style>
