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
        <div class="mx-24">
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
                    <NavLink @click="setActive('educ')" href="#education" :active="activeNav === 'educ'"
                        class="text-white">
                        Education
                    </NavLink>
                    <NavLink @click="setActive('cert')" href="#certification" :active="activeNav === 'cert'"
                        class="text-white">
                        Certificates
                    </NavLink>
                    <NavLink @click="setActive('Skills')" href="#Skills" :active="activeNav === 'Skills'"
                        class="text-white">
                        Skills
                    </NavLink>
                    <NavLink @click="setActive('Projects')" href="#Projects" :active="activeNav === 'Projects'"
                        class="text-white">
                        Projects
                    </NavLink>

                    <img :src="modeImg" title="light dark icons" class="w-8 h-8" @click="toggleMode"></img>
                </div>
            </header>

            <main>
                <section class="h-screen flex items-center justify-center space-x-52">
                    <!-- <div class="ml-56">
                        <img :src="`/image`" alt="Profile Picture" class="w-56 h-89 object-cover rounded" />
                    </div> -->
                    <div>
                        <h1 class="text-4xl md:text-5xl font-bold leading-snug">
                            Hi,<br>
                            I'm <span class="text-teal-700 font-semibold">Lester</span><br>
                            Aspirant Web Developer
                        </h1>
                        <div class="flex justify-center item-center mt-16">
                            <button
                                class="inline-flex items-center rounded-md border border-transparent bg-gray-700 px-4 py-2 text-xs font-semibold uppercase tracking-widest text-white transition duration-150 ease-in-out hover:bg-teal-900">
                                Contact me
                            </button>
                        </div>
                        <div class="mt-16 flex justify-center items-center space-x-6">
                            <a href="https://www.linkedin.com/in/jlhebres/" target="_blank">
                                <img :src="'https://cdn-icons-png.flaticon.com/128/4494/4494497.png'" alt="LinkedIn"
                                    class="w-8 h-8"></img>
                            </a>
                            <a href="https://www.facebook.com/jl.hebres1" target="_blanck">
                                <img :src="'https://cdn-icons-png.flaticon.com/128/5968/5968764.png'" alt="LinkedIn"
                                    class="w-8 h-8"></img>
                            </a>
                            <a href="https://github.com/resuta17" target="_blanck">
                                <img :src="'https://cdn-icons-png.flaticon.com/128/5968/5968896.png'" alt="Github"
                                    class="w-8 h-8"></img>
                            </a>
                        </div>

                    </div>

                </section>

                <section id="about" class="mt-10 ">
                    <div class="text-center text-xl font-semibold mb-16 text-teal-700">
                        <p>About me</p>
                        <hr class="border-t-2 border-teal-700 mt-2 w-24 mx-auto" />
                    </div>
                    <div class="flex items-top gap-24 px-4">
                        <div class="ml-56">
                            <img :src="`/image`" alt="Profile Picture" class="w-56 h-56 object-cover rounded-full" />
                        </div>
                        <div class="max-w-xl">

                            <p class="text-lg leading-relaxed">
                                I'm <strong>John Lester Hababag Hebres</strong>, a <em>BSCS cum laude</em> graduate with
                                a strong interest in web development. I'm currently focusing on learning and building
                                projects
                                with <strong>Laravel</strong> and <strong>Vue.js</strong> to sharpen my skills in
                                full-stack
                                development.
                            </p>

                            <div class="flex justify-center item-center mt-8">
                                <button
                                    class="inline-flex items-center rounded-md border border-transparent bg-gray-700 px-4 py-2 text-xs font-semibold uppercase tracking-widest text-white transition duration-150 ease-in-out hover:bg-teal-900">
                                    Download CV
                                </button>
                            </div>
                        </div>
                    </div>

                </section>

                <section id="experience" class="mt-36">
                    <div class="text-center text-xl font-semibold mb-16 text-teal-700">
                        <p>Experience</p>
                        <hr class="border-t-2 border-teal-700 mt-2 w-24 mx-auto" />
                    </div>
                    <div class="flex justify-center">
                        <div
                            class="flex items-start space-x-4 max-w-4xl w-full px-4 border border-teal-700 rounded-xl p-6 shadow-lg">
                            <div class="w-20 flex justify-center">
                                <img :src="'https://media.licdn.com/dms/image/v2/D560BAQEeJkkTZrZb8A/company-logo_200_200/company-logo_200_200/0/1704273708397?e=1753315200&v=beta&t=QzK7HH73jp-GElxDH6VSiASxXIZrbI1InnQwIktOUR4'"
                                    title="phCollab Logo" class="w-16 h-16 flex-shrink-0">
                            </div>

                            <div>
                                <p class="text-base font-semibold">phCollab - Internship</p>
                                <p class="text-gray-500 font-semibold">Feb 2025 - May 2025</p>
                                <p class="text-sm leading-relaxed">
                                    I completed my internship at phCollab as part of my
                                    Bachelor's degree requirement, where
                                    I gained hands-on experience in Quality Assurance (QA), test automation, and
                                    frontend development.
                                </p>
                            </div>
                        </div>
                    </div>



                </section>

                <section id="education" class="mt-36">
                    <div class="text-center text-xl font-semibold mb-16 text-teal-700">
                        <p>Education</p>
                        <hr class="border-t-2 border-teal-700 mt-2 w-24 mx-auto" />
                    </div>

                    <div class="flex justify-center mb-4">
                        <div
                            class="flex items-start space-x-4 max-w-4xl w-full px-4 border border-teal-700 rounded-xl p-6 shadow-lg">
                            <div class="w-20 flex justify-center items-start">
                                <img :src="'https://www.ccdisorsogon.edu.ph/wp-content/uploads/2018/04/cropped-ccdilogo.png'"
                                    title="CCDI Sorsogon" class="w-16 h-16 flex-shrink-0">
                            </div>
                            <div>
                                <a href="https://www.ccdisorsogon.edu.ph/" target="_blank"
                                    class="text-base font-semibold">
                                    Computer Communication Development Institute - Sorsogon City
                                </a>
                                <p class="text-sm">Bachelor of Science in Computer Science</p>
                                <p class="text-gray-500 font-semibold">2021 - 2025</p>
                            </div>
                        </div>
                    </div>

                    <div class="flex justify-center">
                        <div
                            class="flex items-start space-x-4 max-w-4xl w-full px-4 border border-teal-700 rounded-xl p-6 shadow-lg">
                            <div class="w-20 flex justify-center items-start">
                                <img :src="'https://www.ccdisorsogon.edu.ph/wp-content/uploads/2018/04/cropped-ccdilogo.png'"
                                    title="CCDI SHS" class="w-16 h-16 flex-shrink-0">
                            </div>
                            <div>
                                <a href="https://www.ccdisorsogon.edu.ph/" target="_blank"
                                    class="text-base font-semibold">
                                    Computer Communication Development Institute SHS - Sorsogon City
                                </a>
                                <p class="text-sm">TVL-ICT Programming NC IV</p>
                                <p class="text-gray-500 font-semibold">2019 - 2021</p>
                            </div>
                        </div>
                    </div>
                </section>


                <section id="certification" class="mt-36">
                    <div class="text-center text-xl font-semibold mb-4 text-teal-700">
                        <p>Certificates</p>
                        <hr class="border-t-2 border-teal-700 mt-2 w-24 mx-auto" />
                    </div>
                </section>

                <section id="Skills" class="mt-36">
                    <div class="text-center text-xl font-semibold mb-4 text-teal-700">
                        <p>Skills</p>
                        <hr class="border-t-2 border-teal-700 mt-2 w-24 mx-auto" />
                    </div>
                </section>

                <section id="Projects" class="mt-36">
                    <div class="text-center text-xl font-semibold mb-4 text-teal-700">
                        <p>Projects</p>
                        <hr class="border-t-2 border-teal-700 mt-2 w-24 mx-auto" />
                    </div>
                </section>
            </main>

        </div>
    </div>

</template>