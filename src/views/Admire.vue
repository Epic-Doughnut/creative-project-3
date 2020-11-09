<template lang="html">
  <div>
    <div class="admiring" :style="'background-color:' + admired + ';'">
      <p>{{admired}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Admire",

  computed: {
    admired(){
      return this.$root.$data.admired;
    },

  }
}
</script>

<style lang="css" scoped>
.admiring{
  width: 80vw;
  height: 80vh;
}
</style>
