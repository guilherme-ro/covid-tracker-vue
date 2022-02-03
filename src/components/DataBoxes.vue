<template>
    <div class="grid md:grid-cols-2 gap-4">
        <div class="shadow-md bg-blue-100 p-10 text-center rounded">
            <h3 class="text-3xl text-blue-900 dont-bold mb-4">
                Casos
            </h3>

            <div class="text-2xl mb-4">
                <span class="font-bold">Novos:</span>
                {{ numberWithDots(stats.NewConfirmed) }}
            </div>
            <div class="text-2xl mb-4">
                <span class="font-bold">Total:</span>
                {{ numberWithDots(stats.TotalConfirmed) }}
            </div>
        </div>

        <div class="shadow-md bg-blue-100 p-10 text-center rounded">
            <h3 class="text-3xl text-blue-900 dont-bold mb-4">
                Óbitos
            </h3>

            <div class="text-2xl mb-4">
                <span class="font-bold">Novos:</span>
                {{ numberWithDots(stats.NewDeaths) }}
            </div>
            <div class="text-2xl mb-4">
                <span class="font-bold">Total:</span>
                {{ numberWithDots(stats.TotalDeaths) }}
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'DataBoxes',
    props: ['stats'],
    methods: {
        numberWithDots(x) {
            return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, '.')
        }
    }
}
</script>
