<template>
  <a @click="loginWithKakao">
    <img src="/kakao_login_medium_narrow.png"></img>
  </a>
</template>

<script>
export default {
  name: 'IndexPage',
  mounted () {
    this.kakaoInit()
  },
  methods: {
    kakaoInit () {
      Kakao.init('74333032742f9886f1a73af03988d9c3')
      Kakao.isInitialized()
    },
    async loginWithKakao () {
      await Kakao.Auth.authorize({
        redirectUri: `${window.location.origin}/kakao-callback`
      })
    }
  }
}
</script>
