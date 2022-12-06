<template>
    <div class="carousel-container">
        <div class="carousel">
            <div class="inner" :style="[innerStyles]" ref="inner">
                <div class="card" v-for="card in cards" :key="card">
                    {{ card }}
                </div>
            </div>
            <i @click="prev" class="bi bi-arrow-left carousel-button carousel-button-prev"></i>
            <i @click="next" class="bi bi-arrow-right carousel-button carousel-button-next"></i>
        </div>
    </div>
</template>

<script>

import { onMounted, ref } from 'vue'
export default {
    setup() {

        const cards = ref([1, 2, 3, 4, 5, 6, 7, 8, 9])
        const innerStyles = ref({})
        const step = ref('');

        const inner = ref(null)

        onMounted(() => {
            const innerWidth = inner.value.scrollWidth;
            const totalCards = cards.value.length;
            step.value = `${innerWidth / totalCards}px`
        })

        const prev = () => {
            moveRight()

            afterTransition(() => {
                const card = cards.value.pop()
                cards.value.unshift(card)
                resetTranslate()
            })
        }

        const next = () => {
            moveLeft()

            afterTransition(() => {
                const card = cards.value.shift()
                cards.value.push(card)
                resetTranslate()
            })
        }

        const afterTransition = (callback) => {
            const listener = () => {
                callback()
                inner.value.removeEventListener('transitionend', listener)
            }
            inner.value.addEventListener('transitionend', listener)
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

        return { cards, inner, next, prev, innerStyles }
    }
}
</script>

<style>
.carousel {
    overflow: hidden;
}

.inner {
    white-space: nowrap;
    transition: transform 0.2s;
}

.card {
    width: 40px;
    margin-right: 10px;
    display: inline-flex;

    height: 40px;
    background-color: #39b1bd;
    color: white;
    border-radius: 4px;
    align-items: center;
    justify-content: center;
}

.carousel-container {
    margin: 2rem;
    padding: 1rem;
    position: relative;
    width: 50%;
    display: flex;
    justify-content: center;
}

.carousel-button-prev {
    position: absolute;
    top: 50%;
    left: 0%;
}

.carousel-button-next {
    position: absolute;
    top: 50%;
    left: 100%;
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
    background-color: #39b1bd;
}
</style>