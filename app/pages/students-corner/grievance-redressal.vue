<template>
    <div class="min-h-screen flex justify-center px-6 py-20">
        <div
            class="max-w-3xl w-full bg-white rounded-3xl shadow-sm border border-slate-100 p-8 md:p-12"
        >
            <!-- TITLE -->
            <h1 class="text-3xl md:text-4xl font-serif italic text-[#1f3a6d]">
                Grievance Form
            </h1>

            <div class="w-20 h-[2px] bg-[#C8A84B] mt-4 mb-10"></div>

            <!-- FORM -->
            <form class="space-y-6">
                <!-- NAME -->
                <div class="grid md:grid-cols-3 gap-4">
                    <input
                        type="text"
                        placeholder="First Name *"
                        class="input"
                        required
                    />
                    <input
                        type="text"
                        placeholder="Middle Name"
                        class="input"
                    />
                    <input
                        type="text"
                        placeholder="Last Name *"
                        class="input"
                        required
                    />
                </div>

                <!-- GENDER + MARITAL -->
                <div class="grid md:grid-cols-2 gap-4">
                    <select class="input" required>
                        <option disabled selected>Gender *</option>
                        <option>Male</option>
                        <option>Female</option>
                        <option>Other</option>
                    </select>

                    <select class="input">
                        <option disabled selected>Marital Status</option>
                        <option>Single</option>
                        <option>Married</option>
                    </select>
                </div>

                <!-- DOB + CLASS -->
                <div class="grid md:grid-cols-2 gap-4">
                    <input type="date" class="input" required />
                    <input
                        type="text"
                        placeholder="Class *"
                        class="input"
                        required
                    />
                </div>

                <!-- CONTACT -->
                <div class="grid md:grid-cols-2 gap-4">
                    <input
                        type="email"
                        placeholder="Email Address *"
                        class="input"
                        required
                    />
                    <input
                        type="tel"
                        placeholder="Mobile Number *"
                        class="input"
                        required
                    />
                </div>

                <!-- ADDRESS -->
                <textarea
                    placeholder="Address *"
                    class="input h-24"
                    required
                ></textarea>

                <!-- COMPLAINT AGAINST -->
                <input
                    type="text"
                    placeholder="Complaint against (Teacher / Staff / Department) *"
                    class="input"
                    required
                />

                <!-- GRIEVANCE -->
                <textarea
                    placeholder="Grievance (write in detail) *"
                    class="input h-32"
                    required
                ></textarea>

                <!-- BUTTON -->
                <button
                    type="submit"
                    class="w-full bg-[#1f3a6d] text-white py-3 rounded-xl font-semibold hover:bg-[#162c54] transition"
                >
                    Submit
                </button>
            </form>
        </div>
    </div>
</template>

<style scoped>
.input {
    width: 100%;
    padding: 0.75rem 1rem;
    border-radius: 0.75rem;
    border: 1px solid #e5e7eb;
    background: white;
    font-size: 0.95rem;
    outline: none;
    transition: 0.2s;
}

.input:focus {
    border-color: #1f3a6d;
    box-shadow: 0 0 0 2px rgba(31, 58, 109, 0.1);
}
</style>
