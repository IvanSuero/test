<template>
  <q-toolbar>
    <q-toolbar-title>
      <div class="title">
        <a @click="this.$router.push({ name: 'areas' })"><h6>.WMS</h6></a>
      </div>
    </q-toolbar-title>
    <q-btn flat round dense :icon="drawer ? 'close' : 'menu'" @click="modifyDrawer" size="20px" />
  </q-toolbar>
</template>

<style>
.q-toolbar{
  height: 75px;
  padding: 0 20px 0 50px ;
}
.title{
  width: 100%;
}
.title h6{
  width: fit-content;
  padding: 0 10px;
}
.title h6:hover{
  cursor: pointer;
}
</style>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'NavBar',
  props: {
    drawer: {
      type: Boolean,
      default: false
    }
  },
  emit: ['drawerModify'],
  methods: {
    modifyDrawer () {
      this.$emit('drawerModify')
    }
  }
})
</script>
