<template>
    <div class="min-h-screen flex flex-col">
        <Navbar />

        <!-- <News /> -->
        <main class="flex-grow w-full max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <slot />
        </main>

        <Footer />

        <Developer />
    </div>
</template>

<style>
body {
    margin: 0;
    padding: 0;
}
</style>
