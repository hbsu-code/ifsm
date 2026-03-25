<template>
    <header class="w-full sticky top-0 z-50">
        <!-- Top utility bar -->
        <div
            class="bg-[#1B2A4A] text-white/60 text-xs py-2 px-8 flex justify-between items-center"
        >
            <span class="tracking-wide font-medium text-white/80"
                >Government of Maharashtra</span
            >
            <div class="flex gap-1">
                <a
                    v-for="link in topLinks"
                    :key="link"
                    href="#"
                    class="px-3 py-1 rounded-full hover:bg-white/10 hover:text-white transition-all duration-200"
                >
                    {{ link }}
                </a>
            </div>
        </div>

        <!-- Main header -->
        <div
            class="bg-white/95 backdrop-blur-md border-b border-gray-100 px-8 py-3 flex items-center justify-between shadow-sm"
        >
            <div class="flex items-center gap-4">
                <div
                    class="w-14 h-14 rounded-2xl bg-[#1B2A4A]/5 flex items-center justify-center overflow-hidden p-1"
                >
                    <img
                        src="/logo.png"
                        alt="IFSM Logo"
                        class="h-12 w-auto object-contain"
                    />
                </div>
                <div>
                    <p
                        class="text-[10px] font-bold tracking-[0.15em] text-[#C9A84C] uppercase"
                    >
                        Government of Maharashtra
                    </p>
                    <h1
                        class="text-lg font-bold text-[#1B2A4A] leading-tight"
                        style="font-family: Georgia, serif"
                    >
                        Institute of Forensic Science, Mumbai
                    </h1>
                    <p class="text-[10px] text-gray-400 tracking-wide">
                        Excellence in Forensic Education & Research Since 1971
                    </p>
                </div>
            </div>

            <!-- Nav pills -->
            <nav class="hidden lg:flex items-center gap-1">
                <a
                    v-for="item in navItems"
                    :key="item.label"
                    :href="item.href"
                    class="px-4 py-2 rounded-full text-sm font-medium transition-all duration-200"
                    :class="
                        item.active
                            ? 'bg-[#1B2A4A] text-white shadow-md'
                            : 'text-gray-500 hover:bg-gray-100 hover:text-[#1B2A4A]'
                    "
                >
                    {{ item.label }}
                </a>
                <a
                    href="/admissions"
                    class="ml-2 px-5 py-2 rounded-full text-sm font-bold bg-[#C9A84C] text-[#1B2A4A] hover:bg-[#DFC070] transition-all duration-200 shadow-sm"
                >
                    Apply Now
                </a>
            </nav>

            <!-- Mobile menu button -->
            <button class="lg:hidden p-2 rounded-xl bg-gray-100 text-[#1B2A4A]">
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                >
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M4 6h16M4 12h16M4 18h16"
                    />
                </svg>
            </button>
        </div>
    </header>
</template>

<script setup>
const topLinks = ["RTI", "Tenders", "Sitemap", "हिंदी", "मराठी"];
const navItems = [
    { label: "Home", href: "/", active: true },
    { label: "About", href: "/about" },
    { label: "Academics", href: "/academics" },
    { label: "Research", href: "/research" },
    { label: "Faculty", href: "/faculty" },
    { label: "News", href: "/news" },
    { label: "Contact", href: "/contact" },
];
</script>
