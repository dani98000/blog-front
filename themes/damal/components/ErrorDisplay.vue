<template>
<ul>
    <li v-for="error in errors" :key="error">{{ error }}</li>
</ul>
</template>

<script>
export default {
    name: "ErrorDisplay",
    props: {
        errors: Array,
    },
};
</script>

<style scoped>
li {
    margin: 0;
    padding: 0;
    display: block;
    color: red;
}
</style>
