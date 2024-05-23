<script setup>

const tab = ref(null)
const items = ref([
          '熱門', '最新',
        ])
const text = ref('Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.')

</script>

<template>

    <div class="h-svh w-svw flex">

    
  <v-card>
    <v-toolbar color="green">
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>全站文章</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon="mdi-magnify"></v-btn>

      <v-btn><v-avatar color="surface-variant"></v-avatar></v-btn>

      <template v-slot:extension>
        <v-tabs
          v-model="tab"
      grow
        >
          <v-tab
            v-for="item in items"
            :key="item"
            :text="item"
            :value="item"
          ></v-tab>
        </v-tabs>
      </template>
    </v-toolbar>

    <v-tabs-window v-model="tab">
      <v-tabs-window-item
        v-for="item in items"
        :key="item"
        :value="item"
      >
        <v-card flat>
          <v-card-text v-text="text"></v-card-text>
        </v-card>
      </v-tabs-window-item>
    </v-tabs-window>
  </v-card>

        <v-bottom-navigation grow>
            <v-btn value="recent">
                <v-icon>mdi-history</v-icon>

                <span>話題</span>
            </v-btn>

            <v-btn value="favorites">
                <v-icon>mdi-heart</v-icon>

                <span>ZOOK</span>
            </v-btn>

            <v-btn value="nearby">
                <v-icon>mdi-map-marker</v-icon>

                <span>學習</span>
            </v-btn>
            <v-btn value="nearby">
                <v-icon>mdi-map-marker</v-icon>

                <span>理財</span>
            </v-btn>
            <v-btn value="nearby">
                <v-icon>mdi-map-marker</v-icon>

                <span>交友</span>
            </v-btn>

        </v-bottom-navigation>

    </div>
</template>