<template>
  <div v-if="form.successful" class="c-alert c-alert--success alert fade show" role="alert">
    <slot>
      <div v-html="message"/>
    </slot>
    <button v-if="dismissible" @click="dismiss" class="c-close" data-dismiss="alert" type="button" aria-label="Close">
      <span aria-hidden="true">×</span>
    </button>
  </div>
</template>

<script>
import Alert from './Alert'

export default {
  name: 'alert-success',

  extends: Alert,

  props: {
    message: { type: String, default: '' }
  }
}
</script>
