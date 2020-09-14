<template>
  <v-container>
    <v-row>
      <v-col cols="12" sm="5" class="my-2 px-1">
        <v-date-picker @click:date="getPictureDate" v-model="picker" full-width>
        </v-date-picker>
        <v-card-text v-if="imageApod"><b>Description:</b> {{imageApod.explanation}}</v-card-text>
        <v-card-text v-else><b>Description:</b> information not available</v-card-text>
      </v-col>
      <v-col cols="12" sm="7" class="my-2 px-1">
        <v-card-title v-if="imageApod"><b> {{imageApod.title}}</b></v-card-title>
        <v-card-text v-if="imageApod"><b>Date: </b>{{imageApod.date}}</v-card-text>
        <v-img v-if="imageApod" :src="imageApod.url"></v-img>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import { mapActions, mapState } from 'vuex'

export default {
  data: () => ({
    picker: new Date().toISOString().substr(0, 10),
  }),
  methods: {
    ...mapActions(['setPicture']),
    getPictureDate (date) {
      this.setPicture(date)
    }
  },
  computed: {
    ...mapState (['imageApod'])
  }
}
</script>
