<template>
  <div id="app">
    <div id="menu">
      <div id="brand">
        <router-link to="/">
          <img src="../images/browse.png">
        </router-link>
      </div>
      <div id="side">
        <router-link to="/help">
          <div class="menu-item browse">
            <img src="../images/help.png">
            <p><strong>HELP</strong></p>
          </div>
        </router-link>
        <router-link to="/admire">
          <div class="menu-item">
            <img src="../images/admire.png">
            <div class="admired" :style="'background-color:'+admired+';'"></div>
          </div>
        </router-link>
      </div>
    </div>
    <router-view />
  </div>
</template>

<script>
  export default{
    name: "App",
    computed:{
      admired(){
        return this.$root.$data.admired;
      }
    }
  }
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;

}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu a {
  color: #ff0000;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}

.admired{
  width: 20px;
  height: 20px;
}
</style>
