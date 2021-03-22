<template>
    <div class="">
        <button v-show="!modal" class="fixed left-12 mt-72 transition duration-500 ease-in-out transform hover:-translate-y-1 hover:scale-150" @click="modal = !modal"> <svg class="w-10 h-10 text-green-300" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M15.707 15.707a1 1 0 01-1.414 0l-5-5a1 1 0 010-1.414l5-5a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 010 1.414zm-6 0a1 1 0 01-1.414 0l-5-5a1 1 0 010-1.414l5-5a1 1 0 011.414 1.414L5.414 10l4.293 4.293a1 1 0 010 1.414z" clip-rule="evenodd"></path></svg> </button>
        <div v-show="modal" class="relative">
            <div @click="modal = !modal" class="w-full h-screen bg-white bg-opacity-0 absolute z-30"></div>
            <div class="fixed ml-5 mt-14 w-56 h-5/6 bg-gray-900 rounded-xl pt-5 z-50">
                <div class="text-gray-100 flex flex-col mx-4">
                    <inertia-link href="/"> 
                        <div class="mt-4 px-3 py-1 pl-10 rounded-md relative text-white" :class="['navbar-link', {'border border-green-300 text-green-300': activeLink === ''}]">
                            <svg class="left-2 w-6 h-6  absolute" :class="['navbar-link', {' text-green-300': activeLink === ''}]" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"></path></svg>
                            <span :class="['navbar-link', {' text-green-300': activeLink === ''}]">Home</span>
                        </div>
                    </inertia-link>

                    <inertia-link href="/work"> 
                        <div class="mt-4 px-3 py-1 pl-10 rounded-md relative text-white" :class="['navbar-link', {'border border-green-300 text-green-300': activeLink === 'work'}]">
                            <svg class="left-2 w-6 h-6  absolute" :class="['navbar-link', {' text-green-300': activeLink === 'work'}]" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M6 6V5a3 3 0 013-3h2a3 3 0 013 3v1h2a2 2 0 012 2v3.57A22.952 22.952 0 0110 13a22.95 22.95 0 01-8-1.43V8a2 2 0 012-2h2zm2-1a1 1 0 011-1h2a1 1 0 011 1v1H8V5zm1 5a1 1 0 011-1h.01a1 1 0 110 2H10a1 1 0 01-1-1z" clip-rule="evenodd"></path><path d="M2 13.692V16a2 2 0 002 2h12a2 2 0 002-2v-2.308A24.974 24.974 0 0110 15c-2.796 0-5.487-.46-8-1.308z"></path></svg>
                            <span :class="['navbar-link', {' text-green-300': activeLink === 'work'}]">Project</span>
                        </div>
                    </inertia-link>

                    <inertia-link href="/about"> 
                        <div class="mt-4 px-3 py-1 pl-10 rounded-md relative text-white" :class="['navbar-link', {'border border-green-300 text-green-300': activeLink === 'about'}]">
                            <svg class="left-2 w-6 h-6  absolute" :class="['navbar-link', {' text-green-300': activeLink === 'about'}]" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11.049 2.927c.3-.921 1.603-.921 1.902 0l1.519 4.674a1 1 0 00.95.69h4.915c.969 0 1.371 1.24.588 1.81l-3.976 2.888a1 1 0 00-.363 1.118l1.518 4.674c.3.922-.755 1.688-1.538 1.118l-3.976-2.888a1 1 0 00-1.176 0l-3.976 2.888c-.783.57-1.838-.197-1.538-1.118l1.518-4.674a1 1 0 00-.363-1.118l-3.976-2.888c-.784-.57-.38-1.81.588-1.81h4.914a1 1 0 00.951-.69l1.519-4.674z"></path></svg>
                            <span :class="['navbar-link', {' text-green-300': activeLink === 'about'}]">About</span>
                        </div>
                    </inertia-link>
                    
                </div>
                <div class="absolute bottom-3 w-full ">
                    <div class=" flex ml-2 p-2">
                        <profile class="w-10 h-10" />
                        <span class="mt-2 ml-2 text-white font-medium">John Kevin Baltazar</span>
                    </div>
                </div>
                
            </div>
        </div>
        
        <slot></slot>


        
    </div>
</template>


<script>
import Profile from './profile.vue';

export default {
    
    components: {
        Profile
    },
    name: 'navbar',
    data: () => ({ activeLink: null, modal: false, }),
    mounted() {
        this.setActiveLink(this.$inertia.page.url);

        window.addEventListener('popstate', this.onPopState);
    },
    beforeDestroy () {
        window.removeEventListener('popstate', this.onPopState)
    },
    methods: {
        setActiveLink(url) {
            this.activeLink = (url || '').replace('/', '').split('?')[0];
        },
        onPopState(event) {
            this.setActiveLink(event?.state?.url);
        },
    }
};
</script>