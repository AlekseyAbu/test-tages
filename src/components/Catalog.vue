<template>
    <section class="catalog">
        <ul class="catalog__products">
            <Card 
                v-for="card of cards" :key="card.id"
                v-bind:card='card'
            />
        </ul>
    </section>
</template>

<script>
import Card from '@/components/Card';

export default {
    props:['cards'],
    name: 'Catalog',
    components: {
        Card,
    }
}
</script>

<style scoped>
    .catalog{
        max-width: 1488px;
        margin: 41px auto 0;
        padding: 0 60px;
    }
    .catalog__products{
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(282px,1fr));
        grid-gap: 48px;
        padding: 0;
        list-style-type: none;
    }
</style>