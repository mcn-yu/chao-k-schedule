<template>
  <div>
    <table class="yg-table table-bordered">
      <thead>
        <tr>
          <th scope="col"></th>
          <th scope="col">Room1</th>
          <th scope="col">Room2</th>
          <th scope="col">Room3</th>
          <th scope="col">Room4</th>
          <th scope="col">Room5</th>
          <th scope="col">Room6</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(i, k) in schedules" :key="k">
          <td class="timeslot">
            {{ i.fields.time }}
          </td>
          <td
            :class="
              i.fields.room1 == true ? 'yg-schedule-full' : 'yg-schedule-empty'
            "
            data-label="room1"
          >
            {{ i.fields.room1 == true ? "×" : "◯" }}
          </td>
          <td
            :class="
              i.fields.room2 == true ? 'yg-schedule-full' : 'yg-schedule-empty'
            "
            data-label="room2"
          >
            {{ i.fields.room2 == true ? "×" : "◯" }}
          </td>
          <td
            :class="
              i.fields.room3 == true ? 'yg-schedule-full' : 'yg-schedule-empty'
            "
            data-label="room3"
          >
            {{ i.fields.room3 == true ? "×" : "◯" }}
          </td>
          <td
            :class="
              i.fields.room4 == true ? 'yg-schedule-full' : 'yg-schedule-empty'
            "
            data-label="room4"
          >
            {{ i.fields.room4 == true ? "×" : "◯" }}
          </td>
          <td
            :class="
              i.fields.room5 == true ? 'yg-schedule-full' : 'yg-schedule-empty'
            "
            data-label="room5"
          >
            {{ i.fields.room5 == true ? "×" : "◯" }}
          </td>
          <td
            :class="
              i.fields.room6 == true ? 'yg-schedule-full' : 'yg-schedule-empty'
            "
            data-label="room6"
          >
            {{ i.fields.room6 == true ? "×" : "◯" }}
          </td>
        </tr>
      </tbody>
    </table>

    <!-- <table class="yg-table table-bordered">
      <thead>
        <tr>
          <th scope="col"></th>
          <th scope="col">Room1</th>
          <th scope="col">Room2</th>
          <th scope="col">Room3</th>
          <th scope="col">Room4</th>
          <th scope="col">Room5</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(i, k) in items" :key="k">
          <td class="timeslot">
            {{ i.time }}
          </td>
          <td
            :class="i.room1 == true ? 'yg-schedule-full' : 'yg-schedule-empty'"
            data-label="room1"
          >
            {{ i.room1 == true ? "予約済み" : "空き" }}
          </td>
          <td
            :class="i.room2 == true ? 'yg-schedule-full' : 'yg-schedule-empty'"
            data-label="room2"
          >
            {{ i.room2 == true ? "予約済み" : "空き" }}
          </td>
          <td
            :class="i.room3 == true ? 'yg-schedule-full' : 'yg-schedule-empty'"
            data-label="room3"
          >
            {{ i.room3 == true ? "予約済み" : "空き" }}
          </td>
          <td
            :class="i.room4 == true ? 'yg-schedule-full' : 'yg-schedule-empty'"
            data-label="room4"
          >
            {{ i.room4 == true ? "予約済み" : "空き" }}
          </td>
          <td
            :class="i.room5 == true ? 'yg-schedule-full' : 'yg-schedule-empty'"
            data-label="room5"
          >
            {{ i.room5 == true ? "予約済み" : "空き" }}
          </td>
        </tr>
      </tbody>
    </table> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      // timeslots: [
      //   "13:00-14:00",
      //   "14:00-15:00",
      //   "15:00-16:00",
      //   "16:00-17:00",
      //   "17:00-18:00",
      //   "18:00-19:00",
      //   "19:00-20:00",
      //   "20:00-21:00",
      //   "21:00-22:00",
      //   "22:00-23:00",
      //   "23:00-00:00",
      //   "00:00-01:00",
      //   "01:00-02:00",
      //   "02:00-03:00",
      //   "03:00-04:00",
      // ],
      schedules: [],
      items: [
        {
          time: "13:00-14:00",
          room1: true,
          room2: false,
          room3: false,
          room4: true,
          room5: false,
        },
        {
          time: "14:00-15:00",
          room1: false,
          room2: false,
          room3: false,
          room4: true,
          room5: true,
        },
        {
          time: "15:00-16:00",
          room1: true,
          room2: true,
          room3: true,
          room4: true,
          room5: false,
        },
        {
          time: "16:00-17:00",
          room1: false,
          room2: false,
          room3: false,
          room4: false,
          room5: false,
        },
        {
          time: "17:00-18:00",
          room1: false,
          room2: false,
          room3: false,
          room4: false,
          room5: false,
        },
        {
          time: "18:00-19:00",
          room1: false,
          room2: true,
          room3: false,
          room4: true,
          room5: false,
        },
        {
          time: "19:00-20:00",
          room1: false,
          room2: false,
          room3: false,
          room4: false,
          room5: false,
        },
        {
          time: "20:00-21:00",
          room1: false,
          room2: false,
          room3: true,
          room4: true,
          room5: true,
        },
        {
          time: "21:00-22:00",
          room1: false,
          room2: false,
          room3: false,
          room4: false,
          room5: false,
        },
        {
          time: "22:00-23:00",
          room1: false,
          room2: false,
          room3: false,
          room4: false,
          room5: false,
        },
        {
          time: "23:00-00:00",
          room1: false,
          room2: false,
          room3: false,
          room4: false,
          room5: false,
        },
        {
          time: "00:00-01:00",
          room1: false,
          room2: false,
          room3: false,
          room4: true,
          room5: false,
        },
        {
          time: "01:00-02:00",
          room1: true,
          room2: false,
          room3: true,
          room4: false,
          room5: false,
        },
        {
          time: "02:00-03:00",
          room1: false,
          room2: false,
          room3: false,
          room4: false,
          room5: false,
        },
        {
          time: "03:00-04:00",
          room1: false,
          room2: false,
          room3: false,
          room4: false,
          room5: false,
        },
      ],
    };
  },
  // async asyncData({ $axios }) {
  //   const schedules = await $axios.$get(
  //     "https://api.airtable.com/v0/appZeqFbVXrGled2I/Table%201",
  //     {
  //       headers: {
  //         Authorization: "Bearer keyda38YqYRDASE5C",
  //       },
  //     }
  //   );
  //   return { schedules };
  // },
  created() {
    this.getData();
  },
  methods: {
    async getData() {
      const reponse = await this.$axios.$get(
        "https://api.airtable.com/v0/appZeqFbVXrGled2I/Schedule?sort%5B0%5D%5Bfield%5D=time",
        {
          headers: {
            Authorization: "Bearer keyda38YqYRDASE5C",
          },
        }
      );
      this.schedules = reponse.records;
    },
  },
};
</script>
<style scoped>
table.yg-table {
  border: 1px solid #ccc;
  border-collapse: collapse;
  margin: 0;
  padding: 0;
  width: 100%;
  table-layout: fixed;
}

table.yg-table caption {
  font-size: 1.5em;
  margin: 0.5em 0 0.75em;
}

table.yg-table tr {
  background-color: #f8f8f8;
  border: 1px solid #ddd;
  padding: 0.35em;
}

table.yg-table th,
table.yg-table td {
  padding: 0.625em;
  text-align: center;
}

table.yg-table th {
  font-size: 0.85em;
  letter-spacing: 0.1em;
  text-transform: uppercase;
}

.yg-thead {
  font-size: 16px;
  line-height: 1.5em;
  background: #f6f6f6;
  color: #000;
  font-family: sans-serif;
}

.yg-schedule-empty {
  background: #69ca47;
  color: black;
  text-align: center;
}

.yg-schedule-full {
  color: black;
  text-align: center;
}

.table-bordered td,
.table-bordered th {
  border: 1px solid #f2f2f2;
}
</style>