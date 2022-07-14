<script setup>
defineProps({
    id: Number,
    title: String,
    completed: Boolean
})
</script>

<template>

    <div class="grid-container">
        <div class="grid-item-checkbox"><input type="checkbox" :checked="completed" /></div>
        <div class="grid-item-title"><h2>{{ title }}</h2></div>
        <button class="grid-item-btn">Delete</button>
    </div>

</template>

<style scoped>
.grid-container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    background-color: #3321f3;
    padding: 10px;
}
.grid-item-checkbox {
    background-color: rgba(255, 255, 255, 0.8);
    border: 3px solid rgba(0, 0, 0, 0.8);
    padding: 5px;
    font-size: 10px;
    text-align: center;
    box-shadow: 1px 1px 0px 0px, 2px 2px 0px 0px, 3px 3px 0px 0px, 4px 4px 0px 0px, 5px 5px 0px 0px;
}
.grid-item-title {
    background-color: rgba(255, 255, 255, 0.8);
    border: 3px solid rgba(0, 0, 0, 0.8);
    padding: 5px;
    font-size: 10px;
    text-align: center;
    margin-right: 0;
    box-shadow: 1px 1px 0px 0px, 2px 2px 0px 0px, 3px 3px 0px 0px, 4px 4px 0px 0px, 5px 5px 0px 0px;
}
.grid-item-btn {
    background-color: rgba(255, 255, 255, 0.8);
    border: 3px solid rgba(0, 0, 0, 0.8);
    padding: 10px;
    font-size: px;
    text-align: center;
    cursor: pointer;
    justify-self: right;
    font-family: "Open Sans", sans-serif;
    letter-spacing: 3px;
    box-shadow: 1px 1px 0px 0px, 2px 2px 0px 0px, 3px 3px 0px 0px, 4px 4px 0px 0px, 5px 5px 0px 0px;
    

}

</style>