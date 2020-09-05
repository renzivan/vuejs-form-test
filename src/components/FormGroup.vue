<template>
    <div class="form-group">
        <label for="input-value" v-show="label">{{ label }}</label>
        <input id="input-value" type="text" placeholder="Value" v-model="inputValue" @input="onChange(inputValue)">
        <button @click="onSubmit">Submit</button>
    </div>
</template>

<script>
export default {
    props: {
        label: {
            type: String,
            default: null,
            required: false
        },
        value: {
            type: String,
            default: '',
            required: false
        }
    },
    data () {
        return {
            inputValue: this.value
        }
    },
    methods: {
        onChange (val) {
            this.$emit('valueChange', val)
        },
        onSubmit () {
            this.$emit('onSubmit', this.inputValue)
        }
    }
}
</script>

<style>

</style>