<template>
  <v-app id="inspire" :dark="setTheme">
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex justify-space-between pt-5" style="width: 100%">
       <h2 class="black--text">Calendar App</h2> 
       <v-switch :label="`Dark Theme`" v-model="goDark"></v-switch>
      </div>
    </v-app-bar>

    <v-content>
      <Calendar />
    </v-content>
    <Footer />
  </v-app>
</template>

<script>
import Calendar from './components/Calendar';
import Footer from '@/components/Footer.vue';

export default {
  name: 'App',

  components: {
    Calendar,
    Footer
  },

  opts: {
        theme: {
            dark: false
        }
    },

    data() {
        return {
            goDark: false
        };
    },


computed: {
        setTheme() {
            if (this.goDark == true) {
                return (this.$vuetify.theme.dark = true);
            } else {
                return (this.$vuetify.theme.dark = false);
            }
        }
    }
};
</script>
