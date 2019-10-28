<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button class="success" @click="deploy"/>
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

    server_response(msg) {
      // eslint-disable-next-line no-console
      console.log("client receive message", msg)
    }
  },

  methods: {
    deploy() {
      // eslint-disable-next-line no-console
      console.log("click button")
      this.$socket.emit("client_event", "I am client, click deploy")
    }
  }
}
</script>