<template>
  <div class="home-page">
      <form @submit.prevent="">
        <FormGroup
            :label="label"
            :value="value"
            @valueChange="valueChange"
            @onSubmit="onSubmit"
        />
      </form>
  </div>
</template>

<script>
import FormGroup from './FormGroup'

export default {
    name: 'HomePage',
    components: {
        FormGroup
    },
    data () {
        return {
            label: '',
            value: '',
        }
    },
    methods: {
        valueChange (val) {
            this.value = val
        },
        onSubmit (val) {
            alert(`Value: ${val}`)
        }
    }
}
</script>
