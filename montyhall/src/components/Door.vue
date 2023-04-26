<template>
  <div class="door-area">
    <div class="door-frame">
        <GiftTodo />
    </div>
    <div class="door">
        <div class="number">{{ number }}</div>
        <div class="knob"></div>
    </div>
  </div>
</template>

<script>
import GiftTodo from './GiftTodo.vue'

export default {
    name: 'Door',
    components: {GiftTodo},
    props: {
        number: {},
        hasGift: {type: Boolean}
    },
    data: function() {
        return {
            open: false,
            selected: false
        }
    }
}
</script>

<style>

</style>