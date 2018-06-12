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
          content: `I don't have time to hear about AppointmentGuru: That's ok, let me send you a link to an intro video that'll take a few minutes to watch. If it sounds interesting, I can provide you with more info.
          OR
          I don't have time to use an app like AppointmentGuru: AppointmentGuru's main aim is to save you time. Businesses who use AppointmentGuru find that they spend less time on admin like setting up appointments for clients, reminding clients to come to their appointments, sending clients information on their appointment like directions, creating invoices, sending invoices and following up on payment of invoices.`
        },
        {
          title: 'I\'m not interested',
          content: `That's ok, let me send you a link to an intro video that'll take a few minutes to watch. If it sounds interesting, I can provide you with more info.`
        },
        {
          title: 'It\'s too expensive',
          content: `Here's what's included in your R400 monthly subscription: * unlimited appointment scheduling (once-off or repeat appointments) * unlimited SMS/email notifications * invoices generated from appointments (including codes for medical aid submission) * a SnapScan integration * calendar syncing * iOS and Android mobile apps to manage your appointments * iOS and Android apps for your clients * a free table talker and business cards. We're constantly improving and introducing new features too! When comparing AppointmentGuru to other appointment management software, you'll find it priced very competitively.`
        },
        {
          title: 'We already use Google Calendar',
          content: `Google Calendar is useful but doesn't have as many awesome features as AppointmentGuru. You're limited to creating, rescheduling and canceling calendar invites with email notifications. AppointmentGuru offers that and so much more.`
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
