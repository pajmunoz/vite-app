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
    <div class="color w-full h-100"
        :style="{ backgroundColor: `rgb(${colors.red.value}, ${colors.green.value}, ${colors.blue.value})` }"></div>

    <template v-for="color in colors" :key="color.index">
        <div class="flex justify-center items-center">
            <div class="w-10 flex-none h-10" :name="color.name" :id="color.name"
                :style="{ backgroundColor: `rgb(${color.name === 'red' ? color.value : 0}, ${color.name === 'green' ? color.value : 0}, ${color.name === 'blue' ? color.value : 0})` }">
            </div>
            <label class="w-10 flex-1 text-center" :for="color.name"> {{ color.name }}</label>
            <input class="w-10 flex-1 " type="range" :name="color.name" :id="color.name" v-model="color.value" max="255" />
            <input class="w-10 flex-1 mx-7" type="number" name="colorVal" id="colorVal" value="color.value" :min="0" :max="255"
                v-model="color.value" max="255" />
        </div>
    </template>



</template>
