<script>
export default {

    data() {
        return {
            count: 0
        }
    },

    methods: {
        increment() {
            this.count++
        }
    },

    mounted() {
        console.log(`The initial count is ${this.count}.`)
    }
}
</script>

<template>
    <div class="mr-10 ml-10 mt-4">
        <header>
            <div class="bg-teal-900 rounded shadow h-16">
                <h1 class="
                flex justify-between 
                items-center
                text-white
                font-bold">
                    John Lester H. Hebres
                </h1>
                <p class="text-white">
                    BSCS Graduate
                </p>
            </div>
        </header>
    </div>

</template>