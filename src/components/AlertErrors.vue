<template>
  <div v-if="form.errors.any()" class="c-alert c-alert--danger alert fade show" role="alert">
    <div v-if="message" v-html="message"/>

    <ul>
      <li v-for="error in form.errors.flatten()" v-html="error"/>
    </ul>

    <button v-if="dismissible" @click="dismiss" class="c-close" data-dismiss="alert" type="button" aria-label="Close">
      <span aria-hidden="true">×</span>
    </button>
  </div>
</template>

<script>
import Alert from './Alert'

export default {
  name: 'alert-errors',

  extends: Alert,

  props: {
    message: {
      type: String,
      default: 'There were some problems with your input.'
    }
  }
}
</script>
