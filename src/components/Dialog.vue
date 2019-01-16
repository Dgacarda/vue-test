<template>
    <div class="text-xs-center">
    <v-dialog
      v-model="dialog"
      width="500"
    >
      <v-btn
        slot="activator"
        color="red lighten-2"
        dark
      >
        Click Me
      </v-btn>

      <v-card>
        <v-card-title
          class="headline grey lighten-2"
          primary-title
        >
          Privacy Policy
        </v-card-title>

        <v-card-text>
          {{ prevRoute }}
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            href="/"
            color="primary"
            flat
            @click="dialog = false"
          >Back to main page
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
import router from '../router';

export default {
  name: 'Dialog',
  beforeRouteEnter (to, from, next) {
     next(vm => {
      vm.prevRoute = from.path
    })
  },
  data () {
    return {
      dialog: true,
      prevRoute: null
    }
  }
}
</script>

<style>

</style>
