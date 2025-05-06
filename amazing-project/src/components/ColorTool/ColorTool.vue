<script>
export default {
    name: "ColorTool",

    data() {
        return {
            colors: {
                red: { index: 0, name: 'red', value: 255 },
                green: { index: 1, name: 'green', value: 255 },
                blue: { index: 2, name: 'blue', value: 255 }
            },
        };
    },
};

</script>

<template>
    <div class="color w-full h-100" :style="{ backgroundColor: `rgb(${colors.red.value}, ${colors.green.value}, ${colors.blue.value})` }"></div>

    <div v-for="color in colors" :key="color.index">
        <label :for="color.name">{{ color.name }}</label>
        <input type="range" :name="color.name" :id="color.name" v-model="color.value" max="255" />
        <input type="number" name="colorVal" id="colorVal" value="color.value" :min="0" :max="255" v-model="color.value" max="255"/>
    </div>


</template>
