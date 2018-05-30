<template>
  <v-app >
    <v-navigation-drawer dark :mini-variant.sync="miniVariant" :clipped="clipped" v-model="drawer" fixed app >
      <v-list>
        <v-list-group v-for="(item,i) in items" v-model="item.active" :key="i" router exact >
          <!-- header -->
          <v-list-tile slot="activator">
            <v-list-tile-content>
              <v-list-tile-title>{{ item.title }}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
          <!-- children -->
          <v-list-tile v-for="(subItem, x) in item.children" :key="`${i}-${x}`" :to='subItem.to' class='ml-2' >
            <v-list-tile-content>
              <v-list-tile-title>{{ subItem.title }}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list-group>
      </v-list>
    </v-navigation-drawer>

    <v-toolbar fixed app dark :clipped-left="clipped" color='orange'>
      <v-toolbar-side-icon @click="drawer = !drawer"></v-toolbar-side-icon>
      <nuxt-link to='/' >
          <img src='~/assets/icon.png' width='40px' height='40px' />
        </nuxt-link>
        <v-toolbar-title color='orange' >
          <nuxt-link to='/' style='text-decoration:none;color:white;' >
          Appointment<span style='color:black;' >Guru</span></nuxt-link>
      </v-toolbar-title>
      <v-toolbar-items class="ml-4 hidden-sm-and-down">
        <v-btn v-for='(item, i) in items' :key='i' :to='item.to' flat>{{item.title}}</v-btn>
      </v-toolbar-items>
      <v-spacer></v-spacer>
      <!-- <v-btn icon @click.stop="rightDrawer = !rightDrawer" >
        <v-icon>menu</v-icon>
      </v-btn> -->
    </v-toolbar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-navigation-drawer temporary :right="right" v-model="rightDrawer" fixed >
      <v-list>
        <v-list-tile @click.native="right = !right">
          <v-list-tile-action>
            <v-icon light>compare_arrows</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Switch drawer (click me)</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-footer :fixed="fixed" app>
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        clipped: true,
        drawer: true,
        fixed: false,
        items: [
          {
            title: 'Getting Started',
            to: '/getting-started'
          },
          {
            title: 'Message',
            to: '/message',
            active: true,
            children: [
              {
                title: 'What is AppointmentGuru',
                to: '/message/about'
              },
              {
                title: 'Short pitches',
                to: '/message/short-pitches'
              },
              {
                title: 'Objections',
                to: '/message/short-pitches'
              },
              {
                title: 'Mobile demo',
                to: '/message/longer-pitches'
              },
              {
                title: 'Computer demo',
                to: '/message/longer-pitches'
              }
            ]
          },
          {
            title: 'Resources',
            to: '/resources',
            children: [
              {
                title: 'Presentations',
                to: '/resources/presentations'
              },
              {
                title: 'Communications',
                to: '/resources/communications'
              },
              {
                title: 'Promotional Video',
                to: '/resources/video'
              }
            ]
          },
          {
            title: 'Guides',
            to: '/guides',
            children: [
              {
                title: 'Brand',
                to: '/guides/brand'
              },
              {
                title: 'Text and tone standards',
                to: '/guides/text-and-tone'
              }
            ]
          }
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'AppointmentGuru'
      }
    }
  }
</script>
