<template>
  <div>
    <v-btn
      @click="getMsg()"
      >
      push
    </v-btn>
    <div>
      {{ msgs }}
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msgs: ""
    }
  },
  methods: {
    getMsg () {
      const url = "/api/v1/hello"
      this.$axios.get(url)
        .then((res) => {
          this.msgs = res.data
        })
        .catch((error) => {
          console.log(error)
        })
    }
  }
}
</script>
