<template>
    <div class="min-h-screen bg-slate-50 py-8 font-sans">
        <div class="max-w-3xl mx-auto px-4">
            <div class="mb-6 px-2">
                <h1 class="text-2xl font-bold text-slate-800">
                    Grievance Form
                </h1>
                <p class="text-slate-500 text-sm">
                    Please fill in the details below to lodge your complaint.
                </p>
            </div>

            <div
                class="bg-white rounded-xl shadow-md border border-slate-200 overflow-hidden"
            >
                <form
                    @submit.prevent="handleSubmit"
                    class="p-6 md:p-8 space-y-6"
                >
                    <section>
                        <h2
                            class="text-xs font-uppercase tracking-wider font-bold text-blue-600 mb-4 uppercase"
                        >
                            1. Personal Information
                        </h2>
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                            <div>
                                <label
                                    class="block text-xs font-semibold text-slate-600 mb-1"
                                    >First Name *</label
                                >
                                <input
                                    v-model="form.firstName"
                                    type="text"
                                    placeholder="John"
                                    class="w-full px-3 py-2 text-sm rounded-md border border-slate-300 focus:ring-2 focus:ring-blue-500 outline-none"
                                    required
                                />
                            </div>
                            <div>
                                <label
                                    class="block text-xs font-semibold text-slate-600 mb-1"
                                    >Middle Name *</label
                                >
                                <input
                                    v-model="form.middleName"
                                    type="text"
                                    placeholder="Q."
                                    class="w-full px-3 py-2 text-sm rounded-md border border-slate-300 focus:ring-2 focus:ring-blue-500 outline-none"
                                    required
                                />
                            </div>
                            <div>
                                <label
                                    class="block text-xs font-semibold text-slate-600 mb-1"
                                    >Last Name *</label
                                >
                                <input
                                    v-model="form.lastName"
                                    type="text"
                                    placeholder="Doe"
                                    class="w-full px-3 py-2 text-sm rounded-md border border-slate-300 focus:ring-2 focus:ring-blue-500 outline-none"
                                    required
                                />
                            </div>
                        </div>

                        <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mt-4">
                            <div class="col-span-1">
                                <label
                                    class="block text-xs font-semibold text-slate-600 mb-1"
                                    >Gender *</label
                                >
                                <select
                                    v-model="form.gender"
                                    class="w-full px-3 py-2 text-sm rounded-md border border-slate-300 bg-white focus:ring-2 focus:ring-blue-500 outline-none"
                                    required
                                >
                                    <option value="" disabled>Select</option>
                                    <option>Male</option>
                                    <option>Female</option>
                                    <option>Other</option>
                                </select>
                            </div>
                            <div class="col-span-1">
                                <label
                                    class="block text-xs font-semibold text-slate-600 mb-1"
                                    >Marital Status</label
                                >
                                <select
                                    v-model="form.marital"
                                    class="w-full px-3 py-2 text-sm rounded-md border border-slate-300 bg-white focus:ring-2 focus:ring-blue-500 outline-none"
                                >
                                    <option>Single</option>
                                    <option>Married</option>
                                </select>
                            </div>
                            <div class="col-span-2">
                                <label
                                    class="block text-xs font-semibold text-slate-600 mb-1"
                                    >DOB *</label
                                >
                                <input
                                    v-model="form.dob"
                                    type="date"
                                    class="w-full px-3 py-2 text-sm rounded-md border border-slate-300 focus:ring-2 focus:ring-blue-500 outline-none"
                                    required
                                />
                            </div>
                        </div>
                    </section>

                    <section class="pt-4 border-t border-slate-100">
                        <h2
                            class="text-xs font-uppercase tracking-wider font-bold text-blue-600 mb-4 uppercase"
                        >
                            2. Contact & Academic
                        </h2>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="md:col-span-1">
                                <label
                                    class="block text-xs font-semibold text-slate-600 mb-1"
                                    >Class/Course *</label
                                >
                                <input
                                    v-model="form.class"
                                    type="text"
                                    placeholder="e.g. FY-IT"
                                    class="w-full px-3 py-2 text-sm rounded-md border border-slate-300 focus:ring-2 focus:ring-blue-500 outline-none"
                                    required
                                />
                            </div>
                            <div class="md:col-span-1">
                                <label
                                    class="block text-xs font-semibold text-slate-600 mb-1"
                                    >Mobile *</label
                                >
                                <input
                                    v-model="form.mobile"
                                    type="tel"
                                    placeholder="+123..."
                                    class="w-full px-3 py-2 text-sm rounded-md border border-slate-300 focus:ring-2 focus:ring-blue-500 outline-none"
                                    required
                                />
                            </div>
                            <div class="md:col-span-2">
                                <label
                                    class="block text-xs font-semibold text-slate-600 mb-1"
                                    >Email Address *</label
                                >
                                <input
                                    v-model="form.email"
                                    type="email"
                                    placeholder="john@example.com"
                                    class="w-full px-3 py-2 text-sm rounded-md border border-slate-300 focus:ring-2 focus:ring-blue-500 outline-none"
                                    required
                                />
                            </div>
                            <div class="md:col-span-2">
                                <label
                                    class="block text-xs font-semibold text-slate-600 mb-1"
                                    >Address *</label
                                >
                                <textarea
                                    v-model="form.address"
                                    rows="2"
                                    class="w-full px-3 py-2 text-sm rounded-md border border-slate-300 focus:ring-2 focus:ring-blue-500 outline-none resize-none"
                                    required
                                ></textarea>
                            </div>
                        </div>
                    </section>

                    <section class="pt-4 border-t border-slate-100">
                        <h2
                            class="text-xs font-uppercase tracking-wider font-bold text-red-600 mb-4 uppercase"
                        >
                            3. Grievance Details
                        </h2>
                        <div class="space-y-4">
                            <div>
                                <label
                                    class="block text-xs font-semibold text-slate-600 mb-1"
                                    >Complaint Against *</label
                                >
                                <input
                                    v-model="form.against"
                                    type="text"
                                    placeholder="Teacher / Dept / Staff Name"
                                    class="w-full px-3 py-2 text-sm rounded-md border border-slate-300 focus:ring-2 focus:ring-red-400 outline-none"
                                    required
                                />
                            </div>
                            <div>
                                <label
                                    class="block text-xs font-semibold text-slate-600 mb-1"
                                    >Description *</label
                                >
                                <textarea
                                    v-model="form.grievance"
                                    rows="3"
                                    placeholder="Provide brief details..."
                                    class="w-full px-3 py-2 text-sm rounded-md border border-slate-300 focus:ring-2 focus:ring-red-400 outline-none"
                                    required
                                ></textarea>
                            </div>
                        </div>
                    </section>

                    <div class="flex items-center justify-end gap-3 pt-2">
                        <button
                            type="button"
                            @click="resetForm"
                            class="text-xs font-semibold text-slate-500 hover:text-slate-800 transition-colors"
                        >
                            Reset
                        </button>
                        <button
                            type="submit"
                            class="px-6 py-2 bg-blue-600 text-white text-sm font-bold rounded-lg shadow-sm hover:bg-blue-700 active:scale-95 transition-all"
                        >
                            Submit Form
                        </button>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script setup>
import { reactive } from "vue";

const initialForm = {
    firstName: "",
    middleName: "",
    lastName: "",
    gender: "",
    marital: "Single",
    dob: "",
    class: "",
    email: "",
    mobile: "",
    address: "",
    against: "",
    grievance: "",
};

const form = reactive({ ...initialForm });

const handleSubmit = () => {
    console.log("Submitted Data:", JSON.stringify(form, null, 2));
    alert("Submitted successfully.");
};

const resetForm = () => {
    if (confirm("Clear form?")) {
        Object.assign(form, initialForm);
    }
};
</script>
