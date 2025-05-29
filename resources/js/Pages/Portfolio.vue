<script>
import NavLink from '@/Components/NavLink.vue';
import DropDownLink from '@/Components/DropdownLink.vue'
import Dropdown from '@/Components/Dropdown.vue'


export default {
    components: {
        NavLink,
        Dropdown,
        DropDownLink,
    },
    data() {
        return {
            activeNav: 'about',
            isDarkMode: true,
        }
    },
    computed: {
        backgroundColor() {
            return this.isDarkMode ? 'bg-gray-900' : 'bg-white';
        },
        textColor() {
            return this.isDarkMode ? 'text-white' : 'text-black';
        },
        modeImg() {
            return this.isDarkMode
                ? "https://cdn-icons-png.flaticon.com/128/17648/17648604.png"
                : "https://cdn-icons-png.flaticon.com/128/12301/12301351.png";
        }
    },

    methods: {
        setActive(section) {
            this.activeNav = section;
        },
        toggleMode() {
            this.isDarkMode = !this.isDarkMode;
        }

    },

    mounted() {

    }
}
</script>

<template>
    <div :class="[backgroundColor, 'min-h-screen', textColor]">
        <div class="mx-20">
            <header class="bg-teal-900 rounded shadow h-16 flex justify-between items-center px-4">
                <div>
                    <h1 class="text-white font-bold text-lg">
                        John Lester H. Hebres
                    </h1>
                    <p class="text-white text-sm">
                        BSCS Graduate
                    </p>
                </div>

                <div class="flex items-center space-x-4">
                    <NavLink @click="setActive('about')" href="#about" :active="activeNav === 'about'"
                        class="text-white">
                        About Me
                    </NavLink>
                    <NavLink @click="setActive('exp')" href="#experience" :active="activeNav === 'exp'"
                        class="text-white">
                        Experience
                    </NavLink>
                    <NavLink @click="setActive('cert')" href="#certification" :active="activeNav === 'cert'"
                        class="text-white">
                        Certification
                    </NavLink>
                    <NavLink @click="setActive('educ')" href="#education" :active="activeNav === 'educ'"
                        class="text-white">
                        Education
                    </NavLink>
                    <NavLink @click="setActive('social')" href="#socials" :active="activeNav === 'social'"
                        class="text-white">
                        Projects
                    </NavLink>

                    <img :src="modeImg" title="light dark icons" class="w-8 h-8" @click="toggleMode"></img>
                </div>
            </header>

            <main>
                <section id="about" class="mt-10 flex items-top gap-6 px-4">
                    <div class="ml-44">
                        <img :src="`/image`" alt="Profile Picture" class="w-52 h-52 object-cover rounded-full" />
                    </div>
                    <div class="mr-44 max-w-2xl">
                        <p class="text-xl font-semibold mb-4">About me</p>
                        <p class="text-lg leading-relaxed">
                            I'm <strong>John Lester Hababag Hebres</strong>, a <em>BSCS cum laude</em> graduate with a
                            strong
                            interest in web development. I'm currently focusing on learning and building projects with
                            <strong>Laravel</strong> and <strong>Vue.js</strong> to sharpen my skills in full-stack
                            development.
                        </p>
                        <div class="mt-4 flex justify-center items-center space-x-4">
                            <a href="https://www.linkedin.com/in/jlhebres/" target="_blank">
                                <img :src="'https://cdn-icons-png.flaticon.com/128/4494/4494497.png'" alt="LinkedIn"
                                    class="w-8 h-8"></img>
                            </a>
                            <a href="https://www.facebook.com/jl.hebres1" target="_blanck">
                                <img :src="'https://cdn-icons-png.flaticon.com/128/5968/5968764.png'" alt="LinkedIn"
                                    class="w-8 h-8"></img>
                            </a>
                        </div>
                        <div class="flex justify-center item-center mt-4">
                            <button
                                class="inline-flex items-center rounded-md border border-transparent bg-gray-700 px-4 py-2 text-xs font-semibold uppercase tracking-widest text-white transition duration-150 ease-in-out hover:bg-gray-700 focus:bg-gray-700 focus:outline-none focus:ring-2">
                                Download CV
                            </button>
                        </div>

                    </div>
                </section>

                <section id="experience" class="mt-20 ml-44">
                    <p class="text-xl font-semibold mb-4">
                        Experience
                    </p>
                    <div class="flex items-top space-x-4">
                        <div class="w-20 flex justify-center items-start">
                            <img :src="'https://media.licdn.com/dms/image/v2/D560BAQEeJkkTZrZb8A/company-logo_200_200/company-logo_200_200/0/1704273708397?e=1753315200&v=beta&t=QzK7HH73jp-GElxDH6VSiASxXIZrbI1InnQwIktOUR4'"
                                title="phCollab Logo" class="w-16 h-16 flex-shrink-0"></img>
                        </div>
                        <div>
                            <p class="text-base font-semibold">phCollab - Internship</p>
                            <p class="text-gray-500 font-semibold">Feb 2025 - May 2025</p>
                            <p class="text-sm leading-relaxed mr-64">
                                I completed my internship at phCollab as part of my
                                Bachelor's degree requirement, where
                                I gained hands-on experience in Quality Assurance (QA), test automation, and frontend
                                development.</p>
                        </div>
                    </div>

                </section>

                <section id="education" class="mt-20 ml-44">
                    <p class="text-xl font-semibold mb-4">
                        Education
                    </p>
                </section>

                <section id="certification" class="mt-20 ml-44">
                    <p class="text-xl font-semibold mb-4">
                        Certification
                    </p>
                </section>

                <section id="Projects" class="mt-20 ml-44">
                    <p class="text-xl font-semibold mb-4">
                        Projects
                    </p>
                </section>
            </main>

        </div>
    </div>

</template>