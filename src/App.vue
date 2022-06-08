<script>
export default {
    name: 'HomeView'
}
</script>

<template>
  <nav>
    <ul>
      <li>
        <router-link to="/">Home</router-link>
      </li>
      <li>
        <router-link to="/about">About</router-link>
      </li>
      <li>
        <router-link to="/personality">Personality</router-link>
      </li>
    </ul>
  </nav>

  <div class="overlap">
    <router-view v-slot="{ Component }">
      <Transition>
        <component :is="Component" />
      </Transition>
    </router-view>
  </div>

  <footer class="footer">
   Mohammed Zayed © 2020
  </footer>
</template>

<style>

@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap');
*{
    margin: 0;
    padding: 0;
}
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease-in-out;
  transition-delay:0.5s;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

body{
  font-family: 'Bebas Neue', cursive;
  color:#EDF5E1;
}
nav{
  color:#EDF5E1;
  z-index:3;
  height:10vh;
  width:100vw;
  background-color: #05386B;
  display:flex;
  position:fixed;
  flex-direction:row;
  justify-content:space-around;
  align-content: center;
  align-items: center;
}
nav ul{
    width:50vw;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    list-style: none;
}
nav ul li a{
    text-decoration: none;
    color: white;
    font-size: 20px;
    padding: 10px;
}

.overlap{
  position:absolute;
  display:flex;
  flex-direction:column;
  justify-content:space-around;
  align-items:center;
  height:100vh;
  width:100vw;
  background-color: #5CDB95;
}

.footer{
  display:flex;
  flex-direction:column;
  justify-content:space-around;
  align-items:center;
  height:5vh;
  width:100vw;
  background-color:#05386B;
  bottom:0;
  position:absolute;
}

</style>
