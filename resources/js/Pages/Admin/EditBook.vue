<template>
    <Navbar2/>

    <!--Body-->
    <!-- <div class="grid grid-cols-6 gap-4 m-2"> -->
        <!--Side bar-->

        <!-- <SideMenu/> -->
        
<!--Right Side-->
        <!-- <div class="col-span-5 ... m-2"> -->
            <!--Book Insertion Form-->
                        <div class="flex items-left justify-left">
                            <Link
                                type="button"
                                class="px-8 py-2 m-2 mt-2 font-semibold text-gray-100 bg-gray-900 rounded text-1xl hover:bg-gray-500 hover:text-white"
                                href="/admin/books"
                            >
                                Back
                            </Link>
                        </div>
            <div
                class="flex flex-col w-5/12 px-4 py-8 m-auto bg-gray-800 shadow-md rounded-2xl"
            >
                <div
                    class="self-center text-xl font-bold text-gray-100 sm:text-3xl"
                >
                    Update Book
                </div>

                <div class="">
                <form @submit.prevent="submitForm">
                    <div class="flex flex-col mb-2">
                        <div class="relative">
                            <label class="text-white">
                                    Book No.
                                </label>
                            <input
                                id="book_no"
                                type="text"
                                v-model="formData.book_no"
                                name="book_no"
                                class="w-full py-2 pl-5 pr-4 text-sm placeholder-gray-500 border border-gray-400 rounded-2xl focus:outline-none focus:border-blue-400"
                                placeholder="Enter book number"
                            />
                        </div>
                    </div>
                    <div class="flex flex-col mb-2">
                        <div class="relative">
                            <label class="text-white">
                                    Book ISBN No.
                                </label>
                            <input
                                id="isbn"
                                type="text"
                                v-model="formData.isbn"
                                name="isbn"
                                class="w-full py-2 pl-5 pr-4 text-sm placeholder-gray-500 border border-gray-400 rounded-2xl focus:outline-none focus:border-blue-400"
                                placeholder="Enter book ISBN Number"
                            />
                        </div>
                    </div>
                    <div class="flex flex-col mb-2">
                        <div class="relative">
                            <label class="text-white">
                                    Subject
                                </label>
                            <input
                                id="subject"
                                type="subject"
                                v-model="formData.subject"
                                name="subject"
                                class="w-full py-2 pl-5 pr-4 text-sm placeholder-gray-500 border border-gray-400 rounded-2xl focus:outline-none focus:border-blue-400"
                                placeholder="Enter Subject Name"
                            />
                        </div>
                    </div>
                    <div class="flex flex-col mb-2">
                        <div class="relative">
                            <label class="text-white">
                                    Category
                                </label>
                            <input
                                id="category"
                                type="category"
                                v-model="formData.category"
                                name="category"
                                class="w-full py-2 pl-5 pr-4 text-sm placeholder-gray-500 border border-gray-400 rounded-2xl focus:outline-none focus:border-blue-400"
                                placeholder="Enter category Name"
                            />
                        </div>
                    </div>
                    <div class="flex flex-col mb-2">
                        <div class="relative">
                            <label class="text-white">
                                    Book Name
                                </label>
                            <input
                                id="book_name"
                                type="text"
                                v-model="formData.book_name"
                                name="book_name"
                                class="w-full py-2 pl-5 pr-4 text-sm placeholder-gray-500 border border-gray-400 rounded-2xl focus:outline-none focus:border-blue-400"
                                placeholder="Enter Book Name"
                            />
                        </div>
                    </div>
                    <div class="flex flex-col mb-2">
                        <div class="relative">
                            <label class="text-white">
                                    Author Name 
                                </label>
                            <input
                                id="author"
                                type="text"
                                v-model="formData.author"
                                name="author"
                                class="w-full py-2 pl-5 pr-4 text-sm placeholder-gray-500 border border-gray-400 rounded-2xl focus:outline-none focus:border-blue-400"
                                placeholder="Enter Author Name"
                            />
                        </div>
                    </div>
                    <div class="flex flex-col mb-2">
                        <div class="relative">
                            <label class="text-white">
                                    Publisher
                                </label>
                            <input
                                id="publisher"
                                type="publisher"
                                v-model="formData.publisher"
                                name="publisher"
                                class="w-full py-2 pl-5 pr-4 text-sm placeholder-gray-500 border border-gray-400 rounded-2xl focus:outline-none focus:border-blue-400"
                                placeholder="Enter Publisher Name"
                            />
                        </div>
                    </div>
                    <div class="flex flex-col mb-2">
                        <div class="relative">
                            <label class="text-white">
                                    Edition
                                </label>
                            <input
                                id="edition"
                                type="edition"
                                v-model="formData.edition"
                                name="edition"
                                class="w-full py-2 pl-5 pr-4 text-sm placeholder-gray-500 border border-gray-400 rounded-2xl focus:outline-none focus:border-blue-400"
                                placeholder="Enter Edition"
                            />
                        </div>
                    </div>
                    <div class="flex flex-col mb-2">
                        <div class="relative">
                            <label class="text-white">
                                    Copies
                                </label>
                            <input
                                id="copies"
                                type="copies"
                                v-model="formData.copies"
                                name="copies"
                                class="w-full py-2 pl-5 pr-4 text-sm placeholder-gray-500 border border-gray-400 rounded-2xl focus:outline-none focus:border-blue-400"
                                placeholder="Enter Copies"
                            />
                        </div>
                    </div>

                    <div class="flex items-center justify-center">
                        <button
                            type="submit"
                            class="px-8 py-2 mt-2 font-semibold text-gray-800 bg-white rounded text-1xl hover:bg-gray-600 hover:text-white"
                        >
                            Update
                        </button>
                    </div>
                </form>
            </div>
        </div>
        <div>
            </div>
    <!-- </div>
    </div> -->
</template>

<script>
import { Link } from "@inertiajs/inertia-vue3";
import Navbar2 from "../../Components/Admin/Navbar2";
// import SideMenu from "../../Components/Admin/SideMenu";
import Swal from 'sweetalert2';


import axios from "axios";
export default {
    components: {
        Link,
        Navbar2,
        // SideMenu,
        Swal,
    },
    props: {
        book: {
            type: Object,
            default: {},
        },
    },

    data() {
        return {
            formData: {
                book_no: this.book.book_no,
                isbn: this.book.isbn,
                subject: this.book.subject,
                category: this.book.category,
                book_name: this.book.book_name,
                author: this.book.author,
                publisher: this.book.publisher,
                edition: this.book.edition,
                copies: this.book.copies,
            },
        };
    },

    methods: {
        submitForm() {
            // this.$inertia.post("/admin/book/update/" + this.book.id, {
            //     formData: this.formData,
            // });

                var vm = this;
                axios
                    .post("/admin/book/update/" + this.book.id, {
                        formData: this.formData,
                    })
                    .then((response) => {
                        window.location.href = "/admin/books";
                    vm.showNotification("Book Updated Successfully", "success");
                    });
        },
                showNotification(message, type) {
                Swal.fire({
                    icon: type,
                    text: message,
                    showConfirmButton: false,
                });
        },
    },
};
</script>
