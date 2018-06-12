<template>
  <small class="c-field__message u-color-danger" v-if="form.errors.has(field)">
    <i class="fa fa-times-circle"></i><span v-html="form.errors.get(field)"></span>
  </small>
</template>

<script>
export default {
  name: 'has-error',

  props: {
    form: {
      type: Object,
      required: true
    },

    field: {
      type: String,
      required: true
    }
  }
}
</script>
