<template>
  <v-container>
    <v-row justify="center" style="padding-top: 8%">
      <v-col cols="6">
        <v-card max-height="600" color="#e2e8f0" elevation="10">
          <v-row justify="center">
            <v-col cols="12" sm="10" md="10" lg="10">
              <h1 class="login-title">HR Reporting Tool</h1>
              <!--<v-card-subtitle>All feedback will be emailed to Christina</v-card-subtitle>-->
              <!--
              <v-text-field
                solo
                label="Full Name"
                name="fullName"
                v-model="fullname"
                autocomplete="nope"
                type="text"
              ></v-text-field>
              -->
              <!--<v-card-text>Please provide feedback below.</v-card-text>-->
              <v-textarea
                solo
                ref="feedback_text"
                v-model="feedback_text"
                placeholder="All feedback will be emailed to Christina at Human Resources."
                rows="12"
                no-resize
              ></v-textarea>
            </v-col>
          </v-row>
          <v-divider></v-divider>
          <v-card-actions>
            <v-btn @click="sendEmail" color="#2c84cf" elevation="2" block dark x-large
              >Submit Feedback</v-btn
            >
          </v-card-actions>
        </v-card>
      </v-col>

      <!--<v-col cols="6"> </v-col>-->
    </v-row>

    <v-dialog
        transition="dialog-bottom-transition"
        max-width="600"
        v-model="success_dialog"
      >
        <template v-slot:default="success_dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Success!</v-toolbar>
            <v-card-text>
              <div class="text-h5 pa-12">Your response has been successfully emailed to Christina at Human Resources</div>
            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="success_dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>

    <v-dialog
        transition="dialog-bottom-transition"
        max-width="600"
        v-model="failed_dialog"
      >
        <template v-slot:default="failed_dialog">
          <v-card>
            <v-toolbar
              color="red"
              dark
            >Error: Message Failed</v-toolbar>
            <v-card-text>
              <div class="text-h6 pa-12">Your response was not able to reach Human Resources.<br><br> Please email support@xsbrokers.com for assitance, if this issue persists.</div>
            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="failed_dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>

  </v-container>
</template>

<script>
import emailjs from '@emailjs/browser';

export default {
  name: "Form",

  data: () => ({
    fullname: null,
    feedback_text: '',
    success_dialog: false,
    failed_dialog: true
  }),

  methods: {
    sendEmail() {
      let template_data = {
        from_name: 'Anonymous',
        to_name: "Christina",
        message: this.feedback_text,    
      }

      emailjs.send('service_ynbpmwq', 'template_eqyzgds', template_data, 'user_n2Ap4T9hcJt4qfvvGKixn')
        .then((result) => {
            console.log('SUCCESS!', result.text);
            this.success_dialog = true
            this.feedback_text = ''
        }, (error) => {
            console.log('FAILED...', error.text);
            this.failed_dialog = true
        });
    }
  }
};
</script>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@600&display=swap");

.login-title {
  font-family: "Montserrat", sans-serif;
  text-align: center;
  font-size: 36px;
  color: #18254A;
  padding: 0px 0px 20px 0px;
  border-radius: 5px 5px 0px 0px;
}

</style>