<template>
  <div class="q-pa-md ">
    <div class="q-gutter-y-md row form" >

      <q-input class="q-pa-md myInput"  rounded outlined v-model="what" label="Study">
        <template v-slot:prepend>
          <span> </span>
        </template>
        <template v-slot:append>
          <q-avatar>
            <span class="material-icons">school</span>
          </q-avatar>
        </template>
      </q-input>

      <q-input class="q-pa-md myInput"   rounded standout bottom-slots v-model="where" label="Country" >
        <template v-slot:prepend>
          <q-icon name="place" />
        </template>

      </q-input>
      <div>
        <q-btn @click="SendData" label="Search" rounded type="submit" color="primary"/>

      </div>
    </div>
  </div>
  <postProps></postProps>

</template>

<script>
import { defineComponent } from 'vue'
import postProps from '../components/postProps.vue'

export default defineComponent({
  name: 'IndexPage',
  components: {
    postProps
  },
  data () {
    return {
      what: '',
      where: ''

    }
  },
  methods: {
    SendData () {
      console.log(`Search for ${this.what} in ${this.where}`)
    }
  }

})
</script>

<style scoped>
 .form{
  display: flex;
  justify-content: center;
  align-items: center;

}
@media screen and (min-width: 480px) {

  .myInput {
    width: 40%;
  }
}
@media screen and (max-width: 480px) {

  .myInput {
    width: 100%;
  }
}

</style>
