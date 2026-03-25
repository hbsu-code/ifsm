<template>
    <section class="bg-[#f6f3ef] min-h-screen py-16 px-6 md:px-16">
        <div class="max-w-7xl mx-auto">
            <!-- TOP GRID -->
            <div class="grid md:grid-cols-2 gap-12 items-center">
                <!-- LEFT: Image -->
                <div class="relative">
                    <div
                        class="bg-gray-200 rounded-2xl h-[420px] w-full overflow-hidden"
                    >
                        <!-- <img
                            src="/college-photo.jpg"
                            class="w-full h-full object-cover"
                            @error="(e) => (e.target.style.display = 'none')"
                        /> -->
                    </div>

                    <!-- EST -->
                    <div
                        class="absolute -top-5 -left-5 bg-[#1e3557] text-white px-5 py-3 rounded-xl shadow-lg"
                    >
                        <p class="text-xs tracking-widest">EST.</p>
                        <p class="text-lg font-bold">2009</p>
                    </div>

                    <!-- NAAC -->
                    <div
                        class="absolute -bottom-5 left-10 bg-white shadow-md rounded-xl px-5 py-3 flex items-center gap-3"
                    >
                        <div class="bg-yellow-100 p-2 rounded-full">🏅</div>
                        <div>
                            <p class="text-sm font-semibold text-gray-700">
                                NAAC Accredited
                            </p>
                            <p class="text-xs text-gray-500">B+ Grade</p>
                        </div>
                    </div>
                </div>

                <!-- RIGHT -->
                <div>
                    <span
                        class="text-xs bg-gray-200 px-4 py-1 rounded-full text-gray-600 tracking-wide"
                    >
                        ABOUT THE INSTITUTE
                    </span>

                    <h1
                        class="text-3xl md:text-4xl font-bold text-[#1e3557] mt-4 leading-snug"
                    >
                        Maharashtra's Centre for <br />
                        Forensic Excellence
                    </h1>

                    <!-- QUOTE -->
                    <blockquote
                        class="mt-6 border-l-4 border-[#1e3557] pl-4 italic text-gray-600"
                    >
                        “Crime is common. Logic is rare. Therefore it is upon
                        the logic rather than upon the crime that you should
                        dwell.”
                        <span class="block mt-2 text-sm text-gray-500">
                            ― Arthur Conan Doyle
                        </span>
                    </blockquote>

                    <p class="text-gray-600 mt-6 text-sm leading-relaxed">
                        Institute of Forensic Science was established in 2009 by
                        the Department of Higher and Technical Education,
                        Government of Maharashtra, with the aim of building a
                        world-class forensic education system.
                    </p>

                    <!-- CARDS -->
                    <div class="grid grid-cols-2 gap-4 mt-8">
                        <div class="bg-[#efeae4] p-4 rounded-xl">
                            <p class="font-semibold text-[#1e3557]">
                                Our Mission
                            </p>
                            <p class="text-xs text-gray-600 mt-1">
                                Educate and train professionals to combat modern
                                crime.
                            </p>
                        </div>

                        <div class="bg-[#efeae4] p-4 rounded-xl">
                            <p class="font-semibold text-[#1e3557]">
                                Our Vision
                            </p>
                            <p class="text-xs text-gray-600 mt-1">
                                Become a global forensic excellence hub.
                            </p>
                        </div>

                        <div class="bg-[#efeae4] p-4 rounded-xl">
                            <p class="font-semibold text-[#1e3557]">Research</p>
                            <p class="text-xs text-gray-600 mt-1">
                                DNA, cyber forensics & toxicology innovation.
                            </p>
                        </div>

                        <div class="bg-[#efeae4] p-4 rounded-xl">
                            <p class="font-semibold text-[#1e3557]">Casework</p>
                            <p class="text-xs text-gray-600 mt-1">
                                Supporting law enforcement & justice system.
                            </p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- FULL CONTENT SECTION -->
            <div
                class="mt-20 max-w-4xl mx-auto space-y-6 text-gray-700 leading-relaxed text-[15px]"
            >
                <h2 class="text-2xl font-bold text-[#1e3557]">
                    About Institute
                </h2>

                <p>
                    Institute of Forensic Science offers a wide range of
                    programs including B.Sc. and M.Sc. in Forensic Science with
                    specializations in Questioned Documents, Fingerprints and
                    Biometrics, Digital and Cyber Forensics, Forensic Physics &
                    Ballistics, Forensic Chemistry & Toxicology, and Forensic
                    Biology, Serology & DNA Fingerprinting. It also offers
                    postgraduate diploma courses and plans to introduce
                    short-term professional courses.
                </p>

                <p>
                    The institute is a constituent college of Dr. Homi Bhabha
                    State University, Mumbai, and is located in the historic
                    Institute of Science campus. The campus blends heritage
                    architecture with modern infrastructure including advanced
                    laboratories and libraries.
                </p>

                <p>
                    Academically, the institute consists of seven
                    multidisciplinary departments: Forensic Science, Chemistry,
                    Physics, Biology, Psychology, Digital & Cyber Forensics, and
                    Law. The goal is to create industry-ready professionals
                    capable of supporting criminal justice systems, corporates,
                    and financial institutions.
                </p>

                <p>
                    The institute achieved a B+ Grade in its NAAC evaluation,
                    reflecting its commitment to academic excellence and
                    continuous improvement.
                </p>

                <p>
                    Moving forward, the institute continues to strengthen its
                    academic foundation through innovation, collaboration, and
                    holistic student development.
                </p>

                <p>
                    NEP-2020 has been implemented from academic session 2023–24,
                    introducing a flexible credit-based curriculum. The CBCS
                    system allows students to choose interdisciplinary subjects
                    and build dynamic career pathways aligned with modern
                    industry needs.
                </p>
            </div>
        </div>
    </section>
</template>

<script setup>
useHead({
    title: "About - Institute of Forensic Science",
});
</script>
