<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },

  sockets: {
    connect() {
      // eslint-disable-next-line no-console
      console.log('connected')
    },

    my_response(msg) {
      // eslint-disable-next-line no-console
      console.log("receive message", msg)
    }
  }
}
</script>