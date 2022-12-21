<template>
    <div class="carousel-container">
        <div class="carousel">
            <div class="inner" :style="[innerStyles]" id="inner">
                <div class="card" v-for="(image, i) in images" :key="i">
                    <img :src="image" alt="">
                </div>
            </div>
        </div>
        <i @click="prev" class="bi bi-arrow-left carousel-button carousel-button-prev"></i>
        <i @click="next" class="bi bi-arrow-right carousel-button carousel-button-next"></i>
    </div>
</template>

<script>

import { ref } from 'vue'
export default {
    setup() {

        const images = ref([require('../assets/images/M.jpg'), require('../assets/images/restaurant_135621509.jpg'), require('../assets/images/Savage-2019-top-50-busy-restaurant.webp'), require('../assets/images/xmnsi-prince-restaurant-6803-hor-wide.webp')])
        const innerStyles = ref({})
        const step = ref('');

        const setStep = () => {
            const innerWidth = document.getElementById('inner').offsetWidth;
            console.log(innerWidth)
            step.value = `${innerWidth}px`
        }

        const prev = () => {
            setStep()
            moveRight()

            afterTransition(() => {
                const card = images.value.pop()
                images.value.unshift(card)
                resetTranslate()
            })
        }

        const next = () => {
            setStep()
            moveLeft()

            afterTransition(() => {
                const card = images.value.shift()
                images.value.push(card)
                resetTranslate()
            })
        }

        const afterTransition = (callback) => {
            const listener = () => {
                callback()
                document.getElementById('inner').removeEventListener('transitionend', listener)
            }
            document.getElementById('inner').addEventListener('transitionend', listener)
        }

        const moveLeft = () => {
            innerStyles.value = {
                transform: `translateX(-${step.value})`
            }
        }

        const moveRight = () => {
            innerStyles.value = {
                transform: `translateX(${step.value})`
            }
        }

        const resetTranslate = () => {
            innerStyles.value = {
                transition: 'none',
                transform: 'translateX(0)'
            }
        }

        return { images, next, prev, innerStyles }
    }
}
</script>

<style>
.carousel {
    overflow: hidden;
    display: flex;
    justify-content: center;
    background-color: var(--mainColor);
}

.inner {
    white-space: nowrap;
    transition: transform 0.2s;
    user-select: none;
}

.card {
    margin-right: 10px;
    display: inline-flex;
    color: white;
    border-radius: 4px;
    width: 100%;
    justify-content: center;

}

img {
    max-width: 100%;
    max-height: 500px;
}


.carousel-container {
    margin: 2rem;
    padding: 2.5rem;
    position: relative;
    display: grid;
    place-content: center;
}

.carousel-button-prev {
    position: absolute;
    top: calc(50% - 1rem);
    left: 10%;
}

.carousel-button-next {
    position: absolute;
    top: calc(50% - 1rem);
    right: 10%;
}

.carousel-button {
    cursor: pointer;
    font-size: larger;
    font-weight: bolder;
    border: 1px solid black;
    border-radius: 50%;
    width: 2rem;
    aspect-ratio: 1/1;
    display: grid;
    place-items: center;
}

.carousel-button:hover {
    background-color: var(--mainColor);
    color: whitesmoke;
}
</style>