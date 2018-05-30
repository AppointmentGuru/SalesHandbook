<template>
  <v-layout row wrap >
    <v-flex xs12>
      <v-card v-for='(item, i) in items' :key='i' class='mt-4' >
        <v-card-title class="headline">{{item.title}}</v-card-title>
        <v-card-text class='blockquote' >{{item.content}}</v-card-text>
      </v-card>
    </v-flex>
    <v-flex >
      <v-spacer></v-spacer>
      <v-btn flat href='http://blog.close.io/how-to-create-a-sales-phone-script-free-template' >Read more <v-icon class='ml-2' >open_in_new</v-icon></v-btn>
    </v-flex>
  </v-layout>
</template>
<script>
export default {
  name: 'Short Pitches',
  data () {
    return {
      items: [
        {
          title: 'I don\'t have time',
          content: `...`
        },
        {
          title: 'I\'m not interested',
          content: `...`
        },
        {
          title: 'It\'s too expensive',
          content: `...`
        },
        {
          title: 'We already use Google Calendar',
          content: `...`
        },
        {
          title: 'We already use Kudu / Panacea etc',
          content: `...`
        },
        {
          title: '... etc',
          content: `...`
        }
      ]
    }
  }
}
</script>
