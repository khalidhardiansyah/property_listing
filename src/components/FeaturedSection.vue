<template>
    <section class="flex flex-col items-center w-full px-5 gap-y-4 md:px-20 ">
        <h2 class="text-[28px] text-center">
            Featured properties in Yogyakarta
        </h2>
        <p class="text-lg text-center">
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Tempora odit quisquam eaque ab nostrum explicabo
            exercitationem
        </p>
        <div class="grid grid-flow-row gap-y-5 md:grid-cols-2 xl:grid-cols-4 md:gap-x-5">
            <CardProperty v-for="item in data" :id="item.id" :key="item.id" :km="item.property.bath"
                :kt="item.property.bed" :harga="item.property.price" :name="item.property.name"
                :gambar="item.images[0].source" :param="item.property.id" />

        </div>
        <ButtonComponent label="View All" themed="outline" />
    </section>
</template>

<script setup>
import CardProperty from './CardProperty.vue';
import ButtonComponent from './ButtonComponent.vue';
import { computed, onMounted, ref } from 'vue';



const data = ref(null)

fetch('http://localhost:5000/properties').then((response) => response.json()).then(result => data.value = result.properties)









</script>

<style lang="scss" scoped></style>