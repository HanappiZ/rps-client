<script>
export default {
  name: 'Login',
  data() {
      return {
          username: ''
      }
  },
  methods: {
    enterGame () {
      this.$store.dispatch('login', this.username)
    }
  },
  computed: {
    userExists() {
      return this.$store.state.invalidUser
    },
    mode: {
      get() {
        return this.$store.state.mode
      },
      set(value) {
        this.$store.dispatch('setMode', value)
      }
    }
  }
}
</script>

<style scoped>
.input {
  margin: 2em;
}
</style>