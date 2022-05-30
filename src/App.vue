<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
    <button @click="locale = 'en'">123</button>
    {{ xxx }}
    {{ t('message') }}
    {{ t('text') }}
  </div>
  <router-view />
</template>

<script>
import { ref } from 'vue'
import { useI18n } from 'vue-i18n'
// import mqtt from '@/worker/mqtt.js'
// const Stomp = require('stompjs')
// const SockJS = require('sockjs-client')

export default {
  setup() {
    const { locale, t } = useI18n()
    console.log(locale.value)
    // const url = 'http://101.32.168.101:8801/market/market-ws'
    // // let client = mqtt.connect(
    // //   'ws://101.32.168.101:8801',
    // //   {
    // //     incomingStore: 10000,
    // //     outgoingStore: 10000,
    // //     authenticationData: 'arraybuffer',
    // //   },
    // // )
    // // client.on('connect', function () {
    // //   console.log('Connected')
    // //   client.subscribe('/topic/market/thumb', function (err) {
    // //     if (!err) {
    // //       client.publish('test', 'Hello mqtt')
    // //     }
    // //   })
    // // })
    // // setTimeout(() => {
    // //   client.end()
    // // }, 5000)
    // const socket = new SockJS(url)
    // console.log(socket)
    // console.log(Stomp.over(socket))
    // const stompClient = Stomp.over(socket)
    // stompClient.connect({}, function (frame) {
    //   console.log(frame)
    //   const a = stompClient.subscribe('/topic/market/thumb', function (msg) {
    //     console.log(msg)
    //   })
    //   setTimeout(() => {
    //     a.unsubscribe()
    //   }, 5000)
    // })
    const xxx = ref('123')

    return {
      xxx,
      locale,
      t,
    }
  },
}
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
