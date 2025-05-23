<script>
import NavLink from '@/Components/NavLink.vue';

export default {
    components: {
        NavLink,
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
                    <NavLink @click="setActive('cert')" href="#certification" :active="activeNav === 'cert'"
                        class="text-white">
                        Certification
                    </NavLink>
                    <img :src="modeImg" title="light dark icons" class="w-8 h-8" @click="toggleMode"></img>
                </div>
            </header>

            <section id="about" class="mt-10 flex items-top gap-6 px-4">
                <div class="ml-44">
                    <img :src="`/image`" alt="Profile Picture" class="w-64 h-64 object-cover rounded-full" />
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
                </div>
            </section>

            <section id="certification" class="mt-10">
                <p class="text-xl font-semibold mb-4">
                    Certification
                </p>
            </section>
        </div>
    </div>

</template>