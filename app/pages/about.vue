<template>
    <section class="bg-[#f6f3ef] min-h-screen py-16 px-6 md:px-16">
        <div class="max-w-7xl mx-auto grid md:grid-cols-2 gap-12 items-center">
            <!-- LEFT: Image Card -->
            <div class="relative">
                <div
                    class="bg-gray-200 rounded-2xl h-[400px] w-full overflow-hidden"
                >
                    <!-- <img
                        src="/college-photo.jpg"
                        class="w-full h-full object-cover"
                        @error="(e) => (e.target.style.display = 'none')"
                    /> -->
                </div>

                <!-- EST Badge -->
                <div
                    class="absolute -top-5 -left-5 bg-[#1e3557] text-white px-5 py-3 rounded-xl shadow-lg"
                >
                    <p class="text-xs tracking-widest">EST.</p>
                    <p class="text-lg font-bold">2009</p>
                </div>

                <!-- NAAC Badge -->
                <div
                    class="absolute -bottom-5 left-10 bg-white shadow-md rounded-xl px-5 py-3 flex items-center gap-3"
                >
                    <div class="bg-yellow-100 p-2 rounded-full">🏅</div>
                    <div>
                        <p class="text-sm font-semibold text-gray-700">
                            NAAC Accredited
                        </p>
                        <p class="text-xs text-gray-500">
                            Govt. of Maharashtra
                        </p>
                    </div>
                </div>
            </div>

            <!-- RIGHT: Content -->
            <div>
                <!-- Label -->
                <span
                    class="text-xs bg-gray-200 px-4 py-1 rounded-full text-gray-600 tracking-wide"
                >
                    ABOUT THE INSTITUTE
                </span>

                <!-- Title -->
                <h1
                    class="text-3xl md:text-4xl font-bold text-[#1e3557] mt-4 leading-snug"
                >
                    Maharashtra's Centre for <br />
                    Forensic Excellence
                </h1>

                <!-- Description -->
                <p class="text-gray-600 mt-4 text-sm leading-relaxed">
                    Institute of Forensic Science, Mumbai was established in
                    2009 by the Government of Maharashtra. It focuses on
                    forensic education, research, and training professionals to
                    support the criminal justice system.
                </p>

                <p class="text-gray-600 mt-3 text-sm leading-relaxed">
                    The institute offers undergraduate, postgraduate, and
                    diploma programs across multiple forensic disciplines.
                </p>

                <!-- Cards -->
                <div class="grid grid-cols-2 gap-4 mt-8">
                    <div class="bg-[#efeae4] p-4 rounded-xl">
                        <p class="font-semibold text-[#1e3557]">Our Mission</p>
                        <p class="text-xs text-gray-600 mt-1">
                            Train skilled forensic professionals for
                            investigative excellence.
                        </p>
                    </div>

                    <div class="bg-[#efeae4] p-4 rounded-xl">
                        <p class="font-semibold text-[#1e3557]">Our Vision</p>
                        <p class="text-xs text-gray-600 mt-1">
                            Become a global centre for forensic science
                            education and research.
                        </p>
                    </div>

                    <div class="bg-[#efeae4] p-4 rounded-xl">
                        <p class="font-semibold text-[#1e3557]">Research</p>
                        <p class="text-xs text-gray-600 mt-1">
                            Advanced work in DNA, toxicology, and cyber
                            forensics.
                        </p>
                    </div>

                    <div class="bg-[#efeae4] p-4 rounded-xl">
                        <p class="font-semibold text-[#1e3557]">Casework</p>
                        <p class="text-xs text-gray-600 mt-1">
                            Supporting law enforcement with forensic analysis.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
useHead({
    title: "About - Institute of Forensic Science",
});
</script>
