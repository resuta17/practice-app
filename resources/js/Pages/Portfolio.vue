<script>
import NavLink from '@/Components/NavLink.vue';
import DropDownLink from '@/Components/DropdownLink.vue'
import Dropdown from '@/Components/Dropdown.vue'


export default {
    components: {
        NavLink,
        Dropdown,
        DropDownLink,
        name: 'CertificateGallery'
        
    },
    data() {
        return {
            activeNav: 'about',
            isDarkMode: true,
            current: 0,
      certificates: [
        {
          title: 'Introduction to Git and GitHub',
          img: 'https://s3.amazonaws.com/coursera_assets/meta_images/generated/CERTIFICATE_LANDING_PAGE/CERTIFICATE_LANDING_PAGE~X35RFUDR4XBT/CERTIFICATE_LANDING_PAGE~X35RFUDR4XBT.jpeg',
          issued: 'May 2024',
          id: 'X35RFUDR4XBT',
          link: 'https://www.coursera.org/account/accomplishments/verify/X35RFUDR4XBT',
        }, {
          title: 'Google IT Support',
          img: 'https://s3.amazonaws.com/coursera_assets/meta_images/generated/CERTIFICATE_LANDING_PAGE/CERTIFICATE_LANDING_PAGE~RK9DHP48APNR/CERTIFICATE_LANDING_PAGE~RK9DHP48APNR.jpeg',
          issued: 'Jun 2024',
          id: 'RK9DHP48APNR',
          link: 'https://www.coursera.org/account/accomplishments/specialization/RK9DHP48APNR',
        }, {
          title: 'Google IT Automation with Python',
          img: 'https://s3.amazonaws.com/coursera_assets/meta_images/generated/CERTIFICATE_LANDING_PAGE/CERTIFICATE_LANDING_PAGE~GGS5N7QWE7FV/CERTIFICATE_LANDING_PAGE~GGS5N7QWE7FV.jpeg',
          issued: 'May 2024',
          id: 'GGS5N7QWE7FV',
          link: 'https://www.coursera.org/account/accomplishments/specialization/GGS5N7QWE7FV',
        }, {
          title: 'Troubleshooting and Debugging Techniques',
          img: 'https://s3.amazonaws.com/coursera_assets/meta_images/generated/CERTIFICATE_LANDING_PAGE/CERTIFICATE_LANDING_PAGE~5ZQHTK6MSB49/CERTIFICATE_LANDING_PAGE~5ZQHTK6MSB49.jpeg',
          issued: 'May 2024',
          id: '5ZQHTK6MSB49',
          link: 'https://www.coursera.org/account/accomplishments/verify/5ZQHTK6MSB49',
        }, {
          title: 'Technical Support Fundamentals',
          img: 'https://s3.amazonaws.com/coursera_assets/meta_images/generated/CERTIFICATE_LANDING_PAGE/CERTIFICATE_LANDING_PAGE~META6P6YPNEV/CERTIFICATE_LANDING_PAGE~META6P6YPNEV.jpeg',
          issued: 'May 2024',
          id: 'META6P6YPNEV',
          link: 'https://www.coursera.org/account/accomplishments/verify/META6P6YPNEV',
        },
          
            ] 
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
        },
         next() {
            this.current = (this.current + 1) % this.certificates.length;
        },
        prev() {
            this.current = (this.current - 1 + this.certificates.length) % this.certificates.length;
        }

    },

    mounted() {

    }
}
</script>

