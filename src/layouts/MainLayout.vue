<template>
  <q-layout view="hHh lpR lFf">

    <q-header reveal elevated class="bg-primary text-white">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="drawer = !drawer" />

        <q-toolbar-title>
          Vox
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer show-if-above v-model="drawer" side="left" bordered>
      <q-list>
        <q-item clickable v-ripple v-for="n in 5" :key="n">
          <q-item-section avatar>
            <q-icon :name="'mdi-numeric-' + (n) + '-circle'" class="q-ml-md q-mr-sm" />
          </q-item-section>
          <q-item-section class="text-body1">
            link {{ n }}
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

  </q-layout>
</template>
<script>
export default {
  name: 'MainLayout',

  data () {
    return {
      drawer: false
    }
  }
}
</script>
