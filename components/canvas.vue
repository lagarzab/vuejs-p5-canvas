<template>
    <div :id="elementId">Element ID added</div>
</template>

<script>
export default {
    name: 'p5Canvas',
    props: {
        elementId: {
            type: String,
            required: true
        }
    },
}
</script>

<style lang='scss'>
</style>