<template>
    <div :class="[backgroundColor, 'min-h-screen', textColor]">

        <header class="bg-teal-900  shadow h-16 flex justify-between items-center px-4 sticky top-0 z-50">
            <div class="ml-8">
                <h1 class="text-white font-bold text-lg">
                    John Lester H. Hebres
                </h1>
                <p class="text-white text-sm">
                    BSCS Graduate
                </p>
            </div>

            <div class="flex items-center space-x-4 mr-8">
                <NavLink @click="setActive('about')" href="#about" :active="activeNav === 'about'" class="text-white">
                    About Me
                </NavLink>
                <NavLink @click="setActive('exp')" href="#experience" :active="activeNav === 'exp'" class="text-white">
                    Experience
                </NavLink>
                <NavLink @click="setActive('educ')" href="#education" :active="activeNav === 'educ'" class="text-white">
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
            <section class="h-screen flex items-center justify-center space-x-52 z-10">
                <!-- <div class="ml-56">
                        <img :src="`/image`" alt="Profile Picture" class="w-56 h-89 object-cover rounded" />
                    </div> -->
                <div>
                    <h1 class="text-4xl md:text-5xl font-bold leading-snug animate__animated animate__jackInTheBox">
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
                    <div class="mt-16 flex justify-center items-center space-x-6 animate__animated animate__slideInUp">
                        <a href="https://www.linkedin.com/in/jlhebres/" target="_blank" class="w-10 h-10 flex items-center justify-center">
                            <img
                            :src="'https://cdn-icons-png.flaticon.com/128/4494/4494497.png'"
                            alt="LinkedIn"
                            class="w-8 h-8 transform transition-transform duration-200 hover:scale-125"
                            />
                        </a>

                        <a href="https://www.facebook.com/jl.hebres1" target="_blank" class="w-10 h-10 flex items-center justify-center">
                            <img
                            :src="'https://cdn-icons-png.flaticon.com/128/5968/5968764.png'"
                            alt="Facebook"
                            class="w-8 h-8 transform transition-transform duration-200 hover:scale-125"
                            />
                        </a>

                        <a href="https://github.com/resuta17" target="_blank" class="w-10 h-10 flex items-center justify-center">
                            <img
                            :src="'https://cdn-icons-png.flaticon.com/128/5968/5968896.png'"
                            alt="GitHub"
                            class="w-8 h-8 transform transition-transform duration-200 hover:scale-125"
                            />
                        </a>
                    </div>
                </div>

            </section>

            <section id="about" class="mt-10 ">
                <div class="text-center text-xl font-semibold mb-20 text-teal-700">
                    <p>About me</p>
                    <hr class="border-t-2 border-teal-700 mt-2 w-24 mx-auto" />
                </div>
                <div class="flex items-top gap-24 px-4">
                    <div class="ml-96">
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
                            <a href="https://www.ccdisorsogon.edu.ph/" target="_blank" class="text-base font-semibold">
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
                            <a href="https://www.ccdisorsogon.edu.ph/" target="_blank" class="text-base font-semibold">
                                Computer Communication Development Institute SHS - Sorsogon City
                            </a>
                            <p class="text-sm">TVL-ICT Programming NC IV</p>
                            <p class="text-gray-500 font-semibold">2019 - 2021</p>
                        </div>
                    </div>
                </div>
            </section>


            <section id="certification" class="mt-36 ">
                <div class="text-center text-xl font-semibold mb-20 text-teal-700">
                    <p>Certificates</p>
                    <hr class="border-t-2 border-teal-700 mt-2 w-24 mx-auto" />
                   
                </div>
                 <div class="flex justify-center items-start items-center space-x-4">
                    <button
                        @click="prev"
                          class="px-4 py-2 bg-teal-700 shadow-xl rounded-full hover:bg-teal-500 text-white"
                    >
                        &#8592;
                    </button>
                    <div class=" border shadow max-w-2xl rounded-xl p-6 shadow-xl border-gray-500">         
                        <a :href="certificates[current].link" target="_blank">
                        <div class="font-semibold mb-2">
                            {{ certificates[current].title }}
                        </div>
                        <img :src="certificates[current].img" class="w-102 h-78 mx-auto" />
                        </a>
                        <p class="text-xs text-gray-500 mt-2">
                        Issued {{ certificates[current].issued }}<br />
                        Credentials ID {{ certificates[current].id }}
                        </p>
                    </div>
                    <button
                        @click="next"
                        class="px-4 py-2 bg-teal-700 shadow-xl rounded-full hover:bg-teal-500 text-white"
                    >
                        &#8594;
                    </button>
                </div>
                <div class="flex justify-center mt-6 space-x-2">
                    <img
                        v-for="(cert, index) in certificates"
                        :key="index"
                        :src="cert.img"
                        @click="current = index"
                        class="w-20 h-12 border cursor-pointer rounded hover:scale-105 transition transform"
                        :class="{ 'ring-2 ring-teal-500': current === index }"
                    />
                </div>
                
            </section>

            <section id="Skills" class="mt-36">
                <div class="text-center text-xl font-semibold mb-20 text-teal-700">
                    <p>Skills</p>
                    <hr class="border-t-2 border-teal-700 mt-2 w-12 mx-auto"/> 
                </div>
                <div class="flex justify-center items-center">
                    <ul class="grid grid-cols-2 gap-x-40 gap-y-5 list-none text-xl ">
                        <li class="flex items-center gap-2 hover:text-2xl">
                            <img :src="'https://cdn-icons-png.flaticon.com/128/1051/1051277.png'" class="w-6 h-6" />
                            HTML
                        </li>
                        <li class="flex items-center gap-2 ">
                            <img :src="'https://cdn-icons-png.flaticon.com/128/5968/5968292.png'" class="w-6 h-6" />
                            JavaScript
                        </li>
                        <li class="flex items-center gap-2">
                            <img :src="'https://cdn-icons-png.flaticon.com/128/732/732190.png'" class="w-6 h-6" />
                            CSS
                        </li>
                        <li class="flex items-center gap-2">
                            <img :src="'https://cdn-icons-png.flaticon.com/128/919/919830.png'" class="w-6 h-6" />
                            PHP
                        </li>
                        <li class="flex items-center gap-2">
                            <img :src="'https://cdn-icons-png.flaticon.com/128/6132/6132221.png'" class="w-6 h-6" />
                            C#
                        </li>
                        <li class="flex items-center gap-2">
                            <img :src="'https://cdn-icons-png.flaticon.com/128/16845/16845837.png'" class="w-6 h-6" />
                            MySQL
                        </li>
                        <li class="flex items-center gap-2">
                            <img :src="'https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/1184px-Vue.js_Logo_2.svg.png'"
                                class="w-4 h-4" />
                            Vue.js
                        </li>
                        <li class="flex items-center gap-2">
                            <img :src="'https://download.logo.wine/logo/Laravel/Laravel-Logo.wine.png'" class="w-8 h-8">
                            Laravel
                        </li>
                        <li class="flex items-center gap-2">
                            <img :src="'https://cdn-icons-png.flaticon.com/128/4494/4494740.png'" class="w-4 h-4">
                            Git
                        </li>
                        <li class="flex items-center gap-2">
                            <img :src="'https://pngimg.com/d/linux_PNG27.png'" class="w-8 h-8">
                            Linux
                        </li>
                    </ul>

                </div>
            </section>

            <section id="Projects" class="mt-36">
                <div class="text-center text-xl font-semibold mb-4 text-teal-700">
                    <p>Projects</p>
                    <hr class="border-t-2 border-teal-700 mt-2 w-24 mx-auto" />
                </div>
            </section>
            
            <section id="contact" class="mt-36 bg-teal-900 p-6">
                <div class="text-center text-xl font-semibold mb-4 text-white">
                    <p>Contact Me</p>
                </div>
                <div class="flex justify-center text-gray-900">
                    <input>
                </div>
            </section>
        </main>

    </div>

</template>