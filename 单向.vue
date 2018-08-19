<template>
  <div>
    <input v-model="msg" />
    <input v-bind:value="msg" v-on:input="msg = $event.target.value" />
  </div>
</template>

<script type="text/javascript">
export default {
  data () {
    return {
      msg: ''
    }
  },
  watch: {
  },
  methods: {
  }
}
</script>
