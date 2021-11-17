<template>
  <v-container>
    <div class="index-header text-center">
      <div><h2>Products for you!</h2></div>
    </div>
    <div class="carousel">
      <v-carousel >
        <v-carousel-item >
          <v-sheet  height="100%" tile>
            <v-row class="fill-height" align="center" justify="center">
              <div class="text-h2">Slide {{ 1 }}</div>
            </v-row>
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
    </div>

    <div>
      <v-row>
        <v-col v-for="i in 3" :key= "i" cols="4">
            <v-card class="mx-auto" max-width="344">
              <v-img
                src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
                height="200px"
              ></v-img>

              <v-card-title> {{categories.title}}</v-card-title>
              <v-card-actions>
                <v-btn color="orange lighten-2" text> More Info </v-btn>

                <v-spacer></v-spacer>

                <v-btn icon @click="show = !show">
                  <v-icon>{{
                    show ? 'mdi-chevron-up' : 'mdi-chevron-down'
                  }}</v-icon>
                </v-btn>
              </v-card-actions>

              <v-expand-transition>
                <div>
                  <v-divider></v-divider>

                  <v-card-text>
                    {{categories.description}}
                  </v-card-text>
                </div>
              </v-expand-transition>
            </v-card>
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>

<script>
export default {
    data: () => ({
      show: false,
      categories: [],
           cards: [],
    }),
    async fetch(){
      console.log(await this.$content('cards'));
      this.cards  = await this.$content('cards')
    },
    
 
}
</script>