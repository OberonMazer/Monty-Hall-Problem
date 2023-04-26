<template>
  <div class="doortodo-area">
    <div class="doortodo-frame" :class="{selected: selected && !open}">
        <GiftTodo v-if="open && hasGift"/>
    </div>
    <div class="doortodo" :class="{open}"
    @click="selected = !selected">
        <div class="number" :class="{selected}">{{ number }}</div>
        <div class="knob" :class="{selected}"
        @click.stop="open = true"></div>
    </div>
  </div>
</template>

<script>
import GiftTodo from './GiftTodo.vue'

export default {
    name: 'DoorTodo',
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
:root {
    --door-border: 5px solid brown;
    --selected-border: 5px solid yellow;
}

.doortodo-area {
    position: relative;
    width: 200px;
    height: 310px;
    border-bottom: 10px solid #aaa;
    margin-bottom: 20px;
    font-size: 3rem;

    display: flex;
    justify-content: center;
}

.doortodo-frame {
    position: absolute;
    height: 300px;
    width: 180px;

    border-left: var(--door-border);
    border-top: var(--door-border);
    border-right: var(--door-border);

    display: flex;
    justify-content: center;
    align-items: flex-end;
}

.doortodo {
    position: absolute;
    top: 5px;
    height: 295px;
    width: 170px;
    background-color: chocolate;

    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 15px;
}

.doortodo .knob {
    height: 20px;
    width: 20px;
    border-radius: 10px;
    background-color: brown;
    align-self: flex-start;
    margin-top: 60px;
}

.doortodo-frame.selected {
    border-left: var(--selected-border);
    border-top: var(--selected-border);
    border-right: var(--selected-border);
}

.doortodo .number.selected {
    color: yellow;
}

.doortodo .knob.selected {
    background-color: yellow;
}

.doortodo.open {
    background-color: #0007;
}

.doortodo.open .knob {
    display: none;
}

.doortodo.open .number {
    display: none;
}
</style>