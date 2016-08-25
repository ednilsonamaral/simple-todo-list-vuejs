<template>
    <span>{{ item.text }}</span>
    <button @click="$emit('remove')">X</button>
</template>

<script>
export default {
    // props - propriedades
    props: {
        item: Object
    }
}
</script>
