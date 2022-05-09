<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          Web Scraper App
        </q-toolbar-title>

        <div>by Mojtaba</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
         <img class="myLogo" src="../assets/logo.png" alt="Mojtaba Mohammadzadeh">

        </q-item-label>

        <ul class="navbarList">
          <li><router-link to="/Home" class="myRouter"><span class="material-icons"><q-icon name="home"/></span>Home</router-link></li>
          <li><router-link to="/About" class="myRouter"><span class="material-icons"><q-icon name="account_circle" /></span> About</router-link></li>
          <li><router-link to="/Contact" class="myRouter"><span class="material-icons"><q-icon name="whatsapp" /></span> Contact</router-link></li>
        </ul>

      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  setup () {
    const leftDrawerOpen = ref(false)

    return {

      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>

<style scoped>
.myLogo{
 margin-left: 3em;
 border-radius: 50%;
 box-shadow: 3px 5px 10px 5px rgba(0, 0, 255, .2);
}
.navbarList{
  list-style-type: none;
  }
  li{
    margin-bottom: 2em;
  }
.material-icons{
  margin-right: 10px;
  font-size: 1.5em;
}
.myRouter{
  color: black;
  text-decoration: none;
  font-size: 1.5em;

}
li:hover{
  background-color: rgba(165, 188, 238, 0.4);
  transition:200ms ease-out 400ms;
  cursor: pointer;
}
</style>
