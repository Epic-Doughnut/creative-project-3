<template>
<div class="wrapper">
  <div class="colors">
    <div class="color" v-for="color in colors" :key="color.id">
      <div class="info" :style="'background-color:'+ color.color+';'">
      </div>

      <div class="price">
        <h2>{{color.name}}</h2>
        <p>{{color.color}}</p>

        <button class="auto" v-on:click="admire(color.color)">Admire</button>
      </div>
    </div>
  </div>
</div>
</template>


<script>
export default {
  name: 'Colors',
  props: {
    colors: Array
  },

  methods:{
    admire(color){
      this.$root.$data.admired = color;
    },
  },

  computed:{
    style(){
      return {
        '--backgroundColor': this.$root.$data.admired
      };
    },
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.colors {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.color {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
  background-color: var(--backgroundColor);
}

.color img {
  border: 2px solid #333;
  height: 100px;
  width: 100px;
  object-fit: cover;
}

.color .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #F2921D;
  color: #000;
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}


.price {
  display: flex;
}

button {
  height: 50px;
  background: #000;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>
