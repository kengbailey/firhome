<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      app
      clipped
    >
      <v-list dense>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-view-dashboard</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Dashboard</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-file-video</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Wav Runner</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      clipped-left
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Fir</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <v-container
        class="fill-height"
        fluid
      >
        <v-col>
          <v-row
           justify="center" 
           align="center"
          >
            <v-form>
              <v-text-field label="Youtube URL">
              </v-text-field>
            </v-form>
            <v-btn class="ml-4" @click="submit">go</v-btn>
          </v-row>
          <v-row
           justify="center" 
           align="center"
          >
            <v-data-table
              :headers="headers"
              :items="songs"
              :items-per-page="10"
              class="elevation-4">
            </v-data-table>
          </v-row>
        </v-col>
      </v-container>
    </v-main>

    <v-footer app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    props: {
      source: String,
    },
    data: () => ({
      drawer: null,
      headers: [
        {
          text: 'Song Title',
          align: 'start',
          sortable: false,
          value: 'title'
        },
        { text: 'Link', value: 'link'},
        { text: 'Download', value: 'dl'},
        { text: 'Date', value: 'date'},
      ],
      songs: [
        {title: 'Young Thug - Boolin', link: 'google.com', dl: 'yesh1', date: new Date().toLocaleString()},
        {title: 'Young Thug - Coolin', link: 'google.com', dl: 'yesh2', date: new Date().toLocaleString()},
        {title: 'Young Thug - Goonin', link: 'google.com', dl: 'yesh3', date: new Date().toLocaleString()},
        {title: 'Young Thug - Vroomin', link: 'google.com', dl: 'yesh4', date: new Date().toLocaleString()},
        {title: 'Young Thug - Droolin', link: 'google.com', dl: 'yesh5'},
        {title: 'Young Thug - Boolin', link: 'google.com', dl: 'yesh1'},
        {title: 'Young Thug - Coolin', link: 'google.com', dl: 'yesh2'},
        {title: 'Young Thug - Goonin', link: 'google.com', dl: 'yesh3', date: new Date().toLocaleString()},
        {title: 'Young Thug - Vroomin', link: 'google.com', dl: 'yesh4'},
        {title: 'Young Thug - Droolin', link: 'google.com', dl: 'yesh5'},
        {title: 'Young Thug - Boolin', link: 'google.com', dl: 'yesh1'},
        {title: 'Young Thug - Coolin', link: 'google.com', dl: 'yesh2'},
        {title: 'Young Thug - Goonin', link: 'google.com', dl: 'yesh3', date: new Date().toLocaleString()},
        {title: 'Young Thug - Vroomin', link: 'google.com', dl: 'yesh4'},
        {title: 'Young Thug - Droolin', link: 'google.com', dl: 'yesh5', date: new Date().toLocaleString()},
        {title: 'Young Thug - Boolin', link: 'google.com', dl: 'yesh1', date: new Date().toLocaleString()},
        {title: 'Young Thug - Coolin', link: 'google.com', dl: 'yesh2', date: new Date().toLocaleString()},
        {title: 'Young Thug - Goonin', link: 'google.com', dl: 'yesh3', date: new Date().toLocaleString()},
        {title: 'Young Thug - Vroomin', link: 'google.com', dl: 'yesh4'},
        {title: 'Young Thug - Droolin', link: 'google.com', dl: 'yesh5'},
      ]
    }),
    created () {
      this.$vuetify.theme.dark = true
    },
    methods: {
      submit () {
        this.$v.$touch()
      },
    }
  }
</script>