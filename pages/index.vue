<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <v-card v-for="post in posts" :key="post.id">
        <v-card-title class="headline">
        {{post.title.rendered}}
        </v-card-title>
        <v-card-text>
         <div v-html="post.excerpt.rendered"></div>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn
            color="primary"
            nuxt
            to="/inspire"
          >
            Continue
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>

export default {
computed: {
              posts() {
                  return this.$store.state.posts;
              },
          },
              created() {
               this.$store.dispatch('getPosts');
              },

};
</script>
