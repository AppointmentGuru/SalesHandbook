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
          title: 'Opening',
          content: `
Hi, my name is ___________. I’m calling some startups in the area to find out if they are a good fit for our product/service/beta program.
What we do in a sentence is we provide companies with xyz. Does this in general sound interes ng to you?`
        },
        {
          title: 'Qualifying',
          content: `
What is your current xyz process? Who are your customers?
How do you currently solve xyz? Etc.`
        },
        {
          title: 'Closing',
          content: `
We would want to start in X weeks - does this work for you?
The beta program is heavily discounted. It’s going to be $X/day per. What is the decision making process in your company?
Etc.`
        },
        {
          title: 'Next Steps',
          content: `
Great. Sounds like this could be a good fit. Let me send you our brochure and schedule a  me next week to discuss all your ques ons etc.
What’s the best email to send you informa on and the calendar invite? What’s a good  me to chat next week?`
        }
      ]
    }
  }
}
</script>
