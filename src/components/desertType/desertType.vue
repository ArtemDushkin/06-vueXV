<template>
    <div  class="desertType">
            <div  class='item' v-for="type in DesertTypes">
                <img v-bind:src="type.imgsrc" style="height: 200px"/>
                <p>{{ type.type }}</p>
                <p>{{ type.description }}</p>
                <button @click="$emit('addToCart')">Выбрать</button>
                <button @click="$emit('deleteFromCart')">Отменить</button>
            </div>
            
    </div>
</template>

<script setup>
import DesertTypes from './desertType';
// import addToCart from '../../App.vue'

</script>
export default {
    props:{
        DesertTypes: {
            type: Array,
            required: true
        }
    },
    methods: {
    addToCart(){
        this.$emit('add-to-cart', DesertType[1].type)
    },
    deleteFromCart(){
        this.$emit('delete-from-cart')
    }
 }}

<style scoped>
.desertType{
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-content: center;
    flex-wrap: wrap;
    align-items: stretch;
    }
 .item{
    margin: 20px;
    width:  200px;
    height: 330px;
    }
</style>