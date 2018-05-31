<template>
  <section>
    <v-card v-for='step in steps' :key='step.id' >
      <v-card-title>{{step.title}}</v-card-title>
      <v-card-text >
        <blockquote class='blockquote' v-html='$md.render(step.summary)' ></blockquote>

        -- Video goes here --

        <blockquote class='blockquote' v-html='$md.render(step.then)' ></blockquote>
        <v-btn flat v-for='choice in step.choices' >{{choice}}</v-btn>
      </v-card-text>
    </v-card>
  </section>
</template>

<script>
export default {
  name: 'ComputerDemoPage',
  data () {
    return {
      steps: [
        {
          id: 'getting-started',
          title: 'Getting started',
          video: '',
          choices: [
            'Creating invoices for a number of appointments',
            'How does it work when my clients book online?',
            'Customizing my notifications'
          ],
          summary: `
  To start, I'd like to show how the process works end to end. We'll go through creating an appointment, adding ICD10 codes, creating an invoice, receiving payment on that invoice
  and how we can track all of this from the reports
  `,
          then: `
  So that's the whole process from end to end. AppointmentGuru can obviously do a lot more, is there anything in particular you'd like me to go into more detail on?

  Some things people often ask about are:`
        }
      ]
    }
  }
}
</script>

<style>

</style>
