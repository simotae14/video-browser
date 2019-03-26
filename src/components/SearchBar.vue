<template>
    <div>
        <input @input="onInput" />
    </div>
</template>

<script>
export default {
    name: 'SearchBar',
    methods: {
        onInput: function(event) {
            // emit event
            this.$emit('termChange', event.target.value);
            console.log(event.target.value);
        }
    }
}
</script>

<style>

</style>
