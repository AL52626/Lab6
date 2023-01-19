<template>
  <div class="text-2xl	m-2 font-bold">
    <h1>{{ welcomeText }}</h1>
  </div>
  <v-container>
    <v-col class="d-flex" cols="1" sm="3">
      <v-select :items="options" label="Outlined style" v-model="selectedOption" outlined></v-select>
    </v-col>

  </v-container>
  <div class="p-3">
    <p class="text-lg font-semibold">Selected option is {{ selectedOption }}</p>
    <v-btn v-if="selectedOption" depressed elevation="2" @click="onClick">Show me a player</v-btn>
  </div>

  <div v-if="showPicture" class="p-3">
    <v-img v-if="this.selectedOption == 'Seria A'" max-height="300" max-width="450"
      src="https://www.thesun.co.uk/wp-content/uploads/2020/05/NINTCHDBPICT000001387914.jpg"></v-img>
    <v-img v-if="this.selectedOption == 'Premiere Leauge'" max-height="300" max-width="450"
      src="https://static.independent.co.uk/s3fs-public/thumbnails/image/2014/10/26/17/drogba-3.jpg?quality=75&width=982&height=726&auto=webp"></v-img>
    <v-img v-if="this.selectedOption == 'La Liga'" max-height="300" max-width="450"
      src="https://images.beinsports.com/jq87X4eACgg7iqh4GJMK_wBs3GQ=/full-fit-in/1000x0/ronaldinho-cropped_1nsieiiy254011d58qieaiq0f5.jpg"></v-img>

    <p class="font-semibold italic font-mono text-lg margin">{{ playerName }}</p>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',

  data: () => ({
    welcomeText: 'Hi, choose a football leauge you like',
    selectedOption: '',
    player: '',
    showPicture: false,
    options: [
      'Seria A',
      'Premiere Leauge',
      'La Liga',
    ]
  }),
  methods: {
    onClick() {
      this.showPicture = true;
    }
  },
  computed: {
    playerName() {
      if (this.selectedOption == 'Seria A')
        return 'Zidane'
      if (this.selectedOption == 'Premiere Leauge')
        return 'Drogba'
      if (this.selectedOption == 'La Liga')
        return 'Ronaldinho'
      else return ''
    }
  }
}
</script>

<style scoped>
.margin {
  margin: 10px;
}
</style>
