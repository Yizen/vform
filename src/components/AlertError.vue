<template>
  <div v-if="form.errors.any()" class="c-alert c-alert--danger alert fade show" role="alert">
    <slot>
      <div v-if="form.errors.has('error')" v-html="form.errors.get('error')"/>
      <div v-else v-html="message"/>
    </slot>
    <button v-if="dismissible" @click="dismiss" class="c-close" data-dismiss="alert" type="button" aria-label="Close">
      <span aria-hidden="true">×</span>
    </button>
  </div>
</template>

<script>
import Alert from './Alert'

export default {
  name: 'alert-error',

  extends: Alert,

  props: {
    message: {
      type: String,
      default: 'There were some problems with your input.'
    }
  }
}
</script>
