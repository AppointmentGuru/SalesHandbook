<template>
  <v-layout row wrap >
    <v-flex xs12>
      <v-card v-for='(item, i) in items' :key='i' class='mt-4' >
        <v-card-title class="headline">{{item.title}}</v-card-title>
        <v-card-text class='blockquote' v-html='$md.render(item.content)' ></v-card-text>
        <v-divider></v-divider>
        <v-form  class='ma-4' >
          <v-text-field v-for='field in item.context' :key='field' :label='field' v-model='dynamicData[item.id][field]' ></v-text-field>
        </v-form>
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
      dynamicData: {
        opening: {
          'name': '...',
          'profession': '...',
          'place': '...'
        }
      }
    }
  },
  computed: {
    items () {
      return [
        {
          id: 'opening',
          title: 'Opening',
          showform: false,
          content: `
Hi, my name is ${this.dynamicData.opening.name}. I’m calling **${this.dynamicData.opening.profession} in ${this.dynamicData.opening.place}** to find out if they are a good fit for our practice management software.
What we do in a sentence is we provide companies with an end to end solution for managing your practice from appointments to invoices, payments and even your online presense.
Does this in general sound interestng to you?`,
          context: ['name', 'profession', 'place']
        },
        {
          title: 'Qualifying',
          content: `
* How do you currently manage your appointments?
* Are you using any kind of practice management software?
* What are the things that you'd like to be doing better?
* What are the pain points you're dealing with today?
`
        },
        {
          title: 'Closing',
          content: `
I'd love to get you set up. Would you like me to setup an account for you so that you can get up and running right away?`
        },
        {
          title: 'Next Steps',
          content: `
Great. Sounds like this could be a good fit. I'll let you know when I've got your account all setup. Can we send you some getting started e-mails to
get you up to speed? I'll follow up with you in a week and check to answer any questions you might have. Thank you so much for your time`
        }
      ]
    }
  }
}
</script>
