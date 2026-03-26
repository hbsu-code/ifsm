<template>
    <div class="min-h-screen bg-[#fcfcf9] flex flex-col">
        <Navbar />

        <main class="flex-grow w-full max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <slot />
        </main>

        <Footer />
        <Developer />
    </div>
</template>

<style>
body {
    background-color: #fcfcf9; /* Or your preferred white shade */
    margin: 0;
    padding: 0;
}
</style>
