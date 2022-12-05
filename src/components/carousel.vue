<template>
    <div>
        <div class="carousel">
            <div class="inner" :style="[innerStyles]" ref="inner">
                <div class="card" v-for="card in cards" :key="card">
                    {{ card }}
                </div>
            </div>
        </div>
        <button class="carousel-button" @click="prev">prev</button>
        <button class="carousel-button" @click="next">next</button>
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