<template>
  <v-app>
    <v-app-bar class="pl-2">
      <v-row>
        <v-col cols="4">
          <v-text-field variant="outlined" density="compact"></v-text-field>
        </v-col>
        <v-col cols="4"><v-select chips multiple variant="outlined" density="compact"></v-select></v-col>
      </v-row>
    </v-app-bar>
    <v-navigation-drawer
      expand-on-hover
      permanent
      rail>
      <v-list>
        <v-list-item v-for="s in canon" class="text-no-wrap">
          <strong>{{ s }}</strong>
          <v-list>
            <v-list-item v-for="b in books[s]">
              {{ b }}
            </v-list-item>
          </v-list>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <v-row>
        <v-col cols="4">1111</v-col>
        <v-col cols="4">2222</v-col>
        <v-col cols="4">
          <HelloWorld />
        </v-col>
      </v-row>
      
    </v-main>

    <v-btn
      class="ma-2"
      icon="mdi-theme-light-dark"
      location="top right"
      position="absolute"
      @click="$vuetify.theme.cycle()"
    />
  </v-app>
</template>

<script lang="ts" setup>
  import HelloWorld from '@/components/HelloWorld.vue'

  const canon = [
    'Book of Mormon'
  ]
  const books = {
    'Book of Mormon': ['1 Nephi', '2 Nephi']
  }
</script>
