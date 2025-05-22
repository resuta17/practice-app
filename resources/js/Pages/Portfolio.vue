<script>
import NavLink from '@/Components/NavLink.vue';

export default {
    components: {
        NavLink,
    },
    data() {
        return {
            activeNav: 'about',
        }
    },

    methods: {
        setActive(section) {
            this.activeNav = section;
        },
    },

    mounted() {

    }
}
</script>

<template>
    <div class="mx-20 mt-4">
        <header class="bg-teal-900 rounded shadow h-16 flex justify-between items-center px-4">
            <div>
                <h1 class="text-white font-bold text-lg">
                    John Lester H. Hebres
                </h1>
                <p class="text-white text-sm">
                    BSCS Graduate
                </p>
            </div>

            <div class="space-x-4">
                <NavLink @click="setActive('about')" href="#about" :active="activeNav === 'about'" class="text-white">
                    About Me
                </NavLink>
                <NavLink @click="setActive('cert')" href="#certification" :active="activeNav === 'cert'"
                    class="text-white">
                    Certification
                </NavLink>
            </div>
        </header>

        <section id="about" class="mt-10 flex items-top gap-6 px-4">
            <div class="ml-44">
                <img :src="`/image`" alt="Profile Picture" class="w-64 h-64 object-cover rounded-full" />
            </div>
            <div class="mr-44 max-w-2xl">
                <p class="text-xl font-semibold mb-4">About me</p>
                <p class="text-lg leading-relaxed">
                    I'm <strong>John Lester Hababag Hebres</strong>, a <em>BSCS cum laude</em> graduate with a strong
                    interest in web development. I'm currently focusing on learning and building projects with
                    <strong>Laravel</strong> and <strong>Vue.js</strong> to sharpen my skills in full-stack development.
                </p>
            </div>
        </section>

        <section id="certification" class="mt-10">
            <p>Certification</p>
        </section>
    </div>

</template>