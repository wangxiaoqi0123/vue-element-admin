<template>
  <div>
    Lodash
  </div>
</template>
<script>
export default {
  data() {
    return {

    }
  },
  computed: {},
  watch: {},
  mounted() {
    this.times()
  },
  methods: {
    times() {
      var users = [
        { 'user': 'barney', 'age': 36, 'active': true },
        { 'user': 'fred', 'age': 40, 'active': false },
        { 'user': 'pebbles', 'age': 1, 'active': true }
      ]
      this.$lodash.times(users.length, (i) => {
        console.log('users[i].age :>> ', users[i].age)
      })
    }
  }
}
</script>
<style lang='scss' scoped>
</style>
