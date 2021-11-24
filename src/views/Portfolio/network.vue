<template>
  <v-container grid-list-xl>
    <h2 class="pl-4">
      <span>Network</span>
      <span class="green--text">Portfolio</span>
    </h2>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-dialog
        v-model="video.dialog"
        lazy
        max-width="800"
        v-for="video in videos"
        :key="video.title"
      >
        <template v-slot:activator="{ on }">
          <v-flex xs12 sm6 md4 lg4 xl4 v-on="on">
            <v-card hover flat color="transparent">
              <v-img
                :src="video.poster"
                aspect-ratio="1.7778"
                :alt="video.title"
                lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif"
                contain
              ></v-img>
              <v-card-title primary-title class="justify-center">{{video.title}}</v-card-title>
            </v-card>
          </v-flex>
        </template>
        <v-card v-if="video.dialog">
          <plyr>
            <div class="plyr__video-embed">
              <iframe :src="video.href" allowfullscreen allowtransparency allow="autoplay"></iframe>
            </div>
          </plyr>
        </v-card>
      </v-dialog>
    </v-layout>
  </v-container>
</template>

<script>
import { PlyrVideo } from 'vue-plyr'

export default {
  metaInfo: {
    title: 'Video Portfolio',
    titleTemplate: "%s ← Eldin's Space",
    meta: [
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        name: 'description',
        content:
          "Eldin Zaimovic's Services Adobe Premire After Effects Video Ad's Social Media Logo Animation Instagram Facebook Video Editing Advetising"
      },
      { charset: 'utf-8' },
      { property: 'og:title', content: "Eldin' Space" },
      { property: 'og:site_name', content: "Eldin' Space" },
      { property: 'og:type', content: 'website' },
      { property: 'og:url', content: 'https://eldin.space' },
      {
        property: 'og:image',
        content: 'https://i.imgur.com/Dcz2PGx.jpg'
      },
      {
        property: 'og:description',
        content:
          "Eldin Zaimovic's Services Adobe Premire After Effects Video Ad's Social Media Logo Animation Instagram Facebook Video Editing Advetising"
      }
    ]
  },
  components: { plyr: PlyrVideo },
  data () {
    return {
      dialog: false,
      videos: [
        {
          dialog: false,
          title: 'Squid Server',
          href: 'https://drive.google.com/file/d/1Y_CAa5rH8giEaAjH1Cg0z1srsysoT5jp/preview',
          type: 'text/html',
          
          poster: 'https://i.imgur.com/LV7nJSw.jpg'
        },
        {
          dialog: false,
          title: 'Owncloud',
          href: 'https://docs.google.com/document/d/e/2PACX-1vScDTbK2Q7DOH4RIpIC0mhtYmzK3L847xdvr_c6XYrblPhO6u3yA0ADbldW7yAxSFriHT6SB9PssLJy/pub?embedded=true',
          type: 'text/html',
          
          poster: 'https://i.imgur.com/AsSjHmW.png'
        },
        {
          dialog: false,
          title: 'Mikrotik Dasar',
          href: 'https://docs.google.com/document/d/e/2PACX-1vScDTbK2Q7DOH4RIpIC0mhtYmzK3L847xdvr_c6XYrblPhO6u3yA0ADbldW7yAxSFriHT6SB9PssLJy/pub?embedded=true',
          type: 'text/html',
          
          poster: 'https://i.imgur.com/MiTA4zw.png'
        },
        {
          dialog: false,
          title: 'Mikrotik Hotspot',
          href: 'https://docs.google.com/document/d/e/2PACX-1vScDTbK2Q7DOH4RIpIC0mhtYmzK3L847xdvr_c6XYrblPhO6u3yA0ADbldW7yAxSFriHT6SB9PssLJy/pub?embedded=true',
          type: 'text/html',
          
          poster: 'https://i.imgur.com/y0F2cny.jpg'
        },
       
      ]
    }
  }
}
</script>

<style  scoped>
@import "../../../node_modules/vue-plyr/dist/vue-plyr.css";
</style>
