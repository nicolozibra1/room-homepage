<template>

    <div class="slider">
        <img :src="store.mobileSlider[this.index].pathMobile" alt="">
        <div class="arrow-container d-flex justify-content-between align-items-center px-4">
            <img src="/img/icon-angle-left.svg" @click="prevImage">
            <img src="/img/icon-angle-right.svg" @click="nextImage">
        </div>
    </div>

</template>

<script>
    import { store } from '../data/store';

    export default {
        name: 'SliderComponent',
        data() {
            return{
                store,
                index: 0
            }
        },
        methods: {
            nextImage() {
                if(this.index < 2) {
                    this.index ++
                }
                else {
                    this.index = 0;
                }
            },
            prevImage() {
                if(this.index > 0) {
                    this.index --;
                }
                else if(this.index = 2) {
                    this.index = 2;
                }
            }
        }
    }
</script>

<style lang="scss" scoped>
    @use '../assets/styles/partials/variables' as *;

    .slider{
        position: relative;
    }
    .arrow-container{
        width: 110px;
        height: 55px;
        background-color: black;
        position: absolute;
        right: 0;
        bottom: 0;
        img{
            width: 15%;
        }
    }
</style>