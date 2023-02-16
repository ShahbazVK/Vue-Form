<template>
<ul>
    <li><button :class="{activeClass:modelValue==='poor'}" @click="activate('poor')" type="button">Poor</button></li>
    <li><button :class="{activeClass:modelValue==='average'}" @click="activate('average')" type="button">Average</button></li>
    <li><button :class="{activeClass:modelValue==='great'}" @click="activate('great')" type="button">Great</button></li>
</ul>
</template>

<script>
export default {
    props:['modelValue'],
    methods: {
        activate(rating) {
            this.$emit('update:modelValue', rating)
        },
    },
}
</script>

<style scoped>
li {
    list-style: none;
    font-size: x-large;
    margin-left: 8px;
    margin-right: 8px;
}

ul {
    display: flex;
}

button {
    font-size: large;
    padding: 20px;
    /* border: none; */
    background-color: rgb(255, 255, 255);
    color: rgb(0, 0, 0);
    font-weight: bold;
    border-radius: 10px;
}

.activeClass {
    background-color: rgba(255, 0, 0, 0.641);
    color: white;
}
</style>
