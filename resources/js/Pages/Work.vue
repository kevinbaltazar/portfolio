<template>
    <layout>
        <div class="container mx-auto sm:px-6 lg:px-8 z-0">
            <div class="absolute mt-20 ml-16 w-10/12 m-auto focus:outline-none">
                <h1 class="text-5xl font-bold -ml-1 text-green-300">Projects</h1> 
                <p class="text-lg text-secondary leading-loose mt-6 text-gray-300">Here are the projects I've done so far..</p>
                <div class="mt-16 grid grid-cols-2 gap-10 px-5 h-44">
                    <!-- grid -->
                    <div class="bg-gray-900 p-6 transition duration-500 ease-in-out transform hover:-translate-y-1 hover:scale-110">
                        <h1 class="text-2xl text-white font-medium">Portfolio</h1>
                        <p class="text-gray-300 mt-4">My personal website and project listing that you are on this page right now.</p>
                        <div class="mt-4 flex flex-row gap-3 text-gray-300">
                            <a href="#">
                                <div class="flex flex-row gap-1 hover:text-green-300">
                                    Website
                                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"></path></svg>
                                </div>
                            </a>
                            <a href="#">
                                <div class="flex flex-row gap-1 hover:text-green-300">
                                    Github
                                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"></path></svg>
                                </div>
                            </a>
                        </div>
                    </div>
                    <!-- grid end -->

                    <!-- grid -->
                    <div class="bg-gray-900 p-6 transition duration-500 ease-in-out transform hover:-translate-y-1 hover:scale-110">
                        <h1 class="text-2xl text-white font-medium">bpls.online</h1>
                        <p class="text-gray-300 mt-4">Our Capstone Project. We automate Business Permit and Business Clearance in our barangay.</p>
                        <div class="mt-4 flex flex-row gap-3 text-gray-300">
                            <a href="#">
                                <div class="flex flex-row gap-1 hover:text-green-300">
                                    Website
                                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"></path></svg>
                                </div>
                            </a>
                            <a href="#">
                                <div class="flex flex-row gap-1 hover:text-green-300">
                                    Github
                                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"></path></svg>
                                </div>
                            </a>
                        </div>
                    </div>
                    <!-- grid end -->
                </div>
            </div>
        </div>
    </layout>
</template>

<script>
import Layout from '../Shared/Layout'

export default {
    components: {
        Layout,
    },
}
</script>