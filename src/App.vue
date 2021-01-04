<template>
  <v-app>
    <div>
      <v-sheet
          tile
          height="54"
          class="d-flex"
      >
        <v-btn
            icon
            class="ma-2"
            @click="$refs.calendar.prev()"
        >
          <v-icon>mdi-chevron-left</v-icon>
        </v-btn>
        <v-select
            v-model="type"
            :items="types"
            dense
            outlined
            hide-details
            class="ma-2"
            label="type"
        ></v-select>
        <v-select
            v-model="mode"
            :items="modes"
            dense
            outlined
            hide-details
            label="event-overlap-mode"
            class="ma-2"
        ></v-select>
        <v-select
            v-model="weekday"
            :items="weekdays"
            dense
            outlined
            hide-details
            label="weekdays"
            class="ma-2"
        ></v-select>
        <v-spacer></v-spacer>
        <v-btn
            icon
            class="ma-2"
            @click="$refs.calendar.next()"
        >
          <v-icon>mdi-chevron-right</v-icon>
        </v-btn>
      </v-sheet>
      <v-sheet height="600">
        <v-calendar
            ref="calendar"
            v-model="value"
            :weekdays="weekday"
            :type="type"
            :events="events"
            :event-overlap-mode="mode"
            :event-overlap-threshold="30"
            :event-color="getEventColor"
            @change="getEvents"
        ></v-calendar>
      </v-sheet>
    </div>
    <v-alert
        color="#C51162"
        dark
        icon="mdi-material-design"
        border="right"
        v-if="hj"
    >
      Phasellus blandit leo ut odio. Morbi mattis ullamcorper velit. Donec orci lectus, aliquam ut, faucibus non,
      euismod id, nulla. In ut quam vitae odio lacinia tincidunt.
    </v-alert>
    <!--    <v-main>-->
    <!--      <HelloWorld/>-->
    <!--    </v-main>-->
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    // HelloWorld,
  },

  data: () => ({
    //
  }),
};
</script>
