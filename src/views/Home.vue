
<template>

  <v-layout column justify-center align-center class="mt-4 pt-2">

    <br>
   <VueCompareImage leftImage="adlin.jpg" 
 height="600px"
    width="1880px"
    rightImage="miftah.jpeg"
    
    style="{ minWidth: '500px' }"
    :sliderLineWidth="sliderLine"
      :handleSize="10"
      hover
      
      
      :sliderPositionPercentage="sliderPosition"
   class="hidden-md-and-down"/>;
    <vue-typer class="headline" :repeat="0" text="AGM"></vue-typer>
    <vue-typer
      :text="text1"
      :repeat="Infinity"
      :shuffle="false"
      initial-action="erasing"
      :pre-type-delay="70"
      :type-delay="70"
      :pre-erase-delay="1980"
      :erase-delay="150"
      erase-style="select-back"
      :erase-on-complete="false"
      caret-animation="smooth"
    ></vue-typer>
    <br>
    <v-flex xs12 sm6 md4 lg4 xl4>
      <v-card flat color="transparent" max-width="500">
        <v-card-title primary-title>
          <div>
                <vue-load-image>

                      <img slot="image" src=""/>

      <div slot="error">error message</div>
    </vue-load-image>

            <h3 class="headline mb-0">
              <span>About</span>
              <span class="green--text">Us</span>
            </h3>
            <div>
              <p>
               Hallo!kami dari AGM project,kawula muda yang ingin mendapatkan pekerjaan tetap maupun 
                <span
                  class="green--text font-weight-bold"
                >Freelance</span>, basic kami ada di fotographer,videographer,IT support,dan Android Developer,Website ini adalah Portofolio kami
              </p>
            </div>
          </div>
        </v-card-title>

        <v-card-actions class="hidden-sm-and-down">
          <v-btn
            v-for="icon in icons"
            :key="icon.icon"
            fab
            dark
            outline
            color="green"
            :href="icon.href"
            target="_blank"
          >
            <v-icon dark>{{icon.icon}}</v-icon>
          </v-btn>
        </v-card-actions>

        <v-card-actions class="hidden-md-and-up justify-center">
          <v-btn
            v-for="icon in icons"
            :key="icon.icon"
            small
            fab
            dark
            outline
            color="green"
            :href="icon.href"
            target="_blank"
          >
            <v-icon dark>{{icon.icon}}</v-icon>
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import { VueTyper } from 'vue-typer'

import VueCompareImage from 'vue-compare-image'
import VueLoadImage from 'vue-load-image'

export default {
  metaInfo: {
    title: 'Home',
    titleTemplate: "%s ← Eldin's Space",

    meta: [
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      { name: 'description', content: "Eldin Zaimovic's Portfolio" },
      { charset: 'utf-8' },
      { property: 'og:title', content: "Eldin' Space" },
      { property: 'og:site_name', content: "Eldin' Space" },
      { property: 'og:type', content: 'website' },
      { property: 'og:url', content: 'https://eldin.space' },
      {
        property: 'og:image',
        content: 'https://i.imgur.com/Dcz2PGx.jpg'

      },
      { property: 'og:description', content: "Eldin Zaimovic's Portfolio" }
    ]

  },
  components: {
    'vue-typer': VueTyper,
    VueCompareImage,
    'vue-load-image': VueLoadImage

  },
  data () {
    return {
      icons: [
        { href: 'https://github.com/agmproject', icon: 'fab fa-github' },
        {
          href: 'https://stackoverflow.com/users/17482573/agmproject',
          icon: 'fab fa-stack-overflow'
        },
      
        {
          href: 'https://www.linkedin.com/in/miftah-akbar-44766b1b1/',
          icon: 'fab fa-linkedin-in'
        },
      
      
        { href: '', icon: 'fab fa-instagram' }
      ],

      text1: ['Android Developer', 'It Support', 'Videographer','Photographer']

    }
  }
}
</script>
<style>
@keyframes rocking {
  0%,
  100% {
    transform: rotateZ(-10deg);
  }

  50% {
    transform: rotateZ(10deg);
  }
}

.vue-typer {
  font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
}
.vue-typer .custom.char.typed {
  color: green;
}
.vue-typer .custom.char.selected {
  color: #e91e63;
}

.vue-typer .custom.caret {
  animation: rocking 1s ease-in-out 0s infinite;
}
.vue-typer .custom.caret.typing {
  background-color: green;
}
.vue-typer .custom.caret.selecting {
  display: inline-block;
  background-color: #e91e63;
}
</style>
